# ChatGPT Work Handoff

Use this file as the **mandatory entrypoint** for any fresh ChatGPT Work session or other agent operating on this repository.

## Authority and precedence

When repository files disagree, use this precedence order:

1. **`WORK.md`** — current handoff contract and operating rules.
2. **`docs/final-build.md`** — current source-of-truth architecture.
3. **`docs/decisions.md`** — closed/superseded decisions and rationale.
4. **`docs/procurement-plan-2026-08-31.md`** — current procurement policy.
5. **`docs/final-order-plan-2026-08-31.md`** — current checkout basket/reference prices.
6. **`docs/checkout-checklist.md`** — operational purchase-verification workflow.
7. Component dossiers under `docs/components/`.
8. Date-stamped analysis/history files.

**Historical/date-stamped files may contain superseded decisions. They must never override a higher-precedence current file.**

If a conflict remains after applying this precedence, stop and surface the conflict rather than silently choosing a component.

## Current objective

The architecture is closed. The current task is **procurement verification and checkout preparation**, not component redesign.

Use current Romanian retailer pages to verify:

- exact manufacturer SKU;
- new-retail condition;
- stock / realistic lead time;
- warranty path;
- delivered price including shipping;
- retailer quality/provenance where relevant.

Do not substitute a different product merely because the marketing name looks similar or because consolidation would be easier.

## Current selected build

| Component | Exact current selection |
|---|---|
| CPU | **AMD Ryzen 9 9950X3D Box/WOF `100-100000719WOF`** |
| Motherboard | **ASUS TUF GAMING B650E-E WIFI `90MB1LT0-M0EAY0`** |
| RAM | **Crucial Pro `CP2K24G56C46U5` — 48 GB = 2×24 GB DDR5-5600, non-ECC** |
| CPU cooler | **Thermalright Phantom Spirit 120 — standard model** |
| Case | **be quiet! Pure Base 501 Airflow Black `BG074`** |
| Primary SSD | **Crucial T710 2 TB `CT2000T710SSD8`**, bare/non-heatsink |
| PSU | **be quiet! Pure Power 13 M 850W `BP027EU`** |
| GPU | **reuse existing RTX 3060 12 GB** |
| Windows | **Windows 11 Pro Retail/FPP English USB `HAV-00163`** |
| UPS | **none** |
| Dedicated surge protector | **none** |

## Critical anti-substitution rules

### Motherboard

Selected:

- `90MB1LT0-M0EAY0` — **TUF GAMING B650E-E WIFI**

Do **not** confuse with:

- `90MB1GT0-M0EAY0` — **TUF GAMING B650-E WIFI**
- B650E-PLUS or other similarly named ASUS boards.

Verify the exact SKU on the retailer page, in cart/order confirmation and on the physical box.

### RAM

Selected:

- `CP2K24G56C46U5` — **48 GB total as 2×24 GB**

Do **not** substitute:

- `CP24G56C46U5` — single 48 GB DIMM;
- 2×32 or 2×64 GB merely for availability;
- four-DIMM configurations;
- RDIMM/server memory.

Install the final kit in **A2/B2** and commission at Auto/JEDEC first.

If 48 GB later proves insufficient, replace the pair with a larger matched two-DIMM kit. Do not add a second pair as the planned upgrade path.

### SSD

Selected:

- `CT2000T710SSD8` — Crucial T710 2 TB, **bare/non-heatsink**.

Install in motherboard **`M.2_1` CPU PCIe 5.0 x4** under the ASUS motherboard heatsink.

### PSU

Selected:

- `BP027EU` — be quiet! Pure Power 13 M **850W**.

Do not substitute another wattage/revision without explicit review. Use only modular cables supplied with the exact PSU.

### CPU

Selected:

- `100-100000719WOF` — Ryzen 9 9950X3D **Box/WOF**.

Do not silently substitute a tray/OEM SKU.

### Windows

Selected:

- `HAV-00163` — Windows 11 Pro **Retail/FPP English USB**.

Do not substitute OEM/System Builder or suspicious low-cost digital keys without explicit licensing review.

## Provider policy

- maximum **three providers overall**;
- target at most **two hardware providers**;
- exact SKU/warranty/product condition outrank a small nominal saving;
- do not pay a large premium solely to force everything into one hardware retailer.

Current likely structure:

- **EvoMAG** as main hardware basket if exact SKUs are verified;
- a second hardware retailer for RAM if `CP2K24G56C46U5` is materially cheaper or unavailable at EvoMAG;
- **PROstore** for Windows if `HAV-00163` remains the best trustworthy Retail/FPP offer.

This provider structure is not itself fixed. Re-optimize delivered price while respecting the provider limit and exact-SKU gates.

## Current price context

Reference values in this repository are **snapshots, not checkout quotes**.

The selected 48 GB RAM was chosen after current 64/128 GB pricing became disproportionately expensive. A reference total around **~11.0–11.3k lei before shipping** was obtained using the then-current non-RAM basket plus the 48 GB kit.

Always refresh live prices before presenting a final total.

## What Work should do

For a procurement-verification run:

1. Read this file and `docs/final-build.md`.
2. Read `docs/checkout-checklist.md`.
3. Browse current Romanian retailer pages for each exact SKU.
4. Verify manufacturer code, stock, warranty, condition and delivered price.
5. Prefer supplier consolidation only when it does not compromise exact SKU or value.
6. Produce a final basket showing provider, exact SKU, item price, shipping, delivered subtotal and total.
7. Explicitly flag any retailer page whose title/specification conflicts with the manufacturer code.
8. Do **not** change the architecture unless a selected exact component is genuinely unavailable or a new material fact justifies reopening it.
9. Do **not** place an irreversible order or submit payment without explicit user authorization at that stage.

## After purchase

The next phase is assembly and commissioning, not component research. Follow `docs/final-build.md` and the component dossiers for:

- BIOS update;
- A2/B2 memory installation and Auto/JEDEC commissioning;
- extended RAM testing;
- T710 firmware/SMART/temperature validation;
- CPU/GPU/storage stress validation;
- Windows 11 Pro + WSL2/Ubuntu setup;
- BitLocker only after firmware/driver/storage stability is established.
