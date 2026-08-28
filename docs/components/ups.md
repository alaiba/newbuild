# UPS Deep Dive

Status: **Open**

## Scope

No UPS topology, VA rating, output wattage or exact model has been selected.

The previously discussed **1000–1500 VA line-interactive** class is a reference range only and must be validated against the final system power model.

## Review focus

- realistic workstation power draw
- actual UPS output wattage, not VA alone
- line-interactive versus other appropriate topologies
- pure sine-wave value/requirement
- AVR
- transfer behavior
- USB monitoring / graceful shutdown
- compatibility with the selected active-PFC PSU
- runtime at realistic workstation load
- whether capacity should cover only the current RTX 3060 configuration or also a future high-power GPU
- surge/power-conditioning characteristics where meaningful
- battery replacement availability and cost
- serviceability
- Romanian availability, warranty and pricing

## Required output

Finish with:

1. present-system load model
2. future-GPU UPS design assumption
3. justified topology and watt/VA class
4. exact UPS recommendation
5. runtime estimates at representative loads
6. PSU compatibility rationale
7. battery-maintenance/replacement expectations
8. Romanian price/value
