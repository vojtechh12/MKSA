## Contents
- principle, types, impact on capacity
---
>[!Goal]
>- the goal is to increase channel BW
>- thus increasing comm capacity as per Shannon

- merging componnet carriers (20 MHz each) for parallel transmission to one UE
- up to 100 MHz (5 component carriers) in LTE
	- up to 640 MHz in rel 13
	- up to 16 CC, 100 MHz each in 5G FR1
- primary CC is used also for singalling
- secondary CC contain no signalling just user data
**3 types of CA**
![[Pasted image 20240204132653.png]]

**Increase in channel capacity due to CA and MIMO**
$C_{MIMO} = min(N_{TX}, N_{RX}) \cdot C_s \cdot N_{CC} \cdot (1-R_{SO})$
	- Cs = single link capacity (20 MHz) = 124.5 Mbit/s
	- Ntx Nrx means MIMO
	- Ncc ... number of component carriers
	- R_so ... signalling overhead

