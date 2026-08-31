# Operating System and Bring-up Deep Dive

Status: **Selected — Windows 11 Pro x64 host + WSL2 + Ubuntu 26.04.1 LTS**

## Host OS decision

Use **Windows 11 Pro x64** as the host operating system.

Use the current supported General Availability Windows 11 release available at installation time and apply normal production updates before workload validation. Do not use Insider/preview builds for baseline commissioning.

## Why Windows 11 Pro

Windows is the best host for this mixed workstation because it supports:

- native IntelliJ IDEA and Android Studio;
- Android Emulator;
- NVIDIA GeForce/CUDA and future local-AI tooling;
- occasional gaming without a compatibility layer;
- WSL2 for Linux command-line/build/container workflows;
- Hyper-V / Windows Hypervisor Platform;
- BitLocker and Secure Boot;
- Remote Desktop hosting.

Windows 11 Pro is selected over Home because the professional virtualization/management features are useful. Pro for Workstations remains unnecessary.

## License status

The Windows 11 Pro license is **already available**.

There is **no remaining Windows purchase target, retailer selection, SKU gate, or software cost to include in procurement**. The previous `HAV-00163` purchase target is obsolete for procurement purposes.

## Linux development environment

Use **WSL2** as the default Linux environment.

Selected distribution: **Ubuntu 26.04.1 LTS**.

Do not use Insider/preview WSL builds for the baseline workstation.

## Windows/WSL filesystem policy

The selected primary drive is the **Crucial T710 2 TB `CT2000T710SSD8`**.

- Windows-native IDE/toolchain repositories may live on the Windows filesystem.
- Linux-native build trees, package caches, container data and other high-I/O Linux workloads should normally live **inside the WSL filesystem**, not under `/mnt/c` merely for convenience.
- The whole active working set initially resides on the one T710; there is no separate system/work SSD architecture.
- `M.2_2` and `M.2_3` remain free for later additive storage only if actual capacity needs grow.

## Firmware settings before OS installation

Start from a current stable BIOS on the selected **ASUS TUF GAMING B650E-E WIFI `90MB1LT0-M0EAY0`** and conservative defaults:

- UEFI-native boot;
- CSM disabled;
- Secure Boot enabled;
- AMD fTPM / TPM 2.0 enabled;
- AMD SVM enabled;
- IOMMU enabled unless a demonstrated stability issue appears;
- memory Auto/JEDEC during commissioning;
- CPU stock/conservative;
- no manual PBO/overclocking during baseline validation.

Perform the initial BIOS update **before enabling BitLocker**.

## Windows installation sequence

1. Verify hardware SKUs and assemble the minimum bootable configuration.
2. Update motherboard BIOS and establish a firmware baseline.
3. Install the selected **48 GB Crucial Pro `CP2K24G56C46U5`** kit in A2/B2 and commission at Auto/JEDEC.
4. Install Windows 11 Pro x64 in UEFI/GPT mode onto the **Crucial T710 2 TB `CT2000T710SSD8`** in `M.2_1`.
5. Complete normal Windows Update production updates.
6. Install current AMD chipset drivers.
7. Install motherboard/network/Wi-Fi/Bluetooth drivers where required.
8. Install the current NVIDIA driver appropriate for the RTX 3060; Studio Driver is a sensible development baseline unless a specific game requires Game Ready behavior.
9. Validate Device Manager, event logs, sleep/resume and network interfaces.
10. Validate T710 firmware, SMART data and temperatures.
11. Run extended memory testing and representative sustained Java/Android workloads.
12. After firmware/driver/storage stability is established, enable BitLocker and retain the recovery key independently.
13. Install/update WSL2 and Ubuntu 26.04.1 LTS.
14. Install development tooling and run representative workload validation.

## RAM / virtualization policy

The final initial memory capacity is **48 GB / 2×24 GB**.

This supports substantial normal development concurrency but is intentionally not sized for unconstrained large-VM use.

Monitor committed memory during real work. If persistent memory pressure appears, replace the pair with a larger matched two-DIMM kit; do not add another pair as the planned upgrade path.

Use:

- WSL2 for normal Linux development/container workflows;
- Android Emulator with the supported Windows hypervisor path;
- Hyper-V VMs when a genuinely separate machine boundary is useful;
- third-party VM stacks only for a specific uncovered requirement.

## BitLocker policy

Enable BitLocker only after the initial firmware/driver/storage baseline is stable.

Store and verify the recovery key independently of the workstation. Suspend BitLocker appropriately before future firmware/TPM changes when required.

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

- motherboard BIOS/AGESA version;
- Windows edition/version/build;
- Secure Boot/TPM/BitLocker state;
- Device Manager state;
- memory capacity/rate/timings/voltage;
- T710 firmware/SMART/temperature baseline;
- extended memory stability test results;
- sustained Java build/test and thermal behavior;
- NVIDIA driver version and representative GPU/game test;
- WSL2/Ubuntu status;
- Android Emulator status;
- sleep/resume and network stability;
- real committed-memory usage during representative development sessions.

## Selected conclusion

- **Host OS:** Windows 11 Pro x64
- **License:** already available; no procurement action
- **Linux environment:** WSL2 + Ubuntu 26.04.1 LTS
- **Dual boot:** not required absent a demonstrated bare-metal Linux need
- **Storage target:** Crucial T710 2 TB `CT2000T710SSD8`
- **Initial RAM:** Crucial Pro `CP2K24G56C46U5`, 48 GB / 2×24 GB
- **Security baseline:** UEFI + Secure Boot + TPM 2.0 + BitLocker after firmware stabilization
- **UPS:** none
