---
title: 365 Administration powershell
description: User account configure
date: 2019-07-20T22:41:21+02:00
tags: ["powershell"]
---

```powershell
#╭──────────────────────────────╮
#│ ◎ ○ ○ ░░░░ 365 E-mails ░░░░░░│
#├──────────────────────────────┤
#│                              │
#│                              │
#│  this is for automation of   │
#│  configure E-mails in 365.   │
#│                              │
#│                              │
#└──────────────────────────────┘

$MSOCred = Get-Credential
$global:Users = @()             #users with their original E-mail address
$global:old_Users = @()         #users with their UserPrincipalName changed to old_xxxx@xxx
$global:confirmation = $false

# path to the excel file
$excelPath = "C:\Script\Faculty.xlsx"


# connect to MsolService 
function logInMsolService {
    # connect to MsolService
    Write-Host "`nConnecting to MsolService..."
    Connect-MsolService -Credential $MSOCred
    Write-Host "Connected to Msolservice."
}

# connect to AzureAD 
function logInAzureAD {
    connect to AzureAD
    Write-Host "`nConnecting to AzureAD..."
    Connect-AzureAD -Credential $MSOCred
    Write-Host "Connected to AzureAD."
}

# connect to Exchange 
function logInExchange {     
    Write-Host "`nConnecting to Exchange Online..."
    $global:Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $MSOCred -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    Write-Host "Connect to Exchange Online successfully."
}


# close exchange session
function closeSession {
    Remove-PSSession $Session
}


# Read user E-mails from Excel
function readExcel {
    $excel = New-Object -ComObject "Excel.Application"
    $excel.Visible = $false
    $book = $excel.Workbooks.Open($excelPath)
    $sheet = $book.workSheets.item(1)
    # The Excel's first column stores information of the person's Status,
    # the second column stores the person's E-mail 

    # Iterate the first column, if status is ehemalig, then put his email to global users array.
    if (($sheet.Range("A1").Text -eq "Status") -and ($sheet.Range("B1").Text -eq "UserPrincipalName")) {
        $i = 1
        Do {
            $status = $sheet.cells.item($i, 1).Text
            $email = $sheet.cells.item($i, 2).Text
            if ($status -eq "ehemalig") {
                $global:Users += $email
            }
            $i++
        }
        While ($status -ne "")

        Write-Host "Read Excel list successfully."
    }
    # throw error when it's not in required format.
    else {
        Throw "The Cell A1 or B1 is not 'Status' or 'UserprincipalName'.
    The script will now stop, please check the file."
    }




    # Nested class to close Excel
    function excelCleanUp {

        # Close connections to Excel
        # set interactive to false so no save buttons are shown
        $excel.DisplayAlerts = $false
        $excel.ScreenUpdating = $false
        $excel.Visible = $false
        $excel.UserControl = $false
        $excel.Interactive = $false

        ## quit the workbook
        $excel.Quit()
        ## function to close all com objects
        function Release-Ref ($ref) {
            ([System.Runtime.InteropServices.Marshal]::ReleaseComObject([System.__ComObject]$ref) -gt 1)
            [System.GC]::Collect()
            [System.GC]::WaitForPendingFinalizers()
        }
        ## close all object references

        Release-Ref($sheet) | Out-Null
        Release-Ref($book) | Out-Null
        Release-Ref($excel) | Out-Null
    }
    excelCleanUp
}


# Read confirmation from User
function confirmEmail {
    Write-Host "--------------  E-mails are  -------------------------"
    foreach ($user in $Users) {
        Write-Host $user
    }
    Write-Host "------------------------------------------------------"
    $input = Read-Host "Above emails will be modified to old_xxx@karlsxxx.de, removed from global mailing list, and will be added to no-reply list. `n  --type 'yes' to comfirn, 'no' to cancel."
    switch ($input) {
        'yes' { $global:confirmation = $true }
        'no' {
            $global:confirmation = $false
            Write-Host "program terminates."
            closeSession
            exit 
        }
        Default {
            Write-Error "No matches, program ends."
            closeSession
            exit 
        }
    }
}

# change E-mails from 'xxx@karlsxxx.com' to 'old_xxx@karlxxxx.com'
function changeEmail {
    if ($confirmation) {
        Write-Host "------------  change user E-mail address  ----------------"
        foreach ($user in $Users) {
            $newEmail = "old_" + $user
            $global:old_Users += $newEmail
            Get-MsolUser -UserPrincipalName $user | Set-MsolUserPrincipalName -NewUserPrincipalName $newEmail
            Write-Host "'$user'  has been change to: '$newEmail'."
        }
        Write-Host "-----------------------------------------------"
    }
    else {
        throw "E-mails not confirmed"
    }
}

