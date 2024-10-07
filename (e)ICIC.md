
## 1. ICIC
>[!important] Principle
>1. cells measure interference (frequencies transmitting with high power)
>2. neighbor cells interchange info (OI, HII, RNTP) via X2
>3. calculate ICIC
>4. schedule RBs to mitigate interference

![[Pasted image 20240206105840.png]]

>[!Warning] Problem with ICIC
>- ICIC advises to schedule orthogonal resources in PDSCH
>- it cannot control orthogonal resource allocation in control plane (PDCCH)

*This problem is solved in eICIC*
- eICIC basically combined FDD and TDD to achieve orthogonality in both PDSCH as well as PDCCH (TDD here)
- eICIC introduces so called Almost Blank Subframe to mitigate control channel interference via time domain duplexing
![[Pasted image 20240206111143.png]]
- this has the disadvantage of lower PDSCH throughput
