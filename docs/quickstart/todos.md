#####Summary:
| Sl No | Category      | ToDo Count |
| :----:| :------------ | :--------: |
| 1 | Core-Function | **3**  |
| 2 | Usability |  **6** |
| 3 | Reliability |  **6** |
| 4 | Performance |  **0** |
| 5 | Security |  **1** |

### <span style="color:darkred">1.) Core-Function</span>
1. Wifi/Network Issue on boot (was occasional previously - now happens on each boot)
2. atom.nucleus not working without internet (udp multicast seems to require internet)
3. weird behaviours in inconsistent network (non-reproducible/ #hard)

### <span style="color:darkblue">2.) Usability</span>
1. issue in either @drona/store_execution_agent or operator-app : order status not updating since one of Sep commits.
2. operator-app - smoothen/optimise css transitions, avoid unnecessary paints, & reduce dom size.
3. operator-app - station ui ontap - open large size view of the picker-tasks at the station.
4. operator-app - ui optimisation - based on order-mode & picker-mode.
5. web-sdk - facilitating integration with athma
6. web-sdk - promisifying sdk.communicate calls 

### <span style="color:darkorange">3.) Reliability</span>
1. tests to verify Job Queue sanctity in @drona/ror_taskspace
2. tests to verify Task sanctity in @drona/ror_taskspace
3. tests to verify Operation sanctity in @drona/ror_agent
4. tests to verify Communicative sanctity between @drona/store_execution_agent & @drona/ror_taskspace
5. tests to verify Order sanctity in @drona/store_execution_agent
6. tests to verify Communicative sanctity between @drona/ror_agent & @drona/blackbox.plc (or @atom.fsm_agent in development)

### <span style="color:darkgreen">4.) Performance</span>

### <span style="color:red">5.) Security</span>
1. More robust authentication for sdk based connections.