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
| Minimum initial memory capacity | **64 GB as 2×32 GB** | **Selected** | This is the minimum acceptable starting configuration for the current workload and already doubles the user's present working capacity. It preserves the rest of the workstation design while keeping initial cost under control. Prefer two DIMMs for easier AM5 memory-controller loading. Treat the initial kit as replaceable rather than assuming it will later be combined with another independently purchased kit. |
| Motherboard memory-capacity eligibility | Consider only AM5 motherboards whose manufacturer officially specifies support for **256 GB** system memory | **Selected** | The motherboard must preserve the 256 GB architectural target without relying on unofficial/user-reported capacity support. Board selection must also consider high-density DIMM QVL coverage, BIOS maturity and realistic 256 GB operating behavior. |
| Future local AI expansion | Preserve a credible upgrade path to a **very high-performance, high-VRAM discrete GPU for local AI training/inference** | **Selected** | AI is a secondary objective and must not distort the primary development-workstation design. Motherboard, case, PSU and cooling choices should avoid unnecessarily blocking a future single high-end GPU. CPU-connected x8/x8 dual-slot capability is desirable when it comes without a material compromise, but multi-GPU AI is not a current hard requirement; if future training needs genuinely require several accelerator GPUs, reopening the platform decision for Threadripper/WRX90 or another workstation platform is acceptable. |
| GPU | Reuse existing NVIDIA GeForce RTX 3060 12 GB initially | **Selected** | Fixed input to the new build; replacement can be reconsidered later if workload requirements justify a materially higher-VRAM GPU, including the future local-AI objective. |
| Cost / longevity philosophy | Prefer to remain meaningfully below 30,000 lei, but allow higher spend only when it buys a credible long-term reliability, stability, endurance, serviceability or productivity benefit | **Selected** | The budget is not a performance-per-leu optimization target. As total cost approaches or exceeds 30,000 lei, the expected useful life should approach the 10-year end of the target range. Stability and conservative operation take precedence over short-term benchmark performance. |
| Chassis thermal strategy | **Airflow-first, spacious, serviceable chassis design** | **Selected** | Strong, low-restriction airflow supports the build's stability and longevity objectives by reducing sustained component temperatures and preserving headroom for a future high-power GPU. Prefer large low-RPM replaceable fans, easy dust filtration and conventional serviceable layouts over restrictive or showcase-oriented enclosures. Exact case and fan layout remain open until motherboard/cooling/PSU dependencies are mature. |

## Open decisions

The following remain open:

- motherboard/chipset/model within AM5, subject to the 256 GB architectural target and future high-end-GPU expansion objective
- exact initial memory kit and whether to start at 64 GB, 96 GB, 128 GB or another capacity above the selected 64 GB floor based on current price/value
- eventual 256 GB DIMM topology, exact kit, data rate and ECC/non-ECC mode
- whether operationally complete system-level ECC should be selected; this requires validation of ECC UDIMM availability, motherboard firmware support and OS-visible error reporting at the relevant capacity
- cooling architecture and model for the Ryzen 9 9950X3D
- storage capacity, topology, interface and exact drives
- PSU wattage/platform/model, including sensible headroom for a future substantially higher-power GPU
- exact chassis model and fan layout within the selected airflow-first strategy, including physical/thermal support for a future large GPU
- UPS topology/capacity/model
- operating system details

Previously discussed models and configurations belong in component research documents as comparison candidates. They are **not decisions** until explicitly added to the closed-decision table above.
