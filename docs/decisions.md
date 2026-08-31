# Decision Log

This file records closed decisions plus any decision explicitly reopened because a requirement changed.

## Current decisions

| Area | Decision | Status | Rationale / reopen condition |
|---|---|---|---|
| CPU / platform | **AMD Ryzen 9 9950X3D on AM5** | **Selected** | Keep the permanent CPU/platform. It fits the very heavy Java/Android workload while retaining excellent occasional gaming performance without workstation-platform TCO/specialization. |
| Motherboard | **Exact motherboard reopened; prior Creator-class shortlist is no longer privileged** | **Reopened** | The old ProArt/Creator rationale depended heavily on 256 GB/four-DIMM validation, 10 GbE, x8/x8 and expansive M.2/future-GPU requirements. Those requirements have been removed or downgraded. Re-optimize from a broader mainstream AM5 candidate set. |
| Final memory capacity | **128 GB from day one** | **Selected / final** | Buy the intended lifetime capacity at initial assembly. |
| Final memory topology | **2×64 GB DDR5 UDIMM, one DIMM per channel (1DPC), normally A2/B2** | **Selected / final** | Preserves the electrically favorable 1DPC topology and avoids four-DIMM training/frequency compromises. |
| Exact memory kit | **2×64 GB exact SKU to be selected with the motherboard** | **Open** | Optimize for stability first: conservative JEDEC behavior, board validation/QVL evidence, sane voltage, module construction and warranty. |
| ECC policy | **Optional** | **Open within RAM optimization** | Prefer ECC UDIMM only if exact-module board support and usable OS-level error reporting are credible without materially worsening value or stability. |
| Cooling architecture | **High-quality air cooling, stock/conservative CPU operation** | **Selected** | Avoid pump/liquid complexity unless a real measured thermal requirement appears. |
| Exact CPU cooler | **Reopened; NH-D15 G2 is no longer a locked purchase target** | **Reopened** | Select the smallest/least-expensive durable cooler that meets sustained 9950X3D thermal and acoustic needs without awkward RAM/case constraints. Compare Phantom Spirit 120-class, NH-U12A and NH-D15 G2-class options. |
| Storage architecture | **~1 TB system drive + 1–2 TB CPU-direct active-work NVMe; add bulk/cold storage only when needed** | **Selected / final architecture** | Separate OS/tools from latency-sensitive work without buying high-performance capacity for inactive data. Storage growth is additive. |
| System drive role | **~1 TB value/reliability-focused storage; NVMe preferred but SATA is acceptable if motherboard trade-offs justify it** | **Selected role / model open** | The OS drive does not justify flagship throughput. A second M.2 slot is desirable, not mandatory. |
| Active-work SSD role | **1 TB sufficient; 2 TB preferred only when price/value is attractive; CPU-direct x4 mandatory; Gen4 TLC preferred** | **Selected role / purchase-size open** | Current repos, caches, WSL2/container data, active VMs/databases and other latency-sensitive data belong here. |
| Bulk/cold storage | **Add only when needed; speed secondary** | **Selected expansion policy** | Spare M.2, SATA SSD/HDD, external/NAS are acceptable. Healthy old HDDs may be reused for infrequent data but never as the only copy of important data. |
| Storage RAID policy | **No RAID required** | **Selected** | Version control and real independent backup solve more relevant failure modes. |
| Required M.2 topology | **One CPU-direct M.2 x4 slot that does not reduce the primary GPU link** | **Selected / mandatory** | This is the only hard M.2 requirement. A second M.2 slot is useful but optional because the system drive can fall back to SATA without harming the workstation's main workload. |
| Wired networking | **1 GbE is sufficient; 2.5 GbE is a harmless bonus; do not pay for 5/10 GbE** | **Selected** | Internet is below 1 Gb/s and local-network throughput is irrelevant. Networking speed must not drive motherboard price. |
| Multi-GPU | **Not a requirement; retire the RTX 3060 when a future GPU replacement happens** | **Selected** | No gaming SLI/NVLink value and no concrete heterogeneous-compute requirement. CPU x8/x8 support is a bonus only if effectively free. |
| GPU | **Reuse RTX 3060 12 GB for as long as it remains useful/reliable** | **Selected** | Gaming is secondary and cloud AI increasingly reduces the need to pre-buy local accelerator capability. No current GPU purchase is planned. |
| Future GPU policy | **Do not pre-provision the platform/power system for a hypothetical 500–600 W flagship GPU** | **Selected** | If a future replacement eventually requires unusually high power, reconsider the PSU at that time. Future GPU efficiency and requirements are uncertain. |
| PSU architecture | **Reopened around premium 750 W and 850 W ATX 3.1 units** | **Reopened** | 750 W is a legitimate long-term target for the current machine and today's ~300 W GPU class; 850 W is a value-dependent headroom upgrade. Quality, warranty, acoustics and electrical design outrank wattage. |
| PSU sizing rule | **Prefer 750 W unless an equally high-quality 850 W model costs only modestly more or has materially better characteristics** | **Selected optimization rule** | Do not pay meaningful money merely to reserve speculative GPU wattage. 1000–1200 W no longer has a default justification. |
| PSU feature baseline | **ATX 3.1 / current PCIe GPU-power standard, strong protections, mature platform, long warranty** | **Selected** | Keep modern transient handling and quality requirements while reducing unnecessary capacity. |
| UPS | **No UPS in the initial BOM** | **Selected** | Short outages are acceptable operationally; continuity is unnecessary because a laptop is available. A large battery-backed unit does not provide enough value. |
| Point-of-use power protection | **Use a reputable plug-in surge protector / surge-protected power strip; no electrical-installation modification required by the build** | **Selected policy** | The objective is transient/surge risk reduction, not ride-through. Protection depends on a sound protective-earth connection and is weaker than layered building-level SPD protection, but is the chosen practical constraint. |
| Motherboard VRM / OC | **Stock/conservative 9950X3D operation only; extreme VRM/overclocking capability has no value** | **Selected** | Require competent VRM thermals and reliability, not phase-count marketing or extreme-overclocking features. |
| Chassis | **Fractal North XL Mesh `FD-C-NOR1X-01` remains selected for now** | **Selected, worth one final value check** | Earlier future-flagship-GPU assumptions have weakened, so case oversizing can be revisited before final procurement. Cooler selection must not force an oversized chassis without a concrete thermal reason. |
| Airflow | **3×140 mm included front intake + 1× Noctua NF-A14x25 G2 PWM rear exhaust** | **Selected under current case only** | Revisit fan layout if the case changes; add fans only if measurements justify them. |
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

### Cooling
- NH-D15 G2 standard as a closed exact-model purchase;
- choosing a larger case or constraining RAM merely to preserve NH-D15 G2 dual-fan clearance.

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

- exact CPU cooler under the selected air-cooling architecture;
- exact motherboard under the simplified requirements;
- exact matched 2×64 GB RAM kit and ECC/non-ECC verdict;
- exact ~1 TB system drive and whether NVMe or SATA is the better value in the final topology;
- exact 1 TB or 2 TB active-work NVMe;
- exact premium 750 W or 850 W PSU;
- whether the North XL still earns its size/cost after the future-GPU and cooler assumptions were relaxed;
- optional future bulk/cold storage when capacity actually requires it;
- future GPU replacement only when a concrete need/failure appears.

Detailed component dossiers are under `docs/components/`.

Current purchase execution plan: `docs/procurement-plan-2026-08-31.md`.
