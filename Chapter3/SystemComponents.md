# Input/Output and Storage Devices

## Input Devices (输入设备)

> [!IMPORTANT]
> **Input Devices (输入设备)** are hardware components that allow users to `interact` with a computer system. They `enable` the user to input data or commands into the system, which the computer then `processes` to produce output.

### Types of Input Devices

| Device (设备) | Description (描述) |
| :--- | :--- |
| ⌨️ **Keyboard (键盘)** | The most common input device. It allows users to input text and commands by pressing keys. |
| 🖱️ **Mouse (鼠标)** | Allows users to `navigate` the computer screen, click on items, and perform other functions using a graphical user interface (GUI). |
| 👆 **Touchscreen (触摸屏)** | Found on smartphones, tablets, and some computers. Touchscreens allow users to interact with the device by touching the screen directly with fingers or a stylus. |
| 🎤 **Microphone (麦克风)** | `Captures` audio input, which can be used for voice commands, recording audio, or video conferencing. |
| 📷 **Webcam (网络摄像头)** | `Captures` video input, often used for video conferencing, live streaming, or recording videos. |
| 📠 **Scanner (扫描仪)** | `Digitises` physical documents or images, converting them into a digital format that the computer can process. |
| 🎮 **Game Controller (游戏控制器)** | Used primarily for video games, these devices allow users to control game characters and interact with the gaming environment. |
| ✍️ **Graphics Tablet (图形输入板)** | Allows artists and designers to draw or sketch directly onto a computer. It's particularly useful for graphic design, 3D modelling, and other visual creative tasks. |
|  biometric **Biometric Devices (生物识别设备)** | These devices, such as fingerprint scanners, iris scanners or facial recognition systems, are used for security purposes to `verify` a user's identity. |
| ║█║ **Barcode Reader (条形码阅读器)** | Scans barcodes, typically used in retail for price lookup and inventory management. |
| 🕹️ **Joystick (游戏摇杆)** | Often used for computer games, especially flight simulators. It allows the user to control movement more fluidly than with a keyboard or mouse. |

---

## Output Devices (输出设备)

> [!IMPORTANT]
> **Output Devices (输出设备)** are hardware components that receive information from a computer system and `present` it to the user in a comprehensible form. They enable the computer to `communicate` the results of processed data.

### Types of Output Devices

| Device (设备) | Description (描述) |
| :--- | :--- |
| 🖥️ **Monitor (显示器)** | This is the most common output device. It displays visual output from the computer, including text, images, and videos. |
| 🖨️ **Printer (打印机)** | Produces a **hard copy (硬拷贝)** of digital documents or images. There are various types, including **Inkjet (喷墨式)**, **Laser (激光式)**, and **3D printers (3D 打印机)**. |
| 🔊 **Speakers (扬声器)** | Output audio from the computer, such as music, sound effects, or voice. |
| 🎧 **Headphones (耳机)** | Similar to speakers, headphones output audio directly to the user, providing a more personal and potentially immersive experience. |
| 📽️ **Projector (投影仪)** | `Projects` the computer's display onto a large screen or wall, useful for presentations or home cinema. |
| ⠗⠗⠗ **Braille Display (盲文显示器)** | This specialised device outputs information in Braille, allowing visually impaired users to read text from the computer via touch. |
| 📈 **Plotter (绘图仪)** | Used for printing large, high-quality vector graphics, diagrams, and designs, often used in engineering or architecture. |
| 🕶️ **Virtual Reality (VR) Headset (虚拟现实头盔)** | Provides an immersive visual and audio output, primarily used for gaming and virtual simulations. |
| 🤖 **Computer-Controlled Machinery (计算机控制机械)** | In manufacturing or robotics, computers often output commands directly to machinery (e.g., CNC machines, robotic arms) to control their operation. |

---

## Choosing the Right I/O Device (选择合适的输入/输出设备)

> [!TIP]
> When asked to recommend a device for a specific situation in an exam, consider the following factors to structure your answer.

-   **User Needs**: What tasks will the user be performing? A graphic designer needs a graphics tablet, while a data entry clerk benefits from a keyboard with a number pad.
-   **User Skills**: Is the user comfortable with the device? A touchscreen might be more intuitive for some users, while others might prefer a mouse and keyboard.
-   **Environment**: Where will the device be used? A wireless mouse is suitable for a clutter-free office, while a wired mouse might be better for a public computer lab to prevent theft.
-   **Cost**: Higher-end devices often have more features but are also more expensive. Consider the budget and whether the extra features are worth the cost.

