# BatteryBridge
The BatteryBridge is a PowerPath control circuit used for powering the essential electronics on the SwitchSystem PCB in case of grid disconnection.
As the SwitchSystem PCB is only having power when the homecharger is in charge state (IEC 61851 state B/C), the PCB will lose power when changing from charging to discharging of the vehicle.
Therefore this PCB was needed to ensure that the essential electronics always had power. The PCB consists of 3 parts, the high-efficiency buck and boost converters, the powerpath controller, and
the battery charger. The battery chosen for this prototype was a labcell 3.7v battery, however talks with various battery manufactures for long-life battery solutions were done to ensure
long lifespan of the add-on charging solution. The schematics is built by hierachichal layers, with the root having the components the user can interact with.
Simplified description:
A 3.7V battery was connected to a battery charger, a power path controller and converters. When the homecharger was in state B/C, the battery would charge, and the power path controllers
would turn of the output of the batterybridge. The output is connected to 3.3v, 12v and 5v (first version only had 5v and 3.3v) for the Raspberry Pi on the main SwitchSystem PCB through 2 JST connectors. 
When the homecharger changed state, and the SwitchSystem PCB therefore lost power, the BatteryBridge outputs would turn on, powering the SwitchSystem PCB.