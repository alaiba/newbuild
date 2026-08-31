# Final Build

This document is the current bill-of-materials and initial software-baseline view. Closed decisions are fixed inputs unless explicitly reopened; deferred items remain subject to their stated future purchase gates.

## Selected initial build

| Component | Model / configuration | Status | Current price reference |
|---|---|---|---:|
| CPU | AMD Ryzen 9 9950X3D | **Selected** | ~3.35–3.52k lei |
| Motherboard | **ASUS ProArt X870E-Creator WiFi** | **Selected** | ~2.68–2.90k lei market range |
| Phase-1 memory | **Crucial `CT2K32G56C46U5`, 64 GB (2×32 GB), DDR5-5600 CL46, 1.1 V** | **Selected target** | ~4.7–4.8k lei current low market |
| Long-term memory | **256 GB target, expected 4×64 GB** | **Target selected / purchase deferred** | Deferred |
| CPU cooler | **Noctua NH-D15 G2 standard base, 7 mm AM5 offset** | **Selected** | ~0.69–0.73k lei |
| System/tools SSD | **Samsung 990 PRO 2 TB `MZ-V9P2T0BW`** | **Selected** | ~1.90–1.95k lei |
| Future work SSD | **4 TB-or-larger NVMe** | **Architecture selected / purchase deferred** | Deferred |
| PSU | **Seasonic VERTEX GX-1200, current ATX 3.1 / PCIe 5.1 / 12V-2x6 revision** | **Selected** | ~1.29k lei explicit Altex ATX 3.1 listing |
| Case | **Fractal Design North XL Mesh** | **Selected** | ~0.93–1.06k lei current market class |
| Rear case fan | **Noctua NF-A14x25 G2 PWM** | **Selected** | ~0.19–0.21k lei |
| Case-fan layout | **3× included 140 mm front intake + 1× Noctua rear exhaust** | **Selected** | Front fans included |
| GPU | NVIDIA GeForce RTX 3060 12 GB | **Existing / selected** | 0 lei initial-build spend |
| UPS | **CyberPower CP1600EPFCLCD** | **Selected** | ~1.53–1.59k lei |
| Host OS | **Windows 11 Pro x64** | **Selected** | 1,199 RON official Microsoft Store reference if a new license is required |
| Initial Windows release | **Windows 11 25H2, General Availability** | **Selected for installation** | Included in license |
| Linux environment | **WSL2 + Ubuntu 26.04.1 LTS** | **Selected** | Free |

## Initial-BOM cost position — 2026-08-31

Current selected hardware with Crucial 64 GB remains approximately **17.3–18.1k lei**, excluding the reused RTX 3060, future 4 TB+ work SSD and future GPU.

If a new Windows 11 Pro retail/digital license is required at the current official Microsoft Store Romania reference of **1,199 RON**, the initial complete hardware + OS purchase is approximately **18.5–19.3k lei**.

If a legitimate transferable Windows 11 Pro license is already available, the OS does not add new spend.

The build therefore remains comfortably below the ~30k planning level even after selecting 64 GB and a normal Pro license.

## Memory

Selected Phase-1 configuration:

- **Crucial `CT2K32G56C46U5`**;
- 64 GB, 2×32 GB;
- DDR5-5600 CL46;
- 1.1 V;
- low-profile unbuffered desktop DIMMs.

Fallback if Crucial stock/warranty/pricing becomes poor:

- **Kingston FURY Beast `KF556C36BBEK2-64`**, 2×32 GB DDR5-5600 CL36 EXPO.

Bring-up:

1. install A2/B2;
2. update BIOS first;
3. boot at Auto/JEDEC;
4. no EXPO/XMP during baseline validation;
5. run extended memory testing;
6. record SKU, BIOS version, trained rate and timings.

The eventual 256 GB configuration remains a separate matched-set purchase; prefer ECC UDIMM only if exact modules, four-DIMM stability and OS-visible ECC reporting are all credible.

## Cooling

Selected:

- **Noctua NH-D15 G2 standard base**;
- **7 mm AM5 offset**;
- stock/conservative CPU settings;
- no PBO/uncapped-power policy.

The selected Crucial modules are low profile. Expect zero or only minimal front-fan lift, with ample margin inside the North XL's 185 mm CPU-cooler envelope.

## Storage

Initial:

- **Samsung 990 PRO 2 TB `MZ-V9P2T0BW`** in **`M.2_3`** as the permanent system/tools drive.

Later:

- reserve CPU-connected **`M.2_1`** for a future **4 TB-or-larger work/VM/container/data SSD**;
- avoid `M.2_2` unless its graphics-lane trade-off is intentionally accepted;
- no RAID; external/network backup remains required.

Do not split the initial 2 TB drive into a complicated permanent layout merely to create a Windows Dev Drive. Reconsider a ReFS Dev Drive on the future work SSD for Windows-native repos/caches if real workload measurements justify it.

## PSU

Selected exact PSU:

**Seasonic VERTEX GX-1200, current ATX 3.1 / PCIe 5.1 / 12V-2x6 revision.**

Current explicit Romanian purchase reference is Altex around **1,289.99 lei**.

Receipt acceptance:

1. box/listing says ATX 3.1;
2. product is PCIe 5.1 compatible;
3. supplied GPU cable is 12V-2x6;
4. reject ATX 3.0 / 12VHPWR old inventory;
5. retain model/serial/warranty evidence.

