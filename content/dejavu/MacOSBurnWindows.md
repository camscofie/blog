---
title: Burn windows USB in MacOS
description: process record
date: 2019-07-13T22:41:21+02:00
---



diskutil list

sudo diskutil eraseDisk FAT32 'name' MBRFormat 'place(/dev/disk2)'

unetbootin

//FAT32 对文件大小有限制，如果 .ios 文件超过4GB，安装时可能出现错误。
