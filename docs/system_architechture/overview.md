##DRONA

1. AutoStore
> robot-driven mini-load storage & fulfillment system. <br/>
```mermaid
graph LR
  INP-AS(Orders) -----> DAS(AutoStore)
  DAS -----> OUT-AS(Packaged-Orders)
```

  
2. Org Moderator
> the org-level management system for planning new stores or moderating performance of existing stores in the org.


``` mermaid
graph LR
  PC>Potential-Customer] --->|requirements| OPLM(Planning Moderator);
  EC>Existing-Customer] --->|requirements| OPLM;
  EC <---> OPEM(Performance Moderator);
  OPEM ----> DAS1[Drona AutoStore 1];
  OPEM ----> DAS2[Drona AutoStore 2];
  OPEM ----> DASn[Drona AutoStore n];
  subgraph Drona-Org-Moderator
    OPLM;
    OPEM;
  end
  subgraph Drona Autostore Instances
    DAS1;
    DAS2;
    DASn;
  end
```



##Drona AutoStore *(or just 'Autostore')* <br/>

``` mermaid
graph TD
  linkStyle default interpolate basis
  INP[Order-Requests] --> SE
  subgraph Drona AutoStore
	  SE[Drona Store Executor] --->|Tasks| G2PA[Goods-to-Person Agent];
	  SE[Drona Store Executor] --->|Tasks| I2OA[Item-to-OrderBuffer Agent];
	  G2PA --> G2PANI[G2P Agent Navigation Interface];
	  G2PANI --> SI[Storage Interaces];
	  G2PANI --> PAI[Picking Agent Interfaces];
	  PAI --> G2PANI --> SI;
	  I2OA ---> PAI;
  end
  PAI --> OUT[Packaged-Orders]
```

An Autostore Instance is composed of the following : 

1. Store Executor
> microservice managing the inventory & orders, sending & monitoring tasks to other agents.

2. Goods2Person Agent(s)
> a pair of 2 microservices & a black-box interface constituting the robot that moves totes/cases between storage & picking-agent interfaces.

3. Storage Interface(s)
> the tote/case storage infrastructure, constituting the goods2person agent's workspace.

4. G2P Agent Navigation Interface
> the infrastructure used by goods2person agent to navigate its workspace.

5. Picking-Agent Interface(s)
> the buffer storage infrastructure where totes are delivered to & returned from, constituting the goods2person agent's workspace as well as the item-picking agent's workspace.

6. Item-to-OrderBuffer Agent(s)
> currently the human agent that picks items from totes/cases into order-buffers at the picking-agent interface.
<br/>

##Org Moderator : <br/>
> *deployed separately for each org(customer), example - *<br/>
> *Demo Org: *<a target="_blank" href="https://demo-org.drona.footloose.io/">
	*demo-org.drona.footloose.io*
  </a><br/>

Org Moderator is composed of the following : 

1. Org-Planning Moderator : 
> helps plan new stores based on models & metrics generated against requirements in realtime. <br/>

2. Org-Performance Moderator : 
> helps modearate performance of existing stores. <br/>


##Org-Planning Moderator
1. Visit drona.footloose.io <br/>
2. Configure Requirements <br/>
> no of ASUs <br/>
> order throughput & frequency <br/>
> tote size <br/>
> no of picking/counter staff <br/>
> type of fulfilment (choose from list) <br/>
> spatial constraints (length, breadth & height) <br/>
	3. Review Cost & Performance of the Generated Model <br/>
> setup costs <br/>
> &nbsp;&nbsp;&nbsp; no of goods2person robots <br/>
> &nbsp;&nbsp;&nbsp; no of picking-interfaces <br/>
> spatial footprint <br/>
> &nbsp;&nbsp;&nbsp; no of aisles & levels <br/>
> operation costs <br/>
> performance <br/>
> &nbsp;&nbsp;&nbsp; mean order time <br/>
> &nbsp;&nbsp;&nbsp; no of orders per day & per hour <br/>

##Org-Performance Moderator
