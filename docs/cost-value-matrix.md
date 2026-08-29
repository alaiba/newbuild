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

## Current decision matrix

| Decision / option | Incremental cost | Performance benefit | Reliability / stability | Endurance / serviceability | Expansion / future value | 10-year value | Status / verdict |
|---|---:|---|---|---|---|---|---|
| **Ryzen 9 9950X3D + AM5** | Baseline | Excellent mixed workstation performance; strong Java/build throughput and interactive responsiveness; excellent gaming | Strong when operated conservatively; mature AM5 ecosystem is a major factor | Mainstream parts ecosystem and broad replacement availability | Up to 256 GB system memory; adequate PCIe for a powerful single-GPU AI system | **High** | **Selected** |
| Threadripper 9960X + TRX50 | Approx. +7–8k lei 5-year TCO versus 9950X3D platform from Aug 2026 analysis; refresh before purchase | Potentially materially faster in highly parallel builds/tests; much less benefit in ordinary IDE/interactive work | RDIMM platform and four memory channels are workstation strengths | Strong workstation platform, but higher power/cooling complexity and more specialized replacement ecosystem | Much stronger PCIe and memory-bandwidth headroom | Medium for this workload | **Rejected** — extra throughput and workstation specialization do not justify TCO for the current mixed workload |
| **256 GB system memory** | TBD once exact 4×64 GB configuration is selected | Capacity benefit rather than direct speed; allows large JVM heaps, concurrent IDEs/services/VMs/containers and future AI support workflows without paging pressure | Potentially strong if configuration is validated conservatively; four-DIMM AM5 stability is the main technical risk | High capacity should remain useful throughout ownership period | Preserves substantial local development/VM/data/AI headroom | **Potentially very high** | **Target selected** — scale back only if cost or 4×64 GB stability/performance is disproportionate |
| ECC UDIMM at 256 GB | TBD | No meaningful performance advantage; may have small implementation-specific cost/latency trade-offs | **Potentially high**: protects against correctable memory errors and improves data-integrity story if ECC is truly end-to-end and OS-visible | Strong fit for long-lived 256 GB workstation if supported reliably | Helpful for long-running JVM/VM/database/AI workloads | Potentially high | **Strong preference / under review** — require stable 256 GB configuration and real error reporting, not merely DIMMs that boot |
| Non-ECC UDIMM at 256 GB | Baseline memory alternative | Potentially easier availability and/or higher clocks | Acceptable if thoroughly validated, but lacks system-level ECC protection | Good if conservative, high-quality DIMMs are used | Same capacity; less data-integrity protection | Medium-high | Fallback if ECC implementation or availability compromises stability |
| B850 motherboard class | Likely lowest eligible cost | No inherent CPU-performance disadvantage if implementation is sufficient | Board-specific | Board-specific | May constrain PCIe/I/O/AI expansion depending on topology | TBD | Under review |
| X870 motherboard class | Moderate premium | No inherent CPU-performance gain versus competent B850 | Board-specific | Board-specific | More high-speed I/O on suitable boards; topology still board-specific | TBD | Under review |
| X870E motherboard class | Higher premium | No inherent CPU-performance gain versus competent lower-tier board | Can be justified by board implementation, firmware and recovery features, not chipset name alone | Potentially stronger long-term I/O/expansion story | Most likely class to preserve x8/x8 GPU topology, multiple NVMe devices and workstation-oriented networking | Potentially high | Under review — premium must buy concrete topology/reliability/serviceability benefits |
| Onboard 10 GbE | TBD board premium | No application performance benefit unless network workload can exploit it | Avoids dependence on an add-in NIC if controller/driver quality is good | Fewer add-in parts; controller quality and thermals matter | Preserves a PCIe slot for another device; useful over long ownership horizon | Potentially high | Under review |
| **Airflow-first chassis strategy** | Usually modest versus restrictive/showcase alternatives; exact case delta TBD | Little direct benchmark benefit unless thermal limits are reached; improves sustained behavior under long loads | **High**: lower VRM/RAM/SSD/GPU temperatures, more thermal margin, less dependence on aggressive fan curves | **High**: large standard fans, easy filters and spacious serviceable layout support long ownership | Strong future high-power GPU/cooling/PSU compatibility when chassis envelope is generous | **High** | **Selected design principle** — exact case/fan layout remains open |
| Future single high-VRAM AI GPU | Future spend; excluded from current initial BOM | Potentially transformative for local AI inference/fine-tuning/training workloads | Requires PSU, chassis and cooling headroom | GPU can be replaced independently of core platform | **Primary AI expansion path**; AM5 is adequate for one very powerful GPU | High if AI objective materializes | Secondary objective; preserve compatibility now, buy GPU later |
| Serious multi-GPU AI platform | Very high future cost | High for workloads that scale across accelerators | Requires platform/chassis/power architecture designed for it | Specialized workstation/server territory | AM5 becomes a meaningful constraint due to PCIe/slot/power topology | Low as a current pre-purchase investment | Do **not** optimize current build for this; reopen platform decision if future workload requires it |

## Component-level matrix to complete

The table below is the working checklist. Add rows as component decisions are researched and closed.

| Area | Baseline / value option | Premium option(s) | Cost delta | Measured workload benefit | Reliability/endurance benefit | Expansion/longevity benefit | Decision |
|---|---|---|---:|---|---|---|---|
| Motherboard | TBD | TBD | TBD | Usually negligible CPU-performance difference | TBD | TBD | **Next: nominate provisional / aspirational target; do not close until promotion gates pass** |
| Memory kit | 256 GB non-ECC candidate | 256 GB ECC candidate | TBD | Capacity equal; speed/timing differences TBD | ECC and validation differences TBD | Both at platform capacity | Open |
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
