# Monitoring vs Control

## Monitoring Systems (监控系统)

> [!IMPORTANT]
> A **monitoring system** is used to **collect data (收集数据)** continuously through observation. It works by _passively gathering data_ and does not interact with or change the environment.

-   The system **does not take action (不采取行动)** based on the data collected.
-   It is designed for high accuracy using precise **sensors (传感器)** and measurements.

---

### 🔬 Examples of Monitoring Systems

*   **Weather Stations (气象站)**
    -   Collect data like **temperature (温度)**, **wind speed (风速)**, **humidity (湿度)**, and **rainfall (降雨量)**.
    -   Used by meteorologists to observe and predict weather patterns.
    -   The system collects data 24/7 but does not react to or change the weather.

*   **Patient Monitoring (病患监护)**
    -   Tracks vital signs like **heart rate (心率)**, **oxygen levels (血氧水平)**, and **blood pressure (血压)** in real-time.
    -   Alerts medical staff if readings go outside safe ranges.
    
    > [!WARNING]
    > The system itself just records and displays data; it does not directly treat the patient. This is a key feature of a monitoring system.

## Control Systems (控制系统)

> [!IMPORTANT]
> A **control system (控制系统)** is used to automatically manage or adjust a process based on data collected from sensors. It actively **interacts with the environment (与环境交互)**.

-   It works by monitoring input, then taking action if certain conditions are met.
-   Control systems are designed to keep systems stable, safe, or working efficiently without human input.
-   They typically involve three main components: **Sensors (传感器)** to gather data, a **Processor (处理器)** to make decisions, and **Actuators (执行器)** to perform actions.

---
<!-- Added the definition of Actuator as it was missing from the original notes and is a required syllabus point. -->

> [!NOTE]
> 🔑 An **Actuator (执行器)** is an output device that converts a control signal from the processor into physical action. It is the component that directly causes a change in the environment. For example, a motor, a pump, a heater, or a valve.


---

### 🔬 Examples of Control Systems

*   **Central Heating System (中央供暖系统)**
    1.  **Sensor**: A **thermostat (恒温器)** monitors the room temperature.
    2.  **Processor**: Compares the current temperature to the set level.
    3.  **Action**: If the temperature drops below the set level, the processor sends a signal.
    4.  **Actuator**: The **boiler (锅炉)** is switched on to heat water.
    5.  Once the target temperature is reached, the system turns the heating off automatically. The system constantly checks and adjusts. This entire process is a **[Feedback Loop](#feedback-loops-反馈回路)**.

*   **Automatic Irrigation System (自动灌溉系统)**
    1.  **Sensor**: A **moisture sensor (湿度传感器)** monitors soil moisture levels.
    2.  **Processor**: Compares the moisture level to a preset threshold.
    3.  **Action**: If moisture drops too low, a signal is sent.
    4.  **Actuator**: A **valve (阀门)** is opened, activating sprinklers to water the plants.
    5.  Once the soil reaches the correct moisture level, the system turns off the water supply. This ensures plants are watered efficiently without wasting resources.

## Use of Sensors (传感器的使用)

### What are sensors? (什么是传感器?)

-   **Sensors (传感器)** are **input devices (输入设备)**.
-   They measure a physical property of their environment, such as light levels, temperature, or movement.
-   Sensors are fundamental components for both monitoring and control systems.

### Sensor Types (传感器类型)

| Sensor Type (传感器类型) | What it Measures (测量对象) | Typical Use (典型应用) |
| --- | --- | --- |
| **Acoustic (声音)** | Sound levels | - To detect changes in sound levels of industrial machinery.<br>- To monitor noise pollution.<br>- In security systems to detect suspicious sounds (e.g., breaking glass). |
| **Accelerometer (加速度计)** | Acceleration rate, tilt, vibration | - In airbag systems to detect sudden deceleration.<br>- In mobile phones to detect the orientation of the device (portrait/landscape). |
| **Flow (流量)** | Rate of gas, liquid, or powder flow | - To detect changes in the flow through pipes in a water system or factory. |
| **Gas (气体)** | Presence of a specific gas (e.g., carbon monoxide, methane) | - To detect dangerous gas levels in confined spaces (e.g., mines).<br>- In carbon monoxide detectors for home safety. |
| **Humidity (湿度)** | Levels of water vapour in the air | - To monitor and control humidity in greenhouses for optimal plant growth. |
| **Infra-red (红外线)** | Detecting motion or a heat source | - In security systems to detect intruders by sensing body heat.<br>- In automatic doors or faucets. |
| **Level (液位)** | Liquid levels | - To detect the level of petrol in a car's fuel tank.<br>- To control the filling of a water tank and prevent overflow. |
| **Light (光线)** | Light intensity / ambient light levels | - To automatically switch on street lights when it gets dark.<br>- In a camera to adjust the automatic flash. |
| **Magnetic Field (磁场)** | Presence and strength of a magnetic field | - In an Anti-lock Braking System (ABS) to measure wheel speed.<br>- To detect if a door or window is open in a security system. |
| **Moisture (水分)** | Presence and levels of moisture in a solid material | - To monitor moisture in soil for an automatic irrigation system.<br>- To detect dampness in buildings. |
| **pH (酸碱度)** | Acidity or alkalinity | - To monitor soil pH to ensure optimum growing conditions for crops.<br>- To monitor pH levels in chemical processes or aquariums. |
| **Pressure (压力)** | Gas, liquid, or physical pressure | - To monitor tyre pressure in a vehicle.<br>- To monitor pressure in pipes during an industrial manufacturing process. |
| **Proximity (接近)** | Distance to an object without physical contact | - To assist with parking in cars by detecting obstacles.<br>- To monitor the position of objects in robotics and on assembly lines. |
| **Temperature (温度)** | Temperature in Celsius, Fahrenheit, or Kelvin | - In a central heating system to maintain room temperature.<br>- In a computer to control the fan speed and prevent the CPU from overheating. |

## Feedback Loops (反馈回路)

### What is a feedback loop? (什么是反馈回路?)

> [!TIP]
> A **feedback loop (反馈回路)** is a process where the output of a system is "fed back" and used as an input to influence its next action. This allows the system to automatically adjust and stay within set conditions.

-   Feedback allows the system to check if it’s working as expected.
-   The output affects the next input, helping the system make continuous adjustments.
-   This means the system can automatically respond to changes in its environment and self-correct.
-   It helps the system stay within set limits or target values (e.g., temperature, moisture), making it more accurate and efficient without needing human control.

### Example: Central Heating System

The process of the central heating system is a perfect example of a feedback loop:

1.  **Input**: The thermostat (sensor) reads the current room temperature.
2.  **Processing**: The system compares this reading to the desired temperature.
3.  **Output**: If it's too cold, the boiler (actuator) turns on. The "output" is the resulting change in room temperature.
4.  **Feedback**: This new, higher room temperature is then "fed back" as the next input for the thermostat to read.
5.  **Self-Correction**: This cycle continues until the desired temperature is reached, at which point the boiler turns off. The feedback loop ensures the system automatically adjusts to keep the room at the right temperature.