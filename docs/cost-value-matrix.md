# Cost / Value Matrix

This is the build-level decision matrix for comparing component choices and upgrades across more than raw benchmark performance.

The build is intended to be a long-lived professional workstation. Cost matters, but the preferred choice is the one that provides the strongest durable value across performance, stability, reliability, endurance, serviceability and expansion over the expected ownership period.

## How to read this matrix

For each decision, evaluate:

- **Incremental cost** — extra purchase cost versus the relevant baseline or cheaper credible alternative.
- **Performance benefit** — improvement in workloads that actually matter: Java/Gradle/Maven builds, tests, IDE responsiveness, Android Studio, containers, VMs and future AI workloads.
- **Reliability / stability benefit** — reduction in operational risk, better memory behavior, power/thermal headroom, mature firmware, error detection/correction, recovery features, etc.
- **Endurance / serviceability benefit** — component lifetime, replaceability, firmware support, maintainability and expected useful life.
- **Expansion / future value** — whether the spend preserves materially useful future options such as larger memory, additional NVMe storage, 10 GbE or a high-end AI GPU.
- **10-year value** — whether the incremental cost is likely to remain useful over the intended long ownership horizon.

Performance figures must not be mixed across unrelated benchmark suites or software versions as if they were directly comparable. Where evidence is incomplete, use qualitative ratings and mark the item for later validation.

## Decision-state rule

This matrix distinguishes between **closed selections** and **provisional / aspirational targets**.

A provisional target is the best current candidate given the evidence available, but it must not be treated as sunk cost or a fixed dependency. It should be promoted to a closed selection only after its important cross-component dependencies are sufficiently validated.

For the motherboard specifically, the preferred board should remain provisional until the exact 256 GB memory path, ECC verdict, PCIe/M.2 topology, future high-end-GPU path and firmware maturity have been checked. If later memory/storage/case/PSU work exposes a material weakness, the board should be replaced rather than forcing the rest of the build around it.

For memory, distinguish **initial purchase capacity** from the **architectural endpoint**. The build may begin at 64–128 GB while still requiring the motherboard/platform to preserve a credible 256 GB path.

## Current decision matrix

