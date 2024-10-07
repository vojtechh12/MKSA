## Contents
- GSM, UMTS, LTE, LTE-A, LTE-A-Pro, 5G
- block diagrams
- functionalities of blocks
- interfaces
---
## GSM

![[Pasted image 20240202105425.png]]

**areas:**
- Base Station Subsystem (BSS)
- Network and Switching Subsystem (NSS)
- Operation and Support System (OSS)
**blocks:**
- Operation and Maintenance Control (OMC
	- network management and operation
- Network Management Center (NMC)
	- Control of information flow

- Base Transceiver Station (BTS)
	- physical element (incl. antenna)
	- no real logic
- Base Station Controller (BSC)
	- control and management of BTSs
	- contains logic
	- connection management of MSs to MN

- Mobile Switching Centre (MSC)
	- switching plus mobility
	- special MSC = Gateway MSC (GMSC) - gw to public switched telephone network
- Home Location Register (HLR)
	- permanent info about every user (location, services, activity status)
- Visitor Location Server (VLS)
	- temp info about subscribers served by the MSC
- Authentication Centre (AuC)
	- for authentication of subscribers
- Equipment Identity Register (EIR)
	- list of all MSs, their status (authorized, stolen..)

## GPRS

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

### Universal Mobile Telecommunications System (UMTS)

![[Pasted image 20240203111904.png]]
![[Pasted image 20240203111927.png]]
- architecture is actually very similar to GPRS
- still supports both circuit switching and packet switching
- **UTRAN**
	- Node B: PHY layer processing (modem, coding, interleaving...), soft handover, power control
	- RNC: controls functions, e.g. admission control, radio resource control, power control
- **CN:**
	- MSC: circuit switched oriented services
	- HLR: stores users profiles (allowed services, forbidden roaming)
	- VLR: users profiles, UE's location
	- Gateway MSC: circuit switching interface to external CS network
	- SGSN: packet switched MSC
	- GGSN: packet switched GMSC
>[!note] evolution of 3G CN
>blocks for support of IP multimedia services were later introduced

![[Pasted image 20240203112712.png]]

## Long Term Evolution (LTE/-A/-Pro)

**Standardization:**
- rel 8 : : first LTE release (2008), rel 10 : : first 4G compliant LTE standard (LTE-A)
>[!warning]
>technically LTE does not equal 4G (LTE-A does suffice)
- to meet IMT-Advanced requirements for 4G, LTE had to adopt new techniques such as:
	- carrier aggregation
	- enhanced downlink MIMO
	- uplink MIMO
	- cooperative mulitpoint communication
	- densification of cells - heterogenous networks
- rel 13 : : first LTE-A-Pro (NB-IoT)

**Architecture:***
- control functionalitites for radio moving closer to users (smart BTS, no controller)
>[!important]
>LTE-A is now entirely IP switched
![[Pasted image 20240203173626.png]]
- UE: MS, laptop, sensor, machine, car...
- eNB (evolved Node B): basically Node B with integrated RNC
	- radio resource mgmt for allocation of resources
	- mobility control, scheduling, encryption
	- Home eNodeB for femtocell
	- Small Cell eNodeB for small cells
---
- Mobility Management Entity (MME):
	- control signalling between UE and EPC
	- (SMF and AMF from 5G)
	- establishment of connection, PDU seshion
	- roaming
- Serving Gateway (S-GW)
	- transfers IP packets of **user data**
	- local mobility anchor for handover betwen eNBs
- Packet Gateway (P-GW)
	- responsible fro QoS and flow mgmt
	- anchor for non-3GPP handover (what might that be?)
- Home Subscriber Server (HSS)
	- users subscription info (QoS, profile, roaming profile)
	- database of users
	- keeps info about users home MME
- Policy Control and Charging Rules Function (PCRF)

>[!example] Interfaces in E-UTRAN and EPC
>- LTE-U_u
>- X2 (eNB to eNB)
>- S1-MME: control plane
>- S1-U: user plane
>- S6a (MME to HSS)
>- S10 (MME to MME)
>- S11 (MME to S-GW)



