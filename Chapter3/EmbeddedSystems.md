# Embedded Systems (嵌入式系统)

## What is an Embedded System? (什么是嵌入式系统?)

> [!IMPORTANT]
> An **embedded system** is a computer system, typically consisting of both hardware and software, which is used to perform a **_dedicated function_** (特定功能) inside a larger mechanical or <ins>electrical</ins> system.

- They are _not_ general-purpose computers like a laptop or desktop PC.
- The software they run is often called **firmware (固件)** and is stored in non-volatile memory.

---

## Examples of Embedded Systems (嵌入式系统的例子)

> [!NOTE]
> Embedded systems are ubiquitous in modern life. They are found in almost any electronic device with a specific function.

A wide range of devices contain embedded systems, including:
- Home Appliances (家用电器):
  - **Washing machines (洗衣机)**
  - **Dishwashers (洗碗机)**
  - **Coffee machines (咖啡机)**
  - **Heating thermostats (暖气温控器)**
- Medical Equipment (医疗设备):
  - **Hospital equipment (医院设备)** such as heart rate monitors or automated insulin pumps.
- Automotive and Transport (汽车与交通):
  - **Satellite navigation systems (卫星导航系统)**
  - Engine management units in cars
  - **Traffic lights (交通信号灯)**
- Industrial and Commercial (工业与商业):
  - **Factory equipment (工厂设备)** and robotics
  - **Security systems (安防系统)**
  - Point-of-Sale (POS) terminals

> [!TIP]
> 💡 When asked for an example in an exam, it's best to choose one you can explain. For instance, "A washing machine's embedded system is dedicated to controlling the wash cycle, water temperature, and spin speed."

---

## Benefits and Drawbacks of Embedded Systems (嵌入式系统的优缺点)

| Benefits (优点) ✅                                                                                                        | Drawbacks (缺点) ❌                                                                                                       |
| ------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| **Compact Size (体积小巧)**: Minimal hardware makes them small and easy to fit into host devices.                         | **Limited Functionality (功能有限)**: Designed to perform only a specific set of tasks and nothing else.                |
| **Low Power Consumption (低功耗)**: Optimized hardware and software lead to high energy efficiency.                       | **Difficult to Upgrade or Repair (难以升级或修复)**: Hardware is often integrated and sealed, making repairs or upgrades difficult. |
| **High Speed and Reliability (高速且可靠)**: Designed and optimized for quick, repetitive tasks, making them very stable. | **Limited Resources (资源有限)**: Typically have very limited memory (RAM/ROM) and processing power.                    |
| **Lower Cost to Produce (生产成本低)**: Mass production of a single design with minimal components reduces costs.         | **Inflexible (灵活性差)**: Cannot be easily reprogrammed by the end-user for different tasks.                             |
| **Real-Time Operation (实时运行)**: Can respond to events instantly, which is critical for time-sensitive operations like alarms or vehicle controls. | **Potential Security Risks (潜在安全风险)**: If connected to a network, their limited resources may offer less protection against cyber threats. |