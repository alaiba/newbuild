# Operating System and Bring-up Deep Dive

Status: **Selected — Windows 11 Pro x64 host + WSL2 + Ubuntu 26.04.1 LTS**

## Host OS decision

Use **Windows 11 Pro x64** as the host operating system.

For the initial installation in August 2026, use **Windows 11 version 25H2, General Availability channel**, fully patched with normal production updates before workload validation.

Do not deliberately install Windows 11 Home, Pro for Workstations, Enterprise/LTSC merely for longevity, Insider/preview builds, or Windows 11 24H2 on a new installation when 25H2 is available.

The selected **edition** is durable even though the feature release will change over the machine's lifetime. Follow the normal supported Windows feature-update path after commissioning.

Reference:
- https://learn.microsoft.com/en-us/windows/release-health/windows11-release-information

## Why Windows 11 Pro

Windows is the best host for this mixed workstation because it simultaneously supports:

- native IntelliJ IDEA and Android Studio;
- Android Emulator;
- NVIDIA GeForce/CUDA and future local-AI tooling;
- occasional gaming without a compatibility layer;
- WSL2 for Linux command-line/build/container workflows;
- Hyper-V / Windows Hypervisor Platform;
- BitLocker and Secure Boot;
- Remote Desktop hosting.

Windows 11 **Pro** is selected over Home because the professional virtualization/management features are useful on this machine. Pro for Workstations remains unnecessary for one CPU socket and a 256 GB memory target.

## Exact license channel and consolidated SKU

A new Windows license is required for this build.

Selected channel:

**Microsoft Windows 11 Pro Retail/FPP.**

For the consolidated Romanian purchase, the preferred exact packaged SKU is now:

**`HAV-00197` — Windows 11 Pro Retail/FPP USB, Romanian package**.

EvoMAG currently lists this exact Retail/FPP product around **1,199.99 lei** and it can therefore stay inside the primary order rather than creating a third retailer relationship for the English-package `HAV-00163` merely to save roughly 50–75 lei.

The Romanian package does **not** require the workstation to remain Romanian-language in daily use. Windows 11 Pro supports installing additional display languages and changing the Windows display language; the Single Language restriction applies to the dedicated Home Single Language edition, not normal Pro. Install/add the English language pack and use English as the display language if desired.

This is a good example of the build's procurement/value policy: a small price premium is justified when the software rights are equivalent and it eliminates a separate ordering/invoice/warranty relationship.

Purchase requirements:

- Windows 11 **Pro**;
- **Retail/FPP**, not OEM/DSP/System Builder;
- preferred consolidated SKU **`HAV-00197`** from EvoMAG;
- normal packaged entitlement and retailer invoice;
- do not substitute an undocumented emailed/grey-market standalone key.

Fallback:

- if `HAV-00197` becomes unavailable or is materially overpriced, buy the English Retail/FPP **`HAV-00163`** from another reputable retailer;
- adding provider #3 purely for a ~50–100 lei saving is not worthwhile under the current consolidation policy.

Retail/FPP preserves transfer rights to a future replacement PC subject to Microsoft's license terms, although portability remains secondary for this intentionally long-lived workstation.

References:
- Microsoft language management: https://support.microsoft.com/windows/manage-the-input-and-display-language-settings-in-windows-219f28b0-9881-cd4c-75ca-dba919c52321
- Microsoft Windows 11 Pro: https://www.microsoft.com/ro-ro/d/windows-11-pro/dg7gmgf0d8h4

## Why not Pro for Workstations

Windows 11 Pro for Workstations adds workstation-scale capabilities that do not materially benefit this build. A future Windows Dev Drive also does not require Pro for Workstations.

References:
- https://www.microsoft.com/en/windows/business/windows-11-pro
- https://learn.microsoft.com/en-us/windows/dev-drive/

## Linux development environment

Use **WSL2** as the default Linux environment.

Selected distribution: **Ubuntu 26.04.1 LTS**.

References:
- https://ubuntu.com/download/wsl
- https://ubuntu.com/about/release-cycle?product=ubuntu&release=ubuntu&version=26.04+LTS
- https://learn.microsoft.com/en-us/windows/wsl/install