| Decision / option | Incremental cost | Performance benefit | Reliability / stability | Endurance / serviceability | Expansion / future value | 10-year value | Status / verdict |
|---|---:|---|---|---|---|---|---|
| **Ryzen 9 9950X3D + AM5** | Baseline | Excellent mixed workstation performance; strong Java/build throughput and interactive responsiveness; excellent gaming | Strong when operated conservatively; mature AM5 ecosystem is a major factor | Mainstream parts ecosystem and broad replacement availability | Up to 256 GB system memory; adequate PCIe for a powerful single-GPU AI system | **High** | **Selected** |
| Threadripper 9960X + TRX50 | Approx. +7–8k lei 5-year TCO versus 9950X3D platform from Aug 2026 analysis; refresh before purchase | Potentially materially faster in highly parallel builds/tests; much less benefit in ordinary IDE/interactive work | RDIMM platform and four memory channels are workstation strengths | Strong workstation platform, but higher power/cooling complexity and more specialized replacement ecosystem | Much stronger PCIe and memory-bandwidth headroom | Medium for this workload | **Rejected** — extra throughput and workstation specialization do not justify TCO for the current mixed workload |
| **64 GB initial memory floor (2×32 GB)** | **Initial baseline** | Already doubles the current working capacity; enough for serious Java/Android development, IDEs, builds, Docker/WSL2 and ordinary emulator/service concurrency | **Strong initial stability posture** from two-DIMM loading; much easier target than four high-density DIMMs | Initial kit can be replaced later without redesigning the workstation | Preserves budget for harder-to-replace platform components while motherboard still targets 256 GB | **High as a budget-control mechanism** | **Selected minimum initial configuration** |
| 96 GB initial memory (2×48 GB) | TBD versus 64 GB | More concurrency/headroom before memory pressure | Similar two-DIMM stability advantages | Can remain useful longer before replacement | More runway while still preserving 256 GB endpoint | Potentially high | Candidate if price premium is modest |
| 128 GB initial memory (2×64 GB) | TBD versus 64/96 GB | Substantial immediate headroom for JVMs, VMs, containers and Android tooling | Two-DIMM configuration is attractive electrically; exact ECC/non-ECC path TBD | May defer the need for 256 GB upgrade | Uses DIMM density relevant to eventual 256 GB validation | High if price is reasonable | Candidate, but not required to preserve the rest of the build |
| **256 GB system memory endpoint** | Deferred until price/stability justify purchase | Capacity benefit rather than direct speed; allows large JVM heaps, concurrent IDEs/services/VMs/containers and future AI support workflows without paging pressure | Potentially strong if configuration is validated conservatively; four-DIMM AM5 stability is the main technical risk | High capacity should remain useful throughout ownership period | Preserves substantial local development/VM/data/AI headroom | **Potentially very high** | **Architectural target selected; not mandatory day-one purchase** |
| ECC UDIMM at 256 GB | TBD | No meaningful performance advantage; may have small implementation-specific cost/latency trade-offs | **Potentially high**: protects against correctable memory errors and improves data-integrity story if ECC is truly end-to-end and OS-visible | Strong fit for long-lived 256 GB workstation if supported reliably | Helpful for long-running JVM/VM/database/AI workloads | Potentially high | **Strong preference / under review** — require stable 256 GB configuration and real error reporting, not merely DIMMs that boot |
| Non-ECC UDIMM at 256 GB | Baseline memory alternative | Potentially easier availability and/or higher clocks | Acceptable if thoroughly validated, but lacks system-level ECC protection | Good if conservative, high-quality DIMMs are used | Same capacity; less data-integrity protection | Medium-high | Fallback if ECC implementation or availability compromises stability |
| **ASUS ProArt X870E-Creator WiFi** | Approx. **2.68–2.90k lei** current RO snapshot; roughly **+0.9–1.1k lei** versus X870 Taichi Creator | No meaningful CPU-performance advantage | **Current strongest evidence for our hardest requirement:** explicit 4×64 GB / 256 GB firmware work, repeated four-DIMM/training/stability updates, ECC support and ECC-specific 2026 firmware work | Good recovery features and mature firmware trail; premium must be justified by reduced configuration uncertainty rather than prestige | 10 GbE + 2.5 GbE, USB4, x8/x8; four M.2, but M.2_2 consumes part of the CPU graphics-lane group | **High if its stronger 256 GB/ECC validation proves material** | **Provisional / aspirational motherboard target** — not selected; exact RAM validation is the next gate |
| **ASRock X870 Taichi Creator** | Approx. **1.69–1.82k lei** current RO snapshot; ~0.9–1.1k lei below ProArt | No meaningful CPU-performance disadvantage | ECC capable; current firmware includes memory/boot improvements. Exact 4×64 GB ECC evidence is currently less explicit than ASUS | **Strong diagnostics/serviceability:** Dr. Debug, onboard controls, Flashback, rear Clear CMOS; strong thermal headroom | **Excellent:** 10 GbE + 5 GbE, x8/x8, cleaner single-GPU + multi-NVMe topology than ProArt; current firmware explicitly addresses workstation-GPU compatibility | **Potentially very high** | **Live challenger / fallback** — can overtake ProArt if exact 256 GB ECC configuration validates cleanly |
| **MSI MAG X870 Tomahawk WiFi** | Approx. **1.43–1.67k lei** for competitive current RO offers | No meaningful CPU-performance disadvantage | Credible 4×64 GB qualification exists and board thermals are good, but **no system-level ECC** | Good mainstream recovery/serviceability | 5 GbE, USB4, four M.2; lacks CPU-connected x8/x8 and onboard 10 GbE | Medium-high | **Value/control reference** — useful sanity check, but capability savings are difficult to justify when Taichi Creator is near its price class |
| B850 motherboard class | Likely lowest eligible cost | No inherent CPU-performance disadvantage if implementation is sufficient | Board-specific | Board-specific | May constrain PCIe/I/O/AI expansion depending on topology | TBD | No current finalist; retain as conceptual lower-bound only unless a board materially changes the comparison |
| X870 motherboard class | Moderate premium | No inherent CPU-performance gain versus competent B850 | Board-specific | Board-specific | Can provide workstation-class topology/features depending on implementation | High on Taichi Creator | **Strong current value class** because X870 Taichi Creator provides ECC, x8/x8 and 10 GbE without X870E pricing |
| X870E motherboard class | Higher premium | No inherent CPU-performance gain versus competent lower-tier board | Can be justified by board implementation, firmware and recovery features, not chipset name alone | Potentially stronger long-term I/O/expansion story | Strong, but board-specific lane sharing matters more than chipset label | Potentially high | ProArt currently leads because of **memory/ECC evidence**, not because X870E is intrinsically required |
| Onboard 10 GbE | Included on both leading Creator boards | No application performance benefit unless network workload can exploit it | Avoids dependence on an add-in NIC if controller/driver quality is good | Fewer add-in parts; controller quality and thermals still require validation | Preserves a PCIe slot for another device; useful over long ownership horizon | Potentially high | Preferred when bundled sensibly; validate AQC113 drivers/firmware during bring-up |
| **Airflow-first chassis strategy** | Usually modest versus restrictive/showcase alternatives; exact case delta TBD | Little direct benchmark benefit unless thermal limits are reached; improves sustained behavior under long loads | **High**: lower VRM/RAM/SSD/GPU temperatures, more thermal margin, less dependence on aggressive fan curves | **High**: large standard fans, easy filters and spacious serviceable layout support long ownership | Strong future high-power GPU/cooling/PSU compatibility when chassis envelope is generous | **High** | **Selected design principle** — exact case/fan layout remains open |
| Future single high-VRAM AI GPU | Future spend; excluded from current initial BOM | Potentially transformative for local AI inference/fine-tuning/training workloads | Requires PSU, chassis and cooling headroom | GPU can be replaced independently of core platform | **Primary AI expansion path**; AM5 is adequate for one very powerful GPU | High if AI objective materializes | Secondary objective; preserve compatibility now, buy GPU later |
| Serious multi-GPU AI platform | Very high future cost | High for workloads that scale across accelerators | Requires platform/chassis/power architecture designed for it | Specialized workstation/server territory | AM5 becomes a meaningful constraint due to PCIe/slot/power topology | Low as a current pre-purchase investment | Do **not** optimize current build for this; reopen platform decision if future workload requires it |

