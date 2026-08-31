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
| CPU / platform | AMD Ryzen 9 9950X3D on AM5 | **Selected** | Best overall balance for very heavy Java/Android development, interactive desktop use and occasional gaming. A 2026 procurement recheck found the boxed 9950X roughly 650 lei cheaper, but the 9950X3D remains marginally faster in GamersNexus' Chromium compile test while preserving substantially stronger gaming performance. Keep the permanent CPU. Reopen only for a material requirement change. |
| Motherboard | **ASUS ProArt X870E-Creator WiFi** | **Selected** | Strongest explicit evidence found for the hardest long-term requirement: four 64 GB DIMMs / 256 GB, followed by high-capacity, four-DIMM, training/stability and ECC-specific firmware work. The cheaper X870 Taichi Creator was reconsidered during procurement optimization, but the ~900–1,000+ lei saving does not justify weakening the strongest stability evidence for the intended 256 GB endpoint. |
| Memory architecture target | Preserve a credible path to **256 GB**, expected 4×64 GB | **Selected** | The platform must preserve a stable 256 GB endpoint. Prefer ECC UDIMM only if exact modules, four-DIMM stability and OS-visible reporting are credible at upgrade time; otherwise use validated non-ECC. |
| Minimum initial memory capacity | **32 GB commissioning floor** | **Selected** | Emergency/minimum-cost floor only. |
| Phase-1 memory capacity | **64 GB, 2×32 GB** | **Selected** | The additional capacity and dual-channel bandwidth are worthwhile for heavy Java/Android/IDE/container/VM use while total build cost remains far below the planning level. |
| Phase-1 memory target | **Crucial `CT2K32G56C46U5`, 64 GB (2×32), DDR5-5600 CL46, 1.1 V** | **Selected target** | Conservative JEDEC-class electrical profile, dual-channel topology and low-profile bare modules. Current EvoMAG indexing around 4,156.99 lei materially strengthens its value. Strict purchase gate: exact desktop `...U5`, never laptop/SO-DIMM `...S5`. Kingston `KF556C36BBEK2-64` remains compatibility fallback. |
| Motherboard memory-capacity eligibility | Consider only AM5 motherboards whose manufacturer officially specifies support for **256 GB** | **Selected** | The 256 GB endpoint must not depend on unofficial/user-reported capacity support. |
| Cooling architecture | **High-end air cooling at stock/conservative CPU settings** | **Selected** | Removes pump/liquid/radiator dependencies while retaining adequate 9950X3D thermal headroom. |
| CPU cooler | **Noctua NH-D15 G2 standard base, included 7 mm AM5 offset mount** | **Selected** | A procurement recheck found Thermalright Phantom Spirit 120 SE roughly 400–490 lei cheaper, but Noctua retains the stronger long-term mounting/support ecosystem, soldered fin/heatpipe construction, >150k-hour fan MTTF and six-year manufacturer warranty. Those benefits match the 10-year stability/endurance goal. |
| Storage architecture | **Staged two-drive NVMe layout: permanent 2 TB system/tools SSD initially, add 4 TB-or-larger work/VM/container SSD later** | **Selected** | Preserves operational separation and future capacity/Gen5 choice without unnecessary day-one spend. No RAID; external/network backup remains required. |
| Initial system/tools SSD | **Samsung 990 PRO 2 TB `MZ-V9P2T0BW`** | **Selected** | Kingston KC3000 2 TB was reconsidered and is excellent, but the current EvoMAG saving is only ~50–60 lei. Keep Samsung for its mature firmware/tooling and already-validated role/topology. Install under ProArt `M.2_3` heatsink. |
| PSU architecture | **1200 W ATX 3.1 / PCIe 5.1 with 600 W-capable 12V-2x6** | **Selected** | Sized for a plausible future ~600 W single accelerator with sustained/thermal/aging margin. |
| Exact PSU | **Seasonic VERTEX GX-1200, current ATX 3.1 / PCIe 5.1 / 12V-2x6 revision** | **Selected** | be quiet! Straight Power 12 1200W `BN339` was reconsidered: it is an excellent ATX 3.1/Platinum unit, but the relevant saving is only ~30–80 lei. Keep Seasonic's 12-year warranty, 160 mm chassis and explicit current-revision Altex purchase path. Reopen only for material availability/reliability change. |
| Chassis | **Fractal Design North XL Mesh `FD-C-NOR1X-01`** | **Selected** | Provides motherboard/GPU/cooler/PSU, filtration, airflow and serviceability headroom. Current EvoMAG exact-SKU pricing around 882.99 lei makes it particularly strong value. Fractal's official mapping confirms `-01` is Charcoal Black Mesh even where a retailer title says “Solid”. |
| Chassis fan layout | **3×140 mm front intake + 1×140 mm rear exhaust; no top/side fans initially** | **Selected** | Simple front-to-rear airflow with mild positive pressure; add fans only if measurements justify them. |
| Rear case fan | **Noctua NF-A14x25 G2 PWM, square-frame 140 mm** | **Selected** | ARCTIC P14/P14 Max was reconsidered as a ~125–160 lei saving. Keep Noctua because EvoMAG now carries the exact single fan, eliminating the provider penalty, while retaining explicit >150k-hour MTTF and six-year warranty. |
| UPS architecture | **Phase-1 line-interactive pure-sine UPS around 1600 VA / 1000 W; reassess with future high-power GPU** | **Selected** | Pure sine, Active-PFC compatibility, AVR and controlled shutdown are deliberate reliability features. |
| Phase-1 UPS | **CyberPower CP1600EPFCLCD** | **Selected** | 1600 VA / 1000 W, pure-sine line-interactive, Active-PFC compatible, AVR, USB/PowerPanel and user-replaceable battery. Do not replace with a cheaper simulated-sine unit simply for VA-per-leu. |
| Host operating system | **Windows 11 Pro x64** | **Selected** | Best fit for native development, NVIDIA/gaming, BitLocker, Remote Desktop and Hyper-V/WSL2. |
| Windows license procurement | **Microsoft Windows 11 Pro Retail/FPP USB English `HAV-00163`** | **Selected / required purchase** | No transferable license exists. Retail/FPP is the clean DIY licensing path. Do not substitute OEM/DSP or undocumented standalone keys. |
| Initial Windows feature release | **Windows 11 25H2, General Availability channel** | **Selected for initial installation** | Current normal supported x64 GA path for this installation; follow normal supported feature updates afterward. |
| Linux development environment | **WSL2 + Ubuntu 26.04.1 LTS** | **Selected** | First-class Linux userland without dual-boot maintenance/reboot friction. |
| Windows/Linux filesystem policy | **Keep heavy native workloads on their native filesystem** | **Selected** | Windows-native source/caches on Windows storage; Linux-native source/caches/container data inside WSL rather than `/mnt/c` when I/O matters. |
| GPU driver branch | **Current NVIDIA Studio Driver, WHQL** | **Selected baseline** | Stability is the priority; switch to Game Ready only for a demonstrated game-specific need. |
| OS security/virtualization baseline | **UEFI + Secure Boot + TPM 2.0 + BitLocker after firmware stabilization + SVM for WSL2/Hyper-V** | **Selected** | Establish firmware baseline before BitLocker and retain recovery key independently. |
| Future local AI expansion | Preserve a credible path to a **very high-performance, high-VRAM single discrete GPU** | **Selected** | AI remains secondary; reopen the platform only if serious multi-GPU requirements emerge. |
| GPU | Reuse existing NVIDIA GeForce RTX 3060 12 GB initially | **Selected** | Fixed input to the initial build. |
| Cost / longevity philosophy | Prefer to remain meaningfully below 30,000 lei; higher spend must earn long-term reliability, stability, endurance, serviceability or productivity benefit | **Selected** | Stability/conservative operation take precedence over short-lived benchmark gains. |
| Procurement consolidation | **Maximum three providers; default target two** | **Selected** | Ordering, delivery, invoices and future warranty/RMA relationships have real ownership cost. Add a third provider only for roughly ≥300 lei net saving, materially better stock, exact-SKU/revision certainty or materially better warranty. Do not fragment the order for 50–150 lei savings. |
| Current provider plan | **EvoMAG primary + Altex for explicit-current Seasonic PSU** | **Selected purchase plan** | EvoMAG currently covers CPU, motherboard, RAM, cooler, SSD, case, exact single Noctua rear fan, UPS and Retail Windows at competitive aggregate pricing. Altex provides the clean explicit ATX 3.1 Seasonic listing. If EvoMAG confirms its VERTEX unit is current ATX 3.1/PCIe 5.1/12V-2x6 before shipment, consolidate to one provider. A third provider is conditional, most plausibly for the UPS if the saving exceeds the complexity threshold. |

## Open / deferred decisions

- eventual 256 GB DIMM implementation: exact 4×64 GB modules, operating rate and ECC/non-ECC verdict;
- operationally complete system-level ECC/OS reporting if ECC is used;
- exact 4 TB-or-larger work-drive model;
- exact container-runtime/tooling choice if licensing/workflow requirements make that material.

Detailed Phase-1 memory: `docs/components/memory.md`.

Detailed PSU: `docs/components/psu.md`.

Detailed OS/bring-up: `docs/components/os.md`.

Current purchase execution plan: `docs/procurement-plan-2026-08-31.md`.
