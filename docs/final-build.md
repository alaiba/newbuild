# Final Build

This is the current source-of-truth BOM for the initial workstation. Closed decisions remain fixed unless explicitly reopened. Purchase-time price/stock details live in `docs/procurement-plan-2026-08-31.md`.

## Selected initial build

| Component | Exact model / configuration | Status | Current purchase reference |
|---|---|---|---:|
| CPU | AMD Ryzen 9 **9950X3D Box/WOF `100-100000719WOF`** | **Selected** | ~3,349.99 lei direct EvoMAG indexed listing |
| Motherboard | **ASUS ProArt X870E-Creator WiFi** | **Selected** | ~2,542–2,654 lei current competitive listings |
| Phase-1 RAM | **Crucial `CT2K32G56C46U5`, 64 GB (2×32), DDR5-5600 CL46, 1.1 V** | **Selected target** | ~5.0k-class market; exact-SKU checkout gate |
| Long-term RAM | **256 GB target, expected 4×64 GB** | **Architecture selected / deferred** | Exact modules/ECC verdict deferred |
| CPU cooler | **Noctua NH-D15 G2 standard `CPNTD15G2`**, 7 mm AM5 offset | **Selected** | ~0.70–0.73k lei |
| System/tools SSD | **Samsung 990 PRO 2 TB `MZ-V9P2T0BW`** | **Selected** | ~1.90–1.95k lei |
| Future work SSD | **4 TB-or-larger NVMe** | **Architecture selected / deferred** | Reserve `M.2_1` |
| PSU | **Seasonic VERTEX GX-1200 current ATX 3.1 / PCIe 5.1 / 12V-2x6 revision** | **Selected** | ~1,289.99 lei explicit Altex ATX 3.1 listing |
| Case | **Fractal Design North XL Mesh Charcoal Black `FD-C-NOR1X-01`** | **Selected** | ~1,018.51 lei exact ForIT listing |
| Rear fan | **Noctua NF-A14x25 G2 PWM**, standard square-frame single fan, EAN `9010018100617` | **Selected** | ~193 lei |
| Case airflow | **3× included 140 mm front intake + 1×140 mm rear exhaust** | **Selected** | No top/side fans initially |
| GPU | Existing NVIDIA GeForce **RTX 3060 12 GB** | **Reuse / selected** | 0 lei new spend |
| UPS | **CyberPower `CP1600EPFCLCD`** | **Selected** | ~1.65–1.75k lei current working checkout envelope |
| Host OS | **Windows 11 Pro x64** | **Selected** | — |
| Windows license | **Retail/FPP USB English `HAV-00163`** | **Selected / required purchase** | ~1,124–1,147 lei current retailer controls |
| Initial Windows release | **Windows 11 25H2 General Availability** | **Selected for installation** | Included in license |
| Linux environment | **WSL2 + Ubuntu 26.04.1 LTS** | **Selected** | Free |

## Current initial-purchase envelope

Representative current complete order, including Windows Retail/FPP and excluding the reused RTX 3060, is approximately **18.9–19.3k lei before shipping**.

Do not treat the low end as a guaranteed checkout total. RAM and UPS prices are currently the most volatile/inconsistent listings.

The build remains comfortably below the ~30k planning level without downgrading any permanent component.

## Purchase gates

### CPU

Buy the boxed/WOF processor **`100-100000719WOF`**. Do not silently substitute Tray `100-000000719` merely because a search result is cheaper.

### RAM

Target **`CT2K32G56C46U5`** exactly:

- 64 GB, 2×32 GB;
- desktop 288-pin UDIMM;
- DDR5-5600 CL46;
- 1.1 V.

Romanian indexing sometimes mixes it with **`CT2K32G56C46S5`**, which is laptop/SO-DIMM memory. The product page/cart/invoice must expose the **`...U5`** SKU before ordering.

If the Crucial kit rises close to the current price of **Kingston `KF556C36BBEK2-64`**, recompare the Kingston kit because Kingston explicitly lists it for the ProArt.

Bring-up: A2/B2, current stable BIOS, Auto/JEDEC first, no EXPO/XMP during baseline validation, extended memory testing.

