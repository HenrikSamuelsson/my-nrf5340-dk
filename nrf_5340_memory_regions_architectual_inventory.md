# nRF5340 Memory Regions – Architectural Inventory

## Scope and method

This note records the **architectural inventory only** of the nRF5340 memory architecture.

- Only **existence, size, and core association** are documented
- **No access rules**, permissions, or execution assumptions are made
- All information is derived from the **nRF5340 Product Specification v1.6**, which is treated as the **normative reference**

Interpretation, access control, and security configuration are intentionally deferred to later stages.

---

## Application core memory regions

### Internal flash (Application core)

- Internal non-volatile flash memory
- Size: **1 MB**
- Associated with the **Application core (Arm Cortex-M33)**
- Intended for application firmware and non-volatile storage

This flash is described as part of the Application core in the Product Specification.

---

### Internal RAM (Application core)

- Internal volatile memory (RAM)
- Size: **512 KB**
- Associated with the **Application core**

The specification identifies this RAM as Application-core memory. No assumptions are made here about visibility to other masters.

---

## Network core memory regions

### Internal flash (Network core)

- Internal non-volatile flash memory
- Size: **256 KB**
- Associated with the **Network core (Arm Cortex-M33)**
- Intended for network and radio-related firmware

This flash is explicitly distinguished from the Application core flash in the Product Specification.

---

### Internal RAM (Network core)

- Internal volatile memory (RAM)
- Size: **64 KB**
- Associated with the **Network core**

At this level, only existence and size are recorded.

---

## Shared memory regions

### Shared RAM

- The Product Specification describes the presence of **RAM accessible by both cores**
- This RAM is distinct from the core-local RAM blocks
- A portion of Application core RAM is described as being dedicated to inter-core communication

At this stage, only the **existence** of shared RAM is recorded. Size, address ranges, and protection mechanisms are not yet documented.

---

## Peripheral address space

- The nRF5340 uses **memory-mapped peripherals**
- Peripherals are accessed through a defined peripheral address space
- Some peripherals are primarily associated with one core

Peripheral regions are acknowledged here for completeness but are not treated as memory regions in the architectural sense at this stage.

---

## Summary table

| Memory region | Associated core | Size |
| ------------- | --------------- | ---- |
| Internal flash | Application core | 1 MB |
| Internal RAM | Application core | 512 KB |
| Internal flash | Network core | 256 KB |
| Internal RAM | Network core | 64 KB |
| Shared RAM | Both cores | Not specified here |

---

## Notes and boundaries

- This document deliberately avoids access rights, execution permissions, and security configuration
- Address ranges, SPU rules, and cross-core access are deferred to subsequent access-classification notes
- Any statement not explicitly listed here should be considered **out of scope** for this document

---

## References

Nordic Semiconductor ASA. (2025). *nRF5340 Product Specification* (Version 1.6).