## Primary Memory (主存储器)

> [!IMPORTANT]
> **Primary Memory (主存储器)** is the memory that is directly accessible by the **CPU (中央处理器)**. It is characterized by much faster access times than secondary storage, which is essential for the efficient operation of the Fetch-Decode-Execute cycle.

-   It stores data and instructions that the CPU is actively using or will need imminently.
-   It acts as a short-term, working memory for the computer.
-   Because it’s fast, it’s also more expensive per byte, so computer systems have less of it compared to secondary storage.
    -   _Example_: RAM = 16–32 GB
    -   _Example_: Secondary storage (like HDDs) = 1–2 TB or more

### Types of Primary Memory

**Random Access Memory (RAM) (随机存取存储器)**
-   This is the main memory used to store currently running programs and data.
-   It is **_Volatile_**, meaning its contents are lost when the power is turned off.
-   It is read/write memory.

---

**Read-Only Memory (ROM) (只读存储器)**
-   This is memory that can be read from but not (easily) written to.
-   It is **_Non-volatile_**, meaning its contents are retained even when the power is turned off.
-   🔑 Its primary purpose is to store the initial instructions for the computer to start up. This includes:
    -   The **BIOS (Basic Input/Output System)** or **UEFI (Unified Extensible Firmware Interface)**.
    -   The **Bootstrap Loader (引导加载程序)**, which is a small program that loads the operating system from secondary storage into RAM.

> [!WARNING]
> A common mistake is to confuse RAM and ROM. Remember: RAM is for *temporary* working data (volatile), while ROM is for *permanent* startup instructions (non-volatile).

#### Comparison: RAM vs. ROM

| Feature (特性) | **RAM (Random Access Memory)** | **ROM (Read-Only Memory)** |
| :--- | :--- | :--- |
| **Volatility (易失性)** | Volatile (data lost without power) | Non-volatile (data retained without power) |
| **Purpose (用途)** | Stores OS, running programs, and current data. | Stores startup instructions (BIOS/UEFI) and bootstrap loader. |
| **Read/Write (读写能力)** | Can be read from and written to. | Read-only (or difficult to write to). |
| **Typical Size (典型容量)** | Large (e.g., 4GB - 64GB+) | Small (e.g., a few MB) |

---

**CPU Cache and Registers (CPU 缓存和寄存器)**
-   These are built directly into the CPU for the fastest possible access.
-   **Registers** hold the single piece of data or instruction the CPU is currently processing.
-   **Cache** is a small amount of memory that stores frequently accessed data from RAM to reduce access time.

## Secondary Storage (辅助存储器)

> [!IMPORTANT]
> **Secondary Storage (辅助存储器)** provides **permanent (永久性)**, non-volatile data storage. These are hardware components that retain digital data, which can include software applications, documents, images, and more, even when the computer is powered off.

### Types of Secondary Storage

There are 3 main types of storage technology: **Magnetic**, **Optical**, and **Solid State**.

| Type of Storage (存储类型) | Description (描述) & Examples | Benefits (优点) ✅ | Drawbacks (缺点) ❌ |
| :--- | :--- | :--- | :--- |
| **Magnetic (磁性)** | Stores data by magnetising particles on a disk or tape. (e.g., Hard Disk Drives, Magnetic Tape) | - High storage capacity<br>- Very low cost per gigabyte<br>- Suitable for long-term backup | - Slower read/write speeds<br>- Susceptible to physical damage due to moving parts<br>- Susceptible to damage from strong magnetic fields |
| **Optical (光学)** | Stores data using a laser to burn microscopic pits into the surface of the disc. (e.g., CDs, DVDs, Blu-ray Discs) | - Durable and relatively immune to environmental conditions<br>- Easy to transport and distribute (e.g., software, movies) | - Low storage capacity<br>- Very slow read/write speeds<br>- Can be easily scratched or damaged |
| **Solid State (固态)** | Stores data in flash memory cells (using floating-gate transistors). (e.g., Solid-State Drives, USB Flash Drives) | - Very fast read/write speeds<br>- No moving parts, so very durable and resistant to physical shock<br>- Silent operation | - Higher cost per gigabyte<br>- Flash memory cells have a limited number of write cycles[^1] |

