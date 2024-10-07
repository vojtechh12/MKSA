## Contents
- general principle, soft combining, (chase combining, incremental redundancy), implementation in LTE/5G
---
### General principle

- HARQ is part of MAC layer (along with scheduling and multiplexing logical channels to transport channels)

>[!note]
>Hybrid ARQ is basically ARQ + FEC

*ARQ part is more dense than in RLC since it deals with units like subframes (miliseconds)*

- HARQ is not a successor to RLC ARQ but rather a complement

>[!important] soft combining
>erroneous packets are not discarded but stored in buffer

- later these packets can be combined to form the original dataword
![[Pasted image 20240204153621.png]]

>[!example] options for restransmission
>1. same packet retransmitted : : **Chase combining**
>2. same data but different codeword is retransmitted : : **Incremental redundancy**

- the codewords in incremental redundandy can differ in e.g. punctuation (which reduntant bits to send and which to neglect)
### Implementation in 4G, 5G
![[Pasted image 20240204154141.png]]
