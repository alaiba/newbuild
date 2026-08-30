# UPS Deep Dive

Status: **Phase-1 architecture selected / exact model provisional**

## Selected strategy

The UPS should be sized for the **current workstation configuration**, not for the hypothetical future 600 W GPU envelope.

This is intentionally different from PSU sizing. The PSU is a long-lived permanent component and is therefore sized now for the future high-power GPU. UPS batteries are consumable and the UPS itself can reasonably be reassessed when the GPU is replaced. Buying an enterprise-class 2.0-2.2 kW UPS now to cover a future accelerator would add several thousand lei and substantial size/weight without improving the current workstation materially.

### Phase-1 UPS architecture

- **Line-interactive** topology
- **Pure sine-wave output on battery**
- **Active-PFC compatible**
- approximately **1600 VA / 1000 W** output class
- AVR
- USB monitoring and graceful shutdown support
- user-replaceable battery
- tower form factor preferred for the current workstation

### Current provisional target

**CyberPower CP1600EPFCLCD**

Official specifications include:

- 1600 VA / 1000 W
- pure sine-wave battery output
- line-interactive topology
- AVR
- active-PFC compatibility
- USB connectivity / PowerPanel management
- user-replaceable sealed lead-acid battery
- approximately 9.7 minutes runtime at half load and 2.6 minutes at full rated load
- six Schuko outputs in the EU variant

Current Romanian pricing observed in August 2026 is approximately **1.5-1.6k lei** for competitive listings.

## Present-system load model

The current GPU is an RTX 3060 12 GB; NVIDIA specifies approximately **170 W graphics-card power** for the reference RTX 3060.

For UPS sizing, a deliberately conservative current workstation envelope is:

- CPU under heavy sustained development/stress: roughly 180-220 W package/platform contribution depending workload;
- RTX 3060: roughly 170 W reference board power, with exact AIB model potentially differing;
- motherboard, RAM, NVMe, fans, USB and conversion margin: roughly 80-130 W;
- combined artificial current-system upper envelope: approximately **450-550 W at the wall**, with ordinary development use typically much lower.

This means a 1000 W UPS normally operates around or below half load for the present machine and retains enough margin for simultaneous CPU/GPU bursts.

The objective is not long runtime under maximum stress. It is to survive short outages, voltage events and transfer to battery cleanly, then allow controlled shutdown if the outage persists.

## Why pure sine wave

The selected Seasonic-class PSU uses active power-factor correction. A pure sine-wave UPS is the conservative compatibility choice and avoids unnecessary waveform-related behavior during battery operation. Modified/stepped-wave units are therefore excluded for this workstation even if their VA rating appears attractive.

## Why line-interactive rather than online/double-conversion

A high-quality line-interactive UPS is appropriate for the current desktop workstation because it provides:

- AVR without consuming battery for ordinary under/over-voltage events;
- pure sine-wave battery output;
- short transfer time compatible with modern active-PFC PSUs;
- lower continuous power loss, heat, noise and cost than online double-conversion units.

Online/double-conversion UPS should be reconsidered only if the actual site power quality proves unusually poor or the workstation later becomes an availability-critical service host rather than primarily an interactive development machine.

## Why not size the UPS for the future 600 W GPU now

The future permanent PSU architecture deliberately supports a 600 W accelerator and a possible 900-980 W artificial whole-system load.

A 1000-1050 W UPS would be too close to its rating for that future worst case. A genuine 2.0-2.2 kW UPS class is technically appropriate if we later want full battery support at those loads. For example, Eaton's current 5PX 2200 Gen2 provides 2200 VA / 2200 W pure-sine line-interactive output, but current Romanian pricing is roughly **6.1k lei** without the network-card premium.

That spend is not justified today because:

- the RTX 3060 system is nowhere near that load;
- the future GPU is not selected or purchased;
- UPS batteries age and will likely be replaced on a much shorter cycle than the chassis/PSU;
- the future GPU generation may have a materially different power envelope;
- a UPS upgrade can be performed independently when the GPU upgrade happens.

Therefore:

> **The UPS is a current-system protection component with a mandatory reassessment at the future high-power GPU upgrade.**

## Candidate comparison

### CyberPower CP1600EPFCLCD — provisional target

- 1600 VA / 1000 W
- pure sine wave
- line-interactive + AVR
- active-PFC compatible
- user-replaceable battery
- Schuko outputs
- current RO price roughly 1.5-1.6k lei

This is the best current value fit for the workstation.

### Eaton 5SC1500I — premium industrial/control reference

- 1500 VA / 1050 W
- sine-wave output
- line-interactive
- AVR
- USB + RS232
- user-replaceable battery
- eight C13 outputs
- current RO pricing roughly **3.4-3.8k lei**

The Eaton provides a more enterprise-oriented ecosystem and excellent serviceability, but its roughly 2k+ lei premium does not currently buy enough practical benefit for this desktop use case.

### Eaton 5PX 2200 Gen2 — future high-power reference

- 2200 VA / 2200 W
- pure sine wave
- line-interactive
- power factor 1.0
- USB/serial and optional network management
- current Romanian pricing roughly **6.1k lei** for the non-Netpack version

This class should be revisited if/when the future GPU materially raises real measured workstation load beyond the Phase-1 UPS's comfortable range.

## Runtime policy

The target is **graceful-shutdown runtime**, not extended operation through a blackout.

For the provisional CyberPower unit:

- manufacturer: ~9.7 minutes at 500 W half-load;
- manufacturer: ~2.6 minutes at 1000 W full load;
- current development workload should commonly sit below 500 W, so practical runtime should generally be sufficient to bridge short events or trigger a clean shutdown.

Actual runtime must be measured after assembly because workload, battery condition and peripherals materially affect it.

## Peripheral policy

Battery-backed UPS outlets should prioritize:

- workstation tower;
- primary monitor if desired for controlled shutdown;
- essential networking equipment only when doing so does not consume excessive runtime.

Do not automatically place printers, speakers, chargers or other nonessential loads on battery-backed outputs.

## Battery maintenance

The UPS battery is explicitly a consumable.

- record battery installation date;
- run periodic self-tests;
- monitor reported runtime/capacity;
- keep the UPS in a cool, ventilated location;
- plan for battery replacement rather than replacing the complete UPS merely because the battery ages;
- perform a real controlled power-loss test after initial setup and after battery replacement.

## Promotion gate

Before the exact UPS is promoted from provisional to **Selected**:

1. refresh Romanian price and warranty;
2. verify the exact CP1600EPFCLCD EU/Schuko model and included USB cable;
3. verify replacement-battery availability and current cost;
4. confirm PowerPanel or native OS UPS integration on the selected operating system;
5. after assembly, measure real wall power under CPU-heavy and combined CPU/GPU loads;
6. confirm the measured load remains comfortably below the UPS's 1000 W rating;
7. configure and test automatic graceful shutdown.

## Reopen condition

Reassess UPS sizing when:

- the RTX 3060 is replaced by a materially higher-power GPU;
- measured full-system load approaches roughly 700-800 W or otherwise leaves inadequate UPS margin;
- runtime becomes insufficient;
- site power quality justifies online/double-conversion topology; or
- the workstation begins hosting availability-critical services.
