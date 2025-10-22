# Machine Code vs. Assembly Language

## 🔑 Machine Code (机器代码)

-   A **first-generation language (第一代语言)**.
-   Instructions are in a binary format, which is _directly executable_ by the **processor (处理器)**.
-   It is the lowest-level programming language, consisting of `0`s and `1`s.

> [!IMPORTANT]
> **Machine Code** is the only language that the CPU can understand and execute without any translation.

---

## 🔑 Assembly Language (汇编语言)

-   A **second-generation language (第二代语言)**.
-   The code is written using **mnemonics (助记符)**, which are short, human-readable text commands (e.g., `LDA` for Load, `STA` for Store).
-   This language allows programmers to write human-readable programs that have a very close correspondence to machine code.

> [!NOTE]
> There is a one-to-one (`1:1`) relationship between an assembly language instruction and a machine code instruction. One assembly instruction translates to exactly one machine code instruction.

-   It needs to be translated into machine code by a special program called an **Assembler (汇编器)** before the CPU can execute it.
-   Each type of computer CPU has its own specific **instruction set (指令集)**.

---

## 🔬 Instruction Set (指令集)

An **instruction set** is the complete collection of all the commands that a **Central Processing Unit (CPU) (中央处理器)** can process. Each command has a unique binary code, which is its machine code equivalent.

In assembly language, an instruction is typically split into two parts: the `Opcode` and the `Operand`.

| Component | Description |
| --- | --- |
| **Opcode (操作码)** | Short for **_Operation Code_**. This part of an instruction tells the CPU what operation to perform. Examples include `LDA` (load), `ADD` (add), and `STO` (store). |
| **Operand (操作数)** | This part provides the data or the memory address that the opcode will work with. It gives the extra detail the CPU needs to complete the instruction. |

**_Example Instruction_**:
```
LDA #123
```
-   `LDA` is the **Opcode**, instructing the CPU to load data into the Accumulator.
-   `#123` is the **Operand**, specifying the actual data to be loaded.

### Addressing Modes (寻址模式)
An addressing mode specifies how the operand of an instruction is interpreted to access data.

> [!WARNING]
> Understanding addressing modes is crucial. Exam questions often require you to trace code and determine the value in a register based on the addressing mode used.

| Mode | Mnemonic Example | Explanation |
| --- | --- | --- |
| **Immediate Addressing (立即寻址)** | `LDM #n` | The operand is the actual value to be used. The `#` symbol denotes an immediate value. The value `n` is loaded directly into the Accumulator. |
| **Direct Addressing (直接寻址)** | `LDD <address>` | The operand is the memory address where the data is stored. The CPU fetches the contents from this address. |
| **Indirect Addressing (间接寻址)** | `LDI <address>` | The operand is an address that holds another address. The CPU first goes to `<address>`, reads the value there, and then uses that value as the _final_ address to fetch the data from. |
| **Indexed Addressing (索引寻址)** | `LDX <address>` | The final memory address is calculated by adding the `<address>` from the operand to the current value of the **Index Register (IX) (索引寄存器)**. `Final Address = <address> + IX`. |
| <ins>**Symbolic Addressing (符号寻址)**</ins> | <ins>`JMP LOOP_START`</ins> | <ins>The operand is a **label (标签)** that represents a memory address. The assembler resolves this label into an actual memory address during the assembly process.</ins> |
| <ins>**Relative Addressing (相对寻址)**</ins> | <ins>`JPE +5`</ins> | <ins>The operand is an **offset (偏移量)** from the current instruction's address. The final address is calculated by adding the offset to the **Program Counter (PC)**. `Final Address = PC + offset`.</ins> |

> [!TIP]
> 💡 **Why use Symbolic and Relative addressing?**
> -   **Symbolic Addressing**: Makes code much easier to read and maintain. Instead of remembering that a loop starts at memory address `204`, you can just use a label like `LOOP_START`. If you add or remove code, the assembler automatically recalculates the address for you.
> -   **Relative Addressing**: Creates **relocatable code**. This means the program can be loaded into any part of main memory and still run correctly, because all jumps are relative to the program's current location, not fixed to absolute addresses.