## Motherboard cost/value interpretation

The current motherboard contest is deliberately **not** simply premium versus value:

- the **ProArt premium** buys the strongest explicit vendor evidence we have found for 4×64 GB / 256 GB and ongoing ECC-specific firmware work;
- the **Taichi Creator saving** does not buy a weaker feature set — it actually has cleaner PCIe/storage topology, better POST diagnostics and 10 GbE + 5 GbE — but its exact 4×64 GB ECC evidence still needs to be proven to the same confidence level;
- the **MSI saving versus the Taichi Creator is relatively small** in current Romanian pricing, while giving up ECC, CPU x8/x8 and 10 GbE.

Therefore the next memory review can materially change the ranking. If the ASRock proves equally stable with a credible 256 GB ECC configuration, its lower price and topology advantages are durable enough that it would likely become the better 10-year value. If it does not, paying roughly 1,000 lei more for the ProArt may be justified as risk reduction on a 256 GB workstation.

## Memory cost/value interpretation

Memory is now explicitly the preferred **budget-release valve**:

- **64 GB (2×32 GB)** is enough to start productively and already doubles the current working capacity;
- spending more for 96 or 128 GB is optional and should be driven by current price/value, not by architectural necessity;
- **256 GB remains the endpoint**, but buying it immediately is not worth distorting the rest of the build when high-density DDR5 pricing is disproportionate;
- the initial kit should be treated as replaceable, so the eventual 256 GB configuration can be chosen from the best validated matched set available at that time rather than being constrained by sunk cost.

