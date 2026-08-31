# Cost / Value Matrix

This matrix evaluates the workstation on **utility per leu**, not benchmark performance in isolation.

The ownership target is long. Cost is justified when it buys a durable benefit in real workload performance, stability, reliability, endurance, serviceability, useful expansion or avoided future replacement. Do **not** spend merely because the planning budget permits it.

Current exact prices must be refreshed before purchase; historical snapshots are not purchase controls.

## Current decision matrix

| Decision / option | Material benefit | Cost/value interpretation | Status |
|---|---|---|---|
| **Ryzen 9 9950X3D / AM5** | Excellent heavy-development performance plus strong occasional gaming | Keeps mainstream AM5 ecosystem while avoiding Threadripper platform/TCO specialization | **Selected** |
| Threadripper/TRX50 | More cores, memory channels and PCIe | Incremental benefit does not justify platform cost/specialization for current mixed workload | **Rejected** |
| **128 GB = 2×64 GB / 1DPC from day one** | Large concurrency headroom with favorable memory topology | Avoids temporary RAM and four-DIMM compromises | **Selected / final architecture** |
| 256 GB / 4×64 GB | More capacity | Capacity not expected to be needed and distorts board/memory selection | **Superseded** |
| ECC 2×64 GB | Potential end-to-end memory error detection/correction | Worth a premium only if exact DIMMs are stable, board support is explicit and OS-visible reporting is usable | **Open / optional** |
| **Broad mainstream AM5 motherboard search** | Same CPU performance without workstation-feature premiums | Creator-class boards must now compete on actual stability/serviceability/value, not 10 GbE/x8+x8/256 GB prestige | **Reopened** |
| 5/10 GbE | Higher LAN bandwidth | No meaningful value because internet is <1 Gb/s and LAN throughput is irrelevant | **Not required** |
| CPU x8/x8 | Easier dual-GPU layout | No concrete dual-GPU requirement; RTX 3060 will be retired on future replacement | **Not required** |
| Extreme VRM/OC capability | Large overclocking current headroom | Stock/conservative 9950X3D does not benefit; competent measured VRM thermals are enough | **Not required** |
| **High-quality air cooling** | Simple long-lived cooling with replaceable fans | Correct architecture for stability/serviceability | **Selected** |
| Thermalright Phantom Spirit 120-class | Strong cooling at low cost and smaller size | Current value baseline; must prove sustained 9950X3D thermals/acoustics and acceptable support | **Candidate** |
| Noctua NH-U12A | Compact premium air cooling, strong mounting/fan ecosystem | Pay premium only if acoustics/serviceability/fit materially beat value baseline | **Candidate** |
| Noctua NH-D15 G2 | Maximum air-cooling headroom and premium ecosystem | Excellent technically, but size/cost must now earn their value; must not force case/RAM choices | **Reopened reference** |
| AIO liquid cooling | More extreme thermal headroom | Pump/liquid complexity not justified unless air cooling fails a real thermal/acoustic requirement | **Fallback only** |
| **~1 TB system storage** | Adequate permanent OS/tools headroom | Optimize reliability/capacity/price; NVMe preferred but SATA acceptable | **Role selected; model open** |
| **1 TB active-work NVMe** | Enough fast capacity for current repos/caches/WSL2/VM data | Lowest-cost valid active-work target | **Sufficient baseline** |
| **2 TB active-work NVMe** | More working-set headroom | Prefer only when incremental price/value is attractive | **Preferred when well priced** |
| 4 TB active-work NVMe | More capacity | Excess likely holds inactive data that does not need performance-tier storage | **Not an initial requirement** |
| Gen5 active-work SSD | Higher sequential bandwidth | Buy only if effectively free or demonstrated workload benefits | **Not required** |
| Later bulk/cold storage | Cheap capacity for archives/inactive data | Add only when needed; NVMe/SATA SSD/HDD/external/NAS all valid | **Selected expansion policy** |
| Reuse healthy old HDD | Near-zero-cost cold capacity | Good for infrequent data after health checks; never sole copy | **Allowed** |
| **One CPU-direct M.2 x4** | Clean active-work path | Only mandatory M.2 topology requirement | **Required** |
| Second clean M.2 | Convenient NVMe OS drive | Nice to have, but SATA system SSD is acceptable if board trade-off is meaningful | **Optional** |
| **Premium 750 W ATX 3.1 PSU** | Plenty for current machine and substantial present-day GPU upgrades | Legitimate long-term baseline; quality matters more than unused wattage | **Preferred baseline class** |
| Premium 850 W ATX 3.1 PSU | More GPU headroom | Choose when modest premium or materially better exact platform/acoustics | **Value-dependent upgrade** |
| 1000–1200 W PSU | More speculative GPU headroom | No default justification after future 500–600 W GPU assumption was removed | **Not required** |
| **No UPS** | Avoids large cost/battery maintenance | Short outages are acceptable; continuity not needed | **Selected** |
| Plug-in surge protector | Point-of-use transient protection | Proportional protection measure without electrical-installation changes | **Selected policy** |
| **Fractal North XL Mesh** | Excellent airflow/serviceability and generous room | Now potentially oversized because future huge-GPU and NH-D15 G2 constraints weakened | **Selected for now / recheck** |
| Smaller normal ATX airflow case | Lower cost/footprint while retaining actual compatibility | Strong candidate if cooler/RAM/GPU fit remains comfortable | **Reconsider with cooler** |
| **Windows 11 Pro Retail/FPP** | Correct DIY licensing path and Pro features | Avoid gray-market/OEM ambiguity | **Selected** |
| Existing **RTX 3060 12 GB** | Adequate current graphics/CUDA capability with no spend | Keep until failure or concrete replacement need | **Selected / reuse** |
| Future high-end GPU pre-provisioning | Avoids possible PSU/case replacement later | Too speculative; GPU efficiency/requirements will change and cloud AI is acceptable | **Rejected as current design driver** |