Do not use Insider/preview WSL builds for the baseline workstation.

## Windows/WSL filesystem policy

- Windows-native IDE/toolchain repositories should live on Windows storage.
- Linux-native build trees, package caches, container data and other high-I/O Linux workloads should live **inside the WSL filesystem**, not under `/mnt/c` merely for convenience.
- When the future 4 TB+ work SSD is added, reassess WSL VHDX/container/cache placement.
- Consider a Windows Dev Drive on the future work SSD for Windows-native source/caches only if measurements justify it.

## Firmware settings before OS installation

Start from a current stable ProArt BIOS and conservative defaults:

- UEFI-native boot;
- CSM disabled;
- Secure Boot enabled;
- AMD fTPM / TPM 2.0 enabled;
- AMD SVM enabled;
- IOMMU enabled unless a demonstrated stability issue appears;
- memory Auto/JEDEC during commissioning;
- CPU stock/conservative;
- no manual PBO/overclocking during baseline validation.

Perform the planned major BIOS update **before enabling BitLocker**.

## Windows installation sequence

1. update motherboard BIOS and establish firmware baseline;
2. install Windows 11 Pro 25H2 x64 in UEFI/GPT mode onto the Samsung 990 PRO;
3. complete normal Windows Update production updates;
4. install current AMD chipset drivers;
5. install motherboard/network/Wi-Fi/Bluetooth drivers where required;
6. install the current **NVIDIA Studio Driver WHQL**;
7. validate Device Manager, event logs, sleep/resume and network interfaces;
8. install/add the desired **English Windows display language** if using the Romanian FPP media/package;
9. after firmware/driver stability is established, enable BitLocker and retain the recovery key independently;
10. install/update WSL2 and Ubuntu 26.04.1 LTS;
11. install development tooling and run representative workload validation.

## NVIDIA driver policy

Use the current **NVIDIA Studio Driver WHQL** as the baseline. Switch to Game Ready only when a specific new game materially needs its day-zero fixes/optimizations.

## BitLocker policy

Enable BitLocker after the initial firmware/driver baseline is stable. Store and verify the recovery key independently of the workstation; suspend BitLocker appropriately before future firmware/TPM changes.

## Virtualization policy

- WSL2 for normal Linux development/container workflows;
- Android Emulator with the supported Windows hypervisor path;
- Hyper-V VMs when a genuinely separate machine boundary is useful;
- third-party VM stacks only for a specific uncovered requirement.

The 64 GB Phase-1 RAM supports moderate concurrency; the eventual 256 GB configuration expands it substantially.

## Initial software baseline

- Windows Terminal;
- PowerShell 7;
- Git for Windows;
- IntelliJ IDEA;
- Android Studio / Android SDK / emulator as required;
- WSL2 + Ubuntu 26.04.1 LTS;
- required JDKs/build tools;
- container tooling after the runtime/licensing choice is made.

Avoid generic optimizer utilities and unnecessary motherboard vendor suites.

## Bring-up validation

Record:

- BIOS version and Windows edition/version/build;
- Secure Boot/TPM/BitLocker state;
- Device Manager state;
- memory capacity/rate/timings;
- Samsung firmware/SMART baseline;
- extended memory stability test;
- sustained Java build/test and thermal validation;
- current NVIDIA Studio driver and representative 3D/game test;
- WSL2/Ubuntu status, Android Emulator, sleep/resume;
- network link/driver stability;
- UPS USB/graceful-shutdown validation.

## Selected conclusion

- **Host OS:** Windows 11 Pro x64 — Selected
- **License channel:** Retail/FPP — Selected
- **Preferred consolidated packaged SKU:** **`HAV-00197` Romanian Retail/FPP USB from EvoMAG**
- **Daily display language:** English can be installed/selected on Windows 11 Pro; package language does not force the UI permanently
- **Initial feature release:** Windows 11 25H2 GA
- **Linux environment:** WSL2 + Ubuntu 26.04.1 LTS
- **Dual boot:** not required absent a demonstrated bare-metal Linux need
- **GPU driver baseline:** NVIDIA Studio Driver WHQL
- **Security baseline:** UEFI + Secure Boot + TPM 2.0 + BitLocker after firmware stabilization
