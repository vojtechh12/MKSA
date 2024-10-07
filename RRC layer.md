## Contents
- key funcitonalitites, states, power saving
---
### Key functionalities
- RRC is a 3rd layer control plane only functionality
>[!example] RRC functionalities
>- radio resource mgmt
>- QoS enforcement
>- setting up and maintenance of bearers
>- control UE CQI measurement reports
>- handover decision
>- admission control
>- broadcasting system info
>- security funcitons
>- semi-persistent scheduling

### RRC states
![[Pasted image 20240205132319.png]]
*RRC_inactive* is like a standby mode. It does not consume much more than an idle mode but is a lot faster to recover into *RRC_connected* state

>[!warning] Problem
>- *RRC_connected* state implies high UE energy consumption through continous monitoring of PDCCH

**Solution**
![[Pasted image 20240205132831.png]]

