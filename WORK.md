# ChatGPT Work Handoff

Use this file as the **mandatory entrypoint** for any fresh ChatGPT Work session or other agent operating on this repository.

## Authority and precedence

When repository files disagree, use this precedence order:

1. **`WORK.md`** — current handoff contract and operating rules.
2. **`docs/final-build.md`** — current source-of-truth architecture and purchase state.
3. **`docs/decisions.md`** — closed/superseded decisions and rationale.
4. **`docs/procurement-plan-2026-08-31.md`** — current procurement policy.
5. **`docs/final-order-plan-2026-08-31.md`** — order/basket state.
6. **`docs/purchases-2026-09-01.md`** — immutable record of the first executed order.
7. **`docs/checkout-checklist.md`** — operational purchase/arrival verification workflow.
8. Component dossiers under `docs/components/`.
9. Other date-stamped analysis/history files.

**Historical/date-stamped files may contain superseded decisions. They must never override a higher-precedence current file.**

If a conflict remains after applying this precedence, surface the conflict rather than silently choosing a component.

## Current objective

The architecture is closed and procurement is **partially executed**.

On **2026-09-01**, the first EvoMAG order was placed for:

- AMD Ryzen 9 9950X3D Box/WOF;
- ASUS TUF GAMING B650E-E WIFI;
- Crucial T710 2 TB;
- be quiet! Pure Power 13 M 850W.

Hardware subtotal: **6,519.96 lei including VAT**. Courier: **11.99 lei**. Order total: **6,531.95 lei including VAT**.

Do **not** re-source or re-optimize these four purchased components unless the delivered item is wrong, damaged, cancelled, or a material compatibility defect is discovered.

The Windows 11 Pro license is **already available** and is no longer part of procurement.

The remaining procurement work is only:

- RAM — Crucial Pro `CP2K24G56C46U5`, 48 GB = 2×24 GB;
- CPU cooler — Thermalright Phantom Spirit 120 standard;
- case — be quiet! Pure Base 501 Airflow Black `BG074`.

For purchased items, the next gate is **physical arrival verification**, not price shopping.

## Current selected build

| Component | Exact current selection | Procurement status |
|---|---|---|
| CPU | **AMD Ryzen 9 9950X3D Box/WOF `100-100000719WOF`** | **Purchased 2026-09-01 — EvoMAG; arrival verification pending** |
| Motherboard | **ASUS TUF GAMING B650E-E WIFI `90MB1LT0-M0EAY0`** | **Purchased 2026-09-01 — EvoMAG; exact box SKU must still be verified** |
| RAM | **Crucial Pro `CP2K24G56C46U5` — 48 GB = 2×24 GB DDR5-5600, non-ECC** | **Not yet purchased** |
| CPU cooler | **Thermalright Phantom Spirit 120 — standard model** | **Not yet purchased** |
| Case | **be quiet! Pure Base 501 Airflow Black `BG074`** | **Not yet purchased** |
| Primary SSD | **Crucial T710 2 TB `CT2000T710SSD8`**, bare/non-heatsink | **Purchased 2026-09-01 — EvoMAG; arrival verification pending** |
| PSU | **be quiet! Pure Power 13 M 850W `BP027EU`** | **Purchased 2026-09-01 — EvoMAG; arrival verification pending** |
| GPU | **reuse existing RTX 3060 12 GB** | Already owned |
| Host OS | **Windows 11 Pro x64** | Selected; license already available |
| UPS | **none** | No purchase planned |
| Dedicated surge protector | **none** | No purchase planned |

## Critical anti-substitution rules

### Motherboard

Selected and ordered model:

- `90MB1LT0-M0EAY0` — **TUF GAMING B650E-E WIFI**

Do **not** confuse with:

- `90MB1GT0-M0EAY0` — **TUF GAMING B650-E WIFI**
- B650E-PLUS or other similarly named ASUS boards.

The EvoMAG order text identifies **TUF GAMING B650E-E WIFI**, but the physical box label remains the decisive exact-SKU check. Do not install it until `90MB1LT0-M0EAY0` is confirmed.

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

Purchased target:

- `CT2000T710SSD8` — Crucial T710 2 TB, **bare/non-heatsink**.

Install in motherboard **`M.2_1` CPU PCIe 5.0 x4** under the ASUS motherboard heatsink after the physical SKU is verified.

### PSU

Purchased target:

- `BP027EU` — be quiet! Pure Power 13 M **850W**.

Verify the box/revision on arrival. Use only modular cables supplied with this exact PSU.

### CPU

Purchased target:

- `100-100000719WOF` — Ryzen 9 9950X3D **Box/WOF**.

Reject a tray/OEM substitution on arrival.

## Provider policy

EvoMAG is now the executed **first hardware provider**. Do not change already purchased items merely for consolidation.

For the remaining items:

- prefer at most one additional hardware provider for RAM + cooler + case if exact models and delivered pricing are acceptable;
- exact SKU/warranty/product condition outrank a small nominal saving;
- do not substitute the cooler or case merely to keep everything at EvoMAG.

Windows is explicitly **outside the remaining procurement scope**.

## Current cost position

### Committed spend

| Order | Hardware | Shipping | Total |
|---|---:|---:|---:|
| EvoMAG — 2026-09-01 | **6,519.96 lei** | **11.99 lei** | **6,531.95 lei** |

This committed amount covers CPU, motherboard, SSD and PSU only.

Remaining spend is only for **RAM + cooler + case**. Windows must not be included in future procurement totals.

## What Work should do now

1. Treat CPU, motherboard, SSD and PSU as **purchased**, not shopping candidates.
2. When they arrive, verify physical box labels, seals, condition and exact identities before opening/installing.
3. In particular, confirm motherboard **`90MB1LT0-M0EAY0`** before assembly.
4. Continue procurement only for **RAM, cooler and case**.
5. For remaining items, verify exact SKU/model, stock, warranty, condition and delivered price.
6. Preserve invoices, order confirmations, serials and packaging through commissioning/return windows.
7. Do **not** change the architecture unless a selected exact component is genuinely unavailable or a new material fact justifies reopening it.

## After all purchases arrive

The next phase is assembly and commissioning. Follow `docs/final-build.md` and the component dossiers for:

- BIOS update;
- A2/B2 memory installation and Auto/JEDEC commissioning;
- extended RAM testing;
- T710 firmware/SMART/temperature validation;
- CPU/GPU/storage stress validation;
- Windows 11 Pro + WSL2/Ubuntu setup;
- BitLocker only after firmware/driver/storage stability is established.
