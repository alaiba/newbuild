# RAM Capacity Sensitivity — 2026-08-31

Status: **RAM purchase capacity reopened because 128 GB pricing is anomalously high. Two-DIMM / 1DPC topology remains mandatory.**

## Executive conclusion

For this workstation, **capacity below 128 GB does not intrinsically slow the Ryzen 9 9950X3D as long as memory remains a two-DIMM DDR5-5600 configuration and the active working set fits in RAM**.

The performance loss from buying less RAM is therefore mostly **threshold-based rather than proportional**:

- below the capacity threshold: usually negligible capacity-related performance loss;
- near the threshold: reduced filesystem cache and more aggressive memory reclamation can make the system less responsive;
- beyond the threshold: paging, compressed memory, JVM/IDE GC pressure, VM/container limits and forced workload serialization can cause large wall-clock slowdowns.

By contrast, populating four DIMMs is a deterministic topology compromise. AMD officially specifies the Ryzen 9 9950X3D for **DDR5-5600 with two DIMMs** and only **DDR5-3600 with four DIMMs**. A Puget Systems AMD 1DPC-vs-2DPC compilation-style test measured the DDR5-5600 1DPC setup about **13% faster** than DDR5-3600 2DPC in Unreal shader compilation. Therefore the project should not plan to reach 128 GB by adding a second pair later.

## Meaningful capacities

The sensible sub-128-GB candidates are all two-DIMM configurations:

| Capacity | Topology | Raw memory-speed effect vs 128 GB 2×64 | Practical interpretation |
|---|---|---|---|
| **32 GB** | 2×16 GB | ~0% while workload fits | Minimum boot/workable configuration; insufficient headroom for the intended workstation workload |
| **48 GB** | 2×24 GB | ~0% while workload fits | Best low-cost bridge at current prices; useful but limited concurrency |
| **64 GB** | 2×32 GB | ~0% while workload fits | Strong value candidate; likely enough for most daily Java/Android work |
| **96 GB** | 2×48 GB | ~0% while workload fits | Excellent capacity, but currently almost the same price as 128 GB and therefore poor value |
| **128 GB** | 2×64 GB | baseline | Maximum concurrency/headroom and largest OS filesystem cache; currently very expensive |

Single-DIMM configurations are rejected because they give up normal dual-channel operation. Four-DIMM 64/96/128 GB configurations are rejected as planned endpoints because they move the platform into 2DPC and AMD's official DDR5-3600 support class.

## How much memory is actually usable for active work?

Installed RAM is not the same as application working-set budget. Windows, drivers, security software, filesystem cache, background services and native allocations consume memory too. A practical planning envelope is approximately:

| Installed | Comfortable active application / VM / container working set before pressure becomes likely |
|---:|---:|
| 32 GB | ~22–26 GB |
| 48 GB | ~35–40 GB |
| 64 GB | ~48–55 GB |
| 96 GB | ~75–82 GB |
| 128 GB | ~100–110 GB |

These are planning ranges, not hard limits. Windows dynamically reclaims cache and memory use varies substantially by project, IDE version, browser workload, WSL/container configuration and VM allocation.

## Workload scenarios

### Scenario A — heavy Java development, no large VM

Representative concurrent load:

- IntelliJ IDEA / Android Studio with a very large project: 6–12 GB total process footprint depending indexing and heap;
- Gradle/Maven/Kotlin daemons and build JVMs: 4–10 GB;
- WSL2 / Docker / local services: 4–10 GB;
- browser, collaboration tools and desktop background: 4–8 GB;
- filesystem cache: whatever remains.

Typical total active footprint: roughly **25–40 GB**.

Expected behavior:

- **32 GB:** frequently constrained; builds may still benchmark normally in isolation, but background concurrency/cache will be sacrificed. Expect noticeable responsiveness loss under real multitasking and potentially large slowdowns during spikes.
- **48 GB:** generally workable; likely near the edge during indexing + builds + Android/containers simultaneously.
- **64 GB:** comfortable. In this scenario, expected wall-clock build performance versus 128 GB is approximately **0–2% different** when the working set fits.
- **96/128 GB:** no meaningful CPU/build-speed advantage; extra RAM mainly becomes cache/headroom.

### Scenario B — Java + Android emulator + WSL/Docker + local databases

Representative total active footprint: approximately **35–55 GB**, with spikes above that plausible.

Expected behavior:

- **32 GB:** unsuitable for unconstrained concurrency; expect paging or forced workload serialization.
- **48 GB:** workable with active management, but pressure during emulator/indexing/build spikes is plausible.
- **64 GB:** strong fit. Usually no meaningful performance loss versus 128 GB, though less filesystem cache remains during the heaviest periods.
- **96/128 GB:** additional convenience and concurrency rather than faster compilation.

### Scenario C — development plus one substantial VM

Example: 24–32 GB assigned to a VM while the Windows host still runs IDEs, builds, WSL/containers and browser tools.

Expected behavior:

- **32/48 GB:** impractical without heavily constraining either host or guest.
- **64 GB:** possible but tight; the host may have only ~25–35 GB left after VM allocation.
- **96 GB:** comfortable.
- **128 GB:** very comfortable; allows larger VM allocation plus substantial host cache.

