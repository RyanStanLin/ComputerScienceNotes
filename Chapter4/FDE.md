# Fetch-Execute Cycle (取指执行周期)

## What is the Fetch-Execute Cycle?

> [!IMPORTANT]
> The **Fetch-Execute Cycle (取指执行周期)** is the fundamental process or sequence of operations that the **Central Processing Unit (CPU)** repeatedly performs to process instructions. It is driven by the **System Clock (系统时钟)**, which generates timing signals to coordinate all CPU actions.

There are 3 primary stages:
1.  **Fetching (取指)**: Retrieving an instruction from a memory location. This involves supplying the memory address and receiving the instruction data.
2.  **Decoding (解码)**: Interpreting the binary instruction to understand the operation to be performed and identifying any data required.
3.  **Executing (执行)**: Carrying out the action specified by the instruction.

---

## 💡 Role of Registers in the Fetch-Execute Cycle

In the section below, **CPU components (CPU组件)** and **registers (寄存器)** appear in **bold**, and assembly language is in _italic_.

> [!NOTE]
> Registers are small, high-speed storage locations within the CPU used to temporarily hold data and instructions during processing.

The cycle proceeds through the following steps:

### 1. Fetch Stage (取指阶段)
1.  The **Program Counter (PC / 程序计数器)** is loaded with the memory address of the first instruction of the program.

> [!WARNING]
> A common misconception is that the **PC** always starts at `0`. In reality, it's loaded with the starting address assigned by the operating system.

2.  The address stored in the **PC** is copied to the **Memory Address Register (MAR / 内存地址寄存器)**.
3.  The address in the **MAR** is sent to main memory via the **Address Bus (地址总线)**. Simultaneously, a 'read' signal is sent on the **Control Bus (控制总线)**.
4.  The instruction at that memory location is sent from memory back to the CPU via the **Data Bus (数据总线)** and is stored in the **Memory Data Register (MDR / 内存数据寄存器)**.
5.  The **PC** is incremented by 1, so it now holds the address of the _next_ instruction.

### 2. Decode Stage (解码阶段)
1.  The instruction from the **MDR** is copied to the **Current Instruction Register (CIR / 当前指令寄存器)**.
2.  The instruction held in the **CIR** is split into two parts: the **opcode (操作码)**, which defines the operation, and the **operand (操作数)**, which contains an address or data.
3.  The **Control Unit (CU / 控制单元)** reads and decodes the opcode to determine the sequence of actions required to execute the instruction.

### 3. Execute Stage (执行阶段)
The specific registers and components used depend on the decoded instruction:
-   _INP_: A value from an input device is placed into the **Accumulator (ACC / 累加器)**.
-   _OUT_: The value currently in the **ACC** is sent to an output device.
-   _LDA_: Loads a value from RAM. The address (from the operand) is placed in the **MAR**, the data is fetched into the **MDR**, and then copied to the **ACC**.
-   _STA_: Stores a value to RAM. The address is placed in the **MAR**, the value from the **ACC** is copied to the **MDR**, and then stored in RAM.
-   _ADD/SUB_: A value from RAM is loaded into the **MDR**. The calculation is performed by the **Arithmetic and Logic Unit (ALU / 算术逻辑单元)** using the value in the **MDR** and the **ACC**. The result is stored back in the **ACC**.
-   _BRA/BRZ/BRP_: These branching instructions are handled by the **CU**. The **ALU** may be used to check if a condition is met (e.g., if the **ACC** is zero). If the condition is true, the operand address is copied to the **PC**.

---

## ## Register Transfer Notation (RTN) (寄存器传输符号)

**Register Transfer Notation (RTN)** is a symbolic way of describing the data flow and operations that occur between CPU registers during the Fetch-Execute cycle. It provides a precise, shorthand representation of these internal processes.

> [!TIP]
> Think of RTN as a formal language to describe "what moves where" inside the CPU for each step of the cycle.

#### Symbol Meanings

| Symbol | Meaning | 描述 |
| :--- | :--- | :--- |
| `←` | Data is transferred into a register. | 数据被传输到寄存器中。 |
| **PC** | Program Counter | 程序计数器 |
| **MAR** | Memory Address Register | 内存地址寄存器 |
| **MDR** | Memory Data Register | 内存数据寄存器 |
| **CIR** | Current Instruction Register | 当前指令寄存器 |
| **ACC** | Accumulator | 累加器 |
| `[address]` | The contents of a memory location. | 某个内存地址中的内容。 |
| `CIR[Opcode]` | The opcode part of the instruction in CIR. | CIR 中指令的操作码部分。 |
| `CIR[Operand]`| The operand part of the instruction in CIR. | CIR 中指令的操作数部分。 |

---

### Fetch Stage RTN

```
MAR ← [PC]         ; Copy the address from the Program Counter to the MAR.
PC ← [PC] + 1      ; Increment the PC to point to the next instruction.
MDR ← [[MAR]]      ; Read instruction from memory (address in MAR) into MDR.
CIR ← [MDR]        ; Copy the instruction from the MDR to the CIR.
```
<!-- Note: The double square brackets [[MAR]] are sometimes used to emphasize dereferencing a memory address, meaning "the contents of the memory location pointed to by the contents of MAR". Simpler notation [MAR] is also acceptable if context is clear. The provided notes used RAM[MAR], which is also clear. For consistency with formal notation, [[MAR]] or [MAR] is often preferred. I will stick to the format from the original notes for clarity. -->
```
MAR ← [PC]
PC ← [PC] + 1
MDR ← Memory[[MAR]]
CIR ← [MDR]
```

### Decode Stage RTN

```
; No specific register transfer occurs.
; The Control Unit (CU) decodes the instruction held in the CIR.
```

### Execute Stage RTN Examples

_LDA X_ (Load the value from memory location X into the ACC):
```
MAR ← CIR[Operand]   ; Load the address part (X) of the instruction into MAR.
MDR ← Memory[[MAR]]  ; Fetch the data from that memory address into MDR.
ACC ← [MDR]        ; Copy the data from MDR into the Accumulator.
```

---

_STA X_ (Store the value from the ACC into memory location X):
```
MAR ← CIR[Operand]   ; Load the address part (X) of the instruction into MAR.
MDR ← [ACC]        ; Copy the data from the Accumulator into MDR.
Memory[[MAR]] ← [MDR] ; Write the value from MDR into the memory location.
```

---

_ADD X_ (Add the value from memory location X to the ACC):
```
MAR ← CIR[Operand]   ; Load the address part (X) of the instruction into MAR.
MDR ← Memory[[MAR]]  ; Fetch the data from that memory address into MDR.
ACC ← [ACC] + [MDR]  ; Add the fetched data to the Accumulator's current value.
```

---

_BRZ X_ (Branch to address X if the ACC contains 0):
```
If [ACC] = 0 Then PC ← CIR[Operand] ; If the condition is met, update the PC.
```
