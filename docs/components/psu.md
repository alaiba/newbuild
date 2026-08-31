# PSU Deep Dive

Status: **Reopened — optimize premium 750 W vs 850 W ATX 3.1; 1200 W target superseded**

## Current architecture

The workstation no longer pre-provisions for a hypothetical future 500–600 W flagship GPU.

Current GPU:

- RTX 3060 12 GB;
- expected to remain installed for as long as it remains useful/reliable;
- future replacement is deferred until a concrete need or failure appears.

If a future GPU replacement eventually needs unusually high power, the PSU may be reconsidered at that time rather than paying now for speculative capacity.

## Sizing target

### 750 W

**Fully valid baseline.**

A premium 750 W ATX 3.1 unit provides substantial headroom for the current 9950X3D + RTX 3060 system and remains compatible with today's roughly 300 W-class GPU tier. This is not an economy compromise; it is a rational size when the build is not designed around a future flagship accelerator.

### 850 W

Keep in the finalist set when:

- the exact 850 W model costs only modestly more than the comparable 750 W unit;
- its acoustics/fan curve are materially better;
- the platform/warranty/components are better;
- the extra 100 W comes essentially free in the final procurement bundle.

Do not pay a meaningful premium solely for the extra 100 W.

### 1000–1200 W

No longer a default target. Buy only if an unusually attractive exact model/price makes it rational or a new concrete GPU requirement appears before purchase.

The former Seasonic VERTEX GX/PX-1200 selection is superseded.

## Quality requirements

Wattage is secondary to quality.

Prioritize:

- ATX 3.1/current transient-handling standard;
- excellent protections: OCP/OVP/UVP/OPP/SCP/OTP as appropriate;
- mature electrical platform;
- reputable OEM/vendor;
- long warranty;
- quiet fan implementation and good efficiency at realistic loads;
- full or sensible modular cabling;
- current GPU-power cable/revision clarity;
- normal Romanian/EU warranty path.

A premium 750 W unit is preferable to a mediocre 1000–1200 W unit.

## Future-GPU interpretation

Performance-per-watt has historically improved substantially across GPU generations, although maximum flagship board power does not necessarily decline. Therefore do not assume that a useful GPU 3–5 years from now will require today's flagship wattage.

The system should support one normal discrete GPU well. It does not need to guarantee compatibility with every future 500–600 W accelerator without a PSU replacement.

## UPS interaction

There is no UPS requirement in the initial BOM. PSU sizing is therefore independent of a hypothetical UPS wattage ceiling.

Use point-of-use surge protection as the practical mains-protection measure under the project's no-electrical-installation-change constraint.

## Next optimization pass

Compare premium Romanian/EU 750 W and 850 W ATX 3.1 models on:

1. electrical quality/protections;
2. warranty and platform maturity;
3. acoustics and fan quality;
4. efficiency at typical workstation loads;
5. exact current GPU-power cabling/revision;
6. delivered price;
7. retailer consolidation.

Do not rank by wattage alone.
