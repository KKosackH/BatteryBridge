# BatteryBridge  

The **BatteryBridge** is a PowerPath control circuit that ensures the essential electronics on the SwitchSystem PCB remain powered during grid disconnection.  

The SwitchSystem PCB only receives power when the home charger is in **IEC 61851 state B/C** (charging mode). When transitioning from charging to discharging, the PCB would normally lose power. The BatteryBridge solves this by automatically switching to battery supply, keeping the system running seamlessly.  

---

## Features  
- **Power continuity**: Maintains operation when the grid is disconnected or charger state changes.  
- **Integrated converters**: High-efficiency buck and boost converters for multiple voltage rails.  
- **PowerPath control**: Manages seamless switching between charger and battery.  
- **Battery charging**: Supports onboard Li-ion battery charging.  
- **Multiple outputs**: 3.3 V, 5 V, and 12 V regulated outputs (v1 only included 3.3 V and 5 V).  

---

## Design  
The BatteryBridge PCB consists of three main parts:  
1. High-efficiency buck and boost converters  
2. PowerPath controller  
3. Battery charger  

For the prototype, a **3.7 V lab cell battery** was used. Long-life battery options are being evaluated with manufacturers to ensure durability of the add-on solution.  

The schematic is organized hierarchically, with the root showing all user-interactable components.  

---

## Operation  
- **State B/C (charging)**:  
  - The battery charges.  
  - Outputs are disabled (system powered directly from charger).  

- **Other states (discharging / grid disconnected)**:  
  - Outputs are enabled.  
  - Battery supplies regulated 3.3 V, 5 V, and 12 V rails to the SwitchSystem PCB via two JST connectors.  

---

## PCB Images  

### Front Side  
![BatteryBridge Front](BatteryBridge/docs/batterybridge_front.png)  

### Back Side  
![BatteryBridge Back](BatteryBridge/docs/batterybridge_back.png)  

---

## Outputs  
- **3.3 V**  
- **5 V**  
- **12 V**  

These outputs are used primarily to power the Raspberry Pi and essential circuits on the SwitchSystem PCB.  

