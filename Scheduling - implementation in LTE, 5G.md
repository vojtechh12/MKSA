## Contents
- principle
- implementation for DL and UL in LTE/5G
---
## DL scheduling
- in downlink, due to exploitation of OFDMA, each RB can be assigned to a different UE
- => scheduling decision is made for each RB, as a result of metric
![[Pasted image 20240205112359.png]]
### 1. FIFO scheduler
- serves usrs in order of resource request arrival
- very simple
- not fair and inefficient
![[Pasted image 20240205112750.png]]

### 2. Round Robin
- cyclic allocation of RBs to UEs -->  fairness in allocation
- no consideration of channel quality --> inefficiency & no fairness in throughput
![[Pasted image 20240205112737.png]]

### 3. Max rate
- assigns RB to the user that can achieve the most throughput
- --> max system throughput
- --> absolutely no fairness (low CQI UEs may not be served at all)

### 4. Proportional fair scheduler
- max rate with consideration of past throughput to achieve farness
![[Pasted image 20240205113446.png]]

---

## UL Scheduling
- since in UL, OFDMA is not exploited, each RB cannot be assigned to a different user
- UL exploits SC-FDMA
![[Pasted image 20240205114241.png]]
