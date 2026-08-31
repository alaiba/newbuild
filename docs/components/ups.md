# UPS Deep Dive

Status: **Selected — CyberPower CP1600EPFCLCD for Phase 1**

## Selected strategy

The UPS is sized for the **current workstation configuration**, not for the hypothetical future 600 W GPU envelope.

This is intentionally different from PSU sizing. The PSU is a long-lived permanent component and is therefore sized now for the future high-power GPU. UPS batteries are consumable and the UPS itself should be reassessed when the GPU is replaced. Buying a 2.0-2.2 kW enterprise UPS now would add several thousand lei, size and weight without materially improving protection of the current RTX 3060 workstation.

### Selected Phase-1 UPS

**CyberPower CP1600EPFCLCD**

Architecture and key specifications:

- **1600 VA / 1000 W**
- **line-interactive** topology
- **pure sine-wave** output on battery
- explicitly **Active-PFC compatible**
- AVR
- six Schuko battery-backed/surge-protected outlets on the current EU/Romanian specification
- USB HID connectivity and included USB cable
- PowerPanel Business support for monitoring and automatic shutdown
- user-replaceable sealed lead-acid battery pack
- official replacement pack: **CyberPower RBP0142**, 24 V / 2×12 V 9 Ah
- approximately **9.7 minutes at 500 W** and **2.6 minutes at 1000 W** with a new battery under manufacturer test conditions
- approximately 11 kg, 100 × 280 × 355 mm
- official Romanian warranty: **2 years for the UPS and 2 years for the battery**

This exact model is **Selected as of 2026-08-31**.

## 2026-08-31 purchase-readiness check

Current Romanian pricing is competitive enough to close the SKU:

- general market: roughly **1.47–1.55k lei** among the cheapest current offers;
- **PC Garage: approximately 1,589.80 lei, in stock** in current comparison listings.

The PC Garage premium is only around 40–120 lei versus the cheapest credible offers, which is small enough to follow the project's procurement preference and buy from PC Garage rather than optimize for the last few percent.

Some retailer/aggregator descriptions incorrectly mention four Schuko outlets. The current official CyberPower Romanian specification for `CP1600EPFCLCD` states **six Schuko outlets**. Verify the exact packaging/EAN and physical outlet count on receipt, but use the manufacturer specification as authoritative rather than stale reseller copy.

### Replacement-battery path

The serviceability gate is also satisfied.

CyberPower explicitly specifies **RBP0142** as the replacement battery pack. It contains two 12 V / 9 Ah sealed lead-acid batteries in a 24 V pack.

In addition to the OEM pack, Romanian/EU retailers currently list compatible 2×12 V / 9 Ah replacement kits for the `RBP0142` class around a few hundred lei. OEM replacement is preferred when sensibly priced, but the existence of a standard-size compatible battery path materially reduces the risk of the UPS becoming disposable when the original battery ages.

## Present-system load model

The current GPU is an RTX 3060 12 GB; NVIDIA specifies approximately **170 W graphics-card power** for the reference RTX 3060.

For UPS sizing, a deliberately conservative current workstation envelope is:

- CPU under heavy sustained development/stress: roughly 180-220 W package/platform contribution depending workload;
- RTX 3060: roughly 170 W reference board power, with exact AIB model potentially differing;
- motherboard, RAM, NVMe, fans, USB and conversion margin: roughly 80-130 W;
- combined artificial current-system upper envelope: approximately **450-550 W at the wall**, with ordinary development use typically much lower.

This means a 1000 W UPS should normally operate around or below half load for the present machine and retains substantial margin for simultaneous CPU/GPU bursts.

The objective is not long runtime under maximum stress. It is to survive short outages and voltage events cleanly, then allow controlled shutdown if the outage persists.

## Why pure sine wave

The selected Seasonic-class PSU uses active power-factor correction. A pure sine-wave UPS is the conservative compatibility choice and avoids unnecessary waveform-related behavior during battery operation. Modified/stepped-wave units are excluded even if their VA rating appears attractive.

## Why line-interactive rather than online/double-conversion

A high-quality line-interactive UPS is appropriate for the current desktop workstation because it provides:

- AVR without consuming battery for ordinary under/over-voltage events;
- pure sine-wave battery output;
- short transfer time compatible with modern active-PFC PSUs;
- lower continuous power loss, heat, noise and cost than online double-conversion units.

The selected CyberPower specifies an **8 ms typical transfer time** at normal sensitivity.

Online/double-conversion UPS should be reconsidered only if actual site power quality proves unusually poor or the workstation later becomes an availability-critical service host rather than primarily an interactive development machine.

## Why not size the UPS for the future 600 W GPU now

The future permanent PSU architecture deliberately supports a 600 W accelerator and a possible 900-980 W artificial whole-system load.

