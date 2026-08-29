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
| CPU / platform | AMD Ryzen 9 9950X3D on AM5 | **Selected** | Best overall balance for very heavy Java/Android development, interactive desktop use and occasional gaming. Threadripper 9960X/TRX50 offers additional sustained parallel throughput, memory bandwidth and I/O, but its materially higher total platform cost and workstation specialization do not justify the expected benefit for this mixed workload. Reopen only if requirements materially change toward highly parallel sustained compute, substantially greater memory capacity/bandwidth, or unusually high PCIe expansion needs. |
| Memory capacity target | **256 GB initial build target** | **Selected** | Design the AM5 system around a stable 256 GB configuration. Scale back to a lower capacity only if current 256 GB memory cost is disproportionate to the overall build budget or if available 4×64 GB configurations impose an unacceptable stability/performance compromise. Exact DIMM topology, kit, data rate and ECC/non-ECC mode remain open until motherboard/memory validation. |
| Motherboard memory-capacity eligibility | Consider only AM5 motherboards whose manufacturer officially specifies support for **256 GB** system memory | **Selected** | The motherboard must support the 256 GB target configuration without relying on unofficial/user-reported capacity support. Board selection must also consider high-density DIMM QVL coverage, BIOS maturity and realistic 256 GB operating behavior. |
| Budget / longevity philosophy | **30,000 lei is a planning level, not a hard cap; stability and long-term value outrank short-term peak performance** | **Selected** | Prefer to stay meaningfully below 30,000 lei when that does not compromise the workstation's technical objectives. Spending at or above this level is acceptable only when the additional cost buys a credible durable benefit in performance, reliability, endurance, serviceability, expansion headroom or reduced operational risk. If the build approaches/exceeds 30,000 lei, it should be designed explicitly around an approximately 10-year useful-life objective. Reopen only if the intended ownership horizon or workload priorities materially change. |
| GPU | Reuse existing NVIDIA GeForce RTX 3060 12 GB initially | **Selected** | Fixed input to the new build; replacement can be reconsidered later if workload requirements justify a materially higher-VRAM GPU |

## Open decisions

The following remain open:

- motherboard/chipset/model within AM5, subject to the 256 GB target
- memory DIMM topology, exact kit, data rate and ECC/non-ECC mode for the 256 GB target
- cooling architecture and model for the Ryzen 9 9950X3D
- storage capacity, topology, interface and exact drives
- PSU wattage/platform/model
- case and fan layout
- UPS topology/capacity/model
- operating system details

Previously discussed models and configurations belong in component research documents as comparison candidates. They are **not decisions** until explicitly added to the closed-decision table above.
