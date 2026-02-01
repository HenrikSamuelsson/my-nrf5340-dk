# Charcoal nRF Development Environment

## Overview

This note documents the **working and verified nRF development environment** on the
Windows machine **Charcoal**. The goal is to capture the final, stable setup after
resolving SDK/toolchain installation issues, avoiding duplicate installs, and ensuring
clean separation between VS Code–managed tooling and the global system environment.

## Operating System

- Windows 11
- Host nick name: **Charcoal**

## Tooling Summary

- **IDE**: Visual Studio Code
- **VS Code Extension**: nRF Connect for VS Code
- **SDK**: nRF Connect SDK v3.2.1
- **Toolchain**: nRF toolchain matching SDK v3.2.1
- **CLI Utility**: nRF Util (`nrfutil`) (installed globally)

## Directory Layout (Canonical)

The canonical installation root is under `C:\tools`.

```text
C:\tools\nrf\
├─ tch\
│  ├─ toolchains\
│  │  └─ <hash>\     # Active toolchain used by VS Code
│  └─ v3.2.1\        # nRF Connect SDK v3.2.1
└─ nrf-util\         # Global nrfutil installation
```

## VS Code Behavior

- The **nRF Connect for VS Code** extension manages:
  - SDK location
  - Toolchain selection
  - Environment activation (PATH, Python, CMake, Ninja, GCC)

- Builds are executed in an **isolated environment** injected by the extension.

- VS Code successfully builds sample applications (e.g. `blinky`) for:
  - `nrf5340dk/nrf5340/cpuapp`

## Global PowerShell Environment

In a *plain* PowerShell session (outside VS Code):

- Available:
  - `nrfutil`

- Not available (by design):
  - `west`
  - `cmake`
  - `ninja`
  - `arm-none-eabi-gcc`

This confirms:

- No PATH pollution
- No accidental dependency on SDK/toolchain outside VS Code
- Clean separation between IDE-managed and global environments

## nrfutil SDK Manager State

- No toolchains registered with `nrfutil`:

```text
nrfutil sdk-manager toolchain list
# (no entries)
```

- The directory `C:\ncs\toolchains` exists but is empty except for metadata
  (`toolchains.json`).

This is expected after uninstalling the nrfutil-managed toolchain and is harmless.

## Intentional Design Choices

- SDK and toolchain are **managed by VS Code**, not globally
- Global PowerShell remains clean
- `C:\ncs` is retained as an empty nrfutil home directory
- No manual PATH modifications

This minimizes long-term maintenance cost and avoids ambiguous tool resolution.

## Verification Checklist

- [x] nRF Connect SDK v3.2.1 installed
- [x] Toolchain installed and used by VS Code
- [x] Sample application builds successfully
- [x] No duplicate active toolchains
- [x] Global PowerShell clean

## Notes / Future Work

- Optional: create a temporary PowerShell script to activate the nRF environment
  manually if CLI-only work is needed
- Optional: delete `C:\ncs` if nrfutil is no longer used

## Status

Stable – verified working configuration.
