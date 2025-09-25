# 🔬 Primary Memory: RAM vs ROM

## RAM (Random Access Memory)

### 🔑 What is RAM?

> [!IMPORTANT]
> **RAM (Random Access Memory / 随机存取存储器)** is a form of **primary storage (主存储)** that is directly connected to the CPU. It holds the data and instructions that are currently in use by the computer.

-   **_Volatility (易失性)_**: `RAM` is **volatile (易失性的)**, which means its contents are lost when the power is turned off.
-   **_CPU Access (CPU访问)_**: For the CPU to process data and instructions, they must first be copied from **secondary storage (二级存储)** into `RAM`.
-   **_Speed (速度)_**: `RAM` is extremely fast working memory, significantly faster than any secondary storage device.
-   **_Read/Write (读/写)_**: `RAM` is **read/write (可读可写)**, meaning data can be both read from it and written to it.
-   **_Capacity (容量)_**: Compared to `ROM`, `RAM` has a much larger storage capacity.

> [!WARNING]
> A common misconception is confusing primary storage (`RAM`) with secondary storage (like SSDs or HDDs). Remember, the CPU can **only** directly access data stored in primary memory.

---

## ROM (Read Only Memory)

### 🔑 What is ROM?

> [!IMPORTANT]
> **ROM (Read Only Memory / 只读存储器)** is a form of **primary storage (主存储)** that holds the initial instructions a computer needs to start up. These instructions are known as the **Bootstrap (引导程序)**.

-   **_BIOS (基本输入输出系统)_**: `ROM` contains the **BIOS (Basic Input Output System)**, which performs hardware checks and loads the operating system.
-   **_Location (位置)_**: `ROM` is a small memory chip located on the computer's motherboard.
-   **_Speed (速度)_**: `ROM` is fast memory, much faster than secondary storage but typically slower than `RAM`.
-   **_Volatility (易失性)_**: `ROM` is **non-volatile (非易失性的)**, meaning its contents are retained even when the power is turned off.
-   **_Read/Write (读/写)_**: As the name suggests, `ROM` is **read-only (只读)**. Its data is written during manufacturing and cannot be easily changed.
-   **_Capacity (容量)_**: Compared to `RAM`, `ROM` has a much smaller capacity.

### 💡 Differences between RAM & ROM

| Feature (特性) | RAM (Random Access Memory) | ROM (Read Only Memory) |
| :--- | :--- | :--- |
| **Speed (速度)** | ✅ Very Fast | Fast (but slower than RAM) |
| **Capacity (容量)** | Gigabytes (GB) | Megabytes (MB) |
| **Stores (存储内容)** | Programs and data currently in use. | **Bootstrap (引导程序)** and start-up instructions. |
| **Read/Write (读/写)** | Read & Write | Read Only |
| **Volatility (易失性)** | **Volatile (易失性)** | **Non-volatile (非易失性)** |

---

## ## Types of RAM: SRAM vs DRAM

### ### SRAM (Static RAM)

**SRAM (Static RAM / 静态随机存取存储器)** is a type of `RAM` that holds data as long as power is supplied.

-   **_Technology (技术)_**: It is made from **flip-flops**[^1], a type of digital logic circuit. <ins>This design does not require the data to be periodically refreshed.</ins>
-   **_Usage (用途)_**: `SRAM` is used where speed is the highest priority, more so than capacity or cost.
    -   🔬 **Example**: **Cache Memory (高速缓存)**, where extremely quick access to frequently used data is critical for CPU performance.
-   **_Characteristics (特点)_**:
    -   ✅ **Very Fast**: Faster than `DRAM` because there is no need for refreshing.
    -   ✅ **Low Power Consumption**: Uses less power than `DRAM` in an active state.
    -   ❌ **Expensive**: More complex and costly to manufacture.
    -   ❌ **Low Density**: Takes up more physical space per bit, leading to a lower storage capacity compared to `DRAM`.

[^1]: A **flip-flop (触发器)** is a circuit that has two stable states and can be used to store state information. It is the fundamental building block of `SRAM`.

### ### DRAM (Dynamic RAM)

**DRAM (Dynamic RAM / 动态随机存取存储器)** is a type of `RAM` that stores each bit of data in a tiny **capacitor (电容器)** within an integrated circuit.

-   **_Technology (技术)_**: Because capacitors leak charge, the information eventually fades unless the capacitor charge is **refreshed (刷新)** periodically. <ins>This refreshing process makes it slower than `SRAM`.</ins>
-   **_Usage (用途)_**: `DRAM` is commonly used as the main system memory in computers and other devices.
    -   🔬 **Example**: The main `RAM` in a PC or laptop, where large amounts of cheaper storage are required.
-   **_Characteristics (特点)_**:
    -   ✅ **Cheaper**: Less expensive to produce than `SRAM`.
    -   ✅ **High Density**: Can store more data in less physical space, allowing for higher capacity modules.
    -   ❌ **Slower**: Slower than `SRAM` due to the need to constantly refresh the data.
    -   ❌ **Higher Power Consumption**: The refreshing cycles consume more power.

> [!TIP]
> To remember the difference: **S**tatic is **S**uper-fast (and stays put), while **D**ynamic is **D**ense (and needs refreshing).

---

## ## Types of ROM: PROM, EPROM & EEPROM

### ### What are PROM, EPROM & EEPROM?

**PROM**, **EPROM**, and **EEPROM** are all types of `ROM` that differ in how they can be programmed and reprogrammed.

| Feature (特性) | PROM (Programmable ROM) | EPROM (Erasable PROM) | EEPROM (Electrically Erasable PROM) |
| :--- | :--- | :--- | :--- |
| **Can be reprogrammed?** | ❌ No – programmed once only. | ✅ Yes – can be erased and rewritten. | ✅ Yes – can be erased and rewritten. |
| **Erased using...** | Cannot be erased. | **UV Light (紫外线)** | **Electric Voltage (电压)** |
| **Must be removed?** | Not applicable. | ✅ Yes – must be removed from the device. | ❌ No – can be erased in-place. |
| **Erased all at once?** | Not applicable. | ✅ Yes – the entire chip is erased at once. | ❌ No – specific parts (bytes) can be erased. |
| **Common Use (常见用途)** | Permanent firmware. | Reprogrammable chip development. | BIOS chips, <ins>**Flash Memory** (e.g., SSDs, USB drives)</ins>. |
| **Examples (示例)** | Remote controls, basic calculators. | Older arcade machines, early device prototypes. | Modern computer BIOS, smart cards, USB sticks. |