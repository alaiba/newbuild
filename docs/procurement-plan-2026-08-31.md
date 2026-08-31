# Procurement Plan — 2026-08-31

Status: **all architecture decisions are closed except RAM purchase capacity, reopened because current 128 GB pricing is anomalously high. EvoMAG exact-board availability has been re-verified.**

## Locked principles

1. Maximum three providers overall; prefer fewer when exact SKUs remain available.
2. Optimize utility per leu, not benchmark prestige.
3. Preserve exact product identities where a similarly named substitute is materially different.
4. Prefer two-DIMM / 1DPC memory topology on AM5.
5. Exact SKU/revision, warranty clarity and product condition outrank small nominal savings.

## Motherboard procurement clarification

Selected motherboard remains:

> **ASUS TUF GAMING B650E-E WIFI `90MB1LT0-M0EAY0`**.

EvoMAG also carries the different **ASUS TUF GAMING B650-E WIFI `90MB1GT0-M0EAY0`**. The names are confusingly similar, but current Romanian comparison data also surfaces the exact selected **B650E-E** at EvoMAG in the approximately **844 lei** class.

Therefore the preferred provider split is again:

- **EvoMAG:** hardware, provided the exact `90MB1LT0-M0EAY0` is confirmed in-cart;
- **PROstore:** Windows 11 Pro Retail/FPP `HAV-00163`.

## Selected purchase targets

| Item | Target | Status |
|---|---|---|
| CPU | Ryzen 9 9950X3D Box/WOF `100-100000719WOF` | selected |
| Motherboard | **ASUS TUF GAMING B650E-E WIFI `90MB1LT0-M0EAY0`** | selected; EvoMAG preferred if exact SKU remains available |
| RAM | two matched DDR5-5600 UDIMMs / A2+B2 / 1DPC | **capacity under review: 48 / 64 / 128 GB** |
| CPU cooler | **Thermalright Phantom Spirit 120 standard** | selected |
| Case | **be quiet! Pure Base 501 Airflow Black `BG074`** | selected |
| Case fans | two included 140 mm PWM only initially | selected |
| Primary SSD | **Crucial T710 2 TB `CT2000T710SSD8`**, bare/non-heatsink | selected |
| PSU | **be quiet! Pure Power 13 M 850W `BP027EU`** | selected |
| GPU | existing RTX 3060 12 GB | reuse |
| Windows | Windows 11 Pro Retail/FPP `HAV-00163` | selected target |
| UPS | none | selected |
| Dedicated surge protector | none | selected |

## RAM capacity/value review

AMD officially rates the Ryzen 9 9950X3D for:

- **DDR5-5600 with two DIMMs** (both 2×1R and 2×2R);
- **DDR5-3600 with four DIMMs**.

Therefore capacity optimization must preserve two DIMMs.

Current representative Romanian snapshots:

| Capacity | Topology | Representative price | Interpretation |
|---|---|---:|---|
| 32 GB | 2×16 | ~2.83–2.95k lei | poor value versus 48 GB |
| **48 GB** | 2×24 | ~2.90k lei | cheapest rational bridge |
| **64 GB** | 2×32 | ~4.71–4.80k lei | **principal value candidate** |
| 96 GB | 2×48 | ~7.40k lei | poor value versus 128 GB |
| **128 GB** | 2×64 | ~7.70k lei | maximum headroom, highest cost |

The meaningful decision is therefore **48 vs 64 vs 128 GB**.

### Performance interpretation

With two DIMMs at DDR5-5600, lower capacity does not intrinsically reduce CPU/build throughput. Expected capacity-related difference versus 128 GB while the working set fits is approximately **0–2%**, often effectively zero.

Performance loss becomes significant only when memory pressure appears:

- little filesystem cache: often ~0–5% on I/O-sensitive repeated workflows;
- occasional paging: ~5–20% wall-clock degradation plausible;
- sustained paging/compressed-memory pressure: ~20–50%+ degradation plausible, with worse interactive latency.

These pressure ranges are engineering estimates, not measurements of the exact Java codebase.

A separate deterministic topology result exists: Puget Systems measured an AMD DDR5-5600 1DPC setup about **13% faster than DDR5-3600 2DPC** in shader compilation. This reinforces the rule: if a smaller kit is purchased now and later proves insufficient, **replace** it with 2×64 rather than adding another pair.

### Capacity choice

- **48 GB:** minimum rational low-cost bridge. Same raw memory speed; likely memory pressure under aggressive Android/WSL/container concurrency.
- **64 GB:** recommended current value/performance balance. Likely indistinguishable from 128 GB for normal heavy development whenever the active working set remains under roughly 50–55 GB. Saves about 2.9–3.0k lei versus the current 128 GB reference.
- **128 GB:** maximum convenience, VM/container/AVD concurrency and filesystem cache; buys headroom rather than proportional compile-speed improvement.

Detailed analysis: `ram-capacity-sensitivity-2026-08-31.md`.

## Current fixed non-RAM basket

Using the EvoMAG exact-board reference and PROstore Windows:

- fixed non-RAM subtotal including Windows: approximately **8,389.54 lei** before shipping.

Approximate complete-build totals then become:

- **48 GB:** ~11.29k lei;
- **64 GB:** ~13.10–13.19k lei;
- **128 GB:** ~16.09k lei.

These are comparison totals only. Perform a fresh exact-kit/provider search after choosing RAM capacity.

## Exact acceptance gates

### CPU
- Ryzen 9 9950X3D Box/WOF `100-100000719WOF`.

### Motherboard
- exact **TUF GAMING B650E-E WIFI `90MB1LT0-M0EAY0`**;
- reject B650-E `90MB1GT0-M0EAY0`, B650E-PLUS and similarly named variants without review.

### RAM
- two matched DDR5 UDIMMs only;
- A2/B2 / 1DPC;
- prefer stable DDR5-5600 operation at conservative voltage;
- capacity selection pending: 48 / 64 / 128 GB;
- do not plan a four-DIMM upgrade path.

### Cooler
- Thermalright Phantom Spirit 120 standard.

### Case
- be quiet! Pure Base 501 Airflow Black `BG074` with two included 140 mm PWM fans.

### Storage
- Crucial T710 2 TB `CT2000T710SSD8`, bare/non-heatsink, `M.2_1`.

### PSU
- be quiet! Pure Power 13 M 850W `BP027EU`;
- use only supplied modular cables.

### Windows
- Windows 11 Pro Retail/FPP English USB `HAV-00163`.

## Next sequence

1. Choose RAM capacity: **48 / 64 / 128 GB**.
2. Optimize the exact two-DIMM kit for that capacity using live Romanian stock/prices.
3. Re-run the final checkout total.
