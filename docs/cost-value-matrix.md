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

For memory, distinguish **Phase-1 commissioning memory** from the **architectural endpoint**. The build may begin with any stable 32 GB-or-larger configuration while still requiring the motherboard/platform to preserve a credible 256 GB path.

For cooling, distinguish the **selected architecture** from the exact model. High-end air cooling is selected; the exact tower remains provisional until motherboard/RAM/case clearance and current pricing are confirmed.

For storage, distinguish the **selected two-drive architecture** from the purchase schedule. The permanent 2 TB system SSD is bought initially; the 4 TB-or-larger work drive is added later when capacity or price/value justifies it.

## Current decision matrix

| Decision / option | Incremental cost | Performance benefit | Reliability / stability | Endurance / serviceability | Expansion / future value | 10-year value | Status / verdict |
|---|---:|---|---|---|---|---|---|
| **Ryzen 9 9950X3D + AM5** | Baseline | Excellent mixed workstation performance; strong Java/build throughput and interactive responsiveness; excellent gaming | Strong when operated conservatively; mature AM5 ecosystem is a major factor | Mainstream parts ecosystem and broad replacement availability | Up to 256 GB system memory; adequate PCIe for a powerful single-GPU AI system | **High** | **Selected** |
| Threadripper 9960X + TRX50 | Approx. +7–8k lei 5-year TCO versus 9950X3D platform from Aug 2026 analysis; refresh before purchase | Potentially materially faster in highly parallel builds/tests; much less benefit in ordinary IDE/interactive work | RDIMM platform and four memory channels are workstation strengths | Strong workstation platform, but higher power/cooling complexity and more specialized replacement ecosystem | Much stronger PCIe and memory-bandwidth headroom | Medium for this workload | **Rejected** — extra throughput and workstation specialization do not justify TCO for the current mixed workload |
| **32 GB Phase-1 commissioning memory** | **Initial baseline** | No intentional performance uplift versus the current working environment; sufficient to commission and use the new platform | A simple 1- or 2-DIMM configuration is easy to stabilize; 2×16 GB preferred when similarly priced | Explicitly temporary/replaceable; minimize sunk cost | Frees budget for harder-to-replace platform components while motherboard still targets 256 GB | **Very high as a budget-control mechanism** | **Selected Phase-1 floor** |
| 48–128 GB temporary memory | TBD versus 32 GB | More concurrency/headroom before memory pressure | Still easy to operate conservatively with one or two DIMMs | May remain useful longer before replacement | More runway, but no architectural requirement | Medium-high only if incremental price is attractive | Optional; do not pay heavily for temporary capacity |
| **256 GB system memory endpoint** | Deferred until price/stability justify purchase | Capacity benefit rather than direct speed; allows large JVM heaps, concurrent IDEs/services/VMs/containers and future AI support workflows without paging pressure | Potentially strong if configuration is validated conservatively; four-DIMM AM5 stability is the main technical risk | High capacity should remain useful throughout ownership period | Preserves substantial local development/VM/data/AI headroom | **Potentially very high** | **Architectural target selected; not mandatory day-one purchase** |
| ECC UDIMM at 256 GB | TBD | No meaningful performance advantage; may have small implementation-specific cost/latency trade-offs | **Potentially high**: protects against correctable memory errors and improves data-integrity story if ECC is truly end-to-end and OS-visible | Strong fit for long-lived 256 GB workstation if supported reliably | Helpful for long-running JVM/VM/database/AI workloads | Potentially high | **Strong preference / under review** — require stable 256 GB configuration and real error reporting, not merely DIMMs that boot |
| Non-ECC UDIMM at 256 GB | Baseline memory alternative | Potentially easier availability and/or higher clocks | Acceptable if thoroughly validated, but lacks system-level ECC protection | Good if conservative, high-quality DIMMs are used | Same capacity; less data-integrity protection | Medium-high | Fallback if ECC implementation or availability compromises stability |
| **ASUS ProArt X870E-Creator WiFi** | Approx. **2.68–2.90k lei** current RO snapshot; roughly **+0.9–1.1k lei** versus X870 Taichi Creator | No meaningful CPU-performance advantage | **Current strongest evidence for our hardest requirement:** explicit 4×64 GB / 256 GB firmware work, repeated four-DIMM/training/stability updates, ECC support and ECC-specific 2026 firmware work | Good recovery features and mature firmware trail; premium must be justified by reduced configuration uncertainty rather than prestige | 10 GbE + 2.5 GbE, USB4, x8/x8; selected storage layout avoids its M.2_2 graphics-lane sharing | **High if its stronger 256 GB/ECC validation proves material** | **Provisional / aspirational motherboard target** — not selected; exact RAM validation remains the main gate |
| **ASRock X870 Taichi Creator** | Approx. **1.69–1.82k lei** current RO snapshot; ~0.9–1.1k lei below ProArt | No meaningful CPU-performance disadvantage | ECC capable; current firmware includes memory/boot improvements. Exact 4×64 GB ECC evidence is currently less explicit than ASUS | **Strong diagnostics/serviceability:** Dr. Debug, onboard controls, Flashback, rear Clear CMOS; strong thermal headroom | **Excellent:** 10 GbE + 5 GbE, x8/x8; selected M2_3 + M2_1 storage layout avoids its USB4/M2_2 trade-off | **Potentially very high** | **Live challenger / fallback** — can overtake ProArt if exact 256 GB ECC configuration validates cleanly |
| **MSI MAG X870 Tomahawk WiFi** | Approx. **1.43–1.67k lei** for competitive current RO offers | No meaningful CPU-performance disadvantage | Credible 4×64 GB qualification exists and board thermals are good, but **no system-level ECC** | Good mainstream recovery/serviceability | 5 GbE, USB4, four M.2; lacks CPU-connected x8/x8 and onboard 10 GbE | Medium-high | **Value/control reference** — useful sanity check, but capability savings are difficult to justify when Taichi Creator is near its price class |
| B850 motherboard class | Likely lowest eligible cost | No inherent CPU-performance disadvantage if implementation is sufficient | Board-specific | Board-specific | May constrain PCIe/I/O/AI expansion depending on topology | TBD | No current finalist; retain as conceptual lower-bound only unless a board materially changes the comparison |
| X870 motherboard class | Moderate premium | No inherent CPU-performance gain versus competent B850 | Board-specific | Board-specific | Can provide workstation-class topology/features depending on implementation | High on Taichi Creator | **Strong current value class** because X870 Taichi Creator provides ECC, x8/x8 and 10 GbE without X870E pricing |
| X870E motherboard class | Higher premium | No inherent CPU-performance gain versus competent lower-tier board | Can be justified by board implementation, firmware and recovery features, not chipset name alone | Potentially stronger long-term I/O/expansion story | Strong, but board-specific lane sharing matters more than chipset label | Potentially high | ProArt currently leads because of **memory/ECC evidence**, not because X870E is intrinsically required |
| Onboard 10 GbE | Included on both leading Creator boards | No application performance benefit unless network workload can exploit it | Avoids dependence on an add-in NIC if controller/driver quality is good | Fewer add-in parts; controller quality and thermals still require validation | Preserves a PCIe slot for another device; useful over long ownership horizon | Potentially high | Preferred when bundled sensibly; validate AQC113 drivers/firmware during bring-up |
| **High-end air cooling** | Architecture-level choice | Sufficient sustained CPU performance at stock/conservative power; no need to trade reliability for uncapped/PBO headroom | **High:** removes pump/liquid/radiator dependencies while retaining adequate thermal margin | **Very high:** heatsink body has no active wear item; standard fans can be replaced independently | Leaves front intake unobstructed for future GPU and does not constrain case around a radiator | **High** | **Selected cooling architecture** |
| **Noctua NH-D15 G2 LBC** | Roughly **0.64–0.85k lei** for standard G2 in RO; LBC may require EU sourcing | Best current 9950X3D noise-normalized air-cooling evidence; enough for stock/conservative operation | Strong AM5-specific contact/mounting design; avoids pump failure mode | 6-year warranty, premium replaceable 140 mm fans, long-running Noctua mounting/support ecosystem | 168 mm height fits all current serious case candidates | **High** | **Provisional exact cooler target** — confirm LBC sourcing, RAM height and board/case clearance |
| Thermalright Phantom Spirit 120 SE | Roughly **0.20–0.25k lei** | Excellent budget air performance; lower absolute thermal/acoustic margin than the Noctua target on flagship CPU loads | Simple air cooler; acceptable stability if adequately tested | Replaceable fans; lower support/premium-hardware value | Compact/easy case fit | High on pure price/performance; lower strategic value than Noctua | **Value/control reference** — saving ~500 lei is not currently compelling enough to displace the Noctua target |
| **ARCTIC Liquid Freezer III Pro 360** | Roughly **0.38–0.48k lei** | **Substantially more thermal headroom**, including direct 9950X3D PBO testing | Excellent thermal margin, but introduces pump/liquid as additional long-term dependencies | 6-year warranty; pump/radiator assembly less field-serviceable than an air heatsink | Top 360 mm fit is shared across current case finalists and preserves front GPU intake | Medium-high | **Liquid fallback**, not preferred architecture; use only if real workload validation justifies it |
| ARCTIC Liquid Freezer III Pro 420 | Roughly **0.43–0.59k lei** | Maximum cooling, but only ~0.9 C better than the best 360 mm result around 200 W in cited testing | Same AIO dependencies as 360; more physical complexity | 6-year warranty | Front-mount dependency on North XL/Silent Base 802 can interfere with clean GPU intake/clearance | Low-medium for this build | **Not targeted** — 420 mm support should not drive chassis selection |
| **2 TB permanent system/tools Gen4 TLC NVMe** | Roughly **1.7–2.0k lei** for current serious 2 TB candidates | Excellent system/IDE/tool performance; no meaningful need for Gen5 headline bandwidth | Mature TLC + DRAM candidates with 5-year-class warranty and established firmware ecosystems | Permanent useful component, unlike Phase-1 RAM | Leaves system usable immediately and becomes dedicated system/tools volume after work-drive expansion | **High** | **Selected initial storage class; exact model provisional** |
| **4 TB+ work/VM/container NVMe added later** | Deferred; current strong 4 TB Gen4 offers roughly **2.6–3.6k lei**, model dependent | Separates heavy random/sustained VM/container/build/database I/O; capacity is the main benefit | Independent drive/controller reduces operational coupling and distributes sustained I/O/thermal load | Independently replaceable/upgradable; no sunk-cost conflict with initial SSD | Preserves 4 TB/8 TB and Gen5 choice for later market/workload conditions | **High** | **Selected long-term architecture; defer purchase until needed** |
| 4 TB Samsung 9100 PRO / premium Gen5 class | Current RO roughly **4.2k lei+** | Large sequential headline gain; much smaller ordinary system-drive/workstation gain | Modern efficient Gen5 design, but extra thermal/power complexity versus mature Gen4 remains | Strong high-end drive, but premium is not needed for current initial workload | Could be useful later if future data workloads genuinely exploit Gen5 | Low-medium today | **Deferred / control reference** — preserve Gen5 slot, do not pay premium now |
| **Airflow-first chassis strategy** | Usually modest versus restrictive/showcase alternatives; exact case delta TBD | Little direct benchmark benefit unless thermal limits are reached; improves sustained behavior under long loads | **High**: lower VRM/RAM/SSD/GPU temperatures, more thermal margin, less dependence on aggressive fan curves | **High**: large standard fans, easy filters and spacious serviceable layout support long ownership | Strong future high-power GPU/cooling/PSU compatibility when chassis envelope is generous | **High** | **Selected design principle** — exact case/fan layout remains open |
| Future single high-VRAM AI GPU | Future spend; excluded from current initial BOM | Potentially transformative for local AI inference/fine-tuning/training workloads | Requires PSU, chassis and cooling headroom | GPU can be replaced independently of core platform | **Primary AI expansion path**; AM5 is adequate for one very powerful GPU | High if AI objective materializes | Secondary objective; preserve compatibility now, buy GPU later |
| Serious multi-GPU AI platform | Very high future cost | High for workloads that scale across accelerators | Requires platform/chassis/power architecture designed for it | Specialized workstation/server territory | AM5 becomes a meaningful constraint due to PCIe/slot/power topology | Low as a current pre-purchase investment | Do **not** optimize current build for this; reopen platform decision if future workload requires it |

