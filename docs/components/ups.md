# UPS Deep Dive

Status: **Selected — CyberPower PR1500ELCD, 1500 VA / 1350 W**

## Decision

Use the **CyberPower PR1500ELCD** as the workstation UPS.

This replaces the previously selected `CP1600EPFCLCD` after the final procurement/value pass widened the comparison to include **higher-priced components when the additional spend materially improves lifetime value**.

The change is deliberate: the UPS now becomes a likely long-lived workstation component rather than a Phase-1-only device that would probably need replacement when the future high-power GPU is installed.

## Why the PR1500ELCD wins

The original `CP1600EPFCLCD` remains an excellent current-system UPS:

- 1600 VA / 1000 W;
- line-interactive;
- pure sine wave;
- Active-PFC compatible;
- AVR;
- USB/PowerPanel;
- user-replaceable battery.

However, the permanent PSU/platform architecture intentionally preserves a future system envelope around **900–980 W** with one roughly 600 W-class GPU.

At that load:

- a 1000 W UPS would be operating near **90–98%** of its real-power rating;
- the `PR1500ELCD`'s **1350 W** real-power rating puts the same load around **67–73%**.

That is a materially better long-term operating point for thermal margin, runtime and overload headroom.

The approximately **1.4k lei** premium over the CP1600 therefore buys more than extra VA on paper: it has a credible chance of avoiding a complete UPS replacement when the GPU is upgraded.

## Selected model specifications

CyberPower **PR1500ELCD**:

- **1500 VA / 1350 W**;
- line-interactive topology;
- **pure sine-wave** battery output;
- explicitly **Active-PFC compatible**;
- **Double Boost + Single Buck AVR**;
- approximately **4 ms transfer time**;
- manufacturer runtime approximately **17 minutes at half load** and **4 minutes at full load**;
- user-replaceable, **hot-swappable** battery pack;
- official replacement battery: **`RBP0023`**;
- USB/serial management and PowerPanel Business support;
- EPO support;
- optional SNMP/network-management path;
- metal chassis;
- approximately **25.1 kg**;
- **8× IEC C13** battery-backed outlets, split into critical/non-critical banks;
- official connected-equipment guarantee class materially above the CP1600 reference;
- official UPS/battery warranty remains 2 years in the current regional specification.

Official source:
- https://www.cyberpower.com/eu/en/product/sku/pr1500elcd

## Outlet/cabling consequence

Unlike the Schuko-oriented CP1600, the PR1500ELCD uses **IEC C13 outlets**.

That is acceptable for this workstation and should not block the upgrade:

- the PC PSU uses a standard IEC appliance inlet;
- most monitors use IEC power inlets or can be supported with appropriate certified cabling;
- use normal rated IEC cables or a suitable high-quality PDU for any peripherals that genuinely need Schuko;
- do not improvise ungrounded adapters.

The cleaner enterprise-style IEC layout is a small logistics cost, not a technical disadvantage.

## Current-system behavior

The existing RTX 3060 configuration is expected to be far below the UPS's 1350 W ceiling.

A conservative current-system artificial upper envelope remains around **450–550 W at the wall**. At that load the PR1500 has abundant headroom and substantially more graceful-shutdown runtime than required.

The purpose remains:

1. ride through short power disturbances cleanly;
2. use AVR instead of battery for ordinary voltage variation;
3. initiate controlled shutdown when an outage persists;
4. protect the workstation without running the UPS near its real-power limit.

## Why line-interactive remains correct

The premium upgrade does **not** change the topology decision.

A good line-interactive pure-sine UPS remains preferable to online/double-conversion for this interactive workstation because it avoids unnecessary continuous conversion loss, heat, fan noise and cost while retaining fast transfer, AVR and clean battery output.

Reconsider online/double-conversion only if actual site power measurements show unusually poor mains quality or the workstation becomes an availability-critical service host.

## Rejected alternatives

### CyberPower CP1600EPFCLCD

**Rejected after final value optimization, not because it is poor.**

It remains the better low-upfront-cost choice for the current RTX 3060 machine, but its 1000 W ceiling makes a future 900–980 W system too close to full load. Buying it now would create a credible second UPS purchase later.

### CyberPower PR1500ERT2U

This raises output to roughly **1500 W** and adds rack/tower-oriented features, but current Romanian pricing is roughly another **~900 lei** above the PR1500ELCD.

The extra 150 W and rack features do not materially improve our single-desktop use case. The PR1500ELCD already provides comfortable margin for the future design envelope.

### APC/Eaton premium alternatives

Credible enterprise alternatives exist, but current pricing does not beat the PR1500ELCD on the combination of:

- 1350 W real output;
- pure sine wave;
- AVR;
- runtime;
- hot-swappable batteries;
- serviceability;
- Romanian availability.

### Simulated-sine high-VA units

Rejected. High headline VA/real-power ratings do not compensate for giving up the pure-sine/Active-PFC compatibility policy.

## Current Romanian procurement position — 2026-08-31

Fresh comparison listings place the **PR1500ELCD around 2.95k lei**, including an EvoMAG offer around **2,948.99 lei**.

This is particularly attractive for the consolidated procurement strategy because EvoMAG is already the primary provider for most of the BOM.

Purchase rule:

- prefer EvoMAG if the live cart remains near **~2.95k lei**;
- do not add a third provider merely to save tens of lei;
- a third provider becomes rational only under the build-level procurement rule: roughly **300 lei+ net saving** or materially better stock/warranty certainty.

## Bring-up and validation

1. record exact model/serial and battery manufacture/install date where visible;
2. use correctly rated IEC cabling;
3. connect USB and configure PowerPanel Business / graceful shutdown;
4. measure idle, development, CPU-heavy and combined CPU/GPU UPS load;
5. perform a controlled mains-loss test;
6. record baseline runtime/load/battery-health values;
7. periodically run self-tests and replace the battery pack when capacity materially deteriorates.

## Reopen conditions

Reassess only if:

- the eventual measured system load approaches roughly **1.1 kW or more** for sustained periods;
- the future GPU/platform changes beyond the planned single-GPU envelope;
- runtime proves inadequate for the desired shutdown policy;
- site power quality justifies online/double-conversion;
- the exact PR1500ELCD becomes unavailable or materially overpriced before purchase.

## Selected conclusion

- **Exact UPS:** CyberPower **PR1500ELCD** — **Selected**
- **Capacity:** 1500 VA / **1350 W**
- **Topology:** line-interactive, pure sine, Active-PFC compatible
- **Serviceability:** hot-swappable `RBP0023` battery path
- **Procurement:** target EvoMAG around the current ~2,949 lei class
- **Reason for premium:** avoids running the future high-power workstation near UPS full load and is likely to eliminate a later UPS replacement
