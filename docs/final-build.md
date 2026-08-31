# Final Build

This is the current source-of-truth architecture for the workstation. Memory is finalized at **128 GB / 2×64 GB / 1DPC from day one**. Storage is finalized at the role/topology level as **~1 TB system storage + 1–2 TB CPU-direct active-work NVMe from day one, with bulk/cold storage added only when needed**. Power, networking and expansion requirements have now also been simplified to avoid speculative future-proofing.

## Current build state

| Component | Configuration | Status |
|---|---|---|
| CPU | AMD Ryzen 9 **9950X3D Box/WOF `100-100000719WOF`** | **Selected** |
| Motherboard | Broad AM5 search; prior Creator-class boards remain references only | **Reopened for optimization** |
| RAM capacity | **128 GB from day one** | **Selected / final** |
| RAM topology | **2×64 GB DDR5 UDIMM, 1DPC, A2/B2** | **Selected / final** |
| Exact RAM kit | Exact 2×64 GB matched kit | **Open for optimization** |
| ECC | Only if end-to-end support/reporting is compelling | **Open within RAM optimization** |
| CPU cooler | **Noctua NH-D15 G2 standard**, 7 mm AM5 offset | **Selected** |
| System storage | **~1 TB**, value/reliability/headroom optimized; NVMe preferred, SATA acceptable if topology/value warrants it | **Role/capacity selected; exact model open** |
| Active-work SSD | **1 TB sufficient; 2 TB if price/value is attractive**, Gen4 TLC preferred; **CPU-direct x4 required** | **Role selected; exact capacity/model open** |
| Bulk/cold storage | Add later only when needed; spare NVMe/SATA SSD/HDD/external/NAS acceptable | **Expansion policy selected** |
| Storage RAID | **No RAID** | **Selected** |
| PSU | **Premium 750 W or 850 W ATX 3.1** | **Reopened; exact model open** |
| UPS | **None in initial BOM** | **Selected** |
| Point-of-use surge protection | Reputable plug-in surge protector / protected power strip | **Selected policy** |
| Case | **Fractal North XL Mesh `FD-C-NOR1X-01`** | **Selected for now; one final value check warranted** |
| Rear fan | **Noctua NF-A14x25 G2 PWM** | **Selected under current case** |
| GPU | Existing **RTX 3060 12 GB** | **Reuse for as long as useful/reliable** |
| Host OS | **Windows 11 Pro x64** | **Selected** |
| Windows license | **Retail/FPP USB English `HAV-00163` from PROstore** | **Selected purchase target** |
| Linux environment | **WSL2 + Ubuntu 26.04.1 LTS** | **Selected** |

## Memory architecture — final

Initial assembly uses **128 GB = 2×64 GB DDR5 UDIMM, one DIMM per channel**. No temporary RAM and no planned four-DIMM/256 GB endpoint.

The exact kit remains open for the motherboard/RAM optimization. Bring-up remains conservative: current stable BIOS, A2/B2, Auto/JEDEC first, no EXPO/XMP during baseline validation, extended memory testing.

## Storage architecture — final

### Active-work SSD

The only hard M.2 requirement is:

> **one CPU-direct M.2 x4 path for the active-work SSD that does not reduce the primary GPU connection.**

1 TB is sufficient; choose 2 TB only when the incremental cost is attractive. Prefer mature Gen4 TLC with good sustained/mixed behavior and sensible endurance. Gen5 is not required.

### System drive

Target about 1 TB. NVMe is preferred when the motherboard provides an inexpensive clean second M.2 path, but **a SATA SSD is acceptable** if that allows a materially better-value motherboard without affecting the main workload.

The OS drive is not a benchmark component; prioritize mature firmware, reliability, headroom, warranty and price.

### Bulk/cold storage

Add later only when capacity is actually needed. Another NVMe, SATA SSD, SATA HDD, external storage or NAS can fill this role. Existing old HDDs may be reused after health checks for infrequently accessed data, but never as the sole copy of important data.

