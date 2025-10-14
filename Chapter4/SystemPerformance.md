# System Performance

This section covers the key factors that determine the performance of a computer system, focusing on the Central Processing Unit (CPU).

## ⚙️ Cores (核心)

### What is a core?

A **Core (核心)** acts like a mini-CPU within the main CPU. It is capable of fetching, decoding, and executing instructions independently.

Each core has its own:
-   **Control Unit (CU)**
-   **Arithmetic Logic Unit (ALU)**
-   **Registers (寄存器)**

A CPU with more than one core is known as a **multicore CPU (多核处理器)**.

> [!IMPORTANT]
> Multicore CPUs allow for **Parallel Processing (并行处理)**, where multiple instructions are processed at the same time by different cores, significantly improving performance for demanding tasks.

---

### Performance Impact

-   A **dual-core processor** has 2 cores.
-   A **quad-core processor** has 4 cores.

Generally, more cores lead to better performance, as more tasks can be handled simultaneously.

🔬 **Example:**
A quad-core CPU running at 3GHz can theoretically process:
`4 cores × 3 billion cycles/second = 12 billion instructions per second`

> [!WARNING]
> A dual-core processor is not always twice as fast as a single-core processor. This is because:
> 1.  Some overhead time is required for the operating system to coordinate and distribute tasks between the cores.
> 2.  Not all tasks can be split across multiple cores. Some tasks are **Sequential (串行)** and must be executed step-by-step on a single core.

## ⏱️ Clock Speed (时钟速度)

### What is clock speed?

The internal clock of a CPU generates regular electrical pulses to synchronize all computer operations. It constantly switches between 0 and 1.

> [!IMPORTANT]
> **Clock Speed (时钟速度)** measures the number of cycles (or state changes) the CPU's clock can perform per second. The unit of measurement is **Hertz (Hz)**.

-   One cycle per second is 1 Hz.
-   A typical modern clock speed is around 2.3 GHz, which means 2.3 billion cycles per second.

---

### Performance Impact

A higher clock speed means more Fetch-Decode-Execute cycles can be completed per second, allowing the CPU to process more instructions in a given amount of time. This results in faster and more efficient task execution.

> [!NOTE]
> Some complex instructions may require more than one clock cycle to complete. Therefore, clock speed is a measure of cycles, not necessarily a direct measure of instructions per second.

## 🗄️ Cache Memory (高速缓存)

### What is cache memory?

**Cache (高速缓存)** is a small, extremely fast type of volatile memory that is part of **Primary Storage (主存储)**. It is located closer to the CPU than RAM, and in some cases, directly integrated into the processor cores.

> [!IMPORTANT]
> The purpose of cache is to store frequently used data and instructions. Because it is much faster to access than RAM, it reduces the time the CPU spends waiting for data, thus speeding up overall system performance.

💡 **Analogy:**
Imagine the CPU is a chef and RAM is a large pantry down the hall. Cache is like a small set of shelves right next to the chef's cooking station, holding the most commonly used ingredients. The chef can grab these ingredients much faster, speeding up the entire cooking process.

---

### Levels of Cache

Cache is organized in a hierarchy of levels, each with different characteristics regarding speed, size, and proximity to the CPU cores.

| Level | Location | Speed | Size |
| :--- | :--- | :--- | :--- |
| **Level 1 (L1)** | Inside each CPU core | Fastest | Smallest (e.g., 32-64 KB) |
| **Level 2 (L2)** | Inside or very near each core | Fast | Medium (e.g., 256 KB - 2 MB) |
| **Level 3 (L3)** | Shared by all cores <ins>on the CPU die</ins> | Slower than L1/L2 | Largest (e.g., 4 MB - 32 MB) |

<!-- The original note incorrectly stated L3 was on the motherboard. This has been corrected. Modern L3 cache is on the CPU package itself. -->

> [!WARNING]
> A common misconception is that L3 cache is on the motherboard. For modern processors, it is located on the CPU chip itself and shared among all the cores.

## 🚌 Bus Width (总线宽度)

### What is bus width?

A **Bus (总线)** is a set of parallel wires that connects different components of a computer system, allowing data to be transferred between them. The system bus is typically composed of a **Data Bus**, **Address Bus**, and **Control Bus**.

> [!IMPORTANT]
> **Bus Width (总线宽度)** refers to the number of bits (or parallel wires) a bus has. It determines how many bits of data can be transferred simultaneously in a single operation.

---

### Performance Impact

A wider bus can transfer more data at the same time, leading to higher data transfer rates.

🔬 **Example:**
-   A **32-bit data bus** can transfer 32 bits of data at once.
-   A **64-bit data bus** can transfer 64 bits of data at once.

A wider **data bus** directly contributes to:
-   ✅ Faster processing, as the CPU is not kept waiting for data.
-   ✅ More efficient memory access.

This is especially important for high-performance tasks such as gaming, video editing, and processing large datasets.