 # 🌬️ Automotive HVAC Control System | Simulink + Stateflow + MIL Testing

## 📌 Project Overview  
This project involves the development of an HVAC (Heating, Ventilation, and Air Conditioning) control system for vehicle cabins using a Model-Based Design approach in MATLAB/Simulink. Starting with a clear understanding of system functionality, I created structured system requirements that drove the development of a bus-based Simulink model integrated with Stateflow for logic control. Each requirement was linked to specific test case scenarios, and the system was validated using Model-in-the-Loop (MIL) simulations to ensure functional accuracy under various operational conditions.

HVAC systems play a vital role in enhancing passenger comfort, maintaining driver alertness, and ensuring visibility through effective defogging and climate control. As vehicles become more intelligent and energy-efficient, precise HVAC control is essential for both thermal management and user experience.

---

## ⚙️ What I Built  

✅ **HVAC Control Model**  
Simulink + Stateflow-based implementation of HVAC logic including:
- Fan Speed Control Logic  
- Mode Selection (Vent, Floor, Defrost)  
- AC and Recirculation Control  
- Temperature Targeting & Feedback Loops  

✅ **Bus-Based Signal Architecture**  
- `HVAC_Bus.mat` for organized and scalable signal handling  

✅ **MIL Simulation & Validation**  
- Developed exhaustive test cases for each system requirement  
- Simulated real-world inputs and logged outputs to verify correctness  
- Generated MIL test reports to trace requirement compliance  

---

## 📈 Key Outcomes  

🧪 **Requirements-Driven Development**  
- Excel-based requirement and test case traceability ensured complete test coverage  

🧠 **Integrated Stateflow Logic**  
- Mode switching and fan logic implemented using Stateflow to handle complex state transitions  

🚗 **Functional Verification Through MIL**  
- Verified system response across normal, boundary, and failure input scenarios  

✅ **Robust Design for Edge Cases**  
- Addressed invalid combinations like simultaneous AC and heater demand or rapid input switching  

---

## 🧠 Tech Stack  
| Tool              | Purpose                                      |
|-------------------|-----------------------------------------------|
| MATLAB & Simulink | Model creation, simulation, and Stateflow     |
| Simulink Test     | MIL testing, signal logging, test manager     |
| Excel             | Requirement & test case documentation         |
| Bus Architecture  | Structured I/O via `HVAC_Bus.mat`             |

---

## 🔍 How It Works  

### 🛠️ Key Inputs  
| Signal Name                       | Description                                  |
|----------------------------------|----------------------------------------------|
| `Fan_Speed_SW`                   | Switch to control blower speed               |
| `Face_Only_SW`                   | Selects air flow to face vents only          |
| `Face_Legs_SW`                   | Selects air flow to both face and leg vents  |
| `Legs_Only_SW`                   | Selects air flow to leg vents only           |
| `Legs_Defog_SW`                  | Selects air flow to legs and windshield      |
| `Defog_Only_SW`                  | Activates defogger for windshield only       |
| `Int_Cir_SW`                     | Internal air circulation toggle              |
| `AC_SW`                          | Air conditioning system switch               |
| `Rear_Defog_SW`                  | Rear defogger control                        |
| `Temp_SW`                        | Cabin temperature setpoint input             |
| `Face_Blow_Enable_Motor_pos`     | Motor position feedback for face airflow     |
| `Legs_Blow_Enable_Motor_pos`     | Motor position feedback for legs airflow     |
| `Defog_Enable_Motor_pos`         | Motor position feedback for defogger         |

### 💡 Key Outputs  
| Signal Name                      | Description                                        |
|----------------------------------|----------------------------------------------------|
| `Fan_Motor`                      | Controls the blower motor                         |
| `Face_Blow_Enable_Motor`        | Activates motor for face vents                    |
| `Legs_Blow_Enable_Motor`        | Activates motor for leg vents                     |
| `Defog_Enable_Motor`            | Activates motor for defogger                      |
| `AC_Compressor_Actuator`        | Engages the AC compressor                         |
| `Cool_Heat_Valve_Motor`         | Controls valve for cooling/heating mode           |
| `Rear_Defog_Ckt_Enable`         | Enables rear defogger circuit                     |

---

## ✅ Example Test Case Scenarios  

| Test Case                        | Input Conditions                                                              | Expected Output Behavior                                                                 |
|----------------------------------|--------------------------------------------------------------------------------|------------------------------------------------------------------------------------------|
| **TC1: AC Cooling with Recirculation** | `AC_SW = ON`, `Int_Cir_SW = ON`, `Fan_Speed_SW = HIGH`                     | `AC_Compressor_Actuator = ON`, `Fan_Motor = HIGH`, internal air loop activated           |
| **TC2: Heating Mode Only**          | `Temp_SW = HIGH`, `AC_SW = OFF`, `Fan_Speed_SW = MEDIUM`                   | `Cool_Heat_Valve_Motor = HEAT`, `Fan_Motor = MEDIUM`, `AC_Compressor_Actuator = OFF`     |
| **TC3: Defog Windshield**           | `Defog_Only_SW = ON`, `Fan_Speed_SW = HIGH`                                | `Defog_Enable_Motor = ON`, `Fan_Motor = HIGH`, `AC_Compressor_Actuator = ON`             |
| **TC4: Face and Legs Mode**         | `Face_Legs_SW = ON`, `Fan_Speed_SW = LOW`                                  | `Face_Blow_Enable_Motor = ON`, `Legs_Blow_Enable_Motor = ON`, `Fan_Motor = LOW`          |
| **TC5: Rear Defog Activation**      | `Rear_Defog_SW = ON`                                                        | `Rear_Defog_Ckt_Enable = ON`                                                             |



## 🚘HVAC Model



