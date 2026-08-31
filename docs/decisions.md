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
| Minimum initial memory capacity | **32 GB commissioning floor** | **Selected** | 32 GB remains the emergency/minimum-cost floor, but no longer the preferred initial purchase after the final BOM review. |
| Phase-1 memory capacity | **64 GB, 2×32 GB** | **Selected** | Final BOM review shows the build at roughly 14.8–15.5k lei with 32 GB versus roughly 17.3–18.1k lei with a good 64 GB kit, leaving substantial room below the ~30k planning level. The additional ~2.5–3k lei buys both double capacity and dual-channel bandwidth without displacing any permanent component, which is worthwhile for heavy Java/Android/IDE/container/VM use. |
| Phase-1 memory target | **Crucial `CT2K32G56C46U5`, 64 GB (2×32), DDR5-5600 CL46, 1.1 V** | **Selected target** | Conservative JEDEC-class electrical profile, dual-channel topology, low-profile bare modules and current ~4.7–4.8k lei market pricing make it the best current balance. Kingston `KF556C36BBEK2-64` is the explicit-ProArt compatibility fallback if Crucial stock/warranty/pricing is materially worse. Boot at Auto/JEDEC and validate extensively. Reopen only for a purchase-time stock/price/warranty anomaly or an actual compatibility issue. |
| Motherboard memory-capacity eligibility | Consider only AM5 motherboards whose manufacturer officially specifies support for **256 GB** | **Selected** | The 256 GB endpoint must not depend on unofficial/user-reported capacity support. |
| Cooling architecture | **High-end air cooling at stock/conservative CPU settings** | **Selected** | Removes pump/liquid/radiator dependencies while retaining adequate 9950X3D thermal headroom. Cooling margin is for reliability/acoustics, not PBO/uncapped power. |
| CPU cooler | **Noctua NH-D15 G2 standard base, using the included 7 mm AM5 offset mount** | **Selected** | Noctua recommends the standard G2 as the best all-rounder and reports excellent/best AM5 behavior with offset mounting. ProArt compatibility is explicit. The selected Crucial 64 GB kit is low-profile and should require zero or only minimal front-fan lift; North XL clearance remains ample. |
| Storage architecture | **Staged two-drive NVMe layout: permanent 2 TB system/tools SSD initially, add 4 TB-or-larger work/VM/container SSD later** | **Selected** | Avoids unnecessary day-one capacity spend while preserving operational separation and future Gen5 choice. No RAID required; external/network backup remains required. |
| Initial system/tools SSD | **Samsung 990 PRO 2 TB (`MZ-V9P2T0BW`)** | **Selected** | Mature TLC + DRAM Gen4 platform, strong mixed/random performance, Samsung tooling and adequate endurance. Install under ProArt `M.2_3` heatsink. |
| PSU architecture | **1200 W ATX 3.1 / PCIe 5.1 with 600 W-capable 12V-2x6** | **Selected** | Sized for a plausible future 600 W single accelerator. 1200 W provides sustained, thermal, acoustic and aging margin without moving to unnecessary 1300–1600 W territory. |
| Exact PSU | **Seasonic VERTEX GX-1200, current ATX 3.1 / PCIe 5.1 / 12V-2x6 revision** | **Selected** | Current GX-1200 satisfies the selected architecture, is compact, fully modular and carries a 12-year warranty. Altex has an explicit current-revision Romanian listing. Receipt acceptance must reject old ATX 3.0 / 12VHPWR inventory. |
| Chassis | **Fractal Design North XL Mesh** | **Selected** | Provides the required motherboard, GPU, cooler, PSU, filtration and airflow headroom without oversized-full-tower penalties. |
| Chassis fan layout | **3×140 mm front intake + 1×140 mm rear exhaust; no top/side fans initially** | **Selected** | Simple front-to-rear airflow with mild positive pressure supports dust control, acoustics and reliability. Add fans only if measurements justify them. |
| Rear case fan | **Noctua NF-A14x25 G2 PWM, square-frame 140 mm** | **Selected** | Premium permanent rear exhaust with broad low-speed PWM range, SSO2 bearing, >150,000 h MTTF and six-year warranty. |
| UPS architecture | **Phase-1 line-interactive pure-sine UPS around 1600 VA / 1000 W; reassess with future high-power GPU** | **Selected** | A current-system protection component rather than a permanent future-GPU constraint. Reopen when measured load approaches ~700–800 W, GPU power changes materially, runtime becomes inadequate or site power quality requires online/double-conversion. |
| Phase-1 UPS | **CyberPower CP1600EPFCLCD** | **Selected** | 1600 VA / 1000 W, pure-sine line-interactive, Active-PFC compatible, AVR, USB/PowerPanel and user-replaceable `RBP0142` battery. |
| Host operating system | **Windows 11 Pro x64** | **Selected** | Best fit for native IntelliJ/Android Studio, NVIDIA/gaming compatibility, BitLocker, Remote Desktop hosting and Hyper-V/WSL2. Home saves only about 509 RON at current Microsoft Store pricing while dropping professional host features. Pro for Workstations costs about 800 RON more than Pro and its 4-CPU/6-TB/SMB-Direct-class advantages are irrelevant to this one-socket/256-GB-target build. |
| Windows license procurement | **Buy a new legitimate Windows 11 Pro license** | **Selected / required purchase** | No existing transferable Windows license is available for this build. Current official Microsoft Store Romania reference is 1,199 RON. Treat the license as a mandatory BOM item rather than conditional spend; do not use a grey-market key as a budget-control mechanism. |
| Initial Windows feature release | **Windows 11 25H2, General Availability channel** | **Selected for initial installation** | Current normal GA release for standard existing x64 PCs; 24H2 Home/Pro reaches end of servicing 2026-10-13. Microsoft describes 26H1 as scoped to new devices and not the normal in-place feature-update path from 24H2/25H2. Follow normal supported feature updates after commissioning; do not pin permanently to 25H2. |
| Linux development environment | **WSL2 + Ubuntu 26.04.1 LTS** | **Selected** | Provides a first-class Linux userland without dual-boot maintenance/reboot friction. Canonical identifies 26.04.1 as the latest LTS for Ubuntu on WSL; 26.04 LTS receives standard maintenance through 2031. Reopen native Linux only for a demonstrated bare-metal kernel/KVM/device/driver requirement that WSL2 cannot satisfy. |
| Windows/Linux filesystem policy | **Keep heavy native workloads on their native filesystem** | **Selected** | Windows-native source/caches belong on Windows storage; Linux-native source/caches/container data belong inside the WSL filesystem rather than `/mnt/c`. Reassess a Windows Dev Drive on the future 4 TB+ work SSD; do not complicate the initial 2 TB system SSD merely to create one. |
| GPU driver branch | **Current NVIDIA Studio Driver, WHQL** | **Selected baseline** | Gaming is secondary, while stability is the workstation priority. NVIDIA states both Studio and Game Ready support games/apps; Studio emphasizes tested production stability. Switch to Game Ready only if a specific new game needs day-zero optimizations/fixes. |
| OS security/virtualization baseline | **UEFI + Secure Boot + TPM 2.0 + BitLocker after firmware stabilization + SVM for WSL2/Hyper-V** | **Selected** | Establish the firmware baseline and perform the planned BIOS update before enabling BitLocker; retain the recovery key independently. Keep memory/CPU conservative during commissioning and avoid Insider/preview OS builds. |
| Future local AI expansion | Preserve a credible path to a **very high-performance, high-VRAM single discrete GPU** | **Selected** | AI is secondary and must not distort the primary development workstation. Reopen the platform if future AI genuinely requires several accelerator GPUs. |
| GPU | Reuse existing NVIDIA GeForce RTX 3060 12 GB initially | **Selected** | Fixed input to the initial build; replacement remains a later decision. |
| Cost / longevity philosophy | Prefer to remain meaningfully below 30,000 lei, but allow higher spend only for credible long-term reliability, stability, endurance, serviceability or productivity benefit | **Selected** | Stability and conservative operation take precedence over short-lived benchmark gains or prestige spending. |
| Chassis thermal strategy | **Airflow-first, spacious, serviceable chassis design** | **Selected** | Strong low-restriction airflow supports component longevity, thermal margin and a future high-power GPU. |
| Retailer policy | **PC Garage and Altex co-preferred; eMAG also acceptable** | **Selected** | Exact SKU/revision, seller quality and normal Romanian/EU warranty take precedence over retailer order. Small price differences do not matter; material differences can justify another reputable seller. |

## Open / deferred decisions

The following remain open or intentionally deferred:

- eventual 256 GB DIMM implementation: exact 4×64 GB modules, operating rate and ECC/non-ECC verdict;
- whether the eventual 256 GB configuration provides operationally complete system-level ECC with usable OS reporting;
- exact 4 TB-or-larger work-drive model;
- exact container-runtime/tooling choice if licensing or workflow requirements make that material.

Detailed motherboard evidence: `docs/components/motherboard-memory-promotion-gate-2026-08-30.md`.

Detailed Phase-1 memory decision: `docs/components/memory.md`.

Detailed PSU evidence and acceptance rules: `docs/components/psu.md`.

Detailed OS/bring-up decision: `docs/components/os.md`.
