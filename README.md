# WSN **Project** - Central Hidrelétrica Cachoeira Dourada S.A.
Explore data from a WSN in a Hydroelectric using Machine Learning methods and Python.

A wireless sensor network (WSN) is a collaborative network that contains a collection of sensor nodes, each of which has a power source, and is able to individually and autonomously complete the function of discovering and maintaining routing to other sensors through wireless links.

A WSN deployed in an industrial environment must assure an acceptable degree of reliability and security, thus, robust network design is required. Traditional methods, in which the propagation channel is evaluated through point-to-point communication links prior to the network installation, are frequently not executed in complex Electric Power System.<br>
Similar to other EPS environments, power plants are complex facilities that present strict regulations for safety, making the wireless channel analysis difficult with the conventional point-to-point methods. Therefore, it is often the case that the radio nodes of the WSN are initially located near the spots where specific equipment needs to be monitored, and then the number of routers and their hardware settings are adjusted following a trial-and-error procedure until a stable topology is achieved. This recurrent procedure may not yield an optimum result from the standpoint of the number of nodes, redundancy, power consumption, etc.<br>

- As an alternative to characterize the channel of communication the authors have propose that the use of the RSSI data registered by the WSN nodes can then be used as a characterization method, and consequently, as a tool for improving the settings of the installed network.
- Through the analysis RSSI data, long-term mean values are obtained and used as a basis for comparing the channel behavior to events related to operations on the power plant that occurred on particular days. Complementary to this, we discuss how the recorded data can reveal issues about the functioning of specific nodes.
- Through a cross-correlation analysis of the measured RSSI data of each bidirectional link, it is possible to estimate the rate of increase on the transmission power of each node, which is directly related to the quality of the links.
- High-level RSSI values registered during recordings, which are treated as undesired information when modeling the channel, can be co-related to the electromagnetic interference (EMI) sources present in the power plant. 

The data comes from the Hydroelectric Power Plant Cachoeira Dourada (MG, Brazil) The systems consist in 7 Routers and 1 Coordinator, total of 8 Routers. The location of the radios can be seen in the image.

1. **There are 8 locations and 1 Router for every location.**
2. **Each router gives information about it's temperature and bus voltage using channels 7 and 6 respectively and a timestamp.**
3. **Only 3 of the radios were used to gather information from sensors, the others were used for network routing.<br>**
    In <span style="color:red">Montante UG5</span> location is Router <span style="color:blue">57.FE.0E</span>, which communicates with Sensors: 
        Acquisition - Temperature E5.5A.24  that extract info from (2) PT100 using channels 0 and 1, and it's temperature and VBus using channel 7 and 6. 
        Acquisition - Current / Voltage CB.0A.C0 that extract info about the level in the dim using channel 1, and it's temperature and VBus using channel 7 and 6.
        Power - Solar Panel B2.9F.A9 that extract the MPPT voltage and the voltage from the solar panel using channels 0 and 1.
    
    In <span style="color:red">Poço de Drenagem A</span> location is Router <span style="color:blue">57.FE.0F</span>, which communicates with: 
        Acquisition - Current / Voltage E9.39.32  which is a level probe , uses channel 1.
        Power - AC/DC Input 0D.82.38 that measures voltage from Battery and Supply voltage using channel 0 and 1, and it's temperature and VBus using channel 7 and 6.
    
    In <span style="color:red">Transformador Elevador</span> location is Router <span style="color:blue">57.FE.03</span>, which communicates with: 
        Acquisition - Temperature sensor 8D.AC.91  which gives 2 temperatures (Oil and Gabinetes) through channels 0 and 1.
        Power - Solar Panel sensor 39.E2.80 that extract the MPPT voltage and the voltage from the solar panel using channels 0 and 1.
    
4. **The <span style="color:red">Montante UG5 and Transformador Elevador Routers</span> are powered by Solar energy.**

5. **The <span style="color:red">Poço de Drenagem A Router</span> is powered by AC energy from the Hydroelectric plant.**

6. **Radio RC is the Coordinator (00.57.FE.04). <br>
   Radio R1 is module 00.57.FE.09 <br>
   Radio R4 is module 00.57.FE.01 <br>
   Radio R5 is in Montante UG5 and module 00.57.FE.0E <br>
   Radio R2 is in Transformador Elevador and module 00.57.FE.03 <br>
   Radio R6 is in Poço de Drenagem A and module 00.57.FE.0F <br>
   Radio R3 is also in Poço de Drenagem A but is a Radio, module 00.57.FE.05 or 00.57.FE.06.**

The radios operated in the 2.4 GHz band under the Zigbee 3.0 protocol and in a mesh configuration. The theoretical receiver sensitivity of each node was −95 dBm. All the radios were set as
routers (relays), so each one was able to establish different routes to communicate up to the coordinator. The coordinator uploaded the radios data to a local database. 

The radios are able to automatically increase their transmission power to improve their link quality

<img src="images\\Router_Location.jpg" style="width:800px;heigth:600px"/> 

