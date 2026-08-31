# Decision Log

This file records closed decisions plus any decision explicitly reopened because a requirement changed.

## Current decisions

| Area | Decision | Status | Rationale / reopen condition |
|---|---|---|---|
| CPU / platform | **AMD Ryzen 9 9950X3D on AM5** | **Selected** | A 9950X saves roughly 650 lei but does not improve the stability/endurance goal, is not better in the relevant compile evidence, and sacrifices substantial gaming performance. Keep the permanent CPU. |
| Motherboard | **Exact motherboard reopened; ASUS ProArt X870E-Creator WiFi remains the incumbent reference** | **Reopened** | The ProArt was promoted largely because of the difficult 4×64 GB / 256 GB requirement. That requirement is now removed. Re-optimize the board against the final 128 GB 2×64 GB / 1DPC target and the finalized two-drive storage topology before purchase. No replacement is selected yet. |
| Final memory capacity | **128 GB from day one** | **Selected / final** | There is no provisional RAM stage. Buy the intended lifetime capacity at initial assembly rather than buying 64 GB now and replacing or expanding it later. |
| Final memory topology | **2×64 GB DDR5 UDIMM, one DIMM per channel (1DPC), installed A2/B2** | **Selected / final** | 128 GB is sufficient as the lifetime target and 2×64 preserves the electrically favorable 1DPC topology. This avoids the four-DIMM training/frequency compromises that drove much of the previous 256 GB motherboard analysis. |
| Exact memory kit | **2×64 GB exact SKU to be selected in the next optimization pass** | **Open** | Optimize for stability first: conservative JEDEC behavior, board validation/QVL evidence, low voltage, module construction, warranty and, if worthwhile, end-to-end ECC support/reporting. Do not buy a temporary 2×32 GB kit. |
| ECC policy | **ECC is optional, not a capacity requirement** | **Open within RAM optimization** | With 2×64 GB, ECC can be evaluated on its own merits. Prefer ECC UDIMM only if exact-module board support and usable OS-level error reporting are credible without materially worsening value or stability. |
| CPU cooling | **Noctua NH-D15 G2 standard + 7 mm AM5 offset** | **Selected** | Cheaper Thermalright options are strong, but Noctua's support/mounting ecosystem, fan endurance and six-year warranty better match 10-year ownership. |
| Storage architecture | **Two internal NVMe drives from day one: ~1 TB system/tools + 4 TB work/data** | **Selected / final architecture** | Separate OS/tools from write-heavy development data immediately. The old staged 2 TB-now / 4 TB-later plan is superseded. Storage capacity remains additively expandable later without replacing either initial drive. |
| System SSD role | **~1 TB value/reliability-focused NVMe; exact model open** | **Selected role / model open** | With 128 GB RAM and a dedicated work SSD, the OS drive does not justify flagship sequential performance. Optimize for adequate headroom, mature firmware, reputable vendor, warranty and sensible price. A chipset-connected x4 M.2 slot is acceptable. |
| Work SSD role | **4 TB high-quality NVMe from day one; Gen4 TLC preferred; exact model open** | **Selected role / model open** | Repositories, Maven/Gradle caches, WSL2/container data, Android SDK/AVDs, VMs, databases, games and similar high-I/O/high-capacity data belong here. Prefer CPU-direct x4, TLC, strong sustained behavior/endurance and mature firmware. Gen5 is not required and is justified only by negligible premium or demonstrated workload benefit. |
| Storage RAID policy | **No RAID required** | **Selected** | Independent drives plus version control and real external/network backup are preferred. RAID1 does not replace backup and adds complexity without solving the main failure modes. |
| PSU architecture | **1200 W ATX 3.1 / PCIe 5.1 / 12V-2x6** | **Selected** | Correct margin for a future single ~600 W GPU without unnecessary 1300–1600 W oversizing. |
| PSU baseline | **Seasonic VERTEX GX-1200 current ATX 3.1 revision** | **Selected / purchase-ready** | 12-year warranty, compact 160 mm chassis and explicit Altex ATX 3.1 listing. |
| PSU premium rule | **Prefer VERTEX PX-1200 when current stock is available at ≤~200 lei premium over GX** | **Selected purchase rule** | At the current ~160 lei reference premium, Platinum efficiency is worthwhile over long ownership. Do not delay the build while PX is out of stock. |
| Chassis | **Fractal North XL Mesh `FD-C-NOR1X-01`** | **Selected** | Excellent airflow/serviceability/future-GPU envelope. |
| Airflow | **3×140 mm included front intake + 1× Noctua NF-A14x25 G2 PWM rear exhaust** | **Selected** | Simple positive-pressure layout; add fans only if measurements justify them. |
| UPS | **CyberPower PR1500ELCD, 1500 VA / 1350 W** | **Selected** | Future 900–980 W system load remains comfortably below its real-power ceiling; hot-swappable battery and stronger AVR improve lifetime value. |
| Host OS | **Windows 11 Pro x64** | **Selected** | Best fit for development, virtualization, NVIDIA/gaming and professional host features. |
| Windows license channel | **Retail/FPP** | **Selected / required purchase** | Clean DIY licensing path; no existing transferable license. |
| Windows purchase target | **`HAV-00163` English Retail/FPP USB from PROstore** | **Selected purchase target** | Verified direct listing, clear Retail/FPP provenance and low delivered cost. Windows has negligible long-term RMA complexity, so a separate provider is acceptable. |
| Initial Windows release | **Windows 11 25H2 GA** | **Selected** | Production baseline; follow normal supported feature updates afterward. |
| Linux environment | **WSL2 + Ubuntu 26.04.1 LTS** | **Selected** | First-class Linux userland without dual-boot friction. |
| GPU driver | **NVIDIA Studio Driver WHQL baseline** | **Selected** | Stability-first; Game Ready only for a demonstrated game-specific need. |
| Security/virtualization | **UEFI + Secure Boot + TPM 2.0 + SVM/IOMMU + BitLocker after firmware stabilization** | **Selected** | Conservative production baseline. |
| GPU | **Reuse RTX 3060 12 GB initially** | **Selected** | Future high-VRAM GPU remains deferred. |
| Future AI path | **One very high-performance/high-VRAM discrete GPU** | **Selected architecture** | Do not optimize current AM5 build for serious multi-GPU workloads. |
| Cost philosophy | **Optimize utility per leu; do not spend for benchmark prestige** | **Selected** | Utility includes stability, endurance, serviceability, warranty, thermal/electrical margin and workload performance. Premiums must buy a material benefit for this workload or avoid a credible future replacement. |
| Provider consolidation | **Maximum 3 providers; default target 2 for hardware** | **Selected** | Hardware provider #3 normally needs roughly ≥300 lei net saving or materially better stock/SKU/revision/warranty certainty. Software such as Windows is exempt when the extra provider has negligible RMA burden. |

## Explicitly superseded decisions

### Memory

The following are no longer part of the build:

- 64 GB / 2×32 GB Phase-1 memory;
- Crucial `CT2K32G56C46U5` as a purchase target;
- 256 GB / 4×64 GB as the planned endpoint;
- the assumption that initial RAM is temporary or disposable;
- motherboard premiums justified primarily by four-DIMM / 256 GB behavior.

### Storage

The following are no longer part of the build:

- Samsung 990 PRO 2 TB `MZ-V9P2T0BW` as a selected system-drive purchase;
- a 2 TB system/tools drive bought first to carry the initial working set;
- deferring the dedicated 4 TB work drive to a later phase;
- reserving Gen5 performance as a requirement for the work drive.

## Open / deferred decisions

- exact motherboard after re-optimization for the 128 GB 1DPC and finalized two-drive storage topology;
- exact matched 2×64 GB RAM kit and ECC/non-ECC verdict;
- exact ~1 TB system SSD;
- exact 4 TB work SSD;
- exact future high-VRAM GPU;
- exact container runtime if licensing/workflow makes it material.

Detailed component dossiers are under `docs/components/`.

Current purchase execution plan: `docs/procurement-plan-2026-08-31.md`.
