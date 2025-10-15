# Ports & Interfaces

## USB (Universal Serial Bus / 通用串行总线)

### What is USB?

> [!IMPORTANT]
> The **Universal Serial Bus (USB)** is a widely used industry standard for transmitting data and power between devices. It is a **serial communication (串行通信)** method, and it operates **asynchronously (异步)**.

🔬 Many devices use USB, such as:
- Keyboards
- Mice
- Video cameras
- Printers
- Portable media players
- Mobile phones
- Disk drives
- Network adapters

---

### USB Connector Types

> [!NOTE]
> The letters (A, B, C) refer to the physical shape and design of the USB connector, while the numbers (2.0, 3.0, 4) refer to the data transfer speed and technical specification.

| Type  | Image | Description & Common Use |
| --- | --- | --- |
| **USB-A** | ⌨️ | The classic rectangular connector. Commonly used for flash drives, mice, keyboards, and external HDDs. |
| **USB-B** | 🖨️ | A square-shaped connector. Typically found in printers, scanners, and older external storage devices. |
| **USB-C** | 📱 | The latest standard, known for its small, oval shape. It is **<ins>reversible</ins>**, meaning it can be plugged in either way up. Known for high transfer speeds and its ability to carry significant power (Power Delivery). |

---

### USB Generations (Speed and Performance)

The version number determines the maximum speed and performance of the connection.

| Version | Maximum Speed | Common Use & Notes |
| --- | --- | --- |
| **USB 1.1** | 12 Mbps | Very slow and largely obsolete. |
| **USB 2.0** | 480 Mbps | Still very common, but considered slow for large file transfers. |
| **USB 3.0/3.1/3.2** | 5 Gbps to 20 Gbps | Often identifiable by a blue-colored port. Much faster, used for external HDDs, SSDs, and modern peripherals. |
| **USB4 / USB4 2.0**| Up to 80 Gbps | The latest and fastest standard, used for high-speed data transfer and high-resolution displays. |

> [!TIP]
> 🔑 **_Backwards Compatibility (向后兼容)_**: Newer USB standards are backwards compatible with older ones. For example, you can plug a USB 2.0 device into a USB 3.0 port, but it will only operate at USB 2.0 speeds.

---

### Connection Process

When a device is connected to a USB port, the computer performs a "plug-and-play" sequence:

1.  The computer automatically **detects** that a device has been connected (often via a small voltage change on the data lines).
2.  The operating system queries the device to identify it.
3.  It then looks for the correct **device driver (设备驱动程序)**:
    - If the driver is already installed, it is loaded, and the device can communicate with the computer.
    - If the device is new, the computer will search its existing driver library for a compatible one.
    - If no suitable driver is found, the user must download and install the appropriate driver manually.

---

### Advantages and Disadvantages of USB

| Advantages ✅ | Disadvantages ❌ |
| --- | --- |
| Devices are automatically detected and drivers are loaded, simplifying setup. | The maximum standard cable length is roughly 5 metres, which is unsuitable for long distances. |
| It has become an industry standard, ensuring wide compatibility and support. | Older versions like USB 2.0 have limited transmission rates (480 Mbps), which can be a bottleneck. |
| A single cable can supply power to the device, removing the need for a separate power adapter for many peripherals. | Very old USB standards (e.g., USB 1.1) may not be supported by modern computers. |
| Several different data transmission rates are supported, up to 80 Gbps with USB4 2.0. | While the host controller can manage many devices, bus bandwidth is shared, which can slow down performance if many high-speed devices are active simultaneously. |
| Newer standards are backwards compatible with older devices. | |
| <ins>Older **USB-A/B** connectors fit only one way, which prevents incorrect electrical connections.</ins> | |

## HDMI (High-Definition Multimedia Interface / 高清晰度多媒体接口)

### What is HDMI?

> [!IMPORTANT]
> **HDMI** is a **digital (数字的)** interface standard that sends both high-definition video and audio from a source (e.g., computer, Blu-ray player) to a display (e.g., TV, monitor) over a single cable. It replaces older **analogue (模拟的)** systems like VGA.

---

### Key Features of HDMI

Modern HD TVs and displays require more data because they support features that older standards cannot handle effectively:
- **Widescreen format** (e.g., 16:9 aspect ratio)
- **Higher resolution (分辨率)** (e.g., 1920×1080, 4K, 8K)
- **Faster refresh rates (刷新率)** (e.g., 120 Hz)
- **Wider colour range** (billions of colours)

These features need the faster and higher bandwidth that HDMI provides.
<!-- Updated HDMI bandwidth figures to reflect modern standards (e.g., HDMI 2.1) as the original 10 Gbps was outdated. -->
- **Bandwidth**: Modern HDMI versions support high bandwidths, such as **<ins>18 Gbps (HDMI 2.0)</ins>** or **<ins>48 Gbps (HDMI 2.1)</ins>**.

#### 🔑 HDCP (High-bandwidth Digital Content Protection)

- HDMI uses **HDCP (高带宽数字内容保护)** to prevent unauthorized copying of protected content.
- The process works as follows:
    1.  Devices check for a valid **authentication (认证)** key before sending data.
    2.  If the receiving device is authenticated, a "handshake" occurs.
    3.  The encrypted data is then transmitted.

## VGA (Video Graphics Array / 视频图形阵列)

### What is VGA?

> [!WARNING]
> **VGA** is an older **analogue (模拟的)** standard for video output, introduced in the late 1980s. It is now considered outdated and is being phased out in favour of digital interfaces like HDMI and DisplayPort.

- **Signal Type**: Analogue. This means the signal is prone to **signal loss** and **interference**, especially over long cables, resulting in lower image quality.
- **Audio**: VGA transmits **video only**. A separate audio cable is required for sound.
- **Resolution and Colour**:
    - The original VGA standard had a maximum **resolution (分辨率)** of **640 × 480 pixels** with 16 colours at a 60 Hz **refresh rate (刷新率)**.
    - At lower resolutions (e.g., 320 × 200), it could support up to 256 colours.
    - 💡 While the VGA interface *can* carry higher resolutions (e.g., 1080p), the analogue signal quality degrades significantly, leading to a blurry or distorted image.