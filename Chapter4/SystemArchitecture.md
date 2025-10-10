# Von Neumann Model (冯·诺依曼模型)

## What is the Von Neumann Model?

The **Von Neumann model** is a computer architecture (计算机体系结构) design proposed by Mathematician John Von Neumann in the 1940s. Most modern general-purpose computers are built based on this model.

> [!IMPORTANT]
> 🔑 The core principle of the Von Neumann model is the **Stored Program Concept (存储程序概念)**. This means that both **program instructions (程序指令)** and the **data (数据)** that the instructions operate on are stored together in the same **Main Memory (主存储器)**.

The model outlines how the computer's **Main Memory (主存储器)**, **Input/Output devices (输入/输出设备)**, and the **Processor (处理器)** work together.

> [!NOTE]
> This architecture allows the computer to treat instructions just like data, meaning a program can modify itself while running, which was a revolutionary concept at the time.

![Logo](https://cdn.savemyexams.com/cdn-cgi/image/f=auto,width=3840/https://cdn.savemyexams.com/uploads/2023/06/von-neumann-architecture.png)

---

## Components of the Von Neumann Model

The Von Neumann model consists of three main components:

-   **Central Processing Unit (CPU) (中央处理器)**: The "brain" of the computer, responsible for executing instructions. It is able to access memory directly.
-   **Main Memory (主存储器)**: A unit that stores both program instructions and data.
-   **Input/Output (I/O) Devices (输入/输出设备)**: Devices that allow the user to interact with the computer (e.g., keyboard, mouse, monitor).

<!-- 原笔记中 "Memory that can store programs as well as data (registers)" 是一个严重的概念错误。冯诺依曼模型的核心是程序和数据存储在主存(Main Memory)中，而不是寄存器。已在此处修正。 -->
<ins>The processor fetches instructions sequentially from memory and executes them.</ins>

## Registers (寄存器)

**Registers** are extremely small, extremely fast memory locations located *inside the CPU*. They hold small amounts of data or control information that is needed immediately as part of the **Fetch-Decode-Execute Cycle (取指-解码-执行周期)**.

There are two main types of registers:
-   **General-Purpose Registers (通用寄存器)**
-   **Special-Purpose Registers (专用寄存器)**

### General-Purpose vs Special-Purpose Registers

A **general-purpose register** can store any data that the CPU is currently working on. It is flexible and can be used for various arithmetic or logical operations.

A **special-purpose register** has a specific, dedicated role within the operation of the CPU. It is used to control the flow of instructions or to hold critical state information.

---

### Special-Purpose Registers (专用寄存器)

There are a number of special-purpose registers that control or track data. For the ALevel exam, you must know their name, acronym, and purpose.

> [!TIP]
> 💡 A great way to revise these is to draw a diagram of the CPU and memory, then trace how data and addresses move between these registers during the Fetch phase of the F-D-E cycle.

| Name (名称) | Acronym (缩写) | Purpose (用途) |
| :--- | :--- | :--- |
| **Program Counter** (程序计数器) | `PC` | > [!IMPORTANT] Holds the memory address of the **next instruction** to be fetched.<br><br> <ins>It is automatically incremented to point to the next instruction after the current one has been fetched.</ins> ~~Increments by 1 as the fetch-decode-execute cycle runs.~~ |
| **Memory Address Register** (内存地址寄存器) | `MAR` | > [!IMPORTANT] Holds the memory address of the instruction or data that is to be fetched from or written to memory. <br><br> <ins>The address held in the MAR is sent to main memory via the **Address Bus (地址总线)**.</ins> |
| **Memory Data Register** (内存数据寄存器) | `MDR` | > [!IMPORTANT] Temporarily stores the data or instruction that has just been fetched from memory, or is about to be written to memory. It acts as a buffer. <br><br> <ins>Data and instructions are transferred between the CPU and main memory via the **Data Bus (数据总线)**, and the MDR is the gateway.</ins> |
| **Current Instruction Register** (当前指令寄存器) | `CIR` | > [!IMPORTANT] Stores the instruction that the CPU is currently decoding or executing. <br><br> The instruction from the `MDR` is copied to the `CIR` at the start of the decode phase. |
| **Accumulator** (累加器) | `ACC` | > [!IMPORTANT] A general-purpose register that stores the results of calculations performed by the **Arithmetic Logic Unit (ALU) (算术逻辑单元)**. It holds the intermediate and final results of operations. |
| **Index Register** (变址寄存器) | `IX` | > [!IMPORTANT] Stores a value (an offset) that is used in **indexed addressing mode (变址寻址模式)**. <br><br> The value in the `IX` is added to a base address given in an instruction to calculate the **effective memory address (有效地址)**. |
| **Status Register** (状态寄存器) | `SR` | > [!IMPORTANT] Holds individual bits called **flags (标志位)** that indicate the outcome of CPU operations. It reflects the current state of the processor. <br><br> 🔬 **Examples of Flags:** <br> - **Zero Flag (Z):** Set if the result of an operation is zero. <br> - **Carry Flag (C):** Set if an operation produced a carry-out. <br> - **Negative Flag (N):** Set if the result of an operation is negative. |