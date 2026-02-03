# Journal

## 2026-01-30

Journal — nRF5340 DK bring-up

Today's goal was to start a minimal dual-core bring-up by creating a simple
Application-core blinky with logging. The application code itself was prepared,
but the build could not be completed due to environment and workspace issues.

The main blocker was that the existing nRF Connect SDK workspace under
`C:\tools\nrf\ncs` had inconsistent ownership (installed as Administrator),
which caused west update to fail repeatedly due to Git "dubious ownership"
errors. In addition, `west` was only available in the nRF Toolchain shell, which
led to some confusion when switching between shells.

Given the time constraints and the state of the workspace, I decided not to
force the setup further tonight. Instead, I started downloading a fresh
nRF Connect SDK toolchain (v3.2.1) with the intention of setting up a clean,
user-owned workspace under:

```text
C:\tools\ncs
```

The plan is to resume from a clean SDK installation and then retry the minimal Application-core blinky build in a controlled environment.

## 2026-01-31

Spending some time setting up and re-learning the nRF Connect SDK. I have used it before, but it has been a while and I no longer clearly remember the roles of the different components. In addition, I expect that newer versions have been released since I last worked with it, so I want to get an updated and structured understanding before continuing development.

## 2026-02-01

Worked through the *nRF Connect for VS Code* workflow using nRF Connect SDK v3.2.1.

- Created, built, and flashed a minimal **Application core blinky** successfully.
- Verified that the Application core runs and produces output via `printk()`.
- Created a corresponding **Network core blinky** project and built/flashed it
  without errors, but observed no LED activity or log output from the Network
  core.
- Began investigating Network core start/reset behavior and debug configuration.
- Noted that **LOG output is not yet visible** for the Application core; only
  `printk()` output is observed.

Next steps will be to fix Application core logging (RTT/UART), and figure out why the network core project does not blink any LED. Will also need to learn how to setup debug projects for both projects.

## 2026-02-03

Downloaded the schematics for the nRF5340 DK. It included a good high resolution image of the top side of the kit.