A 1000 W UPS would be too close to its rating for that future worst case. A genuine ~2 kW UPS class is technically appropriate if we later want full battery support at those loads.

That spend is not justified today because:

- the RTX 3060 system is nowhere near that load;
- the future GPU is not selected or purchased;
- UPS batteries age and will likely be replaced on a much shorter cycle than the chassis/PSU;
- the future GPU generation may have a materially different power envelope;
- a UPS upgrade can be performed independently when the GPU upgrade happens.

Therefore:

> **The UPS is a current-system protection component with a mandatory reassessment at the future high-power GPU upgrade.**

## Candidate comparison

### CyberPower CP1600EPFCLCD — Selected

- 1600 VA / 1000 W
- pure sine wave
- line-interactive + AVR
- Active-PFC compatible
- six Schuko outlets per current official EU/Romanian specification
- USB HID + PowerPanel Business
- user-replaceable `RBP0142` battery
- current PC Garage price around **1.59k lei**
- official Romanian warranty: 2 years UPS / 2 years battery

This is the best current balance of electrical suitability, runtime, serviceability and Romanian purchase cost.

### APC Back-UPS Pro BR1600SI — rejected as current purchase

The APC is a credible technical alternative:

- 1600 VA / 960 W
- sine-wave output
- line-interactive + AVR
- user-replaceable battery
- USB management

However, current Romanian pricing is roughly **3.2–3.6k lei**, approximately twice the cost of the CyberPower, while providing slightly *less* real output power. APC's service ecosystem is attractive, but the price delta does not buy a corresponding improvement in protection or runtime for this desktop workload.

It remains a fallback if CyberPower service/availability deteriorates materially before purchase.

### Eaton 5SC1500I — premium industrial/control reference

- 1500 VA / 1050 W
- sine-wave output
- line-interactive
- AVR
- USB + RS232
- user-replaceable battery

Its enterprise-oriented ecosystem is useful, but its several-thousand-lei price class is not justified for the current workstation.

### ~2 kW enterprise UPS class — future high-power reference

Revisit Eaton 5PX-class or equivalent 2 kW+ equipment if/when a future GPU materially raises measured workstation load beyond the selected UPS's comfortable range.

## Runtime policy

The target is **graceful-shutdown runtime**, not extended operation through a blackout.

Manufacturer figures for the selected CyberPower:

- ~9.7 minutes at 500 W half-load;
- ~2.6 minutes at 1000 W full load.

The current development workstation should commonly sit well below 500 W outside synthetic combined CPU/GPU stress, so practical runtime should be adequate to bridge short disturbances or initiate a clean shutdown.

Actual runtime must still be measured after assembly because workload, battery condition and connected peripherals materially affect it.

## Peripheral policy

Battery-backed outlets should prioritize:

- workstation tower;
- primary monitor if desired for controlled shutdown;
- essential networking equipment only when doing so does not consume excessive runtime.

Do not automatically place printers, speakers, chargers or other nonessential loads on the battery-backed outlets.

## Software / graceful shutdown

The UPS exposes a USB HID interface and CyberPower recommends **PowerPanel Business** for local monitoring and automatic shutdown.

Operating-system details remain open elsewhere in the build, so the selected UPS must not force a particular OS. During bring-up, validate either PowerPanel or the chosen OS's native UPS integration and perform a controlled mains-loss shutdown test.

The exact hardware decision does **not** remain provisional merely because shutdown software still needs configuration; that is a bring-up task rather than a hardware-selection dependency.

## Battery maintenance

The UPS battery is explicitly a consumable.

- record battery installation/manufacture date if visible;
- run periodic self-tests;
- monitor reported runtime/capacity;
- keep the UPS in a cool, ventilated location;
- replace the battery pack when capacity materially deteriorates rather than replacing the whole UPS;
- perform a real controlled power-loss test after initial setup and after battery replacement.

## Purchase and bring-up checks

The model is selected; remaining work is acceptance/configuration rather than selection:

1. prefer **PC Garage** while its premium remains small;
2. confirm exact SKU **`CP1600EPFCLCD`** and current EU/Schuko packaging;
3. verify the delivered unit has the expected **six Schuko outlets**;
4. retain invoice/warranty information;
5. connect USB and configure PowerPanel/native graceful shutdown;
6. measure real wall/UPS load under CPU-heavy and combined CPU/GPU workloads;
7. perform a controlled mains-loss test;
8. record initial estimated runtime/load as a battery-health baseline.

## Reopen conditions

Reassess the UPS selection when:

- the RTX 3060 is replaced by a materially higher-power GPU;
- measured full-system load approaches roughly **700-800 W** or otherwise leaves inadequate UPS margin;
- runtime becomes insufficient;
- site power quality justifies online/double-conversion topology;
- CyberPower warranty/service availability materially deteriorates before purchase; or
- the workstation begins hosting availability-critical services.
