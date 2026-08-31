# Operating System and Bring-up Deep Dive

Status: **Selected — Windows 11 Pro x64 host + WSL2 + Ubuntu 26.04.1 LTS**

## Host OS decision

Use **Windows 11 Pro x64** as the host operating system.

For the initial installation in August 2026, use **Windows 11 version 25H2, General Availability channel**, fully patched with normal production updates before workload validation.

Do **not** deliberately install:

- Windows 11 Home;
- Windows 11 Pro for Workstations;
- Windows 11 Enterprise/LTSC merely for longevity;
- Windows Insider / preview builds;
- Windows 11 24H2 on a new installation when 25H2 is available.

Microsoft currently lists Windows 11 25H2 as the normal General Availability release for existing x64 PCs, with Home/Pro servicing through **2027-10-12**. Windows 11 24H2 Home/Pro reaches end of servicing on **2026-10-13**. Windows 11 26H1 exists, but Microsoft explicitly describes it as scoped to new devices introduced in early 2026 and **not** as the normal feature-update path from 24H2/25H2.

Reference:
- https://learn.microsoft.com/en-us/windows/release-health/windows11-release-information

The selected **edition** is durable even though the specific feature release will change over the machine's lifetime. Follow the normal supported Windows feature-update path after commissioning rather than pinning the workstation permanently to 25H2.

## Why Windows is the host

Windows is the best primary host for this mixed workstation because it simultaneously supports:

- native IntelliJ IDEA and Android Studio;
- Android emulators;
- NVIDIA GeForce drivers and future CUDA/local-AI tooling;
- occasional gaming without a compatibility layer;
- WSL2 for first-class Linux command-line/build/container workflows;
- Hyper-V and Windows Hypervisor Platform when needed;
- BitLocker and Secure Boot;
- Remote Desktop hosting.

A native Linux dual boot is not justified for the current workload. It adds reboot friction, another OS installation to patch/recover, additional disk-layout complexity and a second set of GPU/device configuration state without providing a material benefit for Java/Android development that WSL2 cannot already cover.

Reopen native Linux/dual boot only if a future workload requires bare-metal Linux kernel behavior, KVM/device passthrough, Linux-only low-level profiling/drivers, or another capability that WSL2 cannot provide adequately.

## Why Pro rather than Home

Windows 11 Pro is selected because this is a development workstation rather than a gaming-only desktop.

Relevant Pro capabilities include:

- **Hyper-V host support** — Microsoft lists Windows 11 Professional or Enterprise as supported Hyper-V client operating systems;
- **Remote Desktop host** — Microsoft requires a Pro edition for the PC receiving Remote Desktop connections;
- professional security/manageability features such as BitLocker and policy controls.

Official references:
- https://learn.microsoft.com/en-us/windows-server/virtualization/hyper-v/host-hardware-requirements
- https://support.microsoft.com/en-us/windows/experience/connectivity-networking/how-to-use-remote-desktop
- https://www.microsoft.com/ro-ro/windows/compare-windows-11-home-vs-pro-versions

At the 2026-08-31 Microsoft Store Romania price, a new Windows 11 Pro download license is **1,199 RON**, versus **690 RON** for Home. The roughly 509 RON premium is acceptable for a machine intended to use virtualization and professional management features.

Official store reference:
- https://www.microsoft.com/ro-ro/d/windows-11-pro/dg7gmgf0d8h4

The user does **not** have an existing Windows license for this build, so a **new legitimate Windows 11 Pro license is a required BOM purchase**. Prefer a normal retail/digital license with a clear Microsoft/authorized-retail path rather than a grey-market key.

## Why not Pro for Workstations

Windows 11 Pro for Workstations is unnecessary for this build.

Microsoft positions it for substantially larger workstation configurations, including support for up to **4 CPUs and 6 TB RAM**, plus workstation-specific features such as SMB Direct and broader ReFS-oriented use cases.

This machine has:

- one Ryzen 9 9950X3D socket;
- a 256 GB long-term RAM target;
- one primary local workstation user;
- no current RDMA/SMB Direct requirement.

Microsoft Store Romania currently lists Pro for Workstations at **1,999 RON**, roughly **800 RON more than normal Pro**. There is no workload benefit here that justifies that premium.

