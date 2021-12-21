## Frequently Asked Question

### Q: Order In Operator APP is not moving to ongoing state?


if the order is created from operator app UI and dispense order is not moving to ongoing state from pending state. it is because the order is not moving from taskspace to execution space. this happens when all the stations are filled. If this happens following steps needs to be performed.
 
- open the drona-store-execution-db on mongo 
- navigate to traystations collection
- if the value of payload is filled with bin number for all stations the clear that coloumn.
- after that orders will start flowing
- <b>Note above steps should be performed on local developement not on original robot </b>


### Q: All Order In Operator APP is moving to Error state?

if the order created from operator UI is moving to error state from pending or ongoing state. possible reason could be ROR-agent and FSM agent are not able to talk to each other. both MODBUS and PLC server and clients are not connected to each other.
Please refer to the [following relationship](../agents/ror_agent.md)