## Motherboard cost/value interpretation

The current motherboard contest is deliberately **not** simply premium versus value:

- the **ProArt premium** buys the strongest explicit vendor evidence we have found for 4×64 GB / 256 GB and ongoing ECC-specific firmware work;
- the **Taichi Creator saving** does not buy a weaker feature set — it actually has cleaner PCIe/storage topology, better POST diagnostics and 10 GbE + 5 GbE — but its exact 4×64 GB ECC evidence still needs to be proven to the same confidence level;
- the **MSI saving versus the Taichi Creator is relatively small** in current Romanian pricing, while giving up ECC, CPU x8/x8 and 10 GbE.

The selected storage layout works cleanly on both Creator finalists: system drive on chipset M.2_3/M2_3 and future work drive on CPU-connected M.2_1/M2_1. This avoids the ProArt's M.2_2 graphics-lane penalty and avoids the Taichi Creator's M2_2/USB4 sharing issue, so storage no longer materially differentiates the two finalists for the planned two-drive configuration.

If the ASRock proves equally stable with a credible 256 GB ECC configuration, its lower price and topology advantages remain durable enough that it would likely become the better 10-year value. If it does not, paying roughly 1,000 lei more for the ProArt may be justified as risk reduction on a 256 GB workstation.

## Memory cost/value interpretation