References:
- https://www.microsoft.com/en/windows/business/windows-11-pro
- https://www.microsoft.com/ro-ro/d/windows-11-pro-pentru-statii-de-lucru/dg7gmgf0kr4m

A future Windows **Dev Drive** does not require Pro for Workstations: Microsoft documents Dev Drive as available on all Windows 11 SKUs. Therefore Pro for Workstations should not be bought merely to obtain ReFS-based developer storage.

Reference:
- https://learn.microsoft.com/en-us/windows/dev-drive/

## Linux development environment

Use **WSL2** as the default Linux environment.

Selected distribution:

**Ubuntu 26.04.1 LTS**

Canonical currently identifies Ubuntu 26.04.1 LTS as the latest LTS for Ubuntu on WSL. Ubuntu 26.04 LTS receives standard security maintenance through **2031**.

References:
- https://ubuntu.com/download/wsl
- https://ubuntu.com/about/release-cycle?product=ubuntu&release=ubuntu&version=26.04+LTS

Microsoft's normal installation path is:

```powershell
wsl --install
```

WSL2 is the default for new WSL installations. Verify after installation with:

```powershell
wsl --status
wsl --list --verbose
```

Reference:
- https://learn.microsoft.com/en-us/windows/wsl/install

Do not use Insider/preview WSL builds for the baseline workstation. Stable WSL updates are sufficient unless a specific production-blocking issue requires a newer release.

## Windows/WSL filesystem policy

Avoid treating Windows and Linux filesystems as interchangeable for high-I/O development work.

- Windows-native IDE/toolchain repositories should live on a normal Windows filesystem.
- Linux-native build trees, package caches, Docker/container data and tools that perform heavy Linux filesystem I/O should live **inside the WSL filesystem**, not under `/mnt/c` merely for convenience.
- Do not move an actively used Linux build tree back and forth across the Windows/WSL filesystem boundary.
- When the future 4 TB+ work SSD is added, reassess moving WSL VHDX/container storage/build caches to that drive.

For Windows-native repositories, consider a **Windows Dev Drive** on the future work SSD if benchmarks on the real Java workload justify it. Do not carve the initial 2 TB system SSD into multiple permanent partitions merely to create a Dev Drive before there is evidence that it helps.

Microsoft documents Dev Drive as intended for source trees, package caches, build outputs and intermediate files, and notes that WSL metadata semantics are not supported on ReFS Dev Drive volumes. Therefore keep Linux-native work inside WSL rather than forcing it onto a Dev Drive.

Reference:
- https://learn.microsoft.com/en-us/windows/dev-drive/

## Firmware settings before OS installation

Start from a current stable ProArt BIOS and conservative defaults.

Required/selected baseline:

- UEFI-native boot;
- CSM/legacy boot disabled;
- Secure Boot enabled;
- AMD fTPM / TPM 2.0 enabled;
- AMD SVM virtualization enabled for WSL2/Hyper-V;
- IOMMU enabled unless a specific stability issue is demonstrated;
- memory at Auto/JEDEC for initial validation;
- CPU at stock/conservative settings;
- no manual PBO/overclocking during commissioning.

Do the major BIOS update **before enabling BitLocker**. Firmware/TPM changes after BitLocker is active can trigger recovery-key requirements.

## Windows installation sequence

1. update the motherboard to the chosen stable BIOS;
2. load conservative defaults and set the firmware baseline above;
3. install Windows 11 Pro 25H2 x64 in UEFI/GPT mode onto the Samsung 990 PRO;
4. complete normal Windows Update production updates — do not opt into Insider or preview channels;
5. install current AMD chipset drivers;
6. install motherboard/network/Wi-Fi/Bluetooth drivers only where Windows Update does not provide a satisfactory current driver;
7. install the current **NVIDIA Studio Driver (WHQL)** as the default stability-oriented branch;
8. validate Device Manager, event logs, sleep/resume and network interfaces;
9. only after firmware/driver baseline is stable, enable BitLocker and securely retain the recovery key;
10. install/update WSL and Ubuntu 26.04.1 LTS;
11. install development tooling and run workload validation.

## NVIDIA driver policy

Use the current **NVIDIA Studio Driver, WHQL** as the default driver branch for the reused RTX 3060.

