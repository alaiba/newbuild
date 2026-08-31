# Final Build

This is the current source-of-truth architecture for the workstation.

## Current build state

| Component | Configuration | Status |
|---|---|---|
| CPU | AMD Ryzen 9 **9950X3D Box/WOF `100-100000719WOF`** | **Selected** |
| Motherboard | Broad AM5 search; prior Creator-class boards are references only | **Reopened for optimization** |
| RAM | **128 GB = 2×64 GB DDR5 UDIMM / 1DPC / A2+B2** | **Architecture selected; exact kit open** |
| ECC | Only if exact end-to-end support/reporting is compelling | **Open within RAM optimization** |
| CPU cooler | **Thermalright Phantom Spirit 120 — standard model** | **Selected** |
| Case | **be quiet! Pure Base 501 Airflow Black `BG074`** | **Selected** |
| Case airflow | **2× included 140 mm PWM: front intake + rear exhaust** | **Selected initial layout** |
| System storage | **~1 TB**, reliability/headroom/value optimized; NVMe preferred, SATA acceptable | **Role/capacity selected; exact model open** |
| Active-work SSD | **1 TB sufficient; 2 TB if price/value is attractive**, Gen4 TLC preferred; **CPU-direct x4 required** | **Role selected; exact model open** |
| Bulk/cold storage | Add later only when needed via spare NVMe/SATA SSD/HDD/external/NAS | **Expansion policy selected** |
| Storage RAID | **No RAID** | **Selected** |
| PSU | **Premium 750 W or 850 W ATX 3.1** | **Reopened; exact model open** |
| UPS | **None initially** | **Selected** |
| Point-of-use surge protection | Reputable plug-in surge protector / protected power strip | **Selected policy** |
| GPU | Existing **RTX 3060 12 GB** | **Reuse for as long as useful/reliable** |
| Host OS | **Windows 11 Pro x64** | **Selected** |
| Windows license | **Retail/FPP USB English `HAV-00163` from PROstore** | **Selected purchase target** |
| Linux environment | **WSL2 + Ubuntu 26.04.1 LTS** | **Selected** |

## Memory architecture

Initial assembly uses **128 GB = 2×64 GB DDR5 UDIMM, one DIMM per channel**. No temporary RAM and no planned four-DIMM/256 GB endpoint.

Select the exact kit together with the motherboard. Bring-up remains conservative: current stable BIOS, A2/B2, Auto/JEDEC first, no EXPO/XMP during baseline validation, extended memory testing.

## Cooling and chassis — final

Selected combination:

- **Thermalright Phantom Spirit 120**, standard model;
- **be quiet! Pure Base 501 Airflow Black `BG074`**;
- use the case's **two included 140 mm PWM fans only at first**: one front intake and one rear exhaust.

Why this combination is now preferred:

- sufficient high-end air-cooling capability for stock/conservative 9950X3D operation;
- approximately **157 mm cooler height inside a 178 mm case limit**, leaving useful physical margin;
- **368 mm GPU clearance** is already generous for the current single-GPU policy;
- normal **ATX** motherboard support is all the build requires;
- two 3.5-inch HDD positions preserve a cheap later cold-storage path;
- substantially lower cost and physical volume than North XL + NH-D15 G2 without sacrificing a current workload requirement.

The Phantom Spirit purchase target is the **standard Phantom Spirit 120**. Do not silently substitute SE, EVO or another variant; review any substitution first.

Do **not** pre-purchase additional case fans. Add another front intake only if closed-case validation shows a material thermal/acoustic benefit.

The previous Fractal North XL, NH-D15 G2 and dedicated Noctua rear-fan selections are superseded.

## Storage architecture

The only hard M.2 requirement is:

> **one CPU-direct M.2 x4 path for the active-work SSD that does not reduce the primary GPU connection.**

