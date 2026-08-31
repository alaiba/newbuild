# Final Order Plan — 2026-08-31

Status: **All components except RAM purchase capacity are selected. EvoMAG exact-board availability re-verified.**

Prices below are reference checkout prices observed on 2026-08-31 and must be confirmed in-cart immediately before payment. Shipping is excluded unless explicitly noted.

## Motherboard clarification

The selected board is:

> **ASUS TUF GAMING B650E-E WIFI `90MB1LT0-M0EAY0`**

EvoMAG also sells the similarly named **TUF GAMING B650-E WIFI `90MB1GT0-M0EAY0`**. They are distinct boards.

Current comparison data identifies an EvoMAG listing for the exact selected **B650E-E** in the approximately **844 lei** class. Therefore EvoMAG remains a valid hardware consolidation provider for the selected board. Always verify exact SKU `90MB1LT0-M0EAY0` in-cart because the two names are easy to confuse.

## Provider position

With the exact B650E-E available at EvoMAG, the preferred final split returns to:

1. **EvoMAG** — hardware, subject to the RAM-capacity choice and exact in-cart SKU verification.
2. **PROstore** — Windows 11 Pro Retail/FPP `HAV-00163`.

This is better than the previous three-provider plan if the exact board remains available at checkout.

## Fixed non-RAM basket

| Provider | Item | Exact target | Reference price |
|---|---|---|---:|
| EvoMAG | CPU | AMD Ryzen 9 9950X3D Box/WOF `100-100000719WOF` | **3,349.99 lei** |
| EvoMAG | Motherboard | ASUS TUF GAMING B650E-E WIFI `90MB1LT0-M0EAY0` | **~843.99 lei** |
| EvoMAG | CPU cooler | Thermalright Phantom Spirit 120 — standard | **249.99 lei** |
| EvoMAG | Case | be quiet! Pure Base 501 Airflow Black `BG074` | **423.99 lei** |
| EvoMAG | Primary SSD | Crucial T710 2 TB `CT2000T710SSD8`, bare/non-heatsink | **1,710.99 lei** |
| EvoMAG | PSU | be quiet! Pure Power 13 M 850W `BP027EU` | **686.99 lei** |
| PROstore | Windows | Windows 11 Pro 64-bit English Retail/FPP USB `HAV-00163` | **1,123.60 lei** |
| Reuse | GPU | Existing RTX 3060 12 GB | **0 lei** |
| Reuse | Cold storage | Existing healthy SATA drives | **0 lei** |
| None | UPS / dedicated surge protector | Not purchased | **0 lei** |

Fixed non-RAM subtotal including Windows: approximately **8,389.54 lei** before shipping.

## RAM capacity sensitivity

The platform rule remains **two matched DIMMs / A2+B2 / 1DPC**. Ryzen 9 9950X3D officially supports DDR5-5600 with two DIMMs, while AMD's official supported rate falls to DDR5-3600 with four DIMMs.

Representative Romanian market snapshots:

| Capacity | Topology | Representative current price | Approx. complete-build total | Savings vs 128 GB |
|---|---|---:|---:|---:|
| **32 GB** | 2×16 GB DDR5-5600 | ~2.83–2.95k lei | **~11.22–11.34k lei** | ~4.75–4.87k lei |
| **48 GB** | 2×24 GB DDR5-5600 | ~2.90k lei | **~11.29k lei** | ~4.80k lei |
| **64 GB** | 2×32 GB DDR5-5600 | ~4.71–4.80k lei | **~13.10–13.19k lei** | ~2.90–2.99k lei |
| **96 GB** | 2×48 GB DDR5-5600 | ~7.40k lei | **~15.79k lei** | ~0.30k lei |
| **128 GB** | 2×64 GB DDR5-5600 | ~7.70k lei | **~16.09k lei** | baseline |

The exact prices are unusually volatile. Capacity should be chosen first; the exact kit/provider should then be optimized again.