## Chassis and airflow

Selected:

- **Fractal Design North XL Mesh**;
- 3× included 140 mm front intake;
- 1× **Noctua NF-A14x25 G2 PWM** rear exhaust;
- top empty initially;
- side empty initially.

Add more fans only if measured thermals justify them.

## UPS

Selected:

**CyberPower CP1600EPFCLCD**

- 1600 VA / 1000 W;
- line-interactive;
- pure sine wave;
- Active-PFC compatible;
- USB HID / PowerPanel;
- user-replaceable `RBP0142` battery.

Reassess when a materially higher-power GPU is installed or measured wall load approaches roughly 700–800 W.

## Operating system

### Host

**Windows 11 Pro x64** is selected.

Initial installation release: **Windows 11 25H2 General Availability**.

Why Pro:

- Hyper-V host capability;
- Remote Desktop hosting;
- BitLocker/professional management features;
- native Windows gaming/NVIDIA/Android Studio compatibility;
- WSL2 for Linux development.

Do not buy Pro for Workstations for this configuration. Its premium does not materially benefit a single-socket system with a 256 GB memory target, and Windows Dev Drive is available on normal Windows 11 editions.

Do not intentionally install Windows 24H2 on this new machine; Home/Pro servicing ends 2026-10-13. Do not force-install 26H1: Microsoft describes it as a new-device release rather than the normal feature-update path from 24H2/25H2. Follow normal supported feature updates after commissioning.

### Linux environment

Selected:

**WSL2 + Ubuntu 26.04.1 LTS**.

No native Linux dual boot initially.

Filesystem policy:

- Windows-native repositories/build caches stay on Windows storage;
- Linux-native repos/caches/container data stay inside the WSL filesystem rather than `/mnt/c` when I/O matters;
- reassess WSL VHDX/container placement when the future work SSD is added.

Reopen dual boot only for a demonstrated bare-metal Linux kernel/KVM/device/driver requirement.

### GPU driver

Default to the current **NVIDIA Studio Driver WHQL**. Gaming is secondary and NVIDIA positions Studio for stability-oriented workflows; switch to Game Ready only when a specific game needs day-zero fixes/optimizations.

Detailed OS/bring-up rationale: `docs/components/os.md`.

## Firmware and security baseline

Before Windows installation:

- update to the chosen current stable ProArt BIOS;
- UEFI-native boot, CSM disabled;
- Secure Boot enabled;
- TPM 2.0 / AMD fTPM enabled;
- AMD SVM enabled;
- IOMMU enabled unless an actual stability issue appears;
- memory Auto/JEDEC;
- CPU stock/conservative, no manual PBO.

Enable **BitLocker only after the first BIOS/firmware/driver baseline is stable**, then retain the recovery key independently of the workstation.

## Driver/software baseline

Order:

1. Windows Update production channel;
2. current AMD chipset driver;
3. current motherboard/network/Wi-Fi/Bluetooth drivers where required;
4. current NVIDIA Studio Driver WHQL;
5. Windows Terminal;
6. PowerShell 7;
7. Git for Windows;
8. WSL2 + Ubuntu 26.04.1 LTS;
9. IntelliJ IDEA / Android Studio / required JDKs and build tools;
10. container runtime only after choosing the preferred workflow/licensing model.

Avoid generic optimizer utilities and unnecessary motherboard vendor suites.

## Procurement policy

- **PC Garage and Altex are co-preferred retailers**;
- **eMAG is also acceptable**;
- exact SKU/revision, seller quality and normal Romanian/EU warranty take precedence over retailer order;
- small price differences do not matter;
- material differences can justify another reputable Romanian/EU seller.

## Deferred items

- exact 256 GB 4×64 GB memory implementation and ECC verdict;
- future 4 TB+ work SSD;
- future high-VRAM GPU;
- exact container-runtime choice if licensing/workflow makes that material.

## Bring-up and validation

### Hardware/firmware

- record BIOS version and firmware settings;
- verify 64 GB memory at Auto/JEDEC;
- extended memory stability test;
- verify CPU remains on selected conservative power policy;
- no unexplained WHEA errors.

### Windows/security

- record Windows edition/version/build;
- confirm Secure Boot and TPM state;
- Device Manager clean;
- enable/test BitLocker recovery after firmware baseline is stable;
- normal production Windows Update only, no Insider/preview baseline.

### Storage

- update Samsung 990 PRO firmware;
- record SMART/health baseline;
- sustained-I/O temperature check.

### Thermal/acoustic

- sustained Java compile/test-style CPU load;
- separate synthetic thermal worst-case;
- combined CPU/GPU case-closed test;
- tune fan curves for sustained load, not short Ryzen spikes.

### GPU

- current WHQL Studio driver;
- representative gaming/3D test;
- later verify CUDA visibility if AI tooling is installed.

### Development/virtualization

- `wsl --status` and `wsl --list --verbose` confirm WSL2;
- Ubuntu update succeeds;
- representative large Java build/test passes;
- Android Emulator runs reliably;
- container runtime validation when installed;
- sleep/resume works with WSL2/virtualization enabled.

### Networking

- verify 2.5/10 GbE enumeration and negotiated speed;
- sustained transfer sanity test;
- sleep/resume retains working networking;
- no repeated driver resets/WHEA events.

### UPS

- CyberPower USB link visible;
- configure graceful shutdown;
- controlled mains-loss shutdown test succeeds.
