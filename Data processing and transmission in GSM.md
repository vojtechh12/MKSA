### Contents
- coding, interleaving, security bursts, modulations. Derivation of data rates, principle of blocks
- evolution: CSD, HSCSD, GPRS, EDGE
---
>[!note]
>- Data processing in GSM is the same as voice processing, modulo voice modelling

![[Pasted image 20240202171043.png]]

### Circuit Switched Data (CSD)
- 2 variants: 9.6 kbit/s and 14.4 kbit/s 
- 9.6 kbit/s variant
	- 240 bits per 20 ms --> 12 kbit/s
	- only 192 of the 240 are user data => 9.6 kbit/s
	- add 4 bits tail (0000) --> 244 bits (per 20 ms)
	- convolutional coding with rate of 1/2 --> 488 bits (20 ms)
>[!important]
>block size for transmission is just 456 bits
>**Punctuation** dictates which bits to neglect (just reduces redundancy)

- Interleaving
	- depth = 19, spread over 22 groups
	- is a bit more complicated than in voice transmission

- CSD 14.4 kbit/s
	- 290 bits per 20 ms --> 14.5 kbit/s
	- 288 of that is user data --> 14.4 kbit/s
	- conv coding 1/2 --> 588 bits
	- block size for tx remains 456 bits
	- **punctuation** needs to ignore more bits (bigger hit in redundancy)

>[!note] CSD 9.6 vs CSD 14.4
>both variants seem like an analogy to various MCS for individual later technologies
>- 14.4 uses less control data and less redundancy

### High Speed CSD (HSCSD)

>[!important] basic idea
>- n parallel CSD transmissions
>- n = 1, ..., 8
>- theoretical max throughput = 8 x 14.4 = 115.2 kbit/s
>- actual max thr limited to 4 concecuive TSs --> 4 x 14.4 = 57.6 kbit/s

### General Packet Radio Service (GPRS)

>[!warning]
>change from circuit switching to **packet switching**

- 3 new entities for pakcet communication
- Packet control unit (PCU)
	- at BSC, recognizes packet traffic a steers it towards SGSN
- Serving GPRS Support Node (SGSN)
	- routing packets, mobility management, user's info
- Gateway GPRS Support Node (GGSN)
	- gateway to packet network outside GSM
![[Pasted image 20240203100950.png]]

>[!note]
>GPRS introduces the idea of (Modulation) and Coding Scheme (MCS)

- 4 different coding schemes
- modulation unchanged thus far
- max theoretical throughput between 72 - 171 kbit/s

### Enhanced Data rates for GSM Evolution (EDGE)

- similar processing as for GPRS
>[!important] 
>EDGE now fully supports adaptive coding AND modulation, therefore full MCS flexibility
- GMSK (1bit/symbol)
- 8-PSK (3bits/symbol)
- MCS adaptive selection based on bit error probability