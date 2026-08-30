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
| Memory architecture target | Preserve a credible path to **256 GB**, while allowing the initial purchase to start lower | **Selected** | The platform, motherboard and memory validation work should preserve a stable 256 GB endpoint. 256 GB is no longer required to be purchased on day one if current pricing is disproportionate. Do not weaken the motherboard/platform merely to reduce initial memory cost. |
| Minimum initial memory capacity | **32 GB commissioning floor**, preferably 2×16 GB when pricing is comparable | **Selected** | The current workstation already functions with 32 GB, so Phase-1 memory only needs to boot the new machine reliably and support the existing workload while preserving budget for permanent components. Treat the initial kit as temporary/replaceable; do not let its topology or SKU constrain the eventual validated 256 GB configuration. A single 32 GB DIMM is acceptable if materially cheaper, though 2×16 GB is preferred for dual-channel operation when cost is similar. |
| Motherboard memory-capacity eligibility | Consider only AM5 motherboards whose manufacturer officially specifies support for **256 GB** system memory | **Selected** | The motherboard must preserve the 256 GB architectural target without relying on unofficial/user-reported capacity support. Board selection must also consider high-density DIMM QVL coverage, BIOS maturity and realistic 256 GB operating behavior. |
| Cooling architecture | **High-end air cooling at stock/conservative CPU settings** | **Selected** | The 9950X3D can be cooled adequately by the best current air coolers at the intended stock/conservative operating point, while air removes the AIO pump, coolant/tubing and radiator-placement dependencies from the long-term reliability model. Extra cooling headroom is to be used for thermal/acoustic margin, not to justify PBO/uncapped power. Exact cooler remains provisional; current target is Noctua NH-D15 G2 LBC, with standard NH-D15 G2 as fallback. Reopen only if real sustained development workloads show materially inadequate thermal/acoustic behavior or a future requirement changes the CPU power target. |
| Storage architecture | **Staged two-drive NVMe layout: permanent 2 TB system/tools SSD initially, add 4 TB-or-larger work/VM/container SSD later** | **Selected** | A 2 TB initial SSD is useful permanently and avoids buying the full long-term storage capacity during elevated SSD pricing. The eventual second drive provides operational separation for VMs, containers, build caches, databases and project data without making day-one 6 TB capacity mandatory. Prefer high-quality TLC, DRAM-equipped PCIe 4.0 drives initially; preserve a CPU-connected Gen5 M.2 slot for the future work drive and reassess Gen5 only when that drive is purchased. No RAID is required; external backup remains mandatory. Reopen only if measured storage use or a materially different workload makes 2 TB initial or the two-drive endpoint inappropriate. |
| PSU architecture | **1200 W ATX 3.1 / PCIe 5.1 with native 12V-2x6** | **Selected** | Size the permanent PSU for the explicit future single-GPU design case rather than the current RTX 3060. A future 600 W accelerator plus stock/conservative 9950X3D and platform load can plausibly approach roughly 900–980 W under simultaneous artificial stress. 1200 W provides useful sustained, thermal, acoustic and aging margin while modern ATX 3.1 transient handling addresses short power excursions. 1000 W is viable for many configurations but too tight for the chosen 600 W future-GPU envelope; 1300–1600 W is unnecessary for the intended single-GPU AM5 architecture. Exact PSU remains provisional; current target is Seasonic VERTEX GX-1200 ATX 3.1. |
| Future local AI expansion | Preserve a credible upgrade path to a **very high-performance, high-VRAM discrete GPU for local AI training/inference** | **Selected** | AI is a secondary objective and must not distort the primary development-workstation design. Motherboard, case, PSU and cooling choices should avoid unnecessarily blocking a future single high-end GPU. CPU-connected x8/x8 dual-slot capability is desirable when it comes without a material compromise, but multi-GPU AI is not a current hard requirement; if future training needs genuinely require several accelerator GPUs, reopening the platform decision for Threadripper/WRX90 or another workstation platform is acceptable. |
| GPU | Reuse existing NVIDIA GeForce RTX 3060 12 GB initially | **Selected** | Fixed input to the new build; replacement can be reconsidered later if workload requirements justify a materially higher-VRAM GPU, including the future local-AI objective. |
| Cost / longevity philosophy | Prefer to remain meaningfully below 30,000 lei, but allow higher spend only when it buys a credible long-term reliability, stability, endurance, serviceability or productivity benefit | **Selected** | The budget is not a performance-per-leu optimization target. As total cost approaches or exceeds 30,000 lei, the expected useful life should approach the 10-year end of the target range. Stability and conservative operation take precedence over short-term benchmark performance. |
| Chassis thermal strategy | **Airflow-first, spacious, serviceable chassis design** | **Selected** | Strong, low-restriction airflow supports the build's stability and longevity objectives by reducing sustained component temperatures and preserving headroom for a future high-power GPU. Prefer large low-RPM replaceable fans, easy dust filtration and conventional serviceable layouts over restrictive or showcase-oriented enclosures. Exact case and fan layout remain open until motherboard/cooling/PSU dependencies are mature. |

## Open decisions

The following remain open:

- motherboard/chipset/model within AM5, subject to the 256 GB architectural target and future high-end-GPU expansion objective
- exact Phase-1 memory kit at 32 GB or more; optimize for reliable boot/use and low sunk cost rather than future reuse
- eventual 256 GB DIMM topology, exact kit, data rate and ECC/non-ECC mode
- whether operationally complete system-level ECC should be selected; this requires validation of ECC UDIMM availability, motherboard firmware support and OS-visible error reporting at the relevant capacity
- exact high-end air cooler model; current provisional target is Noctua NH-D15 G2 LBC, subject to motherboard/RAM/case clearance and price/availability
- exact initial 2 TB SSD model and eventual 4 TB-or-larger work-drive model; current policy is mature TLC + DRAM Gen4 unless later pricing/workload makes Gen5 worthwhile
- exact 1200 W PSU model; current provisional target is **Seasonic VERTEX GX-1200 ATX 3.1**, with the exact ATX 3.1 / 12V-2x6 revision and warranty path to be verified at purchase
- exact chassis model and fan layout within the selected airflow-first strategy, including physical/thermal support and 12V-2x6 cable clearance for a future large GPU
- UPS topology/capacity/model
- operating system details

Previously discussed models and configurations belong in component research documents as comparison candidates. They are **not decisions** until explicitly added to the closed-decision table above.
