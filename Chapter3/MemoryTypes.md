# 💾 Primary Memory: RAM & ROM

## RAM vs ROM

### 🔑 What is RAM?

**RAM (Random Access Memory / 随机存取存储器)** is a type of **primary storage (主存储)** that is directly connected to the `CPU` and holds the data and instructions that are _currently in use_ by the system, also called "Main Memory" in Von Neumann Model.

-   **RAM** is **_Volatile (易失性)_**, which means its contents are lost when the power is turned off.
-   For the `CPU` to access data and instructions, they must first be copied from **secondary storage (二级存储)** into RAM.
-   It serves as very fast working memory, significantly faster than secondary storage devices like HDDs or SSDs.
-   RAM is **read/write (可读写)**, meaning data can be both read from and written to it.
-   Compared to ROM, it has a much larger storage capacity.

> [!WARNING]
> ⚠️ Because RAM is **volatile**, any unsaved work will be permanently lost if the computer loses power unexpectedly. This is why saving files to a secondary storage device is crucial.

---

### 🔑 What is ROM?

**ROM (Read Only Memory / 只读存储器)** is a type of **primary storage** that holds the initial instructions a computer needs to start up. This start-up program is known as the **_Bootstrap (引导程序)_**.

-   ROM contains the **BIOS (Basic Input Output System / 基本输入输出系统)** or the more modern **UEFI (Unified Extensible Firmware Interface)**.
-   It is typically a small memory chip located on the computer's motherboard.
-   ROM is fast memory, much faster than secondary storage but generally slower than RAM.
-   **ROM** is **_Non-volatile (非易失性)_**, meaning its contents are retained even when the power is turned off.
-   Traditionally, ROM is **read-only (只读)**, meaning data can only be read from it.
-   Compared to RAM, it has a much smaller storage capacity.

> [!NOTE]
> 💡 While traditional ROM is "read-only", modern computers use updatable firmware. This is achieved using special types of ROM like **EEPROM** (Flash memory), which can be rewritten. [See section on PROM, EPROM, & EEPROM](#prom-vs-eprom-vs-eeprom).

### ⚖️ Differences between RAM & ROM

| Feature (特性) | **RAM (随机存取存储器)** | **ROM (只读存储器)** |
| :--- | :--- | :--- |
| **Speed (速度)** | Very fast | Fast (but slower than RAM) |
| **Capacity (容量)** | Gigabytes (GB) | Megabytes (MB) |
| **Stores (存储内容)** | Programs and data currently in use | **Bootstrap (引导程序)** and **BIOS** |
| **Read/Write (读写)** | ✅ Read & Write | ❌ Read Only (Typically) |
| **Volatility (易失性)** | **Volatile (易失性)** | **Non-volatile (非易失性)** |
| **Name in Von Neumann Model (Von Neumann Model中的别称)** | **Main Memory** | N/A |

> [!IMPORTANT]
> **_Volatile Memory_** requires power to maintain the stored information.
> **_Non-volatile Memory_** retains the stored information even when not powered.

## SRAM vs DRAM

### ### What is SRAM?

**SRAM (Static RAM / 静态随机存取存储器)** is a type of RAM that holds data as long as power is supplied, without needing to be periodically refreshed.

-   SRAM is constructed using **flip-flops**[^1], which allows it to be much faster and more reliable than DRAM.
-   Due to its high speed, SRAM is used in applications where access speed is more critical than cost or capacity.
-   🔬 **Example Use Case**: **Cache Memory (高速缓存)**, where the `CPU` needs the quickest possible access to frequently used data.

| Pros (优点) | Cons (缺点) |
| :--- | :--- |
| ✅ **Very fast** – faster than DRAM. | ❌ **Expensive** to manufacture. |
| ✅ **Uses less power** in an idle state. | ❌ **Takes up more space** – lower storage density. |

---

### What is DRAM?

**DRAM (Dynamic RAM / 动态随机存取存储器)** is the most common type of RAM. It stores each bit of data in a separate **capacitor**[^2] within an integrated circuit.

-   DRAM requires the data to be **refreshed constantly**; otherwise, the capacitors will lose their charge and the data will be lost.
-   DRAM is primarily used where large, cost-effective memory is needed.
-   🔬 **Example Use Case**: **Main memory (主内存)** in PCs, laptops, and servers.

| Pros (优点) | Cons (缺点) |
| :--- | :--- |
| ✅ **Cheaper** to produce than SRAM. | ❌ **Slower** than SRAM due to refresh cycles. |
| ✅ **Higher capacity** – greater storage density. | ❌ **Uses more power** due to the need for constant refreshing. |

> [!TIP]
> Think of it this way: **S**RAM is for **S**peed (Cache), and **D**RAM is for **D**ense storage (Main RAM).

## PROM vs EPROM vs EEPROM

### ### What are PROM, EPROM & EEPROM?

**PROM**, **EPROM**, and **EEPROM** are all types of Read-Only Memory that evolved to allow for writing and rewriting under specific conditions, overcoming the limitations of traditional, factory-programmed ROM.

| Feature (特性) | **PROM (可编程只读存储器)** | **EPROM (可擦除可编程只读存储器)** | **EEPROM (电可擦除可编程只读存储器)** |
| :--- | :--- | :--- | :--- |
| **Can be reprogrammed? (能否重编程)** | ❌ No – programmed once only. | ✅ Yes – can be erased and rewritten. | ✅ Yes – can be erased and rewritten many times. |
| **Erased using... (擦除方式)** | Cannot be erased. | **UV light (紫外线)** | **Electric voltage (电压)** |
| **Must be removed? (是否需移除)** | Not applicable. | ✅ Yes – must be removed from the device. | ❌ No – can be erased in-place. |
| **Erased all at once? (是否整体擦除)** | Not applicable. | ✅ Yes – the entire chip is erased. | ❌ No – specific bytes/parts can be erased. |
| **Common Use (常见用途)** | Permanent firmware, prototypes. | Chip development, older devices. | Modern **BIOS/UEFI**, **Flash Memory** |
| **Examples (示例)** | 🔬 Remote controls, basic calculators, early model washing machines. | 🔬 Arcade machines (older models), <ins>early games consoles</ins>. | 🔬 BIOS chips, Smart cards, USB sticks, SSDs. |

<!-- 
I have moved "Early games consoles" from the EEPROM examples to the EPROM examples. Early console cartridges used Mask ROM for mass production and sometimes EPROMs for development or smaller production runs, not EEPROM. This change improves factual accuracy.
-->

[^1]: A **flip-flop** is a digital circuit that can store one bit of data. It has two stable states and does not require refreshing as long as it has power.
[^2]: A **capacitor** is a tiny electronic component that stores electrical charge. In DRAM, a charged capacitor represents a '1' and a discharged one represents a '0'. This charge leaks away over time, hence the need for refreshing.