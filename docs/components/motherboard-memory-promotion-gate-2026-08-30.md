# Motherboard / 256 GB Memory Promotion Gate — 2026-08-30

Status: **Completed**

## Decision

**ASUS ProArt X870E-Creator WiFi is promoted to Selected.**

The ASRock X870 Taichi Creator remains an excellent value alternative, but it does not meet the same evidence threshold for the build's hardest long-term requirement: conservative, stable 256 GB operation with an ECC-capable path.

The exact eventual 256 GB memory configuration remains deferred. ECC UDIMM remains strongly preferred if a mature, validated 4×64 GB configuration is available when the upgrade is actually purchased.

## Why ASUS wins the promotion gate

### 1. Explicit 4×64 GB / 256 GB firmware support

ASUS BIOS 1003 (2025-01-23) explicitly added support for four 64 GB DIMMs, total 256 GB, at up to 5200 MT/s when compatible modules are populated.

This is unusually direct evidence for the exact topology we care about. It is stronger than simply advertising a 256 GB maximum.

Source:
- https://www.asus.com/motherboards-components/motherboards/proart/proart-x870e-creator-wifi/helpdesk_bios?model2Name=ProArt-X870E-CREATOR-WIFI

### 2. Continued four-DIMM / high-capacity stability work

ASUS subsequently shipped firmware specifically addressing the same risk area:

- BIOS 1303: enhanced compatibility with high-capacity memory modules;
- BIOS 1504: significantly enhanced memory compatibility with a focus on all four DIMM slots and improved system stability;
- BIOS 2103: additional stability margin during DDR5 training and Ryzen 9000 boot/stability fixes;
- BIOS 2306: explicit ECC-UDIMM performance optimization;
- BIOS 2402: further memory-performance, system-stability and compatibility work.

Starting with AGESA ComboAM5 PI 1.3.0.0, ASUS also states that ECC UDIMM speed is limited to 5200 MT/s with Ryzen 9000 processors.

For this workstation that is a positive constraint, not a disadvantage: we prefer a boring validated operating point over fragile high-frequency memory tuning.

### 3. ASUS QVL structure explicitly covers the relevant categories

The current ProArt memory support page exposes filters for:

- **4×64 GB**;
- **4-DIMM socket support**;
- **ECC-UDIMM** and ordinary U-DIMM;
- 5200 MT/s among supported data-rate classes.

This does not prove that every 4×64 entry is ECC, but it demonstrates that ASUS is actively validating the relevant density/population classes on this board rather than merely listing a theoretical 256 GB maximum.

Source:
- https://www.asus.com/us/supportonly/proart%20x870e-creator%20wifi/helpdesk_qvl_memory/

## ASRock result

The ASRock X870 Taichi Creator remains technically strong:

- official 256 GB maximum;
- official ECC/non-ECC unbuffered DDR5 support;
- two CPU-connected PCIe 5.0 x16 physical slots with x16 or x8/x8 operation;
- 10 GbE + 5 GbE;
- strong diagnostics and recovery features;
- BIOS 4.10 explicitly optimized memory compatibility;
- BIOS 4.50 (2026-08-27) explicitly optimized workstation GPU compatibility.

Sources:
- https://www.asrock.com/mb/AMD/X870%20Taichi%20Creator/index.asp
- https://www.asrock.com/mb/amd/X870%20Taichi%20Creator/bios.html

However, the review still did not find an ASRock statement equivalent to ASUS BIOS 1003 that explicitly validates **four 64 GB modules / 256 GB at a stated operating rate** on this exact board.

Because the whole reason to pay for a workstation-oriented board is to reduce configuration uncertainty, the ASRock's lower price is not enough to overcome that evidence gap.

## 256 GB ECC reality check

A separate issue emerged during the promotion review: **64 GB DDR5 ECC UDIMM availability is still much less mature than 64 GB RDIMM or 32/48 GB ECC UDIMM availability.**

Important distinction:

- AM5 Creator boards require **unbuffered DIMMs (UDIMM)**;
- common 64 GB server modules from Kingston/Micron/Samsung are often **RDIMM**, which is electrically incompatible and must not be purchased for this system;
- mainstream Kingston Server Premier currently exposes 64 GB DDR5 ECC parts primarily as Registered DIMMs, while its readily documented ECC UDIMM line is lower-density;
- 64 GB ECC UDIMMs do exist from specialist/workstation suppliers and newer module vendors, including recent 64 GB ECC UDIMM products from SMART Modular Technologies, but this market is still niche compared with ordinary 64 GB non-ECC UDIMM.

Relevant sources:
- Kingston memory finder: https://www.kingston.com/en/memory
- SMART Modular 2026 DDR5 ECC UDIMM brief: https://www.smtreports.com/salesLiterature/dram/%5BSMART%5D%20DDR5_VLP_ECC_UDIMM_VLP_ECC_CUDIMM_product_brief.pdf

Therefore the build must **not** pretend that a mature retail 4×64 GB ECC kit is already selected.

## Final memory policy after this gate

### Phase 1

Unchanged:

- 32 GB minimum commissioning memory;
- 2×16 GB preferred when similarly priced;
- 1×32 GB acceptable;
- ECC not required;
- temporary kit is replaceable.

### Eventual 256 GB

At the time of purchase:

1. update the ProArt to the then-current stable BIOS;
2. re-check ASUS QVL for exact 64 GB modules and four-DIMM population;
3. first preference: **4×64 GB ECC UDIMM**, but only if exact modules are credible, obtainable and stable;
4. fallback: **4×64 GB non-ECC UDIMM** with strong QVL/vendor evidence;
5. start at JEDEC/Auto settings and accept 5200 MT/s or lower if required for stability;
6. do not use EXPO/XMP merely to preserve a marketing frequency at 256 GB;
7. perform extended memory testing before trusting the workstation;
8. if ECC is installed, verify that corrected/uncorrected events are visible through Windows WHEA and/or Linux EDAC/RAS before treating ECC as operationally useful.

## Price/value

Current Romanian snapshots around 2026-08-30:

- ASUS ProArt X870E-Creator WiFi: approximately **2,590–2,685 lei at the lowest current offers**, with many listings around 2,700–3,000+ lei;
- ASRock X870 Taichi Creator: approximately **1,690–1,820 lei**.

Sources:
- https://www.price.ro/preturi-asus-proart-x870e-creator-wifi-4691168
- https://www.compari.ro/placi-de-baza-c3128/asus/proart-x870e-creator-wifi-p1134442678/
- https://www.compari.ro/placi-de-baza-c3128/asrock/x870-taichi-creator-p1255221784/

The ASUS premium is therefore roughly **800–1,000 lei** at competitive offers.

That premium buys essentially no CPU performance. It is accepted because it buys the strongest available vendor evidence around 4×64 GB / 256 GB and the best firmware trail for the memory/ECC behavior that matters to this build.

## Reopen condition

Reopen the motherboard only if, before actual purchase:

- ASRock publishes equally explicit 4×64 GB / 256 GB validation and its price advantage remains substantial;
- ASUS develops a material firmware/reliability regression;
- ProArt availability or warranty becomes materially worse;
- a new AM5 workstation board offers materially stronger validated 256 GB/ECC behavior without compromising the selected system architecture; or
- the workload changes enough to reopen AM5 itself.
