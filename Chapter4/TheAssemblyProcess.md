# The Assembly Process (汇编过程)

## The Assembler (汇编器)

An **Assembler (汇编器)** is a type of language translator that converts **_low-level assembly language_** into **_machine code_**. Each assembly language instruction corresponds directly to a single machine code instruction.

> [!IMPORTANT]
> 🔑 The primary role of an assembler is to translate human-readable **mnemonics (指令助记符)** into binary **machine code (机器码)** that the **Central Processing Unit (CPU) (中央处理器)** can directly execute.

The translation process involves converting symbolic instructions into binary **opcodes (操作码)** and resolving symbolic names for memory addresses into actual binary addresses.

---

A typical assembly instruction consists of two parts:
- **Opcode (操作码)**: Specifies the operation to be performed (e.g., `LOAD`, `ADD`, `STORE`).
- **Operand (操作数)**: Provides the data or memory address that the opcode will operate on (e.g., a value like `#5` or a label like `VAR1`).

## Two-Pass Assembler (两遍扫描汇编器)

A **Two-Pass Assembler (两遍扫描汇编器)** is a standard approach for translating assembly code. It scans the source code twice to complete the translation. This method is particularly effective at handling **forward references** (when a label is used before it is defined in the code).

> [!TIP]
> 💡 The core reason for needing two passes is to resolve all symbolic addresses (**labels (标签)**) before generating the final machine code. The first pass builds a map of all labels, and the second pass uses this map to perform the translation.

### First Pass (第一遍扫描)

The main goal of the first pass is to build a **Symbol Table (符号表)**.

> [!IMPORTANT]
> A **Symbol Table (符号表)** is a data structure that stores every label from the source code along with its corresponding memory address.

During the first pass, the assembler performs the following steps:
1.  **Read Source Code (读取源代码)**: It reads the assembly program line by line.
2.  **Assign Addresses (分配地址)**: It keeps track of the memory location for each instruction and data directive.
3.  **Identify Labels (识别标签)**: When it encounters a line with a label, it stores the label and its current memory address in the symbol table.
4.  **Ignore Non-essentials (忽略非必要项)**: It removes comments and whitespace.
5.  **No Code Generation (不生成代码)**: Crucially, _no machine code is generated_ during this pass.

### Second Pass (第二遍扫描)

The second pass generates the final **Object Code (目标代码)**, which is the machine-readable version of the program.

During the second pass, the assembler performs these steps:
1.  **Read Source Code Again (再次读取源代码)**: It re-reads the source code from the beginning, line by line.
2.  **Translate Instructions (翻译指令)**: For each instruction, it converts the mnemonic (like `LOAD`) into its binary opcode using a predefined opcode table.
3.  **Resolve Symbolic Addresses (解析符号地址)**: It looks up any labels used as operands in the **Symbol Table (符号表)** created during the first pass and replaces them with their actual memory addresses.
4.  **Generate Object Code (生成目标代码)**: It combines the opcode and the operand's address/value to form the final machine code instruction.
5.  **Output (输出)**: The complete object code is then saved to a file, ready to be loaded and executed.

---

#### Comparison of the Two Passes

| Feature | First Pass (第一遍扫描) | Second Pass (第二遍扫描) |
| :--- | :--- | :--- |
| **Primary Goal** | Build the **Symbol Table** | Generate **Object Code** |
| **Input** | Assembly Source Code | Assembly Source Code + Symbol Table |
| **Output** | Symbol Table | Executable Object Code |
| **Handles Labels** | ✅ Records all label definitions | ✅ Replaces label references with addresses |
| **Generates Code?** | ❌ No | ✅ Yes |

## 🔬 Worked Example: Assembling a Program (实例分析：汇编一个程序)

Let's trace the assembly process for a simple program that adds two numbers.

### Assembly Source Code (汇编源代码)

The program loads the value at label `A`, adds the value at label `B`, stores the result at label `C`, and then halts.

```assembly
LOAD A
ADD B
STORE C
HALT
A: DATA 5
B: DATA 3
C: DATA 0
```

### Pass 1: Building the Symbol Table (第一遍：构建符号表)

The assembler reads the code line by line, assigning memory addresses starting from `00`. When it finds a label, it adds it to the symbol table.

| Address | Instruction | Label | Action / Comment |
| :--- | :--- | :--- | :--- |
| 00 | `LOAD A` | | Instruction at address 00 |
| 01 | `ADD B` | | Instruction at address 01 |
| 02 | `STORE C` | | Instruction at address 02 |
| 03 | `HALT` | | Instruction at address 03 |
| 04 | `DATA 5` | **A** | Label `A` found at address `04`. Add `A: 04` to Symbol Table. |
| 05 | `DATA 3` | **B** | Label `B` found at address `05`. Add `B: 05` to Symbol Table. |
| 06 | `DATA 0` | **C** | Label `C` found at address `06`. Add `C: 06` to Symbol Table. |

The final **Symbol Table** after Pass 1 is:

| Label | Address |
| :--- | :--- |
| **A** | 04 |
| **B** | 05 |
| **C** | 06 |

### Pass 2: Generating Object Code (第二遍：生成目标代码)

The assembler now uses the symbol table and an opcode table to generate the machine code.

**Assumed Opcode Table:**
| Mnemonic | Opcode (Binary) | Opcode (Hex) |
| :--- | :--- | :--- |
| `LOAD` | `00000001` | `01` |
| `ADD` | `00000010` | `02` |
| `STORE` | `00000011` | `03` |
| `HALT` | `00000000` | `00` |
| `DATA` | N/A | `00` (as placeholder) |

The assembler now generates the final code:

| Address | Assembly Instruction | Machine Code | Explanation |
| :--- | :--- | :--- | :--- |
| 00 | `LOAD A` | `01 04` | Opcode for `LOAD` is `01`. Address for `A` is `04` (from Symbol Table). |
| 01 | `ADD B` | `02 05` | Opcode for `ADD` is `02`. Address for `B` is `05` (from Symbol Table). |
| 02 | `STORE C` | `03 06` | Opcode for `STORE` is `03`. Address for `C` is `06` (from Symbol Table). |
| 03 | `HALT` | `00 00` | Opcode for `HALT` is `00`. Operand is not needed. |
| 04 | `DATA 5` | `00 05` | Represents the data value `5`. |
| 05 | `DATA 3` | `00 03` | Represents the data value `3`. |
| 06 | `DATA 0` | `00 00` | Represents the data value `0`. |

The final object program is the sequence of machine code: `0104020503060000000500030000`.

## Program Execution Tracing (程序执行追踪)

This involves tracking the state of the CPU registers (like the Accumulator) and memory as the *translated machine code* is executed.

> [!WARNING]
> ⚠️ **Exam Alert**: Tracing program **execution** is different from tracing the **assembly process**.
> - **Assembly Process Trace**: You show how the Symbol Table is built (Pass 1) and how the Object Code is generated (Pass 2).
> - **Execution Trace**: You show how register values (e.g., `ACC`) and memory contents change as each instruction is run by the CPU.

### Example Execution Trace

Using the code from above, a trace of its execution would look like this:

| Step | Instruction Executed | Accumulator (ACC) | Memory[04] (A) | Memory[05] (B) | Memory[06] (C) |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 0 | (Start) | `0` | `5` | `3` | `0` |
| 1 | `LOAD A` | `5` | `5` | `3` | `0` |
| 2 | `ADD B` | `8` | `5` | `3` | `0` |
| 3 | `STORE C` | `8` | `5` | `3` | `8` |
| 4 | `HALT` | `8` | `5` | `3` | `8` |