Memory is now explicitly the strongest **budget-release valve**:

- **32 GB is enough for Phase 1** because it matches the capacity already supporting the current workload;
- temporary RAM is a commissioning purchase, not a long-term investment;
- 2×16 GB is preferable when pricing is similar, but 1×32 GB or any other stable 32 GB+ configuration is acceptable if cheaper;
- spending more for temporary capacity should happen only when the incremental price is unusually attractive;
- **256 GB remains the endpoint**, but buying it immediately is not worth distorting the rest of the build when high-density DDR5 pricing is disproportionate;
- the temporary kit should be treated as replaceable so the eventual 256 GB configuration can be chosen from the best validated matched set available at that time rather than being constrained by sunk cost.

This preserves the motherboard, chassis, cooling, storage and PSU quality while minimizing initial memory spend.

## Cooling cost/value interpretation

Cooling is a case where the cheapest technically adequate option is **not automatically** the best long-term value.

- A roughly 200–250 lei Thermalright tower shows that excellent air cooling can be inexpensive.
- The roughly 500 lei premium to move to the NH-D15 G2 class is acceptable in a 10-year workstation because it buys additional flagship-CPU thermal/acoustic margin, AM5-specific mounting/contact engineering, premium replaceable fans, warranty and a strong long-term mounting/support ecosystem.
- The ARCTIC 360 AIO is actually **cheaper than the Noctua** in current Romanian listings and cools better at extreme CPU power. Therefore air cooling is not being chosen to save money; it is being chosen for the simpler long-term failure/service model.
- The 420 mm AIO adds little at roughly stock CPU power and can compromise chassis/GPU airflow design, so its low purchase price does not make it a better system-level value.

