# Cost / Value Matrix

This matrix evaluates the workstation on **utility per leu**, not benchmark performance in isolation.

The ownership target is long. Cost is justified when it buys a durable benefit in real workload performance, stability, reliability, endurance, serviceability, useful expansion or avoided future replacement. Do **not** spend merely because the planning budget permits it.

Current exact prices must be refreshed before purchase; historical snapshots are not purchase controls.

## Evaluation dimensions

For every component or premium, ask:

- **Workload benefit:** does it materially improve Java/Gradle/Maven builds, IDE/Android work, containers, WSL2, VMs, databases, gaming or the future single-GPU AI path?
- **Stability/reliability:** does it materially reduce operational risk or improve conservative operation?
- **Endurance/serviceability:** is it likely to last longer or be easier to maintain/replace?
- **Topology/expansion:** does it preserve useful GPU, M.2, networking or I/O capability?
- **Avoided replacement:** does spending more now credibly prevent buying the component again later?
- **10-year value:** will the benefit still matter several years from now?

A higher price is acceptable only when one or more of those benefits are concrete.

## Current decision matrix

| Decision / option | Material benefit | Cost/value interpretation | Status |
|---|---|---|---|
| **Ryzen 9 9950X3D / AM5** | Excellent heavy-development performance plus strong occasional gaming | Keeps mainstream AM5 ecosystem while avoiding Threadripper platform/TCO specialization | **Selected** |
| Threadripper/TRX50 | More cores, memory channels and PCIe | Incremental benefit does not justify platform cost/specialization for current mixed workload | **Rejected** |
| **128 GB = 2×64 GB / 1DPC from day one** | Large concurrency headroom with electrically favorable one-DIMM-per-channel topology | Avoids temporary RAM purchase and four-DIMM training/frequency compromises | **Selected / final architecture** |
| 64 GB temporary RAM | Lower initial spend | No longer useful because 128 GB is affordable enough to buy once and is the lifetime target | **Superseded** |
| 256 GB / 4×64 GB target | More capacity | Capacity not expected to be needed; creates substantially harder 2DPC topology and distorted motherboard selection | **Superseded** |
| ECC 2×64 GB | Potential end-to-end memory error detection/correction | Worth a premium only if exact DIMMs are stable, board support is explicit and OS-visible reporting is usable | **Open / optional** |
| **ASUS ProArt X870E-Creator WiFi** | Strong firmware/recovery/networking/workstation feature set | Previous premium was heavily justified by 4×64/256 GB evidence; that requirement is gone, so it must compete again on remaining features/value | **Incumbent / reopened** |
| **ASRock X870 Taichi Creator** | Strong networking, diagnostics and workstation I/O at lower historical price | Becomes more attractive now that 4×64 GB evidence is no longer the key gate | **Live challenger** |
| Lower-cost B850/X870 boards | Potentially substantial savings with same CPU performance | Now eligible if they meet 2×64 stability, two-drive M.2 topology, networking/serviceability and future-GPU requirements | **Reconsider during motherboard pass** |
| **Noctua NH-D15 G2 standard** | Long-lived air-cooling platform, replaceable fans, support ecosystem | Cheaper coolers can cool the CPU, but Noctua's serviceability/endurance premium remains relevant over long ownership | **Selected** |
| Cheaper high-end air cooler | Lower purchase price | Reopen only if saving becomes large enough to outweigh support/fan/endurance advantages | **Value reference** |
| **Two internal NVMe drives from day one** | Immediate OS/recovery and workload separation | Permanent architecture; avoids oversizing C: for a temporary one-drive phase | **Selected / final architecture** |
| **~1 TB system/tools NVMe** | Adequate permanent C: headroom | Optimize reliability/capacity/price. Flagship throughput, DRAM and Gen5 are not requirements. | **Role/capacity selected; exact model open** |
| **4 TB work/data NVMe** | Capacity plus isolated I/O for repos, caches, WSL2, containers, Android, VMs and DBs | Put storage-performance/endurance budget here; TLC and mature sustained behavior matter more than C: benchmark speed | **Role/capacity selected; exact model open** |
| High-end Gen4 TLC work SSD | Strong real-world NVMe performance with mature thermals/firmware | Expected storage sweet spot | **Preferred class** |
| Premium Gen5 work SSD | Much higher sequential benchmark bandwidth | Buy only if premium is negligible or a demonstrated workload benefits; otherwise money is better spent elsewhere | **Not required** |
| Samsung 990 PRO 2 TB as system drive | Excellent mature flagship Gen4 drive | Technically strong but no longer automatically worth buying for C:; must compete on price like any other candidate | **Prior selection superseded** |
| RAID1 internal storage | One-drive hardware-failure tolerance | Does not protect against deletion, replicated corruption, malware, theft or machine loss; adds complexity | **Not required** |
| **1200 W ATX 3.1 PSU architecture** | Future single ~600 W GPU margin and current transient standard | Useful durable headroom without unnecessary 1600 W oversizing | **Selected** |
| **Seasonic VERTEX GX-1200** | Mature high-quality platform, long warranty | Purchase-ready baseline | **Selected baseline** |
| **VERTEX PX-1200 at ≤~200 lei premium** | Better efficiency over long ownership | Small premium can repay partly in energy and represents a higher-tier implementation; do not chase it if unavailable | **Conditional preference** |
| 1300–1600 W PSU | Extra unused power ceiling | No current workload or future single-GPU requirement justifies the additional size/cost | **Rejected** |
| **Fractal North XL Mesh** | Airflow, serviceability and very large future-GPU envelope | Larger than strictly necessary today, but expansion/maintenance benefit is durable | **Selected** |
| **3×140 front + 1×140 rear** | Simple positive-pressure airflow | Avoid buying extra fans until measurements show a need | **Selected** |
| **CyberPower PR1500ELCD 1350 W** | Preserves UPS usefulness through future high-power GPU, battery serviceability | Premium is justified because it credibly avoids replacing a too-small 1000 W UPS later | **Selected** |
| **Windows 11 Pro Retail/FPP** | Correct DIY licensing path, Pro host features | Avoid gray-market/OEM ambiguity; retailer choice can be price/provenance driven because RMA burden is negligible | **Selected** |
| Existing **RTX 3060 12 GB** | Adequate current GPU, no new spend | Reuse until future high-VRAM GPU requirement becomes concrete | **Selected / reuse** |
| Future single high-VRAM GPU | AI capability upgrade | Preserve PSU/case/PCIe path now; buy the GPU only when the workload exists | **Deferred** |
| Serious multi-GPU AI design on AM5 | More accelerator capacity | Would distort motherboard/PSU/case topology; reopen platform instead if this requirement appears | **Not a current requirement** |

