# Components of the CPU

## What is the CPU?

> [!IMPORTANT]
> The **Central Processing Unit (CPU)** (中央处理器) is often called the 'brain' of the computer. Its primary purpose is to **_fetch, decode, and execute_** instructions from memory to perform tasks.

The CPU is made up of a number of essential components, each with a specific role. These include:
- **Arithmetic and Logic Unit (ALU)**
- **Control Unit (CU)**
- **Registers**
- **System Clock**
- **Immediate Access Store (IAS)**
- **Buses**

---

##  Core Components

![img](https://cdn.savemyexams.com/cdn-cgi/image/f=auto,width=3840/https://cdn.savemyexams.com/uploads/2025/04/33319_2025-04-04-0ha-kleki.png)

The main components work together to process instructions. Their functions are summarized below:

| Component | Full Name | Purpose / Function |
| --- | --- | --- |
| **ALU** | **Arithmetic Logic Unit** (算术逻辑单元) | Performs arithmetic calculations (e.g., `add`, `subtract`) and logical operations (e.g., `AND`, `OR`, `NOT`). |
| **CU** | **Control Unit** (控制单元) | Manages the execution of instructions by sending control signals to other components. It coordinates the flow of data within the CPU and is central to the **Fetch-Decode-Execute cycle**. |
| **System Clock** | - | Generates regular electrical pulses to synchronise all CPU operations, ensuring actions happen in a coordinated sequence. The rate of these pulses is known as the **clock speed**. |
| **IAS** | **Immediate Access Store** (立即访问存储) | Temporarily stores instructions and data that are being actively used by the CPU. |

> [!NOTE]
> 💡 The **Immediate Access Store (IAS)** is the term used for the main memory that can be directly accessed by the CPU. In modern systems, this is known as **Random Access Memory (RAM)** (随机存取存储器).

---
<!-- This entire section on Registers is new, added to meet syllabus requirements. -->
<ins>

## Registers (寄存器)

> [!IMPORTANT]
> 🔑 **Registers** are small, high-speed memory locations within the CPU itself. They are used to temporarily hold data, instructions, or memory addresses that are needed for the current operation. They provide the fastest data access for the CPU.

There are several special-purpose registers you must know:

| Register | Full Name | Purpose / Function |
| --- | --- | --- |
| **PC** | **Program Counter** (程序计数器) | Holds the memory address of the _next instruction_ to be fetched from the IAS. |
| **MAR** | **Memory Address Register** (内存地址寄存器) | Holds the memory address of the instruction or data that is to be fetched from or written to the IAS. |
| **MDR** | **Memory Data Register** (内存数据寄存器) | Temporarily stores the data or instruction that has just been fetched from memory, or is about to be written to memory. It is sometimes called the **Memory Buffer Register (MBR)**. |
| **CIR** | **Current Instruction Register** (当前指令寄存器) | Holds the current instruction being decoded and executed. |
| **ACC** | **Accumulator** (累加器) | A general-purpose register used to store the results of calculations performed by the ALU. |

</ins>

---

## Buses (总线)

![img](https://cdn.savemyexams.com/cdn-cgi/image/f=auto,width=3840/https://cdn.savemyexams.com/uploads/2023/05/3-1-computer-architecture--von-neumann-architecture-1.png)

A **bus** (总线) is a set of parallel wires that connect components within the computer system, allowing data and control signals to be transmitted between them.

> [!WARNING]
> ⚠️ A common point of confusion is between registers and buses.
> - **MAR/MDR** are *storage locations* within the CPU.
> - **Address/Data Bus** are the *pathways* connecting the CPU to memory.
>
> For example, the address in the **MAR** is sent along the **Address Bus**. The data from memory travels along the **Data Bus** to be stored in the **MDR**.

There are three main types of bus:

*   **Address Bus (地址总线)**
    *   **Purpose**: Carries the memory address from the processor to other components, such as main memory and input/output devices.
    *   **Direction**: **Unidirectional** (单向) – data travels only from the CPU to memory. The CPU specifies the address, memory responds.

*   **Data Bus (数据总线)**
    *   **Purpose**: Carries the actual data or instructions between the processor and memory.
    *   **Direction**: **Bidirectional** (双向) – data can be read from memory (CPU ← Memory) or written to memory (CPU → Memory).

*   **Control Bus (控制总线)**
    *   **Purpose**: Carries command and control signals to manage and synchronise the activities across the system. Examples of control signals include `memory read`, `memory write`, and `clock signals`.
    *   **Direction**: **Bidirectional** (双向) – The CPU sends out control signals (e.g., "read from memory"), and other components can send signals back (e.g., "interrupt request").

> [!TIP]
> 💡 To remember the bus directions:
> - The CPU is the "master" that decides the **address**, so the Address Bus flows *away* from it (unidirectional).
> - **Data** needs to go in and out, so the Data Bus must be a two-way street (bidirectional).

---
<ins>

### Impact of Bus Size on Performance

The **width** of a bus (the number of parallel wires it has) directly impacts system performance.

-   **Address Bus Width**:
    -   Determines the maximum number of memory locations the CPU can address.
    -   An `n`-bit address bus can address `2ⁿ` memory locations. For example, a 32-bit address bus can address `2³²` unique memory locations (approximately 4 GB of RAM).

-   **Data Bus Width**:
    -   Determines the number of bits that can be transferred simultaneously in a single operation.
    -   A wider data bus means more data can be moved to and from the CPU in one clock cycle, leading to faster data transfer rates and improved performance. For example, a 64-bit data bus can transfer twice as much data per cycle as a 32-bit data bus.

</ins>