The intended policy is therefore:

> **Pay the moderate Noctua premium for a durable air-cooling subsystem, but do not spend or redesign the chassis for liquid-cooling capacity that the stock/conservative 9950X3D workload does not require.**

## Storage cost/value interpretation

Storage now follows the same staged-investment discipline as RAM, but with one important difference: **the initial SSD is permanent rather than disposable**.

- Buying one good **2 TB Gen4 TLC + DRAM SSD** now gives the machine enough initial working capacity and costs roughly 1.7–2.0k lei in the current market.
- Buying the planned 4 TB work drive immediately would add roughly another 2.6–3.6k lei without being necessary to commission the system.
- Deferring that drive costs us no architectural option and no sunk-cost loss; the 2 TB drive simply becomes the permanent system/tools volume.
- PCIe 5.0 is preserved as a future option via M.2_1, but paying roughly 4.2k lei or more for a current premium 4 TB Gen5 drive is not justified by the expected development workload today.
- Extremely high TBW ratings are welcome but should not attract a large premium once the drive already has ample endurance for a decade-scale development workload.

Therefore the cost-optimal long-term strategy is **buy the permanent 2 TB system SSD now, buy capacity later, and let later market conditions decide the exact 4 TB/8 TB and Gen4/Gen5 work drive.**