### Cooler

Buy **NH-D15 G2 standard `CPNTD15G2`**, not LBC/HBC. Use the included 7 mm AM5 offset mount. CPU remains stock/conservative; no PBO/uncapped-power policy.

### Storage

Install **Samsung 990 PRO 2 TB `MZ-V9P2T0BW`** under the ProArt heatsink in **`M.2_3`**.

Reserve CPU-connected **`M.2_1`** for the future 4 TB+ work/VM/container/data drive. Avoid `M.2_2` unless its graphics-lane trade-off is deliberately accepted. No RAID; external/network backup remains required.

### PSU

The exact PSU is closed, but the received revision must pass all of these checks:

1. ATX 3.1 on listing/box;
2. PCIe 5.1 compatibility;
3. supplied current **12V-2x6** GPU cable;
4. reject explicit ATX 3.0 / PCIe 5.0 / 12VHPWR old stock;
5. use only Seasonic-approved modular cables.

### Case / airflow

Exact case: **`FD-C-NOR1X-01`**, Charcoal Black **Mesh**. Do not substitute TG Dark `FD-C-NOR1X-02` or an ambiguously labelled variant.

Initial airflow remains:

- 3× included 140 mm front intake;
- 1× standard square-frame **NF-A14x25 G2 PWM** rear exhaust;
- top/side empty.

Add fans only if measurements justify them.

### UPS

Exact model remains **`CP1600EPFCLCD`**. The seller is a purchase-time decision because current aggregators/direct pages disagree materially on price.

Buy new/sealed and verify the delivered European/Schuko configuration. Reassess the UPS after a materially higher-power future GPU or if measured load approaches roughly 700–800 W.

### Windows

For this DIY self-build, the selected license channel is explicitly:

**Microsoft Windows 11 Pro Retail/FPP USB English `HAV-00163`.**

Do not substitute:

- OEM/DSP/System Builder;
- Pro for Workstations;
- Home;
- an undocumented emailed/grey-market standalone key.

Install Windows 11 Pro 25H2 GA, then follow the normal supported feature-update path over the machine's lifetime.

## OS / software baseline

- Windows 11 Pro x64 host;
- WSL2 + Ubuntu 26.04.1 LTS;
- current NVIDIA Studio Driver WHQL baseline;
- Windows-native repositories/caches on Windows storage;
- Linux-native high-I/O repos/caches/container data inside the WSL filesystem rather than `/mnt/c`;
- no native Linux dual boot unless a future workload demonstrates a bare-metal requirement.

## Firmware / security baseline

Before serious workload validation:

- update ProArt to the chosen current stable BIOS;
- UEFI native, CSM disabled;
- Secure Boot enabled;
- TPM 2.0 / AMD fTPM enabled;
- SVM enabled;
- IOMMU enabled unless a real stability issue appears;
- RAM Auto/JEDEC;
- CPU stock/conservative.

Enable BitLocker **after** the first firmware/driver baseline is stable and retain the recovery key independently of the workstation.

## Initial validation

Record a baseline before tuning:

- BIOS version and firmware settings;
- exact RAM SKU, trained speed/timings and extended memory-test result;
- Windows edition/version/build, Secure Boot/TPM/BitLocker state;
- Samsung firmware + SMART baseline;
- sustained Java compile/test-style load and separate synthetic thermal check;
- no unexplained WHEA errors or thermal throttling;
- RTX 3060 Studio Driver + representative 3D/game test;
- WSL2, Ubuntu update, large Java build/test, Android Emulator and sleep/resume;
- 2.5/10 GbE enumeration and negotiated speed;
- CyberPower USB management + controlled mains-loss shutdown test.

## Deferred purchases / decisions

- exact eventual 256 GB 4×64 GB matched memory configuration and ECC/non-ECC verdict;
- operational ECC reporting validation if ECC is used;
- exact future 4 TB+ work SSD;
- future high-VRAM GPU;
- UPS enlargement when the future GPU/load requires it;
- exact container runtime if licensing/workflow makes that material.

Detailed decisions: `docs/decisions.md`.

Purchase execution: `docs/procurement-plan-2026-08-31.md`.
