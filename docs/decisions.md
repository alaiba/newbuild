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
| Motherboard memory-capacity eligibility | Consider only AM5 motherboards whose manufacturer officially specifies support for **256 GB** system memory | **Selected** | Preserves the maximum memory ceiling supported by the selected Ryzen 9 9950X3D and avoids choosing a board that would artificially constrain future memory expansion. This is a board-selection requirement, not a decision to install 256 GB initially. Actual memory capacity, DIMM topology and operating data rate remain open and must be validated separately. |
| GPU | Reuse existing NVIDIA GeForce RTX 3060 12 GB initially | **Selected** | Fixed input to the new build; replacement can be reconsidered later if workload requirements justify a materially higher-VRAM GPU |

## Open decisions

The following remain open:

- motherboard/chipset/model within AM5, subject to the 256 GB support requirement
- memory capacity, topology, speed and ECC/non-ECC within AM5 constraints
- cooling architecture and model for the Ryzen 9 9950X3D
- storage capacity, topology, interface and exact drives
- PSU wattage/platform/model
- case and fan layout
- UPS topology/capacity/model
- operating system details

Previously discussed models and configurations belong in component research documents as comparison candidates. They are **not decisions** until explicitly added to the closed-decision table above.
