## Contents
- handover 
	- types, general principle, implementation in LTE/5G, handover interruprion, problems related to hadover, hysteresis, offset, TTT
- neighborhood scanning 
	- neighborhood relation table, reporting, metrics RSRP, RSRQ
---
### Neighborhood scanning

![[Pasted image 20240205133920.png]]
**Terminology**
- serving eNB
- neighbor eNB
- target eNB

- to identify best target eNB in time, UE performs periodic or aperiodic measurement of channel from neighboring eNBs
- serving eNB delivers UEs a *Neighbor Relation Table* (UE can then scan these)

### Handover

**types**
1. soft handover
	- *make b4 break*
	- only in UMTS, not in 4G
	- CMDA allows for more than 1 connected NodeBs
2. hard handover
	- *break b4 make*
	- UE can only be connected to 1 eNB at all times
	- first disconnect from serving
	- then connect to target
	- 4G requirements on interruption <=> **max 27.5 ms**
	- 5G requirements on interruption <=> 0 ms (soft) (Dual Active Protocol Stack)
---
>[!note] Motivation for handover
>apart from channel quality and service continuity also **load balancing**

**Handover tradeoffs**
- maximising channel capcity --> frequent handovers --> overhead and breaks in connection
- minimisng ammount of handovers --> low channel quality and degraded performance
- target: *balance in the middle - not too early, not too late*

**Handover optimisation**
1. hysteresis (usually about 1 ~ 5 dB)
2. Time to Trigger (TTT) (from n ms to seconds)

as per matlab sessions
```matlab
if RSS_targetENB > RSS_servENB + dH
	timer ++
	if timer >= TTT
		timer = 0
		change bsID
	end
end
else
	timer = 0
end
```

---

>[!note] Call Admission Control (CAC)
>- deals with load balancing vs handover
>- target eNB decides if it can admit new user (immigration policy)
>- based on new users QoS and its (eNB's) load

>[!Warning] handovers vs scheduling
>- how to reserve resources for incoming users?
>- task of radio resource reservation

>[!Warning] SINR at target
>- how to predict noise from neighboring cells at target BS?

There are two kinds of handover different in how they redirect the transmission from one eNB to the other.
- one option is to have a direct tunnel between eNBs (X2 hadnover)
- the other is to have them interact via the CN (indirect tunnel, S1 handover)

**Handover interruption**
*After serving eNB issues handover command the UE enters a time period during which it cannot transmit or receive any packets, while it initiates its conversation with target eNB via contention free RAP*
![[Pasted image 20240205165408.png]]

>[!How does 5G achieve zero interruption ?]
>Dual Active Protocol Stack (DAPS)

DAPS has the UL switched upon completion of RAP. DL communication is with serving AND target gNBs in parallel untill RAP completes. This requires PDCP layer to handle the duplicity of PDUs.




