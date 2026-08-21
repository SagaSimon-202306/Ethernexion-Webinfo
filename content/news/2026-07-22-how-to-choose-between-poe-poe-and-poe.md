---
url: https://www.ethernexion.com/news/how-to-choose-between-poe-poe-and-poe
title: "How to Choose Between PoE, PoE+, and PoE++?"
type: Press Release
date: 2026-07-22
cover: https://www.ethernexion.com:8001/media/images/123.width-640.jpg
fetched: 2026-08-22
---

[← Back to News](https://www.ethernexion.com/news)

With the rapid expansion of the Internet of Things (IoT), an increasing number of devices require network connectivity—many of which also need power to operate. Traditional Ethernet switches only transmit data and cannot deliver power, which led to the emergence of Power over Ethernet (PoE) technology.

This article provides a comprehensive overview of PoE switches, including their architecture, working principles, standards, and how they differ from conventional switches.

**What Is PoE?**

PoE (Power over Ethernet) is a technology that supplies power to network devices via network cables. PoE technology enables the simultaneous transmission of power and data signals, eliminating the need for separate power cables for the devices. It works by injecting direct current (DC) power into the Ethernet cable, allowing network devices to be powered directly through the network connection.

![](https://www.ethernexion.com:8001/media/original_images/POE_SWITCHE.webp)

**Components of a PoE Power Supply System**

**PSE (Power Sourcing Equipment)**

PSE refers to network equipment that supports PoE technology and serves as a core component of the PoE power supply system. PSE typically comes in two forms: PoE injectors and PoE switches. Its primary function is to transmit power and data signals via Ethernet cables and to supply power to Powered Devices (PDs).

**PD (Powered Device)**

PDs are endpoint devices that receive power from the PoE system. Common examples include IP phones, IP cameras, and wireless access points. These devices draw power through the Ethernet cable while simultaneously exchanging data with the network.

**PoE Power Supply**

The PoE power supply is the energy source of the system. It converts AC input into DC power and feeds it into the Ethernet infrastructure. The total power budget determines how many PDs a PSE can support simultaneously.

**Ethernet Cabling**

Ethernet cables serve as the medium connecting PoE injectors to PoE devices, enabling the simultaneous transmission of power and data signals to network equipment. Commonly used types include Cat5, Cat5e, and Cat6 cables, with transmission distances varying according to the specific PoE technology version.

In a PoE power supply system, the interaction between PSE and PD devices is governed by the IEEE 802.3af/at/bt standard protocols. These standards define key parameters—such as the method of power delivery, power levels, and transmission distance—thereby ensuring the stability and reliability of the PoE system.

**Definition and Classification of PoE Switches**

A PoE switch is a switch capable of supplying power to network devices.

Based on the power delivery method, PoE switches can be classified into two types:

- End-Span: Power and data are delivered together directly from the switch ports.
- Mid-Span: A PoE injector is inserted into the cable to add power, separating the roles of data switching and power injection.

**Working Principle of PoE Switches**

A PoE switch works by connecting its internal power supply to Ethernet ports and transmitting power to powered devices through Ethernet cables.

It also determines the required power level based on the connected device and controls how and when power is delivered.

When a device is connected:

- If the device does not support PoE, the switch only transmits data and does not supply power.
- If the device supports PoE, the switch delivers both power and data simultaneously.

**PoE Power Standards**

Currently, PoE standards are mainly divided into three types:

- IEEE 802.3af (PoE)
- IEEE 802.3at (PoE+)
- IEEE 802.3bt (PoE++)

PoE++ is further divided into Type 3 and Type 4 based on power levels.

![](https://www.ethernexion.com:8001/media/original_images/WeiXinTuPian_20260722155256_344_28.png)

**IEEE 802.3af Standard**

The IEEE 802.3af standard, released in 2003, is the earliest PoE standard.

- Maximum power per port: 15.4W
- Maximum voltage: 48V
- Maximum current: 350mA
- Maximum transmission distance: 100 meters

Under this standard, a PoE switch can deliver up to 15.4W of power to a connected PD via Ethernet cable, enabling simultaneous power and data transmission.

It is mainly used in low-power application scenarios.

**IEEE 802.3at (PoE+) Standard**

The IEEE 802.3at (PoE+) standard was introduced after IEEE 802.3af (2019).

It provides higher power delivery, with a maximum of **30W per port.**

Compared with 802.3af, PoE+ can support more devices requiring higher power, such as IP phones, Wi-Fi access points, IP cameras, and high-performance laptops.

It also supports bidirectional communication, allowing PDs to send information back to the PSE to adjust power requirements.

**IEEE 802.3bt (PoE++) Standard**

The IEEE 802.3bt standard, released in 2018, is the latest PoE standard, also known as PoE++.

It enables all four pairs (eight conductors) in an Ethernet cable to carry power simultaneously, significantly increasing power delivery capacity.

- Power per port: **60W to 90W**, up to **100W** in some cases

This allows PoE to support a wider range of devices, such as medical equipment, industrial devices, and high-power LED lighting.

To support PoE++, both PSE and PD must handle higher voltage and power levels, requiring more advanced hardware design and more complex negotiation mechanisms.

**Differences Between PoE Switches and Traditional Switches**

**PoE Support**

The main difference lies in PoE capability:

- Traditional switches only transmit data
- PoE switches transmit both power and data

Traditional switches require additional power adapters or power cables for connected devices.

**Supported Devices**

PoE switches can supply power to PoE-enabled devices such as IP phones, network cameras, and wireless access points, while traditional switches cannot.

**Cabling Effort**

PoE switches transmit power and data over a single cable, simplifying installation and reducing cabling complexity.

**Cost Differences**

PoE switches eliminate the need for additional power adapters and separate power cabling, reducing overall deployment costs.

However, due to their more advanced technology, PoE switches are generally more expensive than traditional switches.

**How to Choose Between PoE, PoE+, and PoE++?**

When choosing between IEEE 802.3af, 802.3at (PoE+), and 802.3bt (PoE++) switches:

- **IEEE 802.3af (PoE):**

Provides up to 15.4W per port, suitable for low-power devices such as IP phones, IP cameras, and wireless access points. It is also the most cost-effective option.

- **IEEE 802.3at (PoE+):**

Provides up to 30W per port, suitable for devices with higher power requirements, such as high-performance cameras and wireless access points. It offers more stable and reliable power delivery.

- **IEEE 802.3bt (PoE++):**

Provides higher per-port power and can support devices requiring around 71W, making it suitable for industrial, commercial, and medical applications.

Compared with the other two, PoE++ switches are more expensive but offer significantly higher power capacity and support a broader range of scenarios.

**Important Note**

PoE standards are backward compatible. For example, a PoE++ switch can also be used with lower-power devices.

How to Choose Between PoE, PoE+, and PoE++? · EtherNexion
