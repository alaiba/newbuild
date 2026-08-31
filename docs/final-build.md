# Final Build

This is the current source-of-truth BOM for the initial workstation. Purchase-time execution lives in `docs/procurement-plan-2026-08-31.md`.

## Selected initial build

| Component | Exact model / configuration | Status | Current purchase reference |
|---|---|---|---:|
| CPU | AMD Ryzen 9 **9950X3D Box/WOF `100-100000719WOF`** | **Selected** | ~3,349.99 lei EvoMAG |
| Motherboard | **ASUS ProArt X870E-Creator WiFi** | **Selected** | ~2.68k lei current EvoMAG-class control |
| Phase-1 RAM | **Crucial `CT2K32G56C46U5`, 64 GB (2×32), DDR5-5600 CL46, 1.1 V** | **Selected** | ~4,799.99 lei fresh EvoMAG/comparison control; exact-SKU gate |
| Long-term RAM | **256 GB target, expected 4×64 GB** | **Architecture selected / deferred** | exact modules/ECC verdict deferred |
| CPU cooler | **Noctua NH-D15 G2 standard**, 7 mm AM5 offset | **Selected** | ~690–710 lei EvoMAG-class control |
| System/tools SSD | **Samsung 990 PRO 2 TB `MZ-V9P2T0BW`** | **Selected** | ~1,899.99 lei EvoMAG |
| Future work SSD | **4 TB-or-larger NVMe** | **Architecture selected / deferred** | reserve `M.2_1` |
| PSU | **Seasonic VERTEX GX-1200 current ATX 3.1 / PCIe 5.1 / 12V-2x6** | **Selected baseline** | ~1,289.99 lei Altex |
| PSU value upgrade | **VERTEX PX-1200 current ATX 3.1** | **Preferred if in stock at ≤~200 lei premium** | ~1,449.99 lei reference; currently explicit listing out of stock |
| Case | **Fractal North XL Mesh `FD-C-NOR1X-01`** | **Selected** | ~882.99 lei EvoMAG exact-SKU control |
| Rear fan | **Noctua NF-A14x25 G2 PWM**, standard square-frame single | **Selected** | ~200.99 lei EvoMAG |
| Case airflow | **3× included 140 mm front intake + 1×140 mm rear exhaust** | **Selected** | no top/side fans initially |
| GPU | Existing **RTX 3060 12 GB** | **Reuse / selected** | 0 lei |
| UPS | **CyberPower PR1500ELCD, 1500 VA / 1350 W** | **Selected** | ~2,948.99 lei EvoMAG/current market |
| Host OS | **Windows 11 Pro x64** | **Selected** | — |
| Windows license | **Retail/FPP USB Romanian `HAV-00197`** | **Selected / required** | ~1,199.99 lei EvoMAG; switch display language to English |
| Initial Windows release | **Windows 11 25H2 GA** | **Selected for installation** | included |
| Linux environment | **WSL2 + Ubuntu 26.04.1 LTS** | **Selected** | free |

## Current optimized purchase envelope

Using current conservative controls and the purchase-ready **GX-1200**:

**approximately 19,950 lei before shipping.**

If a current-revision **PX-1200** is available at the current ~160 lei premium:

**approximately 20,110 lei before shipping.**

This still leaves almost **10,000 lei** below the ~30k planning level while materially improving the UPS's lifetime usefulness.

The total is a checkout envelope, not a promise; RAM and stock can move quickly.

## Why the final optimization spends more on the UPS

The previous CP1600EPFCLCD was 1000 W and excellent for the current RTX 3060 machine, but the build intentionally preserves a future whole-system envelope around **900–980 W**.

At that future load a 1000 W UPS would operate near its limit and would likely need replacement. The selected **PR1500ELCD** provides **1350 W**, placing the same load around 67–73% of rating, while adding longer runtime, stronger AVR behavior and a hot-swappable battery path.

The ~1.4k lei premium therefore has a credible chance of eliminating an entire future UPS replacement and is justified by the stability/endurance/lifecycle objective.

## Procurement consolidation

Default provider plan: **two providers**.

### EvoMAG primary order

Target EvoMAG for:

- CPU;
- motherboard;
- exact Crucial RAM;
- NH-D15 G2;
- Samsung 990 PRO;
- North XL Mesh;
- Noctua rear fan;
- CyberPower PR1500ELCD;
- Windows 11 Pro Retail/FPP `HAV-00197`.

