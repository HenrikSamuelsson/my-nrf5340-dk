# My nRF5340 DK

My structured learning and experiments on the nRF5340 DK.

## nRF5340 DK – Platform Overview

The nRF5340 DK is a development kit for the nRF5340 System-on-Chip (SoC). Both the SoC and the development kit are provided by Nordic Semiconductor. It provides a convenient way to experiment with a wide variety of embedded technologies.

The goal of this repository is to build a solid understanding of the nRF5340 platform through hands-on experiments, documentation, and incremental exploration.

> **Definition: Development kit**  
A development kit is hardware designed to help engineers get started with a specific technology for evaluation and prototyping. A well-designed kit is typically centered around a primary feature, while also including secondary components and connectors for power, programming, and communication. Development kits are not intended to serve as production reference designs.

### nRF5340 SoC

The primary component of the kit is the nRF5340 SoC, which integrates two Arm® Cortex®-M33 processors referred to as the Application core and the Network core. Each core has its own flash memory and RAM for code and data storage. The SoC also provides a set of peripherals associated with each core. The Application core has access to a broader set of peripherals; however, the radio subsystem is owned by the Network core.

### Development Kit Peripherals and I/O

The nRF5340 DK exposes the majority of the SoC's general-purpose input/output (GPIO) signals through pin headers, allowing external hardware to be connected directly to both the Application core and the Network core, subject to the SoC's pin multiplexing and ownership rules.

In addition to the external headers, the development kit includes a small set of on-board peripherals intended to simplify early experimentation and bring-up. These include four user-programmable buttons and four user-programmable LEDs, which provide basic input and output capabilities without requiring external components.

The board also integrates external non-volatile memory connected via the QSPI interface. This memory can be used for data storage or, depending on configuration, for execute-in-place (XIP) use cases and experimentation with memory hierarchies.

### Power Supply Options

During development, the nRF5340 DK is most conveniently powered via the on-board USB connector, which provides both power and access to the integrated debugger. This is the typical setup for firmware development, debugging, and experimentation.

In addition to USB power, the development kit supports several alternative power supply options intended for flexibility and in-field testing. These include external power sources as well as battery-based operation. The availability of multiple power options makes it possible to evaluate different power scenarios and to study power consumption behavior under conditions that more closely resemble real-world use cases.

### On-board Debugger and USB Connectivity

The nRF5340 DK includes an on-board SEGGER J-Link debugger, which enables programming and debugging of the nRF5340 SoC without requiring external debug hardware. This simplifies the development setup and allows the board to be used directly with standard development tools.

Connection to the development kit is made using a USB cable with a Micro-USB connector. The USB connection provides both power to the board and a communication interface to the on-board debugger, making it sufficient for most development and debugging tasks.

## References

1. Nordic Semiconductor. (n.d.).
   *[About Nordic Semiconductor](https://www.nordicsemi.com/About-us)*.

2. EDN Network. (n.d.).
   *[Development and evaluation kits](https://www.edn.com/development-and-evaluation-kits/)*.

3. Nordic Semiconductor. (n.d.).
   *[nRF5340 System-on-Chip (SoC)](https://www.nordicsemi.com/Products/nRF5340)*.

4. Nordic Semiconductor. (n.d.).
   *[nRF5340 Development Kit](https://www.nordicsemi.com/Products/Development-hardware/nRF5340-DK)*.

5. Nordic Semiconductor. (n.d.).
   *nRF5340 DK Product Brief (Version 1.1)*.

6. Nordic Semiconductor. (February 2025).
   *nRF5340 Product Specification (Version 1.6)*.
