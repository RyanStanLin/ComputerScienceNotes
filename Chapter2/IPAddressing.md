# IP Addressing

## What is an IP address?

An **IP (Internet Protocol) address (互联网协议地址)** is a unique identifier given to devices which **communicate (通信)** over the Internet (WAN).

-   IP addresses are _dynamic_, they can change.
-   IP addresses make it possible to **deliver (传送)** data to the right device.
-   A device connecting to a network will be given an IP address; if it moves to a different network, then the IP address will change.

> [!IMPORTANT]
> An **IP Address** is a unique numerical label assigned to each device connected to a computer network that uses the Internet Protocol for communication.

---
### IPv4

**Internet Protocol version 4 (互联网协议第四版)** is represented as 4 blocks of denary numbers ~~between 0 and 255~~ <ins>from 0 to 255 inclusive</ins>, separated by full stops.

-   Each block is one **byte (字节)** (8 bits).
-   Each address is 4 **bytes (字节)** (32 bits) in total.

> [!NOTE]
> 💡 Example of an IPv4 address: `192.168.1.1`

IPv4 provides over 4 billion unique addresses (`2³²`), however, with over 7 billion people and countless devices per person, a solution was needed.

---
### IPv6

**Internet Protocol version 6 (互联网协议第六版)** is represented as 8 blocks of 4 hexadecimal digits, separated by colons.

-   Each block is 2 **bytes (字节)** (16 bits).
-   Each address is 16 **bytes (字节)** (128 bits) in total.

> [!NOTE]
> 💡 Example of an IPv6 address: `2001:0db8:85a3:0000:0000:8a2e:0370:7334`

IPv6 could provide over ~~one billion unique addresses for every person on the planet~~ <ins>340 undecillion (3.4 x 10³⁸) unique addresses</ins> (`2¹²⁸`).

## Subnetting (子网划分)

**Subnetting (子网划分)** is the process of dividing a larger network into smaller, more manageable parts, called **subnets (子网)**. Each subnet works like a mini-network within the main network, allowing devices to communicate more efficiently.

🔑 **Benefits of subnetting include:**
-   **Reduces network traffic (减少网络流量)** – less data is broadcast across the whole network.
-   **Improves speed and performance (提升速度与性能)** – data stays within its local subnet.
-   **Increases security (增强安全性)** – limits access so not all devices can reach all parts of the network.
-   **Easier to manage and maintain (易于管理和维护)** – changes can be made to one subnet without affecting the rest.
-   **Improves organisation (改善组织结构)** – helps group devices by department or function.

> [!TIP]
> It's commonly used in larger networks, like schools or businesses, to reduce traffic, keep data local, and make management easier.

## IP Address Types

### Public vs Private IP Addresses

| Feature                | **Public IP Address (公共IP地址)**                               | **Private IP Address (私有IP地址)**                               |
| ---------------------- | ---------------------------------------------------------------- | ----------------------------------------------------------------- |
| **Scope (范围)**       | Globally unique and routable on the internet.                    | Local to a specific network (LAN) and not routable on the internet. |
| **Assignment (分配)**  | Assigned by an Internet Service Provider (ISP).                  | Assigned by a local router on a Local Area Network (LAN).         |
| **Uniqueness (唯一性)** | No two devices can have the same public IP address globally.     | Can be reused on different private networks.                      |
| **Purpose (目的)**     | Allows devices to be directly accessed from anywhere on the internet. | Allows internal communication without exposing devices to the public internet. |
| **Examples (示例)**    | Web servers, Email servers.                                      | Laptops, Phones, Printers within a home or office.                |
| **Security (安全性)**  | Directly exposed to the internet.                              | Protected from the public internet, which improves network security. |

---

### Static vs Dynamic IP Addresses

| Feature                 | **Static IP Address (静态IP地址)**                                     | **Dynamic IP Address (动态IP地址)**                                                               |
| ----------------------- | ---------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| **Nature (性质)**       | A fixed IP address that does not change.                               | A temporary IP address assigned when a device connects to a network.                              |
| **Assignment (分配)**   | Manually assigned to a device.                                         | Automatically assigned from a pool of available IPs by a `DHCP` server.                           |
| **Management (管理)**   | No management required once set.                                       | Managed automatically by a **DHCP (<ins>Dynamic Host Configuration Protocol</ins>)** server. |
| **Use Cases (使用场景)**  | Websites, remote access services, email or file servers.               | Laptops, smartphones, or guest devices where a fixed address isn't needed.                        |
| **Reliability (可靠性)** | Allows reliable and consistent access from anywhere on the network or internet. | Less reliable for services that need a constant address.                                          |

> [!WARNING]
> A common mistake is confusing static/dynamic with public/private. A public IP can be either static or dynamic, and a private IP is almost always dynamic (though it can be set statically).
