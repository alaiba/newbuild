# Decision Log

This file records closed decisions plus any decision explicitly reopened because a requirement changed.

## Current decisions

| Area | Decision | Status | Rationale / reopen condition |
|---|---|---|---|
| CPU / platform | **AMD Ryzen 9 9950X3D on AM5** | **Selected** | Fits the very heavy Java/Android workload while retaining excellent occasional gaming performance without workstation-platform TCO/specialization. |
| Motherboard | **Exact motherboard reopened; prior Creator-class shortlist is no longer privileged** | **Reopened** | Re-optimize from a broad AM5 set against the simplified requirements. |
| Final memory capacity | **128 GB from day one** | **Selected / final** | Buy the intended lifetime capacity at initial assembly. |
| Final memory topology | **2×64 GB DDR5 UDIMM, one DIMM per channel (1DPC), normally A2/B2** | **Selected / final** | Preserves the electrically favorable 1DPC topology. |
| Exact memory kit | **2×64 GB exact SKU to be selected with the motherboard** | **Open** | Stability first: conservative JEDEC behavior, board validation/QVL evidence, sane voltage, module construction and warranty. |
| ECC policy | **Optional** | **Open within RAM optimization** | Prefer ECC UDIMM only if exact-module board support and usable OS-level reporting are credible without materially worsening value or stability. |
| Cooling architecture | **High-quality air cooling, stock/conservative CPU operation** | **Selected** | Avoid pump/liquid complexity unless a real measured thermal requirement appears. |
| Exact CPU cooler | **Thermalright Phantom Spirit 120 — standard model** | **Selected** | Strong sustained air-cooling capability at much lower cost/size than NH-D15 G2-class alternatives. Do not silently substitute PS120 SE/EVO or another variant without review. |
| Chassis | **be quiet! Pure Base 501 Airflow Black `BG074`** | **Selected** | Normal ATX mid-tower with 178 mm CPU-cooler and 368 mm GPU clearance, two included 140 mm PWM fans and sufficient HDD/storage support. Removes North XL size/cost that was justified mainly by speculative future hardware. |
| Initial case airflow | **Use the two included 140 mm PWM fans: one front intake + one rear exhaust** | **Selected** | Start simple; add a second front intake only if measured CPU/GPU/VRM/SSD temperatures justify it. |
| Storage architecture | **~1 TB system drive + 1–2 TB CPU-direct active-work NVMe; add bulk/cold storage only when needed** | **Selected / final architecture** | Separate OS/tools from latency-sensitive work without buying high-performance capacity for inactive data. |
| System drive role | **~1 TB value/reliability-focused storage; NVMe preferred but SATA acceptable if motherboard trade-offs justify it** | **Selected role / model open** | A second M.2 slot is desirable, not mandatory. |
| Active-work SSD role | **1 TB sufficient; 2 TB preferred only when price/value is attractive; CPU-direct x4 mandatory; Gen4 TLC preferred** | **Selected role / purchase-size open** | Current repos, caches, WSL2/container data, active VMs/databases and other latency-sensitive data belong here. |
| Bulk/cold storage | **Add only when needed; speed secondary** | **Selected expansion policy** | Spare M.2, SATA SSD/HDD, external/NAS are acceptable. Healthy old HDDs may be reused for infrequent data but never as the only copy of important data. |
| Storage RAID policy | **No RAID required** | **Selected** | Version control and real independent backup solve more relevant failure modes. |
| Required M.2 topology | **One CPU-direct M.2 x4 slot that does not reduce the primary GPU link** | **Selected / mandatory** | This is the only hard M.2 requirement. |
| Wired networking | **1 GbE is sufficient; 2.5 GbE is a harmless bonus; do not pay for 5/10 GbE** | **Selected** | Internet is below 1 Gb/s and LAN throughput is irrelevant. |
| Multi-GPU | **Not a requirement; retire the RTX 3060 when a future GPU replacement happens** | **Selected** | CPU x8/x8 support is a bonus only if effectively free. |
| GPU | **Reuse RTX 3060 12 GB for as long as it remains useful/reliable** | **Selected** | Gaming is secondary and cloud AI reduces the need to pre-buy local accelerator capability. |
| Future GPU policy | **Do not pre-provision the platform/power system for a hypothetical 500–600 W flagship GPU** | **Selected** | Reconsider PSU/case only if a concrete future GPU actually requires it. |
| PSU architecture | **Reopened around premium 750 W and 850 W ATX 3.1 units** | **Reopened** | 750 W is a legitimate long-term target; 850 W is a value-dependent headroom upgrade. Quality outranks wattage. |
| PSU sizing rule | **Prefer 750 W unless an equally high-quality 850 W model costs only modestly more or has materially better characteristics** | **Selected optimization rule** | Do not pay meaningful money merely to reserve speculative GPU wattage. |
| PSU feature baseline | **ATX 3.1 / current PCIe GPU-power standard, strong protections, mature platform, long warranty** | **Selected** | Keep modern transient handling and quality requirements while reducing unnecessary capacity. |
| UPS | **No UPS in the initial BOM** | **Selected** | Short outages are acceptable operationally; continuity is unnecessary. |
| Point-of-use power protection | **Use a reputable plug-in surge protector / surge-protected power strip** | **Selected policy** | Objective is transient/surge risk reduction without electrical-installation modification. |
| Motherboard VRM / OC | **Stock/conservative 9950X3D operation only; extreme VRM/overclocking capability has no value** | **Selected** | Require competent VRM thermals/reliability, not phase-count marketing. |
| Host OS | **Windows 11 Pro x64** | **Selected** | Best fit for development, virtualization, NVIDIA/gaming and professional host features. |
| Windows license channel | **Retail/FPP** | **Selected / required purchase** | Clean DIY licensing path; no existing transferable license. |
| Windows purchase target | **`HAV-00163` English Retail/FPP USB from PROstore** | **Selected purchase target** | Verified Retail/FPP provenance and low delivered cost. |
| Initial Windows release | **Windows 11 25H2 GA** | **Selected** | Production baseline. |
| Linux environment | **WSL2 + Ubuntu 26.04.1 LTS** | **Selected** | First-class Linux userland without dual-boot friction. |
| GPU driver | **NVIDIA Studio Driver WHQL baseline** | **Selected** | Stability-first. |
| Security/virtualization | **UEFI + Secure Boot + TPM 2.0 + SVM/IOMMU + BitLocker after firmware stabilization** | **Selected** | Conservative production baseline. |
| Cost philosophy | **Optimize utility per leu; do not spend for prestige, unused capacity or speculative future-proofing** | **Selected** | Premiums must buy a material workload, stability, endurance, serviceability or lifecycle benefit. |
| Provider consolidation | **Maximum 3 providers; default target 2 for hardware** | **Selected** | Extra supplier fragmentation needs meaningful value. |

