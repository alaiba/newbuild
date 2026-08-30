# Decision Log

This file records **closed decisions only**, together with their rationale and any condition that could reopen them.

## Decision status vocabulary

- **Open** — no decision has been made
- **Under review** — active technical evaluation
- **Selected** — decision closed unless a dependency or requirement changes
- **Rejected** — explicitly considered and not selected
- **Deferred** — intentionally postponed

## Current closed decisions

| Area | Decision | Status | Rationale / reopen condition |
|---|---|---|---|
| CPU / platform | AMD Ryzen 9 9950X3D on AM5 | **Selected** | Best overall balance for very heavy Java/Android development, interactive desktop use and occasional gaming. Threadripper 9960X/TRX50 offers additional sustained parallel throughput, memory bandwidth and I/O, but its materially higher total platform cost and workstation specialization do not justify the expected benefit for this mixed workload. Reopen only if requirements materially change toward highly parallel sustained compute, substantially greater memory capacity/bandwidth, unusually high PCIe expansion needs, or a future multi-GPU AI workload that materially exceeds AM5 capabilities. |
| Motherboard | **ASUS ProArt X870E-Creator WiFi** | **Selected** | Promotion gate completed 2026-08-30. ASUS provides the strongest explicit evidence for the hardest long-term requirement: BIOS 1003 explicitly supports four 64 GB DIMMs / 256 GB up to 5200 MT/s with compatible modules, followed by high-capacity, four-DIMM, memory-training and ECC-specific firmware work. The ASRock X870 Taichi Creator remains a strong lower-cost alternative with better diagnostics/topology, but equivalent explicit 4×64 validation was not found. The roughly 800–1,000 lei premium is accepted as configuration-risk reduction, not CPU-performance spend. Reopen only if ASRock or another board reaches equivalent 256 GB/ECC validation before purchase, ASUS develops a material regression/availability problem, or the platform requirement changes. |
| Memory architecture target | Preserve a credible path to **256 GB**, while allowing the initial purchase to start lower | **Selected** | The platform and motherboard preserve a stable 256 GB endpoint. 256 GB is not required on day one. The eventual exact configuration remains deferred because 64 GB ECC UDIMMs are still a relatively niche market; when upgrading, prefer 4×64 GB ECC UDIMM only if exact modules are credible, obtainable and stable, otherwise use a validated 4×64 GB non-ECC configuration. |
| Minimum initial memory capacity | **32 GB commissioning floor**, preferably 2×16 GB when pricing is comparable | **Selected** | The current workstation already functions with 32 GB, so Phase-1 memory only needs to boot the new machine reliably and support the existing workload while preserving budget for permanent components. Treat the initial kit as temporary/replaceable; do not let its topology or SKU constrain the eventual validated 256 GB configuration. A single 32 GB DIMM is acceptable if materially cheaper. |
| Motherboard memory-capacity eligibility | Consider only AM5 motherboards whose manufacturer officially specifies support for **256 GB** system memory | **Selected** | The motherboard must preserve the 256 GB architectural target without relying on unofficial/user-reported capacity support. High-density DIMM QVL coverage, BIOS maturity and realistic four-DIMM behavior remain important at the eventual memory purchase. |
| Cooling architecture | **High-end air cooling at stock/conservative CPU settings** | **Selected** | The 9950X3D can be cooled adequately by the best current air coolers at the intended stock/conservative operating point, while air removes the AIO pump, coolant/tubing and radiator-placement dependencies from the long-term reliability model. Extra cooling headroom is for thermal/acoustic margin, not PBO/uncapped power. Exact cooler remains provisional; current target is Noctua NH-D15 G2 LBC. |
| Storage architecture | **Staged two-drive NVMe layout: permanent 2 TB system/tools SSD initially, add 4 TB-or-larger work/VM/container SSD later** | **Selected** | A 2 TB initial SSD is useful permanently and avoids buying the full long-term capacity immediately. Prefer mature TLC + DRAM PCIe 4.0 initially; reserve CPU-connected M.2_1 for the later work drive and reassess Gen5 then. No RAID is required; external/network backup remains required. |
| PSU architecture | **1200 W ATX 3.1 / PCIe 5.1 with native 12V-2x6** | **Selected** | Size the permanent PSU for a plausible future 600 W single accelerator rather than the current RTX 3060. 1200 W provides useful sustained, thermal, acoustic and aging margin without moving into an unnecessary 1300–1600 W class. Exact PSU remains provisional; current target is Seasonic VERTEX GX-1200 ATX 3.1. |
| Chassis | **Fractal Design North XL Mesh** | **Selected** | Provides enough permanent headroom without oversized-full-tower penalties: ATX/E-ATX support, 413 mm GPU length, 185 mm CPU-cooler height, front/PSU filtration, three included 140 mm PWM front fans, 290 mm PSU clearance and top 360 mm AIO fallback support. Reopen if a final component exceeds its clearance envelope or purchase-time availability changes materially. |
| Chassis fan layout | **3×140 mm front intake + 1×140 mm rear exhaust; no top/side fans initially** | **Selected** | Simple front-to-rear airflow with mild positive pressure supports dust control, acoustics and reliability. Additional top/side fans should be added only if measured thermals justify them. Exact rear-fan model remains provisional. |
| UPS architecture | **Phase-1 line-interactive, pure-sine UPS around 1600 VA / 1000 W; size for the current RTX 3060 system and reassess with a future high-power GPU** | **Selected** | The UPS is a current-system protection component rather than a permanent power-envelope constraint. A 1000 W pure-sine unit provides ample margin for the current system and enough runtime for graceful shutdown. Reopen when measured load approaches ~700–800 W, the GPU changes materially, runtime becomes inadequate, or site power quality justifies online/double-conversion. Exact model remains provisional; current target is CyberPower CP1600EPFCLCD. |
| Future local AI expansion | Preserve a credible upgrade path to a **very high-performance, high-VRAM discrete GPU for local AI training/inference** | **Selected** | AI is a secondary objective and must not distort the primary development-workstation design. Motherboard, case, PSU and cooling choices should avoid unnecessarily blocking a future single high-end GPU. CPU-connected x8/x8 is desirable headroom, not a current hard requirement. Reopen the platform if future AI genuinely requires several accelerator GPUs. |
| GPU | Reuse existing NVIDIA GeForce RTX 3060 12 GB initially | **Selected** | Fixed input to the initial build; replacement can be reconsidered later if workload requirements justify a materially higher-VRAM GPU. |
| Cost / longevity philosophy | Prefer to remain meaningfully below 30,000 lei, but allow higher spend only when it buys a credible long-term reliability, stability, endurance, serviceability or productivity benefit | **Selected** | The budget is not a performance-per-leu optimization target. As total cost approaches or exceeds 30,000 lei, the expected useful life should approach the 10-year end of the target range. Stability and conservative operation take precedence over short-term benchmark performance. |
| Chassis thermal strategy | **Airflow-first, spacious, serviceable chassis design** | **Selected** | Strong, low-restriction airflow supports stability and longevity by reducing sustained component temperatures and preserving headroom for a future high-power GPU. Prefer large low-RPM replaceable fans, easy dust filtration and conventional serviceable layouts. |

## Open decisions

The following remain open:

- exact Phase-1 memory kit at 32 GB or more; optimize for reliable boot/use and low sunk cost rather than future reuse
- eventual 256 GB DIMM topology implementation details: exact 4×64 GB modules, operating rate and ECC/non-ECC verdict at purchase time
- whether the eventual 256 GB configuration uses operationally complete system-level ECC; 64 GB ECC UDIMM availability/QVL evidence is not yet mature enough to force the decision now
- exact high-end air cooler model; current provisional target is Noctua NH-D15 G2 LBC, subject to RAM clearance and purchase-time price/availability
- exact initial 2 TB SSD model and eventual 4 TB-or-larger work-drive model
- exact 1200 W PSU model; current provisional target is Seasonic VERTEX GX-1200 ATX 3.1
- exact rear 140 mm case fan model
- exact Phase-1 UPS model; current provisional target is CyberPower CP1600EPFCLCD
- operating system details

Detailed evidence for the motherboard promotion is recorded in `docs/components/motherboard-memory-promotion-gate-2026-08-30.md`.