## Memory cost/value interpretation

The governing choice is now simple:

**buy 128 GB once as 2×64 GB.**

This is preferable to buying 2×32 GB and later either filling all four slots or discarding the first kit. It keeps AM5 in the favorable 1DPC topology for the lifetime target.

The exact kit should be optimized for stability and value rather than headline frequency. ECC is evaluated independently: it wins only if the complete ECC path is credible and the premium is reasonable.

## Motherboard cost/value interpretation

The motherboard must now earn its price on the requirements that remain:

- stable 9950X3D + 2×64 GB operation;
- mature BIOS/AGESA;
- recovery/diagnostics;
- good VRM and long-duration behavior;
- two clean M.2 x4 paths while preserving GPU x16;
- networking and useful I/O;
- serviceability and firmware support;
- future single high-power GPU compatibility.

The previous requirement for especially strong **4×64 GB / 256 GB** evidence is gone. Therefore the ProArt premium is no longer protected by that argument, and lower-cost boards must be reconsidered seriously.

Gen5 M.2 count should not drive the board choice. One CPU-direct x4 path for the work SSD plus a chipset x4 path for C: is sufficient.

## Storage cost/value interpretation

Storage spending is deliberately asymmetric.

### System SSD

The OS drive is primarily a **reliability/capacity component**, not a performance component.

The user's existing decade-old 240 GB SATA SSD already provides acceptable boot responsiveness; its real problem is being nearly full. With 128 GB RAM and a dedicated work SSD, paying for flagship sequential C: performance would produce little practical value.

Target roughly 1 TB, but choose capacity by price curve: if 1 TB costs only slightly more than 500 GB, buy 1 TB. Do not automatically pay for a flagship controller, DRAM or Gen5.

### Work SSD

The 4 TB drive is where performance/endurance spending can matter because it carries repositories, build caches, WSL2/container storage, VMs, databases, Android data and other large/high-I/O working sets.

Prefer mature Gen4 TLC. Pay more for materially better sustained behavior, endurance, firmware/warranty or a meaningfully lower price/TB—not for synthetic sequential numbers alone.

### Expansion

Unlike RAM, storage remains additive. Extra M.2 capacity can be added later without replacing the initial system/work drives. Therefore there is no need to oversize either initial drive solely to predict ten years of capacity growth.

## Premium rule

When two candidates both satisfy the requirements, choose the cheaper one unless the premium buys a **specific durable advantage**.

Valid premium examples:

- better proven memory stability;
- materially better firmware/recovery support;
- longer useful warranty/serviceability;
- avoiding a future component replacement;
- substantially better endurance for a workload that will use it;
- necessary I/O/topology that cannot be added cleanly later.

Invalid premium examples:

- higher benchmark numbers with no workload effect;
- unused Gen5 lanes;
- extreme overclocking features;
- decorative features;
- capacity or wattage margin with no credible use case;
- spending simply because the total remains below 30,000 lei.
