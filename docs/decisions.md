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
| CPU / platform | AMD Ryzen 9 9950X3D on AM5 | **Selected** | Best overall balance for very heavy Java/Android development, interactive desktop use and occasional gaming. Threadripper 9960X/TRX50 does not justify its materially higher platform/TCO cost for this mixed workload. Reopen only if requirements shift toward sustained highly parallel compute, much greater memory bandwidth/capacity, unusually high PCIe expansion or serious multi-GPU AI. |
| Motherboard | **ASUS ProArt X870E-Creator WiFi** | **Selected** | Strongest explicit evidence found for the hardest long-term requirement: four 64 GB DIMMs / 256 GB, followed by high-capacity, four-DIMM, training/stability and ECC-specific firmware work. Reopen for a material firmware/availability regression or equivalent/better validated alternative before purchase. |
| Memory architecture target | Preserve a credible path to **256 GB**, expected 4×64 GB | **Selected** | The platform must preserve a stable 256 GB endpoint. Prefer ECC UDIMM only if exact modules, four-DIMM stability and OS-visible reporting are credible at upgrade time; otherwise use validated non-ECC. |
| Minimum initial memory capacity | **32 GB commissioning floor** | **Selected** | The existing workload is already being managed with 32 GB. Phase-1 memory is temporary and must not constrain the eventual 256 GB configuration. |
| Phase-1 memory purchasing policy | **32 GB GOODRAM baseline plus optional 64 GB 2×32 tier; final capacity choice deferred to end-of-build price review** | **Selected** | Baseline is GOODRAM `GR5600D564L46/32G` 1×32 GB at ~2.20k lei PC Garage. 64 GB is optional rather than selected: prefer 2×32 GB if a credible kit falls near ~4.5–4.8k lei; current serious candidates include Crucial `CT2K32G56C46U5` and Kingston ProArt-listed `KF556C36BBEK2-64` / `KF560C36BBEK2-64`. The final 32-vs-64 purchase decision is intentionally postponed until the complete initial BOM cost is known. |
| Motherboard memory-capacity eligibility | Consider only AM5 motherboards whose manufacturer officially specifies support for **256 GB** | **Selected** | The 256 GB endpoint must not depend on unofficial/user-reported capacity support. |
| Cooling architecture | **High-end air cooling at stock/conservative CPU settings** | **Selected** | Removes pump/liquid/radiator dependencies while retaining adequate 9950X3D thermal headroom. Cooling margin is for reliability/acoustics, not PBO/uncapped power. |
| CPU cooler | **Noctua NH-D15 G2 standard base, using the included 7 mm AM5 offset mount** | **Selected** | Noctua recommends the standard G2 as the best all-rounder and reports excellent/best AM5 behavior with offset mounting. ProArt compatibility is explicit. Current 32 GB baseline needs no fan lift; the serious Kingston 64 GB alternatives need only ~3 mm and remain safely inside the North XL 185 mm envelope. |
| Storage architecture | **Staged two-drive NVMe layout: permanent 2 TB system/tools SSD initially, add 4 TB-or-larger work/VM/container SSD later** | **Selected** | Avoids unnecessary day-one capacity spend while preserving operational separation and future Gen5 choice. No RAID required; external/network backup remains required. |
| Initial system/tools SSD | **Samsung 990 PRO 2 TB (`MZ-V9P2T0BW`)** | **Selected** | Mature TLC + DRAM Gen4 platform, strong mixed/random performance, Samsung tooling and adequate endurance. Install under ProArt `M.2_3` heatsink. PC Garage preferred over eMAG when price difference is small. |
| PSU architecture | **1200 W ATX 3.1 / PCIe 5.1 with 600 W-capable 12V-2x6** | **Selected** | Sized for a plausible future 600 W single accelerator. 1200 W provides sustained, thermal, acoustic and aging margin without moving to unnecessary 1300–1600 W territory. |
| Exact PSU | **Seasonic VERTEX GX-1200, current ATX 3.1 / PCIe 5.1 / 12V-2x6 revision** | **Selected** | Seasonic's current GX-1200 satisfies the selected architecture, is compact, fully modular and carries a 12-year warranty. A current Romanian Altex listing explicitly identifies the GX-1200 as ATX 3.1 and in stock around 1,289.99 lei; direct current PX-1200 evidence is more expensive and/or out of stock. Prefer PC Garage first and eMAG second only when they explicitly identify the current revision; otherwise use a reputable retailer with unambiguous ATX 3.1 stock. Receipt acceptance must reject old ATX 3.0 / 12VHPWR inventory. Reopen only for a material availability/reliability issue or if a known-current PX-1200 is available within roughly 100–150 lei at checkout. |
| Chassis | **Fractal Design North XL Mesh** | **Selected** | Provides the required motherboard, GPU, cooler, PSU, filtration and airflow headroom without oversized-full-tower penalties. |
| Chassis fan layout | **3×140 mm front intake + 1×140 mm rear exhaust; no top/side fans initially** | **Selected** | Simple front-to-rear airflow with mild positive pressure supports dust control, acoustics and reliability. Add fans only if measurements justify them. |
| Rear case fan | **Noctua NF-A14x25 G2 PWM, square-frame 140 mm** | **Selected** | Premium permanent rear exhaust with broad low-speed PWM range, SSO2 bearing, >150,000 h MTTF and six-year warranty. Do not buy an unnecessary two-pack solely to satisfy retailer preference. |
| UPS architecture | **Phase-1 line-interactive pure-sine UPS around 1600 VA / 1000 W; reassess with future high-power GPU** | **Selected** | A current-system protection component rather than a permanent future-GPU constraint. Reopen when measured load approaches ~700–800 W, GPU power changes materially, runtime becomes inadequate or site power quality requires online/double-conversion. |
| Phase-1 UPS | **CyberPower CP1600EPFCLCD** | **Selected** | 1600 VA / 1000 W, pure-sine line-interactive, Active-PFC compatible, AVR, USB/PowerPanel and user-replaceable `RBP0142` battery. PC Garage price premium is small relative to broader Romanian market. |
| Future local AI expansion | Preserve a credible path to a **very high-performance, high-VRAM single discrete GPU** | **Selected** | AI is secondary and must not distort the primary development workstation. Reopen the platform if future AI genuinely requires several accelerator GPUs. |
| GPU | Reuse existing NVIDIA GeForce RTX 3060 12 GB initially | **Selected** | Fixed input to the initial build; replacement remains a later decision. |
| Cost / longevity philosophy | Prefer to remain meaningfully below 30,000 lei, but allow higher spend only for credible long-term reliability, stability, endurance, serviceability or productivity benefit | **Selected** | Stability and conservative operation take precedence over short-lived benchmark gains or prestige spending. |
| Chassis thermal strategy | **Airflow-first, spacious, serviceable chassis design** | **Selected** | Strong low-restriction airflow supports component longevity, thermal margin and a future high-power GPU. |

## Open decisions

The following remain open:

- **final Phase-1 memory purchase: 32 GB baseline vs optional 64 GB 2×32 configuration**, to be decided at the end of the initial BOM review using then-current prices and remaining budget
- eventual 256 GB DIMM implementation: exact 4×64 GB modules, operating rate and ECC/non-ECC verdict
- whether the eventual 256 GB configuration provides operationally complete system-level ECC with usable OS reporting
- exact 4 TB-or-larger work-drive model
- operating system details

Detailed motherboard evidence: `docs/components/motherboard-memory-promotion-gate-2026-08-30.md`.

Detailed Phase-1 memory alternatives and current pricing: `docs/components/memory.md`.

Detailed PSU evidence and acceptance rules: `docs/components/psu.md`.
