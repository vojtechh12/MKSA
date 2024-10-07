## Contents
- general principle (assignment of resources based on metric)
- metrics
- dynamic and semi persistent
---
### General

>[!note] Scheduling
>- efficient assignment of RBs to UEs
>- associate MCS to each RB & UE

**Dynamicity of scheduling**
1. (semi)-persistent
	- static allocation of resources by the RRC
2. dynamic
	- allocation decided on every TTI for each RB


>[!important]
>*Scheduling decision must be of low complexity, since complex alogorihms might to converge in time*

----
### Metrics
- Scheduler allocates k-th RB to the j-th UE if its metric is the highest of all UEs
- *for each RB, scheduler calculates given metric for all UEs and assigns the RB to the UE with the highest metric*
	$m_{j,k}= \max_i {m_{i,k}}$

>[!example] parametres considered for metric
>- Channel quality
>- Buffer status (to avoid buffer overflow)
>- QoS (buffer status, priority)
>- Resource allocation history (control **fairness**)






