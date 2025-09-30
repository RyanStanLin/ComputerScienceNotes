# Chapter 3.2: Logic Gates and Logic Circuits

> [!NOTE]
> In digital electronics, a **Logic Gate (逻辑门)** is a fundamental building block of a digital circuit. Most logic gates have two inputs and one output. At any given moment, every terminal is in one of the two binary conditions, `FALSE` (low, 0) or `TRUE` (high, 1), representing different voltage levels.

---

## Types of Logic Gates

The logic gates covered in the ALevel Computer Science syllabus are: **AND**, **OR**, **NOT**, **XOR**, **NAND**, and **NOR**.

### 🔑 AND Gate

| Property | Description |
| --- | --- |
| **Key Term (关键术语)** | **AND Gate (与门)** |
| **Boolean Expression (布尔表达式)** | `Q = A AND B` <br> `Q = A.B` <br> `Q = A ∧ B` |
| **Circuit Symbol (电路符号)** | <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/b/b9/AND_ANSI_Labelled.svg/240px-AND_ANSI_Labelled.svg.png" alt="AND Gate Symbol" width="150"/> |
| **Function (功能)** | Outputs `TRUE (1)` if and only if **both** of its inputs are `TRUE (1)`. |

#### Truth Table (真值表)
A **Truth Table (真值表)** is a mathematical table used in logic to compute the functional values of logical expressions on each of their functional arguments.

| Input A | Input B | Output Q = A.B |
| :---: | :---: | :---: |
| 0 | 0 | 0 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 1 |

---

### 🔑 OR Gate

| Property | Description |
| --- | --- |
| **Key Term (关键术语)** | **OR Gate (或门)** |
| **Boolean Expression (布尔表达式)** | `Q = A OR B` <br> `Q = A + B` <br> `Q = A ∨ B` |
| **Circuit Symbol (电路符号)** | <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/16/OR_ANSI_Labelled.svg/240px-OR_ANSI_Labelled.svg.png" alt="OR Gate Symbol" width="150"/> |
| **Function (功能)** | Outputs `TRUE (1)` if **at least one** of its inputs is `TRUE (1)`. It outputs `FALSE (0)` only when both inputs are `FALSE (0)`. |

#### Truth Table (真值表)

| Input A | Input B | Output Q = A+B |
| :---: | :---: | :---: |
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 1 |

---

### 🔑 NOT Gate

> [!IMPORTANT]
> The **NOT Gate (非门)** is the only logic gate with a single input. It is also known as an **Inverter (反相器)**.

| Property | Description |
| --- | --- |
| **Key Term (关键术语)** | **NOT Gate (非门)** |
| **Boolean Expression (布尔表达式)** | `Q = NOT A` <br> `Q = Ā` <br> `Q = ¬A` |
| **Circuit Symbol (电路符号)** | <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/6/60/NOT_ANSI_Labelled.svg/240px-NOT_ANSI_Labelled.svg.png" alt="NOT Gate Symbol" width="150"/> |
| **Function (功能)** | Outputs the reverse of the input. If the input is `TRUE (1)`, the output is `FALSE (0)`, and vice versa. |

#### Truth Table (真值表)

| Input A | Output Q = Ā |
| :---: | :---: |
| 0 | 1 |
| 1 | 0 |

---

### 🔑 XOR Gate (Exclusive OR)

| Property | Description |
| --- | --- |
| **Key Term (关键术语)** | **XOR Gate (异或门)** |
| **Boolean Expression (布尔表达式)** | `Q = A XOR B` <br> `Q = A ⊕ B` |
| **Circuit Symbol (电路符号)** | <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/17/XOR_ANSI_Labelled.svg/240px-XOR_ANSI_Labelled.svg.png" alt="XOR Gate Symbol" width="150"/> |
| **Function (功能)** | Outputs `TRUE (1)` only if the inputs are **different**. If the inputs are the same, the output is `FALSE (0)`. |

> [!WARNING]
> A common mistake is to confuse the **XOR** gate with the **OR** gate. Remember: for an OR gate, `1 OR 1` results in `1`. For an XOR gate, `1 XOR 1` results in `0`.

#### Truth Table (真值表)

| Input A | Input B | Output Q = A ⊕ B |
| :---: | :---: | :---: |
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

---

### 🔑 NAND Gate (NOT-AND)

| Property | Description |
| --- | --- |
| **Key Term (关键术语)** | **NAND Gate (与非门)** |
| **Boolean Expression (布尔表达式)** | `Q = A NAND B` <br> `Q = ¬(A.B)` <br> `Q = (A.B)'` |
| **Circuit Symbol (电路符号)** | <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/e/e6/NAND_ANSI_Labelled.svg/240px-NAND_ANSI_Labelled.svg.png" alt="NAND Gate Symbol" width="150"/> |
| **Function (功能)** | Outputs `FALSE (0)` only if **both** inputs are `TRUE (1)`. Otherwise, the output is `TRUE (1)`. <ins>It is equivalent to an AND gate followed by a NOT gate.</ins> |

#### Truth Table (真值表)

| Input A | Input B | Output Q = ¬(A.B) |
| :---: | :---: | :---: |
| 0 | 0 | 1 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

---

### 🔑 NOR Gate (NOT-OR)

| Property | Description |
| --- | --- |
| **Key Term (关键术语)** | **NOR Gate (或非门)** |
| **Boolean Expression (布尔表达式)** | `Q = A NOR B` <br> `Q = ¬(A+B)` <br> `Q = (A+B)'` |
| **Circuit Symbol (电路符号)** | <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/c/c6/NOR_ANSI_Labelled.svg/240px-NOR_ANSI_Labelled.svg.png" alt="NOR Gate Symbol" width="150"/> |
| **Function (功能)** | Outputs `TRUE (1)` only if **both** inputs are `FALSE (0)`. Otherwise, the output is `FALSE (0)`. <ins>It is equivalent to an OR gate followed by a NOT gate.</ins> |

> [!TIP]
> 💡 Both **NAND** and **NOR** gates are known as **Universal Gates (通用门)**. This means that any other logic gate (AND, OR, NOT, etc.) can be constructed using only NAND gates or only NOR gates. This is a frequent topic in exam questions.

#### Truth Table (真值表)

| Input A | Input B | Output Q = ¬(A+B) |
| :---: | :---: | :---: |
| 0 | 0 | 1 |
| 0 | 1 | 0 |
| 1 | 0 | 0 |
| 1 | 1 | 0 |