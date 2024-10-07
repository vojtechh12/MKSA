>[!Example] Why CoMP
>- ICIC only restricts RB usage for cell edge users
>- ICIC does not focus on throughput optimisation, only interference mgmt
>- ICIC procedure takes very long time (tens of ms) - cannot react to quick changes in radio channel

CoMP therefore focuses on speeding up the interference mitigation calculations, sharing more elaborate info and even using advanced techniques to achieve higher throughput for cell edge users.

The following introduces the various types of CoMP:
### 1. Coordinated Scheduling
- basically ICIC with sharing more elaborate info more frequently
	- CQI, Precoding Matrix Indicator (which coding to use), rank indicator (MIMO effectiveness report)
- info shared on every TTI (1ms)
- **allocating different resources to cell edge UEs**
- backhaul need to transfer more data and faster

### 2. Coordinated Beamforming
- allocates the same resources to cell edge users
- uses antenna beamforming to differentiate users
- may not be applicable if both users are very close to each other
- often deployed together with CS

### 3. Joint Transmission
- neighboring cells both transmit to the UE concurrently
- notable improvement in throughput
- tigh sync between xNBs required
- advanced signal processing need to be performed at the UE

### 4. Dynamic Point Selection
- similar to JT
- instead of both xNBs transmitting, the one with better channel is dynamically selected
- drops the need for complicated UE's signal processing and tight xNBs sync
- 
