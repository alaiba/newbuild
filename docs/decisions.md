# Decision Log

This file records **closed decisions only**, together with rationale and reopen conditions.

## Current closed decisions

| Area | Decision | Status | Rationale / reopen condition |
|---|---|---|---|
| CPU / platform | **AMD Ryzen 9 9950X3D on AM5** | **Selected** | A 9950X saves roughly 650 lei but does not improve the stability/endurance goal, is not better in the relevant compile evidence, and sacrifices substantial gaming performance. Keep the permanent CPU. |
| Motherboard | **ASUS ProArt X870E-Creator WiFi** | **Selected** | The cheaper X870 Taichi Creator saves roughly 900–1,000+ lei but gives up the strongest explicit vendor/firmware evidence found for 4×64 GB / 256 GB and ECC-oriented stability. |
| Memory architecture | **Credible 256 GB endpoint, expected 4×64 GB** | **Selected** | Prefer ECC only if exact modules, four-DIMM stability and OS-visible reporting are credible; otherwise validated non-ECC. |
| Phase-1 memory | **64 GB, 2×32 GB** | **Selected** | Appropriate development/VM/container headroom without distorting permanent component spend. |
| Phase-1 exact RAM target | **Crucial `CT2K32G56C46U5`, DDR5-5600 CL46, 1.1 V** | **Selected** | Conservative electrical profile and strong current value. Exact `...U5` desktop SKU required. Kingston `KF556C36BBEK2-64` is reconsidered only if its premium shrinks to roughly 200–250 lei. |
| CPU cooling | **Noctua NH-D15 G2 standard + 7 mm AM5 offset** | **Selected** | Cheaper Thermalright options are strong, but Noctua's support/mounting ecosystem, fan endurance and six-year warranty better match 10-year ownership. |
| Storage architecture | **2 TB system/tools SSD now + future 4 TB+ work SSD** | **Selected** | Avoids unnecessary capacity spend while preserving separate work-drive and Gen5 choice later. |
| System SSD | **Samsung 990 PRO 2 TB `MZ-V9P2T0BW` in `M.2_3`** | **Selected** | KC3000 saves too little; 9100 PRO costs more but its PCIe 5 bandwidth would be wasted in the selected PCIe 4 system slot or consume the reserved `M.2_1` future work slot. |
| PSU architecture | **1200 W ATX 3.1 / PCIe 5.1 / 12V-2x6** | **Selected** | Correct margin for a future single ~600 W GPU without unnecessary 1300–1600 W oversizing. |
| PSU baseline | **Seasonic VERTEX GX-1200 current ATX 3.1 revision** | **Selected / purchase-ready** | 12-year warranty, compact 160 mm chassis and explicit Altex ATX 3.1 listing. |
| PSU premium rule | **Prefer VERTEX PX-1200 when current stock is available at ≤~200 lei premium over GX** | **Selected purchase rule** | At the current ~160 lei reference premium, Platinum efficiency is worthwhile over long ownership. Do not delay the build while PX is out of stock. |
| Chassis | **Fractal North XL Mesh `FD-C-NOR1X-01`** | **Selected** | Excellent airflow/serviceability/future-GPU envelope; current EvoMAG exact-SKU pricing strengthens value. |
| Airflow | **3×140 mm included front intake + 1× Noctua NF-A14x25 G2 PWM rear exhaust** | **Selected** | Simple positive-pressure layout. Exact Noctua fan is available from primary provider, so no endurance downgrade is needed for consolidation. |
| UPS | **CyberPower PR1500ELCD, 1500 VA / 1350 W** | **Selected** | Replaces CP1600EPFCLCD after lifetime-value review. Future 900–980 W system would put a 1000 W UPS near full load; PR1500 runs it around 67–73%, adds longer runtime, stronger AVR behavior and hot-swappable battery serviceability, and may eliminate a later UPS replacement. |
| Host OS | **Windows 11 Pro x64** | **Selected** | Best fit for development, virtualization, NVIDIA/gaming and professional host features. |
| Windows license channel | **Retail/FPP** | **Selected / required purchase** | Clean DIY licensing path; no existing transferable license. |
| Windows consolidated SKU | **`HAV-00197` Romanian Retail/FPP USB from EvoMAG** | **Selected purchase target** | Equivalent Pro Retail/FPP rights; Windows 11 Pro can add/switch to English display language. Paying roughly 50–75 lei over the lowest English package removes a third retailer relationship. `HAV-00163` English FPP remains fallback. |
| Initial Windows release | **Windows 11 25H2 GA** | **Selected** | Production baseline; follow normal supported feature updates afterward. |
| Linux environment | **WSL2 + Ubuntu 26.04.1 LTS** | **Selected** | First-class Linux userland without dual-boot friction. |
| GPU driver | **NVIDIA Studio Driver WHQL baseline** | **Selected** | Stability-first; Game Ready only for a demonstrated game-specific need. |
| Security/virtualization | **UEFI + Secure Boot + TPM 2.0 + SVM/IOMMU + BitLocker after firmware stabilization** | **Selected** | Conservative production baseline. |
| GPU | **Reuse RTX 3060 12 GB initially** | **Selected** | Future high-VRAM GPU remains deferred. |
| Future AI path | **One very high-performance/high-VRAM discrete GPU** | **Selected architecture** | Do not optimize current AM5 build for serious multi-GPU workloads. |
| Cost philosophy | **Optimize utility per leu, including justified premium upgrades** | **Selected** | Utility explicitly includes stability, endurance, serviceability, warranty, thermal/electrical margin, workload performance and avoiding future replacement—not just benchmark speed or lowest purchase price. |
| Provider consolidation | **Maximum 3 providers; default target 2** | **Selected** | Logistics, invoices and RMA relationships are ownership costs. Provider #3 needs roughly ≥300 lei net saving or materially better stock/SKU/revision/warranty certainty. |
| Current provider plan | **EvoMAG primary + Altex PSU** | **Selected purchase plan** | EvoMAG covers CPU, board, RAM, cooler, SSD, case, fan, PR1500ELCD and Retail Windows. Altex provides explicit-current Seasonic GX. If EvoMAG can verify a current VERTEX revision, one-provider procurement is acceptable. |

## Open / deferred decisions

- eventual 256 GB exact matched DIMMs, operating rate and ECC/non-ECC verdict;
- operational ECC reporting if ECC is used;
- exact future 4 TB+ work-drive model;
- future high-VRAM GPU;
- exact container runtime if licensing/workflow makes it material.

Detailed component dossiers are under `docs/components/`.

Current purchase execution plan: `docs/procurement-plan-2026-08-31.md`.