NVIDIA states that both Game Ready and Studio drivers support games and creative applications; Game Ready prioritizes day-zero game releases, while Studio emphasizes stability/testing for production workflows. Gaming is secondary in this build, so the Studio branch better matches the workstation policy.

Switch to Game Ready only if a specific newly released game materially benefits from its day-zero fixes/optimizations. There is no need to reinstall Windows to switch driver branches.

Reference:
- https://www.nvidia.com/en-us/geforce/drivers/

## BitLocker policy

Enable BitLocker on the Windows system volume after initial firmware and driver validation.

Before enabling it:

- finish the first planned BIOS update;
- confirm TPM/Secure Boot state is stable;
- save the recovery key somewhere independent of the workstation;
- verify recovery-key retrieval before relying on encryption.

Suspend BitLocker before future BIOS/TPM changes when appropriate.

## Virtualization policy

WSL2 is part of the baseline.

Full Hyper-V virtual-machine use is available because Windows 11 Pro is selected, but do not create a large permanent VM estate by default. Use the lightest isolation mechanism that matches the task:

- WSL2 for Linux command-line/dev/container workflows;
- Android Emulator with the supported Windows hypervisor path;
- Hyper-V VMs when a genuinely separate Windows/Linux machine boundary is useful;
- conventional third-party VMs only when they offer a specific capability not covered by the selected stack.

The 64 GB Phase-1 memory makes moderate VM/WSL concurrency practical; the eventual 256 GB configuration will expand this substantially.

## Initial software baseline

Install only the tooling required to establish a reproducible development baseline:

- Windows Terminal;
- PowerShell 7;
- Git for Windows;
- IntelliJ IDEA as required;
- Android Studio and Android SDK/emulator as required;
- WSL2 + Ubuntu 26.04.1 LTS;
- required JDKs/build tools;
- container tooling only after deciding the preferred runtime/licensing model.

Avoid motherboard/vendor suites and generic "optimizer" utilities unless a specific function requires them. Prefer direct firmware/driver installation and native monitoring tools.

## Bring-up validation

After OS installation, record a baseline before tuning:

### Platform

- BIOS version;
- Windows edition/version/build;
- Secure Boot and TPM state;
- memory capacity/rate/timings;
- CPU stock power-policy state;
- Device Manager with no unexplained devices/errors.

### Storage

- Samsung 990 PRO firmware;
- SMART/health baseline;
- BitLocker state after activation;
- sustained-I/O temperature check.

### CPU / memory

- extended memory test at Auto/JEDEC;
- sustained CPU compile/test-style workload;
- synthetic thermal check as a separate worst case;
- no WHEA errors or thermal throttling under the selected policy.

### GPU

- current WHQL Studio driver;
- representative game/3D test;
- CUDA visibility if local-AI tooling is installed later.

### Virtualization / development

- `wsl --status` and `wsl --list --verbose` confirm WSL2;
- Ubuntu package update succeeds;
- large Java build/test workload runs successfully;
- Android Emulator starts and runs reliably;
- Docker/container runtime validation when installed;
- sleep/resume with WSL2/virtualization enabled.

### Networking

- 2.5/10 GbE interfaces enumerate correctly;
- negotiated speed and sustained transfer are reasonable for the connected network;
- no repeated driver resets/WHEA events;
- sleep/resume retains working networking.

### UPS

- CyberPower USB link is visible;
- graceful-shutdown policy is configured;
- controlled mains-loss test succeeds.

## Selected conclusion

- **Host OS:** Windows 11 Pro x64 — **Selected**.
- **Windows license:** **new legitimate Windows 11 Pro license required for this build**; current official Microsoft Store Romania reference is **1,199 RON**.
- **Initial feature release:** Windows 11 25H2 General Availability — **Selected for installation in August 2026**.
- **Linux environment:** WSL2 + Ubuntu 26.04.1 LTS — **Selected**.
- **Dual boot:** not required; reopen only for a demonstrated bare-metal Linux need.
- **Windows Pro for Workstations:** rejected; no material benefit for this one-socket / 256 GB target build.
- **GPU driver baseline:** current NVIDIA Studio Driver WHQL.
- **Security baseline:** UEFI + Secure Boot + TPM 2.0 + BitLocker after firmware stabilization.
