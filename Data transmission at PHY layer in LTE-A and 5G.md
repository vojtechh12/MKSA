## Contents
- frame, RE, RB, cyclic prefix, duplex, special subframe, derivation of LTE capacity, numerologies in 5G
---

### Bands in LTE-A or 5G
- FDD (paired bands) or TDD (unpaired bands)
- scalable bandwidth - 1.4 up to 400 MHz (+ possible carrier aggregation)
- major bands in Europe: 800, 900, 1800, 2100, 2600, 3500, 3700

### Modulations
- QPSK
- M-ary QAM (max 256 QAM in rel 12, planning 1024 QAM in rel 15)

### Frame
- frame : : 1 ms
- subframe : : 1 ms
- slot : : 0.5 ms
![[Pasted image 20240204105558.png]]
- frequency x time grid
![[Pasted image 20240204105849.png]]
- RB is the smallest unit allocated to UE
- RE is used to calculate communication capacity

### Cyclic prefix
- protection against inter-symbol interference
- CP supresses ISI by retransmitting the end part of a symbol ath the beginning
- increases robustness, decreases capacity
- normal CP - 6.5% : : 4.7 us (one symbol lasts 71.4 us) 
- extended CP : 20%

### Duplexing
- FDD
- TDD
	- TDD is a bit more complicated
	- it neccessitates introduction of different kinds of subframes
		- D subframe for DL
		- U subframe for UL
		- Special Subframe for ***
	- 7 diff configs for DL : UL ratio (from 2:3 to 9:1)
**Special Subframe**
![[Pasted image 20240204111529.png]]
>[!Warning]
>- Do note how GP relates to cell radius
>- wider cell radius requires more time for UL/DL antenna switching on UE side
>- bcs of propagation delay

![[Pasted image 20240204111956.png]]

### Derivation of LTE (-A/-Pro) capacity
nRE in 1 second ~14 000 = N \[RE/s] per subcarrier
20 MHz channel --> 100 RBs --> 1200 REs per channel
=> 14000 x 1200 = 16.8 M REs
--> apply MCS (max MCS = 7.41 bits/RE)
==> 16.8 M RE/s x 7.41 bits/RE = **124.5 Mbits/s**


### Numerologies in 5G
- frame and subframe same as in LTE 
	- frame = 10 ms
	- subframe = 1 ms
- number of slots per subframe can vary (slot of variable length
	- 1,2,4,8 or 16 slots per subframe
	- managing latency
- always 14 symbols per slot --> symbols vary in length
- slot contains
	- DL sumbol
	- UL symbol
	- Flexible symbol (can be allocated for UL or DL based on needs)