### Dominated capacities at current prices

- **32 GB:** costs almost as much as 48 GB, so there is little reason to choose it.
- **96 GB:** costs almost as much as 128 GB, so there is little reason to choose it.

The meaningful decision is therefore **48 vs 64 vs 128 GB**.

## Performance interpretation

Smaller capacity does **not** reduce CPU or memory-channel performance as long as the machine remains in a two-DIMM DDR5-5600 configuration and the active working set fits.

Expected capacity-related loss versus 128 GB:

| Situation | Expected effect |
|---|---|
| Working set fits comfortably | **~0–2%**; often effectively zero |
| Fits but leaves little filesystem cache | usually **~0–5%** on I/O-sensitive repeated workflows |
| Moderate memory pressure / occasional paging | **~5–20%** wall-clock degradation plausible |
| Sustained paging / compressed-memory pressure | **20–50%+** slowdown plausible, with worse interactivity |
| Workload cannot fit (VM/heap/container commitments) | workload must be reduced/serialized; percentage comparison stops being useful |

These pressure ranges are engineering estimates, not benchmark measurements of the user's exact source tree.

The deterministic topology penalty is different: a Puget Systems AMD test found **DDR5-5600 1DPC about 13% faster than DDR5-3600 2DPC** in shader compilation. Therefore do not buy 2×32 now with a plan to add another 2×32 later; if 128 GB becomes necessary, replace the pair with 2×64.

## Capacity recommendations

### 48 GB / 2×24 — cheapest rational bridge

Use when minimizing initial spend is the priority.

- same DDR5-5600 dual-channel class as larger two-DIMM configurations;
- should perform identically to 128 GB while the working set remains below roughly 35–40 GB;
- likely to encounter pressure sooner with Android Studio + emulator + WSL/Docker + large Java builds together;
- currently almost the same price as 32 GB, making 32 GB unattractive.

### 64 GB / 2×32 — recommended current value/performance balance

This is the principal alternative to 128 GB.

- doubles the current machine's capacity;
- preserves 1DPC / DDR5-5600;
- expected **~0–2% capacity-related build-performance loss versus 128 GB** whenever the active working set stays below roughly 50–55 GB;
- enough for substantial IntelliJ/Android/WSL/container concurrency;
- saves roughly **2.9–3.0k lei** at current market prices;
- if future telemetry proves it insufficient, replace the pair with 2×64 and resell/repurpose the 2×32 kit.

### 128 GB / 2×64 — maximum headroom

Keep if the ~3k-leu premium over 64 GB is acceptable in exchange for:

- large VM allocations;
- multiple AVDs / containers / local services concurrently;
- larger JVM heaps without trade-offs;
- more filesystem cache;
- no future RAM replacement or memory-management attention.

It does **not** make a normal build materially faster than 64 GB if 64 GB already contains the entire working set.

## Current purchase position

The rest of the build is purchase-ready. RAM capacity is the only intentionally reopened decision.

Detailed performance analysis: [`ram-capacity-sensitivity-2026-08-31.md`](ram-capacity-sensitivity-2026-08-31.md).

## Checkout gates

1. Verify EvoMAG motherboard exact SKU **`90MB1LT0-M0EAY0`**; reject `90MB1GT0-M0EAY0` despite the similar name.
2. Choose RAM capacity: **48 / 64 / 128 GB**.
3. Re-search exact two-DIMM kits for the chosen capacity immediately before payment.
4. Keep RAM at **A2/B2 / 1DPC**; do not plan a four-DIMM expansion.
5. Confirm T710 is bare/non-heatsink `CT2000T710SSD8`.
6. Confirm CPU is Box/WOF `100-100000719WOF`, not tray.
7. Confirm PSU is Pure Power 13 M 850W `BP027EU`.
8. Confirm Windows is genuine Retail/FPP English USB `HAV-00163`.
9. Preserve invoices, serial numbers and packaging through commissioning/return windows.
