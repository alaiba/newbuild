# Final Build

This is the current source-of-truth architecture for the workstation. A requirement change on 2026-08-31 finalized memory at **128 GB / 2×64 GB / 1DPC from day one**, which reopens the exact motherboard and RAM-model optimization before purchase.

## Current build state

| Component | Configuration | Status |
|---|---|---|
| CPU | AMD Ryzen 9 **9950X3D Box/WOF `100-100000719WOF`** | **Selected** |
| Motherboard | ASUS **ProArt X870E-Creator WiFi** incumbent reference | **Reopened for optimization** because 4×64/256 GB is no longer required |
| RAM capacity | **128 GB from day one** | **Selected / final** |
| RAM topology | **2×64 GB DDR5 UDIMM, 1DPC, A2/B2** | **Selected / final** |
| Exact RAM kit | Exact 2×64 GB matched kit | **Open for optimization** |
| ECC | ECC UDIMM only if end-to-end support/reporting is compelling | **Open within RAM optimization** |
| CPU cooler | **Noctua NH-D15 G2 standard**, 7 mm AM5 offset | **Selected** |
| System/tools SSD | **Samsung 990 PRO 2 TB `MZ-V9P2T0BW`** in the incumbent storage architecture | **Selected incumbent; storage architecture now under requested review** |
| Future work SSD | Current plan: 4 TB-or-larger NVMe later | **Selected incumbent; under requested storage review** |
| PSU | **Seasonic VERTEX GX-1200 current ATX 3.1 / PCIe 5.1 / 12V-2x6** | **Selected baseline** |
| PSU value upgrade | **VERTEX PX-1200 current ATX 3.1** | **Preferred if in stock at ≤~200 lei premium** |
| Case | **Fractal North XL Mesh `FD-C-NOR1X-01`** | **Selected** |
| Rear fan | **Noctua NF-A14x25 G2 PWM**, standard square-frame single | **Selected** |
| Case airflow | 3× included 140 mm front intake + 1×140 mm rear exhaust | **Selected** |
| GPU | Existing **RTX 3060 12 GB** | **Reuse / selected** |
| UPS | **CyberPower PR1500ELCD, 1500 VA / 1350 W** | **Selected** |
| Host OS | **Windows 11 Pro x64** | **Selected** |
| Windows license | **Retail/FPP USB English `HAV-00163` from PROstore** | **Selected purchase target** |
| Initial Windows release | **Windows 11 25H2 GA** | **Selected** |
| Linux environment | **WSL2 + Ubuntu 26.04.1 LTS** | **Selected** |

## Memory architecture — final

The workstation will not use temporary RAM.

Initial assembly uses the final intended memory configuration:

**128 GB = 2×64 GB DDR5 UDIMM, one DIMM per channel.**

This permanently supersedes:

- 64 GB / 2×32 GB Phase-1 memory;
- adding another 2×32 GB kit later;
- a planned 256 GB / 4×64 GB endpoint;
- any motherboard premium justified mainly by four-DIMM/256 GB behavior.

The exact 2×64 GB SKU is intentionally not selected yet. It will be optimized together with the reopened motherboard after the requested storage discussion.

Bring-up remains conservative: current stable BIOS, A2/B2, Auto/JEDEC first, no EXPO/XMP during baseline validation, extended memory testing.

## Motherboard consequence

The ASUS ProArt X870E-Creator WiFi remains the incumbent technical reference, but it is no longer final.

Its strongest differentiator in the previous analysis was explicit evidence for the difficult 4×64 GB / 256 GB / ECC-oriented use case. With the lifetime endpoint now 2×64 GB / 128 GB, the motherboard can be re-optimized for the remaining requirements: stability, firmware quality, networking, PCIe/storage topology, serviceability, future high-power GPU support and value.

No replacement board has been selected yet.

## Storage — incumbent architecture pending review

The current storage plan remains:

- Samsung 990 PRO 2 TB as permanent system/tools drive;
- separate 4 TB-or-larger work/VM/container/data SSD later;
- no RAID;
- external/network backup required.

The user has explicitly requested a storage-architecture optimization discussion **before** the next whole-build optimization pass. Therefore the current storage plan is an incumbent, not something to change silently.

## Current price envelope

The previous complete-order totals are now **obsolete** because they assumed a 64 GB RAM kit and a final motherboard selection.

Do not publish a new purchase total until:

1. the exact 2×64 GB kit is selected;
2. the motherboard re-optimization is complete;
3. the requested storage review determines whether the SSD architecture changes.

## Hard purchase gates that remain valid

### CPU
- exact Ryzen 9 9950X3D;
- Box/WOF `100-100000719WOF` preferred.

### RAM
- **128 GB total**;
- **2×64 GB matched DDR5 UDIMM kit**;
- 1DPC / A2+B2;
- no temporary 2×32 GB purchase;
- exact SKU selected only after motherboard/RAM optimization.

### Cooler
- NH-D15 G2 **standard**;
- included AM5 offset mount;
- no LBC/HBC substitution.

### PSU
For GX or conditional PX:
- ATX 3.1;
- PCIe 5.1;
- current 12V-2x6 cable;
- reject explicit old ATX 3.0 / 12VHPWR stock.

### Case
- exact `FD-C-NOR1X-01` North XL Charcoal Black Mesh.

### UPS
- exact **CyberPower PR1500ELCD**;
- 1500 VA / 1350 W;
- new/sealed;
- correctly rated IEC cabling;
- USB graceful-shutdown validation.

### Windows
- Windows 11 Pro;
- **Retail/FPP**;
- current purchase target `HAV-00163` English USB from PROstore;
- not OEM/DSP or an undocumented activation key.

## OS / firmware baseline

- Windows 11 Pro 25H2 GA;
- WSL2 + Ubuntu 26.04.1 LTS;
- NVIDIA Studio Driver WHQL baseline;
- current stable motherboard BIOS;
- UEFI, Secure Boot, TPM 2.0, SVM/IOMMU;
- RAM Auto/JEDEC during commissioning;
- CPU stock/conservative;
- BitLocker only after firmware/driver stabilization.

## Next decision sequence

1. **Discuss/review storage architecture.**
2. Re-optimize motherboard for the 128 GB 1DPC endpoint and finalized storage requirements.
3. Select the exact 2×64 GB RAM kit, including the ECC/non-ECC verdict.
4. Recalculate provider consolidation and the purchase total.

Detailed decisions: `docs/decisions.md`.
