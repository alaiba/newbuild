# Memory Deep Dive

Status: **Selected — Crucial `CT2K64G56C46U5`, 128 GB as 2×64 GB / 1DPC / non-ECC**

## Final decision

Use:

> **Crucial `CT2K64G56C46U5` — 128 GB (2×64 GB) DDR5-5600 CL46, 1.1 V, non-ECC UDIMM**

Install the two DIMMs in **A2/B2** on the selected ASUS TUF GAMING B650E-E WIFI.

There is no temporary RAM stage and no planned four-DIMM/256 GB expansion.

## Why this topology

128 GB is accepted as sufficient lifetime capacity for the expected Java/Android/IDE/WSL2/container/VM workload.

Using two 64 GB DIMMs keeps AM5 at **one DIMM per channel (1DPC)**, avoiding the harder signal-integrity/training conditions of four populated DIMM slots.

The chosen policy is therefore:

> enough capacity once, in the electrically cleaner topology.

## Why this exact kit

The Crucial kit fits the stability-first objective particularly well:

- matched **2×64 GB** retail kit;
- native **DDR5-5600 JEDEC** behavior;
- conservative **1.1 V** operating voltage;
- CL46-class JEDEC timings rather than an aggressive OC profile;
- low-profile unbuffered modules;
- Micron high-density DDR5 construction.

There is no requirement to enable EXPO/XMP. Unlike many enthusiast 128 GB kits whose advertised 5600 rate relies on a higher-voltage profile, this kit reaches the intended rate through its normal JEDEC definition.

### Compatibility basis on the selected board

The motherboard change from B850 to B650E-E does not change the intended 2×64 / JEDEC-5600 topology:

- AMD officially specifies the Ryzen 9 9950X3D for DDR5-5600 with two DIMMs, including both 2×1R and 2×2R cases;
- the ASUS TUF GAMING B650E-E WIFI supports up to 256 GB DDR5 and its memory-support interface explicitly includes **2×64 GB** and **5600** validation categories;
- ASUS continues to maintain the board's Ryzen 9000/JEDEC memory firmware path;
- the selected Crucial kit is a conservative 1.1 V JEDEC product rather than an overclocked profile.

The current public ASUS table does not surface the exact Crucial part number in the static result we can inspect, so do **not** record an unsupported claim that this exact kit is ASUS-QVL-listed for this exact board. The practical acceptance gate is successful A2/B2 training at native JEDEC plus extended validation during commissioning.

## ECC verdict

The final configuration is **non-ECC**, but this is a procurement/topology decision rather than a platform limitation.

The Ryzen 9 9950X3D and ASUS TUF GAMING B650E-E WIFI support ECC UDIMM. The problem is module availability at the required density:

- mainstream current ECC UDIMM product families commonly stop below 64 GB per module;
- readily available 64 GB server DDR5 modules are predominantly **RDIMM**;
- **RDIMM is incompatible with AM5**.

Obtaining ECC should therefore not force this workstation away from its selected 128 GB / 2×64 GB / 1DPC architecture.

Do not substitute:

- 4×32 GB merely to obtain ECC;
- 2×48 GB and reduce the intended capacity;
- RDIMM/server memory;
- an expensive enthusiast kit merely for tighter timings.

ECC support on the selected board remains an unused platform capability, not a motherboard selection driver.

## Physical compatibility

Selected cooler/case:

- Thermalright **Phantom Spirit 120 standard**;
- be quiet! **Pure Base 501 Airflow `BG074`**.

The Crucial modules are low-profile, making them a clean match for the dual-tower cooler. The case provides substantial additional cooler-height tolerance if minor front-fan adjustment is ever necessary.

## Bring-up policy

1. Install DIMMs in **A2/B2**.
2. Update the motherboard to a current stable production BIOS.
3. First boot at **Auto/JEDEC**.
4. Confirm native **DDR5-5600 at 1.1 V** behavior when trained normally.
5. Do not enable EXPO/XMP during commissioning.
6. Run extended memory testing before treating the workstation as stable.
7. Record BIOS/AGESA version, trained timings, memory voltage and SoC voltage.
8. Do not raise voltage or tighten timings merely for benchmark gains.

Representative validation should include a boot/cold-boot cycle set plus long memory stress testing and real sustained development workloads.

## Procurement note

128 GB 2×64 GB DDR5 pricing is currently unusually high and volatile. The exact SKU is selected, but **supplier/price is not locked** until the final procurement refresh.

A recent direct Romanian reference for this exact kit was around **7.7k lei at EvoMAG**, materially higher than older cached Romanian offers around the mid-6k range. Treat older indexed prices as stale and recheck live stock before ordering.

Do not replace the selected kit with a more expensive RGB/EXPO product solely because memory-market pricing is temporarily distorted.

## Superseded memory plans

- 32 GB commissioning configuration;
- 64 GB / 2×32 GB Phase 1;
- Crucial `CT2K32G56C46U5`;
- 128 GB via four 32 GB DIMMs;
- 256 GB / 4×64 GB endpoint;
- ECC as a hard requirement.

## Selected conclusion

- **Capacity:** 128 GB.
- **Topology:** 2×64 GB / 1DPC / A2+B2.
- **Exact kit:** Crucial `CT2K64G56C46U5`.
- **Operating point:** native JEDEC DDR5-5600, 1.1 V, Auto/JEDEC first.
- **ECC:** non-ECC final configuration.
- **Temporary RAM:** none.