# change user license to only EXCHANGESTANDARD_ALUMNI
function licenseChange {
    if ($confirmation) {
        Write-Host "----------   Licenses change  ---------------"
        foreach ($user in $global:Users) {
            (Get-MsolUser -UserPrincipalName $user).Licenses.AccountSkuId | ForEach-Object { Set-MsolUserLicense -UserPrincipalName $user -RemoveLicenses $_ }
            Get-MsolUser -UserPrincipalName $user | Set-MsolUserLicense -AddLicenses "karlshochschule:EXCHANGESTANDARD_ALUMNI"
            Write-Host "User $user 's license has been changed to Exchangestandard_Alumni"
        }
        Write-Host "-----------------------------------------------"
    }
    else {
        throw "E-mails not confirmed"
    }
}

# change user password to ramdon auto-generated password from MS
function changePassword {
    if ($confirmation) {
        Write-Host "--------------  Password change  ------------------"
        $newPassword
        foreach ($user in $global:Users) {
            $newPassword = Set-MsolUserPassword -UserPrincipalName $user
            Write-Host "User $user 's pasword has been to change to $newPassword"
        }
        Write-Host "-----------------------------------------------"
    }
    else {
        throw "E-mails not confirmed"
    }
}


# hide address from global list
function hiddenAddress {
    Write-Host "-------   hide Address from global list  ----------"
    if ($confirmation) {
        foreach ($user in $global:Users) {
            Get-mailbox -Identity $user | set-mailbox -HiddenFromAddressListsEnabled $true
            Get-mailbox -Identity $user | Select-Object DisplayName, UserPrincipalName , HiddenFromAddressListsEnabled
        }
        Write-Host "-----------------------------------------------"
    }
    else {
        throw "E-mails not confirmed"
    }
}

# delete alias after change user's UserPrincipalName
function deleteAlias {
    if ($confirmation) {
        Write-Host "------------  deleting Alias   ---------------------"
        foreach ($user in $old_Users) {
            set-mailbox -Identity $user -emailAddresses "SMTP:$user"
            Write-Host "Successfully deleted all Alias in E-mail $user"
        }
        Write-Host "-----------------------------------------------"
    }
    else {
        throw "E-mails not confirmed"
    }
}

# add all xxx@karlxxx.com to no-reply@karlxxxx.de
function addToNoReply {
    if ($confirmation) {
        Write-Host "------------  adding E-mail to No-reply   ---------------------"
        foreach ($user in $Users) {
            set-mailbox -Identity "no-reply@karlshochschule.de" -emailAddresses @{add = $user }
            Write-Host "Successfully add $user to No-reply Alias."
        }
        Write-Host "-----------------------------------------------"
    }
    else {
        throw "E-mails not confirmed"
    }
}

# .───────────────────────────────. 
#(     Factory Pattern: main()     )
# `───────────────────────────────' 
function main {
    
    # warm up
    logInMsolService             # login to MSol service
    logInExchange                # login to Exchange
    readExcel                    # read Excel file, gets the emails that we need to modify
    confirmEmail                 # ask for confirmation!

    # begin to modify
    hiddenAddress                # hide emails from global adress list
    licenseChange                # change user licenses
    changePassword               # change user's passord to MS random generated password
    changeEmail                  # change emials from 'xxx@karlxxx.com' to 'old_xxx@karlxxxx.com'
    closeSession                 
    Write-Host "Now take a break to let MS changes apply..."
    Start-Sleep -s 100            # after changed the email adress, wait for 60 seconds for MS service to take affect.

    # wait for 100 seconds
    logInExchange                
    deleteAlias                  # delete the alias that automatically sign to the modified account
    closeSession                 
    Write-Host "Now take a break to let MS changes apply..."
    Start-Sleep -s 100            # after changed the alias, wait for 60 seconds for MS service to take affect.

    # wait for 100 seconds
    logInExchange                
    addToNoReply                 # add the 'xxx@karlxxx.com' to 'no-reply@karlxxx.com'
    closeSession                 

    # done!
    Write-Host "All done! Thanks for using this script."
}

#                           ┌────────────────────────────────┐
#             *             │                                │
#             **            │                                │
#            **       **    │                                │
#    *     **      **       │                                │
#    *    *      **         │           This runs            │
#    *   *     **      **   │                                │
#    * **    **   ******    │                                │
#    ***    *******         │                                │
#    * *****                │                                │
#    ***                    └────────────────────────────────┘


main

```

[Yange]:    http://camscofie.github.io  "Yange"
[1]:    {{ page.url}}  ({{ page.title }})
