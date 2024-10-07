## Contents
- funcitonalitites and modes
---
>[!note]
>RLC is basically mobnet version of TCP

**Main goals**
- segmentation and reassembly
- error correction using ARQ (ACK, NACK)

*RCL maps higher layer units (PDCP blocks) to fit into MAC transport blocks*

PDU datagrams are split to fit into MAC transport block

In LTE, RLC SDUs are concatenated to fit into MAC transport block. This is not the case in 5G, where RLC is moved to MAC to fit low latency requirements

### ARQ
- successful reception of RLC PDUs is acknowledged by ACK
- packets are retransmitted if:
	a) retransmission timeout is triggered (too long a wait for ACK)
	b) error was detected (e.g. via CRC)
- similarly to TCP, RLC uses a sliding window to define how many packets can be transmitted wihtout ACK

### RLC modes
1. **Transparent Mode**
	- no modification to PDCP PDU
	- no header added
	- if size exceeds MAC SDU size, excess is dropped
	- used for cases when PDU sized are known a priori (i.e. control signalling info)
2. **Unacknowledged Mode**
	- segmentation (concatenation), and reassembly
	- RLC header included
	- use case: transport of real time services such as voice
	- ==UDP like==
1. **Acknowledged Mode**
	- segmentation (concatenation), and reassembly
	- RLC header included (overhead)
	- **ARQ enabled**
	- use case: non realtime services such as file downloads
	- ==TCP like==