## Component-level matrix to complete

| Area | Baseline / value option | Premium option(s) | Cost delta | Measured workload benefit | Reliability/endurance benefit | Expansion/longevity benefit | Decision |
|---|---|---|---:|---|---|---|---|
| Motherboard | MSI MAG X870 Tomahawk WiFi | **ASRock X870 Taichi Creator** / **ASUS ProArt X870E-Creator WiFi** | MSI→ASRock roughly +0–0.4k lei at competitive offers; ASRock→ASUS roughly +0.9–1.1k lei | Essentially none in CPU throughput at stock | ASUS currently strongest 256 GB/ECC firmware evidence; ASRock stronger diagnostics and needs exact RAM validation | ASRock/ASUS add ECC, CPU x8/x8 and 10 GbE; selected storage layout works on both without GPU-lane compromise | **ProArt provisional target; Taichi Creator live challenger; MSI control** |
| Memory kit | **32 GB+ commissioning RAM** | Larger temporary kit only if unusually good value; eventual 256 GB matched configuration | Keep Phase-1 delta minimal | Temporary capacity only affects concurrency/headroom | Simple one/two-DIMM config is easy to stabilize; eventual ECC may add data-integrity protection | Platform still preserves 256 GB endpoint | **32 GB floor selected; minimize temporary RAM spend** |
| Cooling | Thermalright Phantom Spirit 120 SE value control | **Noctua NH-D15 G2 LBC**; ARCTIC LF III Pro 360 as liquid fallback | Noctua roughly +0.4–0.6k lei vs budget tower; Arctic 360 may actually cost less than Noctua | Noctua provides best observed air margin; Arctic provides more extreme-load headroom | **Air wins serviceability/failure simplicity; Noctua adds support/fan quality** | Air avoids radiator constraints and preserves clean front GPU intake | **High-end air selected; NH-D15 G2 LBC provisional target** |
| Storage | **2 TB Gen4 TLC + DRAM system SSD now** | Add 4 TB/8 TB work drive later; Gen5 only if later justified | ~1.7–2.0k lei initial; second-drive spend deferred | Two-drive endpoint improves isolation/concurrency more than buying Gen5 headline bandwidth now | Mature firmware, SMART, adequate TBW and independent-drive serviceability | M.2_1 reserved for future high-performance work drive; M.2_3 used for system drive | **Architecture selected; exact SSD SKU provisional** |
| PSU | TBD | Higher-quality / higher-headroom option | TBD | None directly | Electrical quality, thermal margin and warranty TBD | Future high-power GPU support TBD | **Next major component review** |
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
