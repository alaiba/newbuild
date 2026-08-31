# Procurement Plan — 2026-08-31

This plan optimizes the selected workstation for **total lifetime value and administrative simplicity**, not the absolute lowest item-by-item price.

## Procurement objective

1. **Maximum three providers.**
2. **Default target: two providers.**
3. One provider is welcome if every revision/SKU can be verified cleanly.
4. Add provider #3 only for roughly **≥300 lei net saving**, materially better stock/revision certainty, or materially better warranty/service.
5. Consider both **cheaper substitutions and premium upgrades**. Extra spend is justified when it buys disproportionate improvement in stability, endurance, serviceability or useful lifetime.

## Recommended provider structure

### Provider 1 — EvoMAG: primary order

Use EvoMAG for the ordinary BOM while the live cart remains close to current controls.

| Item | Exact target | Working price control | Gate |
|---|---|---:|---|
| CPU | Ryzen 9 9950X3D Box/WOF `100-100000719WOF` | **3,349.99 lei** | exact Box/WOF preferred |
| Motherboard | ASUS ProArt X870E-Creator WiFi | ~**2,685 lei** | recompare only if live cart moves materially above ~2.85k |
| RAM | Crucial `CT2K32G56C46U5`, 64 GB 2×32 | fresh EvoMAG/comparison control ~**4,799.99 lei** | exact `...U5`; reject laptop `...S5` |
| Cooler | Noctua NH-D15 G2 standard | ~**690.99 lei** | standard, not LBC/HBC |
| SSD | Samsung 990 PRO 2 TB `MZ-V9P2T0BW` | **1,899.99 lei** | exact bare 2 TB drive |
| Case | Fractal North XL Mesh `FD-C-NOR1X-01` | **882.99 lei** | exact SKU; `-01` is Mesh |
| Rear fan | Noctua NF-A14x25 G2 PWM standard single | **200.99 lei** | square-frame standard PWM |
| UPS | **CyberPower PR1500ELCD** | **~2,948.99 lei** | exact 1500 VA / 1350 W model |
| Windows | **Windows 11 Pro Retail/FPP USB Romanian `HAV-00197`** | **~1,199.99 lei** | Retail/FPP; use English display language after install if desired |
| GPU | existing RTX 3060 12 GB | 0 lei | reuse |

### Provider 2 — Altex: PSU

Practical baseline:

- **Seasonic VERTEX GX-1200 ATX 3.1**
- current explicit Altex reference: **1,289.99 lei**
- hard receipt gate: PCIe 5.1 + supplied 12V-2x6.

#### Premium PSU rule

If a **known-current VERTEX PX-1200 ATX 3.1** becomes available from Altex/Media Galaxy or EvoMAG at **≤~200 lei premium over GX**, prefer PX.

Current reference PX price is around **1,449.99 lei**, approximately +160 lei, which is good lifetime value for Platinum efficiency. The explicit current listing is presently out of stock, so **do not delay the build for PX**.

### One-provider opportunity

If EvoMAG confirms in writing that its Seasonic VERTEX 1200 W unit is:

- ATX 3.1;
- PCIe 5.1;
- supplied with current 12V-2x6;

then the full order may be consolidated to **EvoMAG alone**, provided the total price is sensible.

## Current representative totals

With the selected **PR1500ELCD** and purchase-ready **GX-1200**:

- representative complete order: **~19,949 lei before shipping**.

With a PX-1200 at the current ~160 lei premium:

- representative complete order: **~20,109 lei before shipping**.

Both remain roughly **10k lei below** the planning level.

These are controls, not guaranteed checkout totals. The exact RAM and stock situation must be confirmed in the cart.

## Widened price/performance review

“Performance” here includes workload throughput **plus stability, endurance, serviceability, warranty and avoiding future replacement**.

| Change considered | Price effect | Verdict | Reason |
|---|---:|---|---|
| 9950X3D → 9950X | save ~650 lei | **Keep 9950X3D** | little/no compile advantage from downgrade and much weaker gaming; permanent CPU |
| ProArt → X870 Taichi Creator | save ~900–1,000+ | **Keep ProArt** | strongest explicit 4×64/256 GB and ECC-oriented firmware evidence is worth the premium |
| NH-D15 G2 → Phantom Spirit | save ~400–490 | **Keep Noctua** | stronger support/mounting ecosystem, fan endurance, six-year warranty for 10-year ownership |
| 990 PRO → KC3000 | save ~50–60 | **Keep Samsung** | trivial saving versus mature firmware/tooling and already-validated topology |
| 990 PRO → Samsung 9100 PRO | spend ~200 more | **Reject upgrade** | PCIe 5 bandwidth is wasted in selected PCIe 4 `M.2_3`; moving it to `M.2_1` consumes the reserved future work-drive slot |
| Crucial 64 GB → Kingston `KF556C36BBEK2-64` | spend ~500–600+ more currently | **Keep Crucial** | explicit Kingston compatibility is useful, but not worth current premium over conservative 1.1 V Crucial; reconsider if gap shrinks to ~200–250 |
| 64 GB → 128 GB Phase-1 | spend ~6k+ more | **Reject** | excessive temporary sunk cost before final 256 GB matched set |
| Phase-1 ECC 64 GB | spend ~6k+ more | **Reject** | large premium without proving end-to-end ECC reporting; defer ECC decision to 256 GB endpoint |
| GX-1200 → PX-1200 | spend ~160 currently | **Prefer if available ≤200 premium** | modest lifelong conversion-loss/heat reduction; same 12-year warranty and architecture |
| GX/PX → 1600 W PSU | spend ~1k+ more | **Reject** | no useful benefit for planned single-GPU AM5 architecture |
| CP1600EPFCLCD → **PR1500ELCD** | spend ~1.4k more | **Upgrade selected** | raises real output 1000→1350 W and likely avoids replacing the UPS at future 900–980 W system load; better runtime/AVR/hot-swap battery |
| PR1500ELCD → PR1500ERT2U | spend ~900 more | **Reject** | only ~150 W extra plus rack features; poor marginal value for desktop |
| line-interactive → online UPS | spend materially more | **Reject absent bad mains evidence** | adds continuous heat/noise/loss without demonstrated site requirement |
| `HAV-00163` English FPP from third seller → `HAV-00197` Romanian FPP at EvoMAG | spend ~50–75 more | **Switch to `HAV-00197`** | equivalent Pro Retail/FPP rights and Windows Pro can use English UI; removes a provider |
| Noctua rear fan → ARCTIC | save ~125–160 | **Keep Noctua** | exact Noctua is already at EvoMAG; MTTF/warranty better match endurance goal |

