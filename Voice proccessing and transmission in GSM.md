### Contents
- A/D, source & channel coding, interleaving, security, bursts/frame structure, modulation
- derivation of bitrates for individual blocks in the processing chain
---
![[Pasted image 20240202111512.png]]
- **A/D conversion:**
	- Microphone converts analog to digital, then I apply a BP filter (300 Hz to 3.4 kHz (basic speech)), then I sample and quantize the signal
>[!Warning]+ **This is not feasible**
This results in unmanagabe bitrate requirements
**Solution:** speech modelling, via DSP methods
	
![[Pasted image 20240202112238.png]]


**Source coding DSP methods:**
- speech broken into 20 ms blocks
- on each block..
1. LPC analysis (decorrelation of signal, results in filter coefficients)
2. Regular Pulse excitation
3. Long Term Prediction: calculates differences between adjacent 5ms blocks

>[!Important]
>output: **13 kbit/s** or 260 bits per 20 ms block
>instead of 832 kbit/s

**Channel coding**
- goal: communication robustness, noise  and interference tolerance
- input: 260 bits per 20 ms of source coded speech signal (13 kbit/s)
- 260 bits of sourced coded speech are grouped into 3 classes ( 50 very important bits, 132 important bits, 78 not so important bits)
- then they are encoded according to the following scheme
- output: 456 bits per 20 ms of speech (i.e. 22.8 kbit/s)
![[Pasted image 20240202142122.png]]

**Interleaving**
- input: 456 bits representing 20 ms of speech
- goal: protection against consecutive errors
- input data split into 8 groups (456/8 = 57 bits )
- every byte is split into these eight groups
- also, interleaving between groups of 20ms speech data
- then I am sending the groups consecutively
![[Pasted image 20240202142653.png]]

---
**Security**
![[Pasted image 20240202143138.png]]

**Burst formatting**
![[Pasted image 20240202144146.png]]
![[Pasted image 20240202144312.png]]
>[!note]-  **Note**
>- 0.25 bit comes from guard period (we are basically converting time axis to bits according to MCS)
>- guard period : : 37.64 us ~ 8.25 bits

types of bursts:
![[Pasted image 20240202145232.png]]
>[!example]
>- basically different burst types for different purposes
>- information, oscillator synchro, timing synchro, random access, power meas

**Frame structure**
>[!important]
>- 1 frame = 8 bursts (time slots)

![[Pasted image 20240202164903.png]]