## Cooling cost/value interpretation

The governing cooling question is no longer “which cooler has the highest capacity?” It is:

> **What is the least expensive/least bulky air cooler that keeps the stock/conservative 9950X3D stable and acceptably quiet under sustained development workloads?**

The NH-D15 G2 remains an excellent reference, but its premium is valid only if it buys a useful acoustic/serviceability margin. A smaller cooler that meets the workload cleanly is preferable if it also allows a smaller case and fewer RAM-clearance constraints.

## Motherboard cost/value interpretation

The motherboard must earn its price on:

- stable 9950X3D + 2×64 GB operation;
- mature BIOS/AGESA;
- recovery/diagnostics;
- competent VRM behavior at stock load;
- one CPU-direct M.2 x4 path without compromising the GPU;
- practical SATA/additive storage;
- reliable normal Ethernet;
- serviceability and firmware support.

Do not reward 10 GbE, x8/x8, many Gen5 M.2 slots or extreme VRM specifications unless they happen to come effectively free on the otherwise best board.

## Storage cost/value interpretation

Storage spending is tiered by access pattern.

- System drive: reliability/headroom/value; SATA remains acceptable.
- Active-work drive: 1 TB sufficient, 2 TB for good-value convenience; mature Gen4 TLC preferred.
- Cold storage: add cheap capacity later rather than oversizing performance storage now.

## PSU cost/value interpretation

A premium **750 W ATX 3.1** supply is not an economy compromise. It is the baseline sized to the machine we actually expect to operate.

An 850 W unit wins only when the exact high-quality model has a small premium or other concrete benefits. Do not pay substantially for speculative future wattage; the PSU can be replaced together with a future GPU if an unusually power-hungry accelerator ever becomes necessary.

## Premium rule

When two candidates satisfy the requirements, choose the cheaper one unless the premium buys a **specific durable advantage** such as:

- better proven stability;
- materially better acoustics under real sustained workload;
- better firmware/recovery support;
- longer warranty/serviceability;
- necessary compatibility/topology;
- endurance that the workload will realistically use.

Invalid premiums include unused benchmark capability, unused Gen5 lanes, extreme overclocking features, oversized cooling/case/wattage, and speculative future-proofing.
