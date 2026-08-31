# Initial BOM Purchase Review — 2026-08-31

> **Superseded historical snapshot. Do not use for ordering or current totals.**
>
> Later on 2026-08-31 the architecture changed materially: final memory became **128 GB / 2×64 GB / 1DPC from day one**, the motherboard was reopened, and storage became **~1 TB system NVMe + 4 TB work NVMe from day one**. Windows procurement also moved to the verified `HAV-00163` Retail/FPP target from PROstore. See `docs/final-build.md`, `docs/decisions.md` and `docs/procurement-plan-2026-08-31.md` for current state.

This file is retained only as an audit trail of an earlier procurement/value snapshot.

## Historical optimized complete-order position

The earlier provider/value pass used a default of two providers and produced these representative totals:

- **~19,949 lei before shipping** with Seasonic VERTEX GX-1200;
- **~20,109 lei before shipping** with VERTEX PX-1200 at the then-reference ~160 lei premium.

These totals are obsolete because they assumed the old RAM, motherboard and storage purchase plan.

## Historical controls

| Component | Earlier target | Earlier working control |
|---|---|---:|
| CPU | Ryzen 9 9950X3D Box/WOF `100-100000719WOF` | 3,349.99 lei EvoMAG |
| Motherboard | ASUS ProArt X870E-Creator WiFi | ~2,685 lei |
| RAM | Crucial `CT2K32G56C46U5`, 64 GB 2×32 | ~4,799.99 lei |
| Cooler | Noctua NH-D15 G2 standard | ~690.99 lei |
| SSD | Samsung 990 PRO 2 TB `MZ-V9P2T0BW` | 1,899.99 lei |
| PSU baseline | VERTEX GX-1200 current ATX 3.1 | 1,289.99 lei Altex |
| PSU conditional upgrade | VERTEX PX-1200 current ATX 3.1 | 1,449.99 lei reference |
| Case | Fractal North XL Mesh `FD-C-NOR1X-01` | 882.99 lei EvoMAG |
| Rear fan | Noctua NF-A14x25 G2 PWM | 200.99 lei EvoMAG |
| UPS | CyberPower PR1500ELCD | 2,948.99 lei |
| GPU | existing RTX 3060 12 GB | 0 lei |
| Windows | Windows 11 Pro Retail/FPP `HAV-00197` Romanian USB | 1,199.99 lei EvoMAG |

## Historical decisions that remain relevant

The snapshot still records useful reasoning for choices that have not been reopened:

- the UPS upgrade from the 1000 W CP1600 class to **PR1500ELCD 1350 W** was intended to avoid a likely UPS replacement when a future high-power GPU is installed;
- **GX-1200** remains the purchase-ready PSU baseline and **PX-1200** remains attractive only at a small premium;
- the Noctua cooler, North XL Mesh and rear-fan selections remain based on long-term serviceability/airflow rather than minimum purchase price.

## Decisions from this snapshot that are explicitly obsolete

Do not carry forward:

- 64 GB / 2×32 GB Crucial Phase-1 RAM;
- 256 GB / 4×64 GB eventual RAM assumptions;
- ProArt motherboard selection justified by 4×64 GB behavior;
- Samsung 990 PRO 2 TB as the selected system SSD;
- deferring the 4 TB work SSD;
- EvoMAG `HAV-00197` as the preferred Windows purchase;
- the ~19.9–20.1k total.

A new priced purchase review will be produced after the exact motherboard, 2×64 GB RAM kit and two SSD models are selected.
