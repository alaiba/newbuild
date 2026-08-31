# Cost / Value Matrix

This matrix evaluates the workstation on **utility per leu**, not benchmark performance in isolation. Current prices must be refreshed before purchase.

## Current decision matrix

| Decision / option | Material benefit | Cost/value interpretation | Status |
|---|---|---|---|
| **Ryzen 9 9950X3D / AM5** | Excellent heavy-development performance plus strong occasional gaming | Avoids Threadripper platform/TCO specialization | **Selected** |
| Threadripper/TRX50 | More cores/channels/PCIe | Incremental benefit does not justify platform cost/specialization | **Rejected** |
| **ASUS TUF B650E-E WIFI `90MB1LT0-M0EAY0`** | PCIe 5.0 x16, two CPU M.2 paths, third Gen4 x4 M.2, FlashBack/Q-LED, SATA, 2.5 GbE, sufficient VRM | Meets actual requirements without B850/Creator premiums | **Selected** |
| MSI B850 GAMING PLUS WIFI `7E56-001R` | Adds real secondary PCIe x4, faster networking and newer wireless | Strong fallback, but premium buys currently unused capabilities | **Fallback** |
| ASUS TUF B850-PLUS WIFI `90MB1J30-M0EAY0` | Stronger VRM, richer rear I/O, newer wireless, secondary x4 | Nicer absolute board, but premium no longer justified | **Superseded** |
| ProArt / Creator-class board | Richer PCIe/networking/workstation positioning | Old value case depended on capacity/expansion requirements that are no longer present | **Superseded** |
| **Crucial Pro `CP2K24G56C46U5`, 48 GB 2×24** | Preserves two-DIMM / 1DPC DDR5-5600 operation at much lower current cost | Best current utility per leu; capacity is treated as concurrency headroom, not an intrinsic CPU-speed lever | **Selected** |
| 32 GB / 2×16 | Lower nominal cost | Too close to the current machine's constraint and currently poor value versus 48 GB | **Rejected** |
| 64 GB / 2×32 | More concurrency headroom | Technically strong, but current premium over 48 GB is too large for only 16 GB additional capacity | **Rejected at current price** |
| 96 GB / 2×48 | Much more capacity | Currently priced too close to 128 GB | **Rejected on value** |
| 128 GB / 2×64 | Maximum concurrency/headroom | Technically ideal but current price is disproportionate; does not materially improve CPU throughput when 48 GB already fits the workload | **Rejected at current price** |
| Four-DIMM RAM expansion | Preserves old pair while adding capacity | Moves away from preferred 1DPC topology and complicates memory stability/speed | **Rejected as upgrade strategy** |
| ECC RAM | Error correction | Not required for this build; do not distort topology/capacity or use incompatible RDIMM | **Not required** |
| 5/10 GbE | Higher LAN bandwidth | No meaningful value for this network | **Not required** |
| CPU x8/x8 | Easier dual-GPU layout | No concrete dual-GPU requirement | **Not required** |
| Secondary PCIe x4 expansion | High-bandwidth NIC/HBA/capture-card path | No concrete use; selected board intentionally accepts x1-only secondary expansion | **Not required** |
| Extreme VRM/OC capability | Very high current headroom | Stock/conservative 9950X3D does not benefit | **Not required** |
| **Thermalright Phantom Spirit 120 standard** | Strong sustained air cooling at low cost/size | Meets CPU cooling objective without Noctua/oversized premiums | **Selected** |
| Noctua NH-D15 G2 | Maximum air-cooling headroom | Extra capacity/size/cost no longer justified | **Superseded** |
| **be quiet! Pure Base 501 Airflow `BG074`** | ATX, useful cooler/GPU clearance, included 140 mm fans, HDD path | Provides required physical envelope at much lower size/cost than North XL | **Selected** |
| Fractal North XL Mesh | More chassis volume | Headroom was driven by hypothetical future hardware | **Superseded** |
| Extra premium case fan | Additional airflow | Measure first; included front/rear 140 mm fans are adequate starting point | **Not initially required** |
| **Crucial T710 2 TB `CT2000T710SSD8`** | One fast primary SSD for all active data; PCIe 5.0 x4, TLC, DRAM | Current ~600 GB use fits comfortably; 2 TB gives ample headroom and avoids unnecessary complexity | **Selected** |
| Separate system/work SSDs | Physical separation | Adds device cost and management without solving a current performance/capacity problem | **Rejected** |
| Dedicated SSD cache/tiering | Potential hot-block acceleration | Adds complexity and duplicated writes while accelerating an already-fast NVMe | **Rejected initially** |
| 4 TB initial primary SSD | Double capacity | Extra capacity not expected to be used soon; additive expansion remains easy | **Rejected initially on value** |
| Existing SATA drives for cold storage | Cheap archive capacity already owned | Appropriate after health validation | **Selected / reuse** |
| **be quiet! Pure Power 13 M 850W `BP027EU`** | Premium ATX 3.1 platform, acoustics, long warranty and useful GPU headroom | Small premium over 750 W makes the extra margin rational without speculative 1000–1200 W sizing | **Selected** |
| Corsair RM850x 2024 `CP-9020270-EU` | Excellent quality/protection/fan implementation | Worth switching only if delivered price/warranty is materially better | **Fallback** |
| 1000–1200 W PSU | Speculative GPU margin | No default justification | **Not required** |
| **No UPS** | Avoids cost/battery maintenance | Short outages are acceptable; continuity not needed | **Selected** |
| Dedicated plug-in surge protector | Adds another transient-protection layer | Incremental benefit does not justify a dedicated purchase for this use case | **Not required** |
| Existing RTX 3060 12 GB | Current graphics/CUDA capability with no spend | Keep until failure or concrete upgrade need | **Selected / reuse** |
| Windows 11 Pro Retail/FPP | Correct DIY licensing path and Pro features | Avoid gray-market/OEM ambiguity | **Selected** |