### Operand Notations (操作数符号)
The following symbols are used to specify the type of operand:

| Symbol | Meaning | Example |
| --- | --- | --- |
| `#` | Denotes a **denary (十进制)** number. | `#123` |
| `B` | Denotes a **binary (二进制)** number. | `B01001010` |
| `&` | Denotes a **hexadecimal (十六进制)** number. | `&4A` |
| `<address>` | Can be an **absolute (绝对)** or **<ins>symbolic (符号)</ins>** address. | `COUNT` or `255`|

> [!NOTE]
> All questions will assume there is only one general-purpose register available: the **Accumulator (ACC) (累加器)**. The **Index Register (IX)** is a special-purpose register used for indexed addressing.

---

### Groups of Instructions

<!-- The original flat table has been reorganized into logical groups as per the ALevel syllabus. -->

#### **Data Movement Instructions**
These instructions move data between memory and CPU registers.

| Opcode | Operand | Explanation |
| --- | --- | --- |
| `LDM` | `#n` | **Immediate addressing**. **L**oa**d** the nu**m**ber `n` to the Accumulator (ACC). |
| `LDD` | `<address>` | **Direct addressing**. **L**oa**d** the contents of the location at the given **d**irect address to ACC. |
| `LDI` | `<address>` | **Indirect addressing**. Use the value at the given address as a new address. **L**oad the contents of the **i**ndirect address to ACC. |
| `LDX` | `<address>` | **Indexed addressing**. Use `<address>` + Index Register (IX) to get the final address. **L**oa**d** from this inde**x**ed address to ACC. |
| `LDR` | `#n` | **Immediate addressing**. **L**oa**d** the number `n` to the Index **R**egister (IX). |
| `STO` | `<address>` | **Sto**re the contents of ACC at the given memory address. |
| `MOV` | `<register>` | **Mov**e the contents of ACC to the given register (e.g., `IX`). |

#### **Arithmetic Operations**
These instructions perform mathematical calculations.

| Opcode | Operand | Explanation |
| --- | --- | --- |
| `ADD` | `<address>` | **Add** the contents of the given address to ACC. |
| `SUB` | `<address>` | **Sub**tract the contents of the given address from ACC. |
| `INC` | `<register>` | **Inc**rement the contents of the specified register (`ACC` or `IX`) by 1. |
| `DEC` | `<register>` | **Dec**rement the contents of the specified register (`ACC` or `IX`) by 1. |

#### **Comparison Instructions**
These instructions are used to compare values, setting internal flags that conditional jump instructions can use.

| Opcode | Operand | Explanation |
| --- | --- | --- |
| `CMP` | `<address>` | **C**o**mp**are the contents of ACC with the contents of the given address. |
| `CMP` | `#n` | **C**o**mp**are the contents of ACC with the number `n`. |
| `CMI` | `<address>` | **C**o**mp**are **i**ndirect. Compare ACC with the contents at the address stored in `<address>`. |

#### **Conditional Jumps (Branching)**
These instructions alter the flow of program execution based on the result of a comparison.

| Opcode | Operand | Explanation |
| --- | --- | --- |
| `JMP` | `<address>` | **J**u**mp** unconditionally to the given address. |
| `JPE` | `<address>` | **J**um**p** if **e**qual. Jump to `<address>` if the previous compare result was true. |
| `JPN` | `<address>` | **J**um**p** if **n**ot equal. Jump to `<address>` if the previous compare result was false. |

> [!NOTE]
> The `<address>` in a jump instruction can be:
> -   An **absolute address** (e.g., `JMP 250`).
> -   A **symbolic address** (e.g., `JMP MY_LABEL`).
> -   A **relative address** (e.g., `JMP +8`).

#### **I/O and Program Control**
These instructions handle input/output operations and program termination.

| Opcode | Operand | Explanation |
| --- | --- | --- |
| `IN` | | Take **in**put from the keyboard and store its ASCII value in ACC. |
| `OUT` | | **Out**put to the screen the character whose ASCII value is stored in ACC. |
| `END` | | **End** the program and return control to the operating system. |

#### Identify the State of Bits

Use AND operation to check the state of the Bit.

Use OR for setting the value to specific 1 and 0.

XOR for flip bits.