Active work: 1 TB is sufficient; choose 2 TB only when incremental price/value is attractive. Prefer mature Gen4 TLC with good sustained/mixed behavior and sensible endurance.

System drive: target ~1 TB. NVMe is preferred when naturally available, but SATA SSD is acceptable if it enables a better motherboard/value choice.

Bulk/cold storage: add later through spare M.2, SATA SSD/HDD, external storage or NAS. Existing healthy HDDs may be reused for inactive data, never as the sole copy of important data.

## Motherboard requirements — simplified and now physically bounded

The selected case means the motherboard must be **ATX or smaller**.

Hard/strong requirements:

1. mature 9950X3D BIOS/AGESA support;
2. strong evidence for stable **2×64 GB / 128 GB / 1DPC**;
3. one **CPU-direct M.2 x4** path for active work without reducing the primary GPU link;
4. competent VRM thermals for stock/conservative operation;
5. BIOS Flashback/recovery strongly preferred;
6. useful diagnostics/serviceability preferred;
7. practical SATA/additive-storage support;
8. reliable Ethernet; **1 GbE is sufficient, 2.5 GbE is a bonus**.

Not requirements:

- 256 GB/four-DIMM validation;
- CPU x8/x8 multi-GPU support;
- multiple Gen5 M.2 slots;
- 5/10 GbE;
- extreme-overclocking VRM capability;
- provisioning for a hypothetical 500–600 W future GPU.

## GPU policy

Reuse the RTX 3060 for as long as it remains useful and reliable. If a future replacement becomes worthwhile, retire the 3060 rather than designing around dual-GPU operation.

Do not distort motherboard, PSU or chassis choices around an unknown future flagship GPU. If a future GPU genuinely exceeds the selected case/power envelope, revisit the replaceable component at that time.

## PSU architecture — reopened

The previous 1200 W requirement is superseded.

Current target:

- premium **750 W ATX 3.1** as a legitimate long-term baseline;
- **850 W** only when an equally good model costs modestly more or offers materially better acoustics/platform characteristics;
- no default 1000–1200 W requirement.

Prioritize electrical design/protections, mature platform, long warranty, low noise and exact current cabling/revision over nameplate wattage.

## UPS / mains protection

No UPS is required initially. Short outages are operationally acceptable.

Use a reputable point-of-use surge protector / surge-protected power strip with a protection-status indicator. No electrical-installation changes are part of this build.

## Hard purchase gates

### CPU
- Ryzen 9 9950X3D;
- Box/WOF `100-100000719WOF` preferred.

### Cooler
- **Thermalright Phantom Spirit 120 standard**;
- AM5 mounting hardware present;
- no silent SE/EVO substitution.

### Case
- **be quiet! Pure Base 501 Airflow Black `BG074`**;
- use the two included 140 mm PWM fans initially;
- no extra fan purchase until measurements justify it.

### RAM
- 128 GB total;
- exactly 2×64 GB matched DDR5 UDIMM kit;
- 1DPC;
- no temporary kit.

### Storage
- one 1–2 TB active-work NVMe with CPU-direct x4;
- ~1 TB system storage, NVMe preferred but SATA acceptable;
- no Gen5 requirement;
- no RAID requirement.

### PSU
- premium 750/850 W class;
- ATX 3.1/current PCIe GPU-power standard;
- strong protections, mature platform and long warranty.

### UPS
- **do not purchase one initially**.

### Windows
- Windows 11 Pro Retail/FPP;
- current target `HAV-00163` English USB from PROstore.

## Next decision sequence

1. Re-optimize the **motherboard** against the simplified requirements and ATX-or-smaller envelope.
2. Select exact **2×64 GB RAM**, including ECC/non-ECC verdict.
3. Select exact system + active-work storage.
4. Select exact premium **750 W / 850 W PSU**.
5. Select the exact plug-in surge protector.
6. Refresh Romanian prices/providers and produce a new order total.

Detailed decisions: `docs/decisions.md`.