This preserves the motherboard, chassis, cooling, storage and PSU quality while keeping the initial system within budget.

## Component-level matrix to complete

| Area | Baseline / value option | Premium option(s) | Cost delta | Measured workload benefit | Reliability/endurance benefit | Expansion/longevity benefit | Decision |
|---|---|---|---:|---|---|---|---|
| Motherboard | MSI MAG X870 Tomahawk WiFi | **ASRock X870 Taichi Creator** / **ASUS ProArt X870E-Creator WiFi** | MSI→ASRock roughly +0–0.4k lei at competitive offers; ASRock→ASUS roughly +0.9–1.1k lei | Essentially none in CPU throughput at stock | ASUS currently strongest 256 GB/ECC firmware evidence; ASRock stronger diagnostics and needs exact RAM validation | ASRock/ASUS add ECC, CPU x8/x8 and 10 GbE; ASRock has cleaner NVMe/GPU sharing | **ProArt provisional target; Taichi Creator live challenger; MSI control** |
| Memory kit | **64 GB 2×32 GB minimum** | 96 GB 2×48 / 128 GB 2×64 initial; eventual 256 GB matched configuration | TBD from current market | More capacity mainly increases concurrency/headroom | Two-DIMM initial config is conservative; eventual ECC may add data-integrity protection | Platform still preserves 256 GB endpoint | **64 GB floor selected; exact initial kit is next research step** |
| Cooling | TBD | TBD | TBD | Sustained clock/acoustic differences TBD | Pump/fan/serviceability trade-offs TBD | TBD | Open |
| Storage | TBD | High-endurance / higher-capacity options | TBD | Build/cache/VM I/O differences TBD | TBW, firmware, thermal/data-integrity differences TBD | Capacity/endurance headroom TBD | Open |
| PSU | TBD | Higher-quality / higher-headroom option | TBD | None directly | Electrical quality, thermal margin and warranty TBD | Future high-power GPU support TBD | Open |
| Case / airflow | Airflow-first spacious conventional chassis | Premium airflow/serviceability options | TBD | Mainly sustained thermal/acoustic margin | Lower component temperatures; easy filtration; standard replaceable fans | Future large/high-power GPU, E-ATX and cooling headroom | **Strategy selected; exact case provisional/open** |
| UPS | TBD | TBD | TBD | None directly | Power-event protection and graceful shutdown TBD | Protects long-lived investment | Open |

## Cost policy

The preferred build should remain meaningfully below **30,000 lei** if that can be achieved without compromising the technical goals.

The 30,000 lei figure is a planning level, not a hard cap and not a spending target. If the build approaches or exceeds it, every material premium should have a concrete and durable justification in one or more of:

- meaningful workload performance;
- stability or data integrity;
- reliability or component endurance;
- thermal/acoustic headroom;
- serviceability;
- expansion capability; or
- credible usefulness over the intended approximately 10-year ownership period.

Short-lived benchmark gains, prestige features and extreme-overclocking capability do not justify major cost increases for this build.

## Update rule

Whenever a component decision is researched or closed:

1. add or update its row here;
2. record current Romanian/EU price and the relevant cheaper/premium comparison;
3. separate measured benchmark evidence from inference;
4. document what the price premium materially buys;
5. record whether the benefit is expected to remain useful over the 10-year horizon;
6. use **Provisional target** when important dependent validation is still outstanding;
7. promote a provisional target to **Selected** only after its promotion gates are satisfied; and
8. keep rejected expensive alternatives when they are useful reference points for future reconsideration.