## Motherboard requirements — simplified

The board no longer needs to justify premiums through speculative workstation features.

Hard/strong requirements:

1. stable 9950X3D support and mature BIOS/AGESA;
2. stable **2×64 GB / 128 GB / 1DPC** operation;
3. one **CPU-direct M.2 x4** path for active work without reducing the primary GPU link;
4. competent VRM thermals for stock/conservative 9950X3D operation;
5. BIOS Flashback/recovery strongly preferred;
6. useful diagnostics/serviceability preferred;
7. normal SATA expansion useful for later bulk storage;
8. 1 GbE is sufficient; 2.5 GbE is a bonus; **5/10 GbE must not command a premium**.

Not requirements:

- CPU x8/x8 multi-GPU support;
- multiple Gen5 M.2 slots;
- a clean second M.2 path at any cost;
- 5/10 GbE;
- extreme-overclocking VRM capability;
- provisioning for a 500–600 W future GPU.

## GPU policy

Reuse the RTX 3060 for as long as it remains useful and reliable. Gaming is secondary, and cloud AI availability reduces the need to pre-buy local accelerator headroom.

If a future replacement becomes desirable, **retire the RTX 3060 rather than designing around dual-GPU operation**. Do not distort the motherboard, PSU or chassis around a hypothetical future flagship GPU.

## PSU architecture — reopened

The previous 1200 W requirement is superseded.

Current optimization target:

- **750 W premium ATX 3.1** is a fully legitimate long-term baseline;
- **850 W** is preferred only when an equally good model costs modestly more or offers materially better acoustics/platform characteristics;
- 1000–1200 W should not be purchased merely to reserve hypothetical GPU wattage.

Quality priorities:

- excellent electrical design and protections;
- ATX 3.1/current GPU transient standard;
- mature platform;
- long warranty;
- low noise and good fan implementation;
- exact current cable/revision clarity.

## UPS / mains protection

No UPS is required in the initial BOM. Short outages are acceptable operationally and there is no need to keep the workstation running through them.

For point-of-use protection, use a reputable surge-protected plug/power strip with protection-status indication. This is a practical compromise under the explicit constraint of **no electrical-installation changes**. It does not provide the same protection as coordinated building-level SPD protection and depends on a sound protective-earth connection.

## Case

The North XL remains selected for now, but the earlier case justification included a hypothetical very large/high-power future GPU. Since that future requirement has been relaxed, perform one final size/value check before treating the chassis as permanently closed.

## Current price envelope

Previous complete-order totals are obsolete. Recalculate only after motherboard, exact RAM, exact SSDs and the new 750/850 W PSU are selected and the case is either reconfirmed or changed.

## Hard purchase gates that remain valid

### CPU
- Ryzen 9 9950X3D;
- Box/WOF `100-100000719WOF` preferred.

### RAM
- 128 GB total;
- exactly 2×64 GB matched DDR5 UDIMM kit;
- 1DPC;
- no temporary kit.

### Storage
- one 1–2 TB active-work NVMe with CPU-direct x4;
- ~1 TB system storage, NVMe preferred but SATA acceptable;
- no Gen5 requirement;
- bulk storage added only when needed;
- no RAID requirement.

### PSU
- premium 750/850 W class;
- ATX 3.1/current PCIe GPU-power standard;
- strong protections, mature platform and long warranty;
- exact current revision/cabling.

### UPS
- **do not purchase one initially**.

### Windows
- Windows 11 Pro Retail/FPP;
- current target `HAV-00163` English USB from PROstore.

## Next decision sequence

1. Perform the final **case value/size check** if desired.
2. Re-optimize the **motherboard** against the simplified requirements.
3. Select exact **2×64 GB RAM**, including ECC/non-ECC verdict.
4. Select exact system + active-work storage.
5. Select exact premium **750 W / 850 W PSU**.
6. Refresh prices/providers and produce a new order total.

Detailed decisions: `docs/decisions.md`.
