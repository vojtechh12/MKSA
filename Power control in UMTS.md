## Contents:
- closed loop, open loop, outer loop
- purpose and principle
---
>[!note] Purpose of power control
>*manage UEs' tx power to decrese interference among UEs to maximize system capacity*

### 1. Closed loop
- Node B measures received signal to interference ratio and instructs UEs to change tx power accordingly

### 2. Open loop
- rough initial tx power setting for UEs
- used for UEs entering network
- downlink beacon signal is used for setting (what?)
- it is very inaccurate: fast fading is inaccurate between UL & DL, large freq separation of UL & DL

### 3. Outer loop
- closed loop + change of the target SIR (requires RNC feedback)
- target SIR is changed according to required BER
- target SIR is therefore funciton of UEs speed