### Altex

Target Altex for the explicitly current **VERTEX GX-1200 ATX 3.1**.

If EvoMAG can confirm in writing that its VERTEX unit is current ATX 3.1 / PCIe 5.1 / 12V-2x6, a one-provider order is acceptable.

A third provider is justified only for roughly **≥300 lei net saving**, or materially better SKU/revision/stock/warranty certainty.

## Component value review

The widened price/performance review considered both cheaper parts and premium upgrades.

### Kept as selected

- **9950X3D:** the ~650 lei 9950X saving is not enough to give up the X3D's gaming advantage; compile performance is not worse in the relevant evidence.
- **ProArt X870E-Creator:** the cheaper Taichi Creator gives up the strongest explicit evidence for our 4×64 GB / 256 GB and ECC-oriented stability target.
- **NH-D15 G2:** cheaper Thermalright alternatives are excellent, but Noctua's mounting/support ecosystem, fan endurance and six-year warranty fit the 10-year objective.
- **990 PRO 2 TB:** KC3000 saves too little; 9100 PRO costs more but PCIe 5 performance would be wasted in the selected PCIe 4 `M.2_3` system slot and would consume the future-work-drive slot if moved to `M.2_1`.
- **Noctua rear fan:** now available inside the primary EvoMAG order, eliminating the logistics reason to downgrade.
- **Crucial 64 GB:** current price and conservative 1.1 V profile remain better value than paying ~500–600+ lei for the Kingston explicit-compatibility kit; recompare Kingston if the gap shrinks to ~200–250 lei.

### Premium changes

- **UPS:** upgrade to PR1500ELCD — selected.
- **PSU:** PX-1200 is preferred only when current stock exists at ≤~200 lei over GX; otherwise GX remains the purchase-ready choice.
- **Windows:** use Romanian Retail/FPP `HAV-00197` at EvoMAG rather than creating another provider for the slightly cheaper English package; Windows 11 Pro can use English as its display language.

## Hard purchase gates

### CPU

- exact Ryzen 9 9950X3D;
- Box/WOF `100-100000719WOF` preferred;
- no silent Tray substitution.

### RAM

- exact **`CT2K32G56C46U5`**;
- 64 GB / 2×32;
- desktop 288-pin UDIMM;
- reject **`CT2K32G56C46S5`** laptop SO-DIMM;
- A2/B2, Auto/JEDEC baseline, extended memory test.

### Cooler

- NH-D15 G2 **standard**;
- included AM5 offset mount;
- no LBC/HBC substitution.

### SSD

- exact Samsung **`MZ-V9P2T0BW`**;
- install in ProArt **`M.2_3`**;
- reserve `M.2_1` for future work SSD.

### PSU

For GX or conditional PX:

- ATX 3.1 on listing/box;
- PCIe 5.1;
- supplied current **12V-2x6** cable;
- reject explicit old ATX 3.0 / 12VHPWR inventory;
- use only Seasonic-approved modular cables.

### Case

- exact **`FD-C-NOR1X-01`** North XL Charcoal Black Mesh;
- reject `FD-C-NOR1X-02` TG Dark unless deliberately reopened.

### UPS

- exact **CyberPower `PR1500ELCD`**;
- 1500 VA / 1350 W;
- new/sealed;
- note **IEC C13** outlet layout and use correctly rated IEC cables;
- configure USB/PowerPanel graceful shutdown and perform a controlled mains-loss test.

### Windows

- Windows 11 **Pro**;
- **Retail/FPP**;
- preferred consolidated SKU **`HAV-00197`**;
- install/switch English display language as desired;
- not OEM/DSP and not an undocumented standalone key.

## OS / firmware baseline

- Windows 11 Pro 25H2 GA;
- WSL2 + Ubuntu 26.04.1 LTS;
- NVIDIA Studio Driver WHQL baseline;
- current stable ProArt BIOS;
- UEFI, Secure Boot, TPM 2.0, SVM/IOMMU;
- RAM Auto/JEDEC during commissioning;
- CPU stock/conservative;
- BitLocker only after firmware/driver stabilization.

## Deferred items

- exact eventual 256 GB matched memory configuration and ECC verdict;
- future 4 TB+ work SSD;
- future high-VRAM GPU;
- exact container runtime if licensing/workflow makes it material.

Detailed decisions: `docs/decisions.md`.

Purchase execution: `docs/procurement-plan-2026-08-31.md`.
