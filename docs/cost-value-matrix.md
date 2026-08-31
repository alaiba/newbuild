# Cost / Value Matrix

This matrix evaluates the workstation on **utility per leu**, not benchmark performance in isolation. Current prices must be refreshed before purchase.

## Current decision matrix

| Decision / option | Material benefit | Cost/value interpretation | Status |
|---|---|---|---|
| **Ryzen 9 9950X3D / AM5** | Excellent heavy-development performance plus strong occasional gaming | Avoids Threadripper platform/TCO specialization | **Selected** |
| Threadripper/TRX50 | More cores/channels/PCIe | Incremental benefit does not justify platform cost/specialization | **Rejected** |
| **ASUS TUF B650E-E WIFI `90MB1LT0-M0EAY0`** | PCIe 5.0 x16, two CPU M.2 paths, third Gen4 x4 M.2, FlashBack/Q-LED, SATA, 2.5 GbE, sufficient VRM | Meets actual requirements at roughly ~0.84k-leu pricing; lowest-cost finalist without a workload compromise | **Selected** |
| MSI B850 GAMING PLUS WIFI `7E56-001R` | Adds real secondary PCIe 4.0 x4, 5 GbE and Wi-Fi 7 | Strong fallback at ~0.90k class, but premium buys currently unused expansion/networking | **Fallback** |
| ASUS TUF B850-PLUS WIFI `90MB1J30-M0EAY0` | Stronger VRM, richer rear I/O, Wi-Fi 7, secondary x4 | Nicer absolute board, but ~1.02–1.07k class premium no longer justified after ECC ceased to be a requirement | **Superseded** |
| ProArt / Creator-class board | 10 GbE, richer PCIe/M.2, workstation positioning | Old value case depended on 256 GB, x8/x8, 10 GbE and speculative expansion that are no longer required | **Superseded** |
| **Crucial `CT2K64G56C46U5`, 128 GB 2×64** | Final lifetime capacity in 1DPC, native DDR5-5600 at 1.1 V | Conservative JEDEC operation is more useful than enthusiast timings/profiles | **Selected** |
| 256 GB / 4×64 GB | More capacity | Capacity not expected to be needed; harder 2DPC topology | **Superseded** |
| ECC 2×64 GB | End-to-end correction/detection potential | Platform supports it, but practical 64 GB ECC UDIMM supply is poor; do not distort capacity/topology | **Rejected for current build** |
| 64 GB ECC RDIMM | Server memory density | Incompatible with AM5 | **Rejected / incompatible** |
| High-voltage EXPO 128 GB kit | Tighter timings/headline performance | No material workload benefit versus native 5600/1.1 V JEDEC; often significantly more expensive | **Rejected on value/stability** |
| 5/10 GbE | Higher LAN bandwidth | No meaningful value for this network | **Not required** |
| CPU x8/x8 | Easier dual-GPU layout | No concrete dual-GPU requirement | **Not required** |
| Secondary PCIe x4 expansion | High-bandwidth NIC/HBA/capture-card path | No concrete use; selected board intentionally accepts x1-only secondary expansion | **Not required** |
| Extreme VRM/OC capability | Very high current headroom | Stock/conservative 9950X3D does not benefit | **Not required** |
| **Thermalright Phantom Spirit 120 standard** | Strong sustained air cooling at low cost/size | Meets actual CPU cooling objective without Noctua/oversized premiums | **Selected** |
| Noctua NH-U12A | Premium fans/mount/support | Real advantages, but not worth current premium for this workload | **Rejected on value** |
| Noctua NH-D15 G2 | Maximum air-cooling headroom | Extra capacity/size/cost no longer justified | **Superseded** |
| **be quiet! Pure Base 501 Airflow `BG074`** | ATX, useful cooler/GPU clearance, included 140 mm fans, HDD path | Provides required physical envelope at much lower size/cost than North XL | **Selected** |
| Fractal North XL Mesh | More E-ATX/GPU/cooler volume | Headroom was driven by hypothetical future hardware | **Superseded** |
| Extra premium case fan | Additional airflow | Measure first; included front/rear 140 mm fans are adequate starting point | **Not initially required** |
| **Crucial T710 2 TB `CT2000T710SSD8`** | One fast primary SSD for all active data; PCIe 5.0 x4, TLC, DRAM | Current ~600 GB use fits comfortably; 2 TB gives ample growth headroom and current Gen5 premium over premium Gen4 is small enough to justify it | **Selected** |
| Separate ~1 TB system SSD | Physical OS/work separation | Adds device cost and management without solving a current performance/capacity problem | **Rejected** |
| Separate active-work SSD | Workload isolation | Unnecessary while the whole active working set fits on one 2 TB flagship SSD | **Rejected** |
| Dedicated SSD cache device | Potential hot-block acceleration | SSD-to-SSD caching adds complexity, duplicated writes and failure semantics while accelerating an already-fast NVMe | **Rejected initially** |
| Automatic SSD tiering / Storage Spaces | Single namespace with hot/cold movement | Solves a capacity hierarchy problem that the current ~600 GB working set does not have | **Rejected initially** |
| 4 TB T710 / flagship Gen5 | Double capacity | Roughly ~1.3k lei extra for capacity not expected to be used soon; expansion remains easy later | **Rejected initially on value** |
| Existing SATA drives for cold storage | Cheap archive capacity already owned | Appropriate for old projects, media, installers and inactive data after health validation | **Selected / reuse** |
| Later NVMe expansion | Additional fast capacity | `M.2_2` and `M.2_3` remain free; buy only when actual use justifies it | **Deferred / additive** |
| **be quiet! Pure Power 13 M 850W `BP027EU`** | Premium ATX 3.1 platform, excellent acoustics, 10-year warranty and useful GPU headroom | Observed premium over 750 W sibling is only ~40–100 lei, so the extra 100 W is a rational low-cost margin rather than speculative overprovisioning | **Selected** |
| Pure Power 13 M 750 W | Fully sufficient for current system | No longer the target because savings are too small versus selected 850 W unit | **Rejected on current value** |
| Corsair RM850x 2024 `CP-9020270-EU` | Excellent ATX 3.1 quality/protection/fan implementation | Worth switching only if delivered price is within ~30–40 lei or warranty/retailer is materially better | **Fallback** |
| 1000–1200 W PSU | Speculative GPU margin | No default justification; replace PSU later only if a concrete future GPU requires it | **Not required** |
| **No UPS** | Avoids cost/battery maintenance | Short outages are acceptable; continuity not needed | **Selected** |
| Plug-in surge protector | Point-of-use transient protection | Proportional no-installation solution | **Selected policy** |
| Existing RTX 3060 12 GB | Current graphics/CUDA capability with no spend | Keep until failure or concrete upgrade need | **Selected / reuse** |
| Future flagship GPU pre-provisioning | Avoids possible future PSU/case change | Too speculative; efficiency/needs can change and cloud AI is acceptable | **Rejected as design driver** |
| Windows 11 Pro Retail/FPP | Correct DIY licensing path and Pro features | Avoid gray-market/OEM ambiguity | **Selected** |