## Explicitly superseded decisions

### Memory
- 64 GB / 2×32 GB Phase-1 memory;
- Crucial `CT2K32G56C46U5` as a purchase target;
- 256 GB / 4×64 GB as the planned endpoint;
- motherboard premiums justified primarily by four-DIMM / 256 GB behavior.

### Cooling / chassis
- Noctua NH-D15 G2 as the selected exact cooler;
- Fractal North XL Mesh `FD-C-NOR1X-01` as the selected chassis;
- dedicated Noctua NF-A14x25 G2 rear-fan purchase;
- choosing a larger chassis or constraining RAM merely to preserve oversized cooler/future-GPU clearance.

### Storage
- Samsung 990 PRO 2 TB `MZ-V9P2T0BW` as a selected system-drive purchase;
- a fixed 4 TB high-performance work SSD;
- Gen5 as a storage requirement;
- two clean M.2 slots as a hard motherboard requirement.

### Expansion / networking
- onboard 5/10 GbE as a meaningful motherboard-selection benefit;
- CPU-connected x8/x8 as a design requirement;
- keeping the RTX 3060 alongside a future flagship GPU.

### Power
- 1200 W as the selected PSU architecture;
- Seasonic VERTEX GX/PX-1200 as purchase-ready targets;
- pre-sizing for a future 500–600 W GPU;
- CyberPower PR1500ELCD as a selected purchase.

## Open / deferred decisions

- exact motherboard under the simplified requirements and **ATX-or-smaller case envelope**;
- exact matched 2×64 GB RAM kit and ECC/non-ECC verdict;
- exact ~1 TB system drive and whether NVMe or SATA is the better value in the final topology;
- exact 1 TB or 2 TB active-work NVMe;
- exact premium 750 W or 850 W PSU;
- optional future bulk/cold storage when capacity actually requires it;
- future GPU replacement only when a concrete need/failure appears.

Detailed component dossiers are under `docs/components/`.

Current purchase execution plan: `docs/procurement-plan-2026-08-31.md`.
