# My nRF5340 DK

My structured learning and experiments on the nRF5340 DK.

## nRF5340 DK – Platform Overview

The nRF5340 DK is a development kit for the nRF5340 System-on-Chip (SoC). Both the SoC and the development kit are provided by Nordic Semiconductor. It provides a convenient way to experiment with a wide variety of embedded technologies.

The goal of this repository is to build a solid understanding of the nRF5340 platform through hands-on experiments, documentation, and incremental exploration.

> **Definition: Development kit**  
A development kit is hardware designed to help engineers get started with a specific technology for evaluation and prototyping. A well-designed kit is typically centered around a primary feature, while also including secondary components and connectors for power, programming, and communication. Development kits are not intended to serve as production reference designs.

### nRF5340 SoC

The primary component of the kit is the nRF5340 SoC, which integrates two Arm® Cortex®-M33 processors referred to as the Application core and the Network core. Each core has its own flash memory and RAM for code and data storage. The SoC also provides a set of peripherals associated with each core. The Application core has access to a broader set of peripherals; however, the radio subsystem is owned by the Network core.

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