## Motherboard interpretation

The B650E-E result pushes the value logic one step further: **B850 itself is not a requirement**.

At roughly ~839–844 lei, the ASUS already provides the durable capabilities the build uses: PCIe 5.0 graphics, two CPU-connected M.2 slots, a full Gen4 x4 third M.2, recovery/diagnostics, SATA, 2.5 GbE and sufficient stock-load power delivery.

The MSI B850 GAMING PLUS remains a rational fallback because a ~60 lei premium can buy 5 GbE and a real secondary x4 slot. But those features still need a concrete use before they become worth paying for. The TUF B850-PLUS premium is larger and even less compelling for the present requirements.

## Memory interpretation

The RAM purchase is unusual because the **capacity is valuable but the current market price is poor**.

128 GB remains the final requirement because it directly supports concurrent IDE/JVM/WSL2/container/VM workloads. The correct response to current pricing is to refresh suppliers carefully, not to buy a technically inferior topology or a high-voltage enthusiast kit.

The Crucial kit is selected because native DDR5-5600 / 1.1 V JEDEC operation aligns better with stability than paying more for EXPO timings.

ECC loses on practical module availability at 64 GB density, not because ECC itself lacks value.

## Storage interpretation

Storage is now deliberately simple:

- `M.2_1`: **Crucial T710 2 TB primary SSD**;
- `M.2_2`: empty for later expansion;
- `M.2_3`: empty for later expansion;
- SATA: reuse healthy existing drives for cold/bulk data.

The current machine uses approximately **600 GB**, so 2 TB already provides substantial headroom. A separate system/work split and SSD caching were investigated but rejected because they add complexity without a demonstrated performance or capacity problem.

Gen4 remains technically sufficient, but at current pricing the selected T710's Gen5 premium is small enough to be a reasonable durable upgrade. Conversely, moving immediately to 4 TB is not justified: capacity can be added later without replacing the selected drive.

## PSU interpretation

A premium **750 W ATX 3.1** unit would already be sufficient. The decision moved to the **Pure Power 13 M 850 W** because the observed 750-to-850 W price step is only roughly 40–100 lei while the selected exact unit also has excellent acoustics, measured platform quality and a long warranty.

That is the correct use of the project's premium rule: a small premium buys a concrete durable margin. It does **not** justify returning to 1000–1200 W sizing for an unknown future GPU.

## Premium rule

When two candidates satisfy the requirements, choose the cheaper one unless the premium buys a **specific durable advantage**: better proven stability, materially better acoustics, better recovery/support, longer serviceability, necessary compatibility/topology or endurance the workload will actually use.

Invalid premiums include unused benchmark capability, unused storage capacity, unused high-bandwidth expansion/networking, extreme OC features, oversized cooling/case/wattage and speculative future-proofing.
