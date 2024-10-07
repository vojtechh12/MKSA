## Contents
- radio frame, spectrum spreading, codes, channelization, scambling, data and control transmission at PHY (incl. HSPA)
---
![[Pasted image 20240203113200.png]]

>[!example] Spectrum spreading
>1. **Direct Sequence (DS)**
>2. Frequency Hopping (FH)
>3. Time Hopping (TH)
>4. Multi-Carrier CDMA (MC-CDMA)

*In principle, input data are encoded (with increased dimensionality) while spreading the spectrum imprint. We need good crosscorrelation capabilities to decode the signals as well as good autocorrelation capabilities for synchronization*

- CDMA developed in military. TX and RX spreading sequence has to be identical - security
- **DS SS CDMA:**
![[Pasted image 20240203113826.png]]
![[Pasted image 20240203114203.png]]
>[!warning]
>notice how contraction in time domain equals sreading in frequency domain

*The despreading operation basically strngthens the relevant signal's SNR in relation to other signals (with different spreading sequence)*

We have various different UMTS codes. They vary in whether they promote good cross correlation (telling signals apart) or good autocorrelation (sync) features
- PN codes (pseudo random?)
- **Gold codes** (used for scrambling in UMTS, improves autocorr features, identifies Node Bs)
- **Walsh** (spreading code in UMTS, identify user within a cell, each code represents a channel), Walsh-Hadamard


### Data and control transmission at PHY layer

- DL : : UL
- data : : control
- both (UL UL, DL DL) channels are transmitted simultaneously but are encoded (CDMA)

**Uplink:**
1. Dedicated PHY Data Channel (DPDC)
	- data
	-  0, 1 or several channels per radio link
	- variable SF, data rate variable from frame to frame
2. Dedicated PHY Control Channel (DPCC)
	- PHY layer info
	- transmission power control, Ch. estimation, feedback
	- 1 channel per radio link
	- fixed SF
**Downlink:**
- same channels as for UL
- this time multiplexed in time, TDMA

### High Speed Packet Access (HSPA)
- same architecture as WCDMA (basic UMTS?)
- some modifications in HW and SW of individual components
- introduced in Rel 5 (2002)

>[!important] Goals
>- increase DL data rates
>- efficient user scheduling
>- reduce radio delay

>[!note] New techniques
>- hybrid ARQ (HARQ)
>- fast scheduling
>- adaptive modulation and coding (AMC)

**PHY channels in HSDPA**
![[Pasted image 20240203135021.png]]
- HS-PDSCH: introduced shorter TTI (2 ms ~ 3 slots), 16 QAM => up to 14.4 Mbit/s

### Radio resource management
- efficient utilization of resources
- guaratneed QoS
- offer high capacity
- techniques: power control, handover, admission control