## Third-provider rule

Do not create provider #3 for small savings.

Examples:

- ~50–100 lei cheaper Windows elsewhere: **not enough**;
- ~100–150 lei on a fan/cooler/SSD: generally **not enough**;
- ≥300 lei net on the exact same component with equal warranty and clear stock: **consider provider #3**.

## Hard acceptance gates

### CPU
- exact Ryzen 9 9950X3D;
- Box/WOF `100-100000719WOF` preferred.

### Motherboard
- exact ASUS ProArt X870E-Creator WiFi.

### RAM
- exact `CT2K32G56C46U5`;
- 64 GB / 2×32;
- desktop 288-pin UDIMM;
- reject `CT2K32G56C46S5`.

### Cooler
- NH-D15 G2 **standard**;
- no LBC/HBC substitution.

### SSD
- exact `MZ-V9P2T0BW`;
- 2 TB bare M.2 2280.

### PSU
For GX or conditional PX:
- ATX 3.1;
- PCIe 5.1;
- current 12V-2x6 cable;
- reject explicit old ATX 3.0 / 12VHPWR stock.

### Case
- exact `FD-C-NOR1X-01` North XL Charcoal Black Mesh.

### Rear fan
- standard square-frame NF-A14x25 G2 PWM single fan.

### UPS
- exact **PR1500ELCD**;
- 1500 VA / 1350 W;
- new/sealed;
- note IEC C13 outlet topology and use correctly rated IEC cables.

### Windows
- Windows 11 Pro;
- **Retail/FPP**;
- preferred consolidated SKU **`HAV-00197`**;
- not OEM/DSP or an undocumented key.

## Ordering strategy

1. Build one EvoMAG cart with all primary items and capture exact SKUs/prices before checkout.
2. Place the Altex Seasonic order in the same purchasing session unless EvoMAG confirms a current VERTEX revision.
3. If an in-stock PX meets the ≤~200 lei premium rule, take PX; otherwise take GX.
4. Do not dismantle the current PC until CPU, motherboard, RAM, cooler and case have physically arrived and passed visual/SKU inspection.
5. Keep invoices, serial numbers, product-page evidence and packaging together in a single long-term warranty folder.

## Core source controls

- EvoMAG CPU: https://www.evomag.ro/componente-pc-gaming-procesoare/amd-procesor-amd-ryzen-9-9950x3d-4.3ghz-144mb-170w-am5-box-4206997.html
- EvoMAG RAM: https://www.evomag.ro/componente-pc-gaming-memorii/crucial-kit-memorii-ram-crucial-dual-channel-2x32gb-ddr5-negru-4147822.html
- EvoMAG cooler: https://www.evomag.ro/componente-pc-gaming-coolere-coolere-cpu/noctua-cooler-procesor-noctua-nh-d15-g2-standard-compatibil-intel-amd-4175302.html
- EvoMAG SSD: https://www.evomag.ro/componente-pc-gaming-solid-state-drive-ssd/samsung-ssd-samsung-990-pro-2tb-pci-express-4.0-x4-m.2-2280-4031722.html
- EvoMAG case: https://www.evomag.ro/componente-pc-gaming-carcase/fractal-design-carcasa-fractal-design-north-xl-solid-middle-tower-fara-sursa-atx-e-atx-negru-4149667.html
- EvoMAG fan: https://www.evomag.ro/componente-pc-gaming-coolere-ventilatoare/noctua-ventilator-noctua-nf-a14x25-g2-pwm-140mm-4197885.html
- CyberPower PR1500ELCD official: https://www.cyberpower.com/eu/en/product/sku/pr1500elcd
- Seasonic GX: https://seasonic.com/vertex-gx/
- Seasonic PX: https://seasonic.com/vertex-px/
- Altex GX: https://altex.ro/sursa-pc-seasonic-vertex-gx-1200-atx-3-1-1200w-135mm-80-plus-gold-full-modular/cpd/VERTEXGX1200/
- Microsoft Windows language management: https://support.microsoft.com/windows/manage-the-input-and-display-language-settings-in-windows-219f28b0-9881-cd4c-75ca-dba919c52321