### Scenario D — multiple VMs / multiple Android AVDs / many local services

Representative footprint can easily exceed **60–90 GB**.

Expected behavior:

- **64 GB:** capacity becomes the bottleneck; performance loss may be substantial because workloads must page, shrink heaps or be stopped.
- **96 GB:** usually adequate.
- **128 GB:** preferred if this becomes normal daily behavior.

## Performance-loss model

The useful way to estimate the loss is not "64 GB is X% slower than 128 GB." Instead:

| State | Estimated effect vs 128 GB |
|---|---|
| Working set comfortably fits | **~0–2%** capacity-related difference for CPU/build work; often effectively zero |
| Fits, but little RAM left for filesystem cache | often **~0–5%** on I/O-sensitive repeated workflows; highly workload-dependent |
| Moderate memory pressure / occasional paging | **~5–20%** wall-clock degradation is plausible, plus visible latency spikes |
| Sustained paging / compressed-memory pressure | **20–50%+** slowdown is entirely plausible; interactivity can degrade more than averages suggest |
| Workload cannot fit at all (VM/heap/container commitments) | not meaningfully expressible as a percentage; the workload must be reduced, serialized or moved elsewhere |

The 5–50% ranges are engineering estimates for memory-pressure behavior, not benchmark claims for this exact source tree. The deterministic measured comparison we do have is topology-related: DDR5-5600 1DPC was ~13% faster than DDR5-3600 2DPC in Puget's AMD shader-compilation test.

## Why four DIMMs are not the upgrade strategy

The tempting path is to buy 2×32 GB now and add another 2×32 GB later. That produces 128 GB, but it changes the electrical topology from 1DPC to 2DPC.

AMD's official Ryzen 9 9950X3D specification:

- 2×1R: DDR5-5600;
- 2×2R: DDR5-5600;
- 4×1R: DDR5-3600;
- 4×2R: DDR5-3600.

The board may train four DIMMs above DDR5-3600 in practice, but relying on that would contradict this project's conservative stability policy.

Therefore, if a smaller kit is bought now and more capacity is needed later:

> replace the original two-DIMM kit with a larger matched two-DIMM kit; resell or repurpose the old kit.

## Current Romanian price/value snapshot

Current market data is severely distorted across DDR5 capacities. Representative current listings are approximately:

| Capacity | Representative 2-DIMM kit | Approx. current price | Value observation |
|---:|---|---:|---|
| 32 GB | Crucial 2×16 DDR5-5600 | ~2.8–3.0k lei | Dominated by 48 GB at similar money |
| 48 GB | Crucial Pro 2×24 DDR5-5600 | ~2.9k lei | **Best low-cost capacity point** |
| 64 GB | Crucial 2×32 DDR5-5600 | ~4.7–4.8k lei | **Best performance-safe compromise** |
| 96 GB | Crucial Pro 2×48 DDR5-5600 | ~7.4k lei | Dominated by 128 GB |
| 128 GB | Crucial 2×64 DDR5-5600 | ~7.7k lei | Maximum headroom; poor absolute price |

At these prices, 32 GB and 96 GB make little sense. The real choice is **48 vs 64 vs 128 GB**.

## Recommendation

### Best overall compromise now: 64 GB / 2×32 GB

For the intended workload, **64 GB is the rational value target if the objective is to avoid paying today's extreme 128 GB premium**.

Why:

- doubles the current-machine capacity;
- preserves DDR5-5600 / 1DPC;
- should have essentially **zero build-performance loss versus 128 GB whenever the actual working set remains below ~50–55 GB**;
- supports serious IntelliJ/Android/WSL/container concurrency;
- saves roughly **2.9k lei** versus the current 128 GB reference;
- leaves a clean future path: replace with 2×64 GB if real telemetry proves 64 GB insufficient or market pricing normalizes.

The downside is that the 2×32 kit becomes a resale/repurpose item if 128 GB is eventually required.

### Cheapest rational bridge: 48 GB / 2×24 GB

48 GB is attractive because it currently costs almost the same as 32 GB. It should be considered if minimizing initial spend is the priority.

However, it provides only ~50% more RAM than the current 32 GB machine and is much more likely than 64 GB to encounter pressure with Android Studio + emulator + WSL/Docker + large Java builds running together.

### Keep 128 GB if convenience is worth ~2.9k lei over 64 GB

128 GB remains technically ideal. The extra money buys:

- VM/container/AVD concurrency;
- larger Java heaps without trade-offs;
- more filesystem cache;
- less need to monitor memory use;
- no future DIMM replacement.

It does **not** buy a proportional compile-speed increase over 64 GB when 64 GB is sufficient.

## Decision gate

Before paying for RAM, choose among:

1. **48 GB / 2×24** — cheapest rational bridge;
2. **64 GB / 2×32** — recommended current value/performance balance;
3. **128 GB / 2×64** — maximum headroom and no future replacement.

Do not choose 32 GB, 96 GB, a single DIMM, or a planned four-DIMM upgrade path at current prices/topology constraints.
