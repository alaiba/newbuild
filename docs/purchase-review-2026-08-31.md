# Initial BOM Purchase Review — 2026-08-31

This is a dated price snapshot. The exact order execution and acceptance gates are in `docs/procurement-plan-2026-08-31.md`.

## Current complete-order position

Representative current complete initial purchase, including the required Windows 11 Pro Retail/FPP license and excluding the reused RTX 3060, is approximately **18.9–19.3k lei before shipping**.

The range is intentional: RAM and UPS listings currently show the largest price/stock inconsistencies, so quoting a single exact total would be false precision.

## Current controls

| Component | Selected target | Current working reference |
|---|---|---:|
| CPU | Ryzen 9 9950X3D Box/WOF `100-100000719WOF` | **3,349.99 lei** direct EvoMAG indexed page |
| Motherboard | ASUS ProArt X870E-Creator WiFi | ~**2,542–2,654 lei** competitive in-stock controls |
| RAM | Crucial `CT2K32G56C46U5`, 64 GB 2×32 | ~**5.0k-class** current market; strict exact-SKU gate |
| Cooler | Noctua NH-D15 G2 standard `CPNTD15G2` | ~**701–730 lei** |
| SSD | Samsung 990 PRO 2 TB `MZ-V9P2T0BW` | ~**1,900–1,953 lei** |
| PSU | Seasonic VERTEX GX-1200 current ATX 3.1 | **1,289.99 lei** explicit Altex listing |
| Case | Fractal North XL Mesh `FD-C-NOR1X-01` | **1,018.51 lei** exact ForIT listing |
| Rear fan | Noctua NF-A14x25 G2 PWM standard single | ~**193 lei** |
| UPS | CyberPower `CP1600EPFCLCD` | use ~**1.65–1.75k lei** checkout envelope |
| GPU | Existing RTX 3060 12 GB | 0 lei new spend |
| Windows | Windows 11 Pro Retail/FPP USB English `HAV-00163` | **1,123.60–1,146.55 lei** current direct retailer controls |

## RAM conclusion

**64 GB remains selected.**

The current target is still Crucial `CT2K32G56C46U5`, 2×32 GB DDR5-5600 CL46 1.1 V. Current pricing is higher/less consistent than the earlier ~4.7–4.8k snapshot, but the complete build still remains far below the planning level.

Purchase gate:

- exact desktop **`CT2K32G56C46U5`** only;
- reject laptop/SO-DIMM **`CT2K32G56C46S5`**;
- if the Crucial checkout price approaches the price of Kingston `KF556C36BBEK2-64`, recompare Kingston because it is explicitly listed by Kingston for the ProArt.

## Windows conclusion

The license decision is now exact:

**Microsoft Windows 11 Pro Retail/FPP USB English `HAV-00163`.**

This is a required purchase because no transferable Windows license is already available. Retail/FPP was selected instead of OEM/DSP for the strict licensing path on a DIY self-build.

Current direct retailer controls:

- Prostore: approximately **1,123.60 lei**, exact `HAV-00163`, Retail/FPP, supplier stock;
- ForIT: approximately **1,146.55 lei**, exact `HAV-00163`, Retail/FPP, supplier stock;
- Microsoft direct remains the **1,199 RON** reference.

Do not substitute OEM/DSP or a cheap standalone emailed key.

## Deferred cost

Excluded from the initial total:

- future 4 TB-or-larger work/VM/container SSD;
- future high-VRAM GPU;
- eventual 256 GB matched memory configuration;
- any future UPS enlargement required by that GPU/load.

## Source controls

- CPU direct: https://www.evomag.ro/componente-pc-gaming-procesoare/amd-procesor-amd-ryzen-9-9950x3d-4.3ghz-144mb-170w-am5-box-4206997.html
- ProArt market: https://www.pricy.ro/ProductUrlId/placa-de-baza-asus-proart-x870e-creator-wifi--socket-am5-7E95DB2CF7553837275C1FDE2803A4E0
- RAM market: https://www.compari.ro/memorii-c3577/crucial/64gb-2x32gb-ddr5-5600mhz-ct2k32g56c46u5-p993167062/
- Kingston fallback: https://www.price.ro/preturi-kingston-memorie-fury-beast-64gb-2x32gb-ddr5-5600mhz-cl36-kf556c36bbek2-64-4046486
- cooler: https://www.price.ro/preturi-noctua-nh-d15-g2-4652246
- SSD: https://solid-state-drive-ssd-intern.compari.ro/samsung/990-pro-2tb-m-2-mz-v9p2t0bw-p885630345/
- PSU: https://altex.ro/sursa-pc-seasonic-vertex-gx-1200-atx-3-1-1200w-135mm-80-plus-gold-full-modular/cpd/VERTEXGX1200/
- case: https://www.forit.ro/fractal-design-north-xl-charcoal-black-tower-case-black-mesh-version-bp939671
- fan: https://www.vexio.ro/noctua/pagina10/
- UPS: https://www.compari.ro/ups-uri-surse-neintreruptibile-c3133/cyberpower/cp1600epfclcd-1600va-p1051248901/
- Windows ForIT: https://www.forit.ro/sistem-de-operare-microsoft-windows-11-pro-64-bit-engleza-retail-fpp-usb-flash-bp414367
- Windows Prostore: https://www.prostore.ro/sisteme_de_operare/microsoft/93926-windows-11-pro-64-bit-engleza-retail-fpp-usb-flash/
