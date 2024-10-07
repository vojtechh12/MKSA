>[!info]
>*signal transmitted by different MSs in different distances from BTS must arrive at correct time interval*

>[!warning]
>GSM uses TDMA. In UL, propagation delay could cause conflict at receiver


Timing advance compensates propagation delay of different MSs

**Implementation of TA**
- 6 bits, resolution = 550 m
- resolution derived from speed of light
	- remember from frames: 1 bit in GSM's MCS takes 3.69 us. In that time, waves travel around 1100 m. Therefore, half a bit duration is 550 m
- radius 35 km
