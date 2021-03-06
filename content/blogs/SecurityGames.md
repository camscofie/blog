---
title: Security Games
description: EUF-CMA IND-CPA
date: 2019-07-26T22:41:21+02:00
tags: ["sicherheit"]
---
## IND-CPA (Indistinguishability under Chosen Plaintext Attack)
**言辞**：攻击者生成两条等长的消息{a,b}，挑战者随机决定加密其中的一条消息，攻击者试图猜测被加密的是哪条消息。

**Schema IND-CPA-sicher ⇔ kein eﬃzienter Angreifer A kann Chiﬀrate von selbstgewählten Klartexten unterscheiden**
1. A erhält im Folgenden Zugriﬀ auf Enc(K, ·)-Orakel
2. A wählt zwei Nachrichten M (1) , M (2) gleicher Länge 
3. A erhält C∗ := Enc(K, M (b) ) für gleichverteiltes b ∈ {1, 2} 
4. A gewinnt, wenn er b richtig rät
![IND-CPA](/postImage/SecurityGames/IND-CPA.png)

## EUF-CMA (Existential Unforgeability under Chosen Message Attack):
**言辞**：攻击者有pk 和 Sig(sk,M) Oracle 的权限，攻击者生成伪造的信息和签名；攻击者获胜，如果伪造的签名解锁后等于被伪造的信息。

__Schema IND-CPA-sicher ⇔ kein PPT-Angreifer A wins.__
1. A has pk and access to Sig(sk,*)-Orakel
2. A gives (M*,σ*)
3. A wins, when Ver(pk,M*,σ*) = 1 and M* != M.
![alt text](/postImage/SecurityGames/EUF-CMA.png)