## Memory interpretation

The final RAM choice is deliberately **48 GB / 2×24 GB**, not because 64 or 128 GB lack technical value, but because current prices make their additional headroom poor value.

The important performance distinction is threshold-based:

- while the active working set fits, larger two-DIMM capacities should not materially accelerate CPU/build throughput;
- when memory pressure appears, paging/reclamation can cause large performance and responsiveness losses;
- therefore the correct future trigger is **measured memory pressure**, not a speculative capacity target.

If 48 GB later proves insufficient, replace the pair with a larger matched two-DIMM kit. Do not add another pair merely because two DIMM slots remain unused.

## Storage interpretation

Storage is deliberately simple:

- `M.2_1`: Crucial T710 2 TB primary SSD;
- `M.2_2`: empty for later expansion;
- `M.2_3`: empty for later expansion;
- SATA: reuse healthy existing drives for cold/bulk data.

The current machine uses approximately 600 GB, so 2 TB already provides substantial headroom. A separate system/work split and SSD caching were investigated but rejected because they add complexity without a demonstrated performance or capacity problem.

## PSU interpretation

A premium 750 W ATX 3.1 unit would already be sufficient. The Pure Power 13 M 850 W won because the price step was small while platform quality, acoustics and warranty remain strong.

That is the correct use of the project's premium rule: a small premium buys a concrete durable margin. It does not justify returning to 1000–1200 W sizing for an unknown future GPU.

## Premium rule

When two candidates satisfy the requirements, choose the cheaper one unless the premium buys a **specific durable advantage**: better proven stability, materially better acoustics, better recovery/support, longer serviceability, necessary compatibility/topology or endurance the workload will actually use.

Invalid premiums include unused benchmark capability, unused storage capacity, unused high-bandwidth expansion/networking, extreme OC features, oversized cooling/case/wattage, unvalued mains-protection premiums and speculative future-proofing.
