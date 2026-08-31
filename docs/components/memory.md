# Memory Deep Dive

Status: **Final architecture selected — 128 GB from day one as 2×64 GB / 1DPC; exact kit under optimization**

## Final decision

The workstation will **not** use a provisional RAM configuration.

Buy the intended lifetime memory capacity at initial assembly:

- **128 GB total**;
- **2×64 GB DDR5 UDIMM**;
- **one DIMM per memory channel (1DPC)**;
- install in the motherboard-recommended two-DIMM slots, normally **A2/B2**;
- exact kit/SKU still to be selected;
- ECC versus non-ECC still to be decided on evidence, not assumed.

This replaces the previous plan to start with 64 GB (2×32 GB) and eventually move to 256 GB (4×64 GB).

## Why 128 GB / 2×64 GB is now the endpoint

For this workstation, 128 GB is accepted as sufficient lifetime capacity for the expected Java/Android/IDE/WSL2/container/VM workload.

The topology is important. On AM5, 2×64 GB keeps the platform at **1DPC** rather than moving to the electrically harder **2DPC** four-DIMM configuration. That gives the CPU memory controller and motherboard firmware a materially easier signal-integrity/training problem and preserves a better chance of conservative, stable operation at useful DDR5 rates.

The build therefore chooses:

> **enough capacity at the electrically cleaner topology**

rather than buying 256 GB merely because the board can physically support it.

## No provisional RAM

The following previous ideas are superseded:

- 32 GB commissioning/minimum-cost memory;
- 64 GB Phase-1 memory;
- Crucial `CT2K32G56C46U5` as the selected purchase target;
- adding a second 2×32 GB kit later for 128 GB;
- replacing Phase-1 RAM with a 4×64 GB matched set for 256 GB.

The RAM purchased for initial assembly should be the final intended set.

## Exact-kit selection criteria

The next optimization pass should choose the exact 2×64 GB kit using the following priority order:

1. **stability and motherboard/CPU validation evidence**;
2. conservative JEDEC behavior and sane operating voltage;
3. exact 2×64 GB matched-kit availability;
4. manufacturer/module consistency and firmware compatibility;
5. low physical profile compatible with the NH-D15 G2;
6. warranty and long-term vendor support;
7. price/performance under the project's stability/endurance definition;
8. ECC only if the entire path is credible and worthwhile.

Headline memory frequency and latency are secondary. There is no requirement to force EXPO/XMP or a particular DDR5 number if Auto/JEDEC provides the more robust baseline.

## ECC

ECC is no longer entangled with the old 256 GB / four-DIMM requirement.

For the final 2×64 GB purchase, evaluate ECC independently:

- exact ECC UDIMM must be supported by the chosen motherboard/platform;
- firmware must expose credible ECC operation;
- Windows/Linux should provide usable evidence/reporting of corrected/uncorrected errors;
- the ECC option must not introduce a large price or compatibility penalty without a corresponding reliability benefit.

If that end-to-end case is weak, use a well-validated non-ECC 2×64 GB kit.

**RDIMM remains incompatible with AM5.**

## Bring-up policy

For the final 128 GB configuration:

1. install the two 64 GB DIMMs in A2/B2 or the exact slots specified by the selected motherboard manual;
2. update to a current stable BIOS before serious validation;
3. boot at **Auto/JEDEC** first;
4. do not enable EXPO/XMP during baseline validation;
5. accept conservative trained settings when necessary;
6. run extended memory stability testing;
7. record exact SKU, BIOS/AGESA, trained rate/timings and voltage behavior;
8. only consider tuning after the baseline is demonstrably stable.

## Cooler clearance

The selected Noctua NH-D15 G2 and Fractal North XL provide substantial clearance margin. The exact 2×64 GB kit should nevertheless prefer low-profile modules where practical so that RAM choice does not force unnecessary front-fan lift or complicate serviceability.

## Motherboard consequence

The previous ASUS ProArt X870E-Creator WiFi selection was influenced heavily by evidence around 4×64 GB / 256 GB and ECC-oriented four-DIMM firmware behavior.

That justification is now materially weakened because the final topology is 2×64 GB / 1DPC.

Therefore the **exact motherboard is reopened for optimization**. The ProArt remains an incumbent reference, not an automatic final purchase.

## Selected conclusion

- **Final capacity:** **128 GB**.
- **Final topology:** **2×64 GB / 1DPC**.
- **Timing:** **buy the final RAM configuration from day one**.
- **Temporary/Phase-1 RAM:** **none**.
- **Exact kit:** open for the next optimization pass.
- **ECC:** evaluate on end-to-end evidence; not mandatory.
- **Operating policy:** Auto/JEDEC first; stability over headline speed.
- **256 GB / 4×64 GB:** no longer a design target.