[^1]: This wear-out process is managed by algorithms like wear-levelling, so for a typical user, it is not a significant concern during the device's expected lifespan.

### Common Storage Devices Comparison (常见存储设备对比)

| Device (设备) | Type (类型) | Typical Capacity (典型容量) | Affordability (成本效益) | Portability (便携性) | Durability (耐用性) |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Hard Disk Drive (HDD) (硬盘驱动器)** | Magnetic | 500GB - 10TB+ | Low cost per GB | Low (internal) / Moderate (external) | Moderate (moving parts are fragile) |
| **Solid-State Drive (SSD) (固态硬盘)** | Solid State | 120GB - 8TB | High cost per GB | High (lightweight and compact) | High (no moving parts) |
| **USB Flash Drive (U盘)** | Solid State | 8GB - 1TB | Moderate cost per GB | Very High (small and lightweight) | Moderate (can be easily lost or broken) |
| **CD/DVD/Blu-ray Disc (光盘)** | Optical | CD: ~700MB, DVD: ~4.7GB, Blu-ray: ~25GB | Low cost per disc | High (thin and lightweight) | Low (easily scratched) |

---
<ins>

### 🔬 Principles of Operation: How Devices Work

#### **How a Hard Disk Drive (HDD) Works**
1.  An HDD consists of one or more rigid, rotating **Platters (盘片)**, typically made of aluminium or glass.
2.  These platters are coated with a thin layer of **ferrous oxide (氧化铁)** or another magnetic material.
3.  The platters are mounted on a central **Spindle (主轴)** and rotate at high speeds (e.g., 5400 to 7200 RPM).
4.  Each platter surface has a **Read-Write Head (读写头)** mounted on an actuator arm, which hovers just above the surface. Electronic circuits control the movement of this arm.
5.  The platter surface is logically divided into concentric circles called **Tracks (磁道)**, and each track is further divided into **Sectors (扇区)**.
6.  **Writing Data**: To write data, a current is passed through the read-write head, generating a magnetic field that magnetises a small spot on the platter's surface, representing a `1` or a `0`.
7.  **Reading Data**: To read data, the head passes over the tracks. The magnetic fields on the platter induce a tiny current in the head. Variations in this current are detected and translated back into binary data.
</ins>
---
<ins>

#### **How a Solid-State Drive (SSD) Works**
1.  SSDs have no moving parts and use **non-volatile** solid-state flash memory to store data.
2.  They are made of arrays of **NAND flash memory (NAND 闪存)** cells, which are a type of integrated circuit built from floating-gate transistors. An **SSD Controller** manages these components.
3.  Each memory cell uses a grid of columns and rows with two transistors at each intersection: a **Control Gate (控制栅)** and a **Floating Gate (浮栅)**.
4.  **Writing Data**: By applying a precise voltage, electrons are forced to pass through a barrier and become trapped in the floating gate. The presence or absence of these trapped electrons determines whether the cell stores a `1` or a `0`.
5.  **Reading Data**: The amount of charge in the floating gate affects the conductivity of the cell, which can be measured to determine the stored bit without altering the charge.
> [!WARNING]
> A key characteristic of flash memory is that it is not possible to directly overwrite existing data. To write new data to a location, the entire **block** of memory containing that location must first be erased, and then the new data is written to the desired **page** within that block. This is known as the erase-before-write cycle.
</ins>

---

## Choosing the Right Storage Device (选择合适的存储设备)

> [!TIP]
> 💡 When recommending a storage device, always justify your choice by referring to these factors.

-   **Storage Needs (Capacity)**: How much data does the user need to store? A videographer needs a high-capacity HDD or SSD, while a student storing documents might only need a small USB flash drive.
-   **Performance Needs (Speed)**: Does the user need fast access to their data? An SSD is best for tasks that require high-speed data access, like running an operating system, video editing, or gaming.
-   **Portability**: Does the user need to transport the data? USB flash drives and external SSDs are highly portable for transferring data between computers.
-   **Reliability & Durability**: Is the data for long-term archival, or will the device be used in a harsh environment? Magnetic tapes are reliable for archival, while SSDs are durable for mobile use.
-   **Cost**: What is the user's budget? HDDs offer the most storage for the lowest cost, making them ideal for bulk data storage.