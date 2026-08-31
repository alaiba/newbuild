# UPS / Power Protection Deep Dive

Status: **No UPS and no dedicated surge protector in the initial BOM**

## Decision

Do **not** buy a UPS for the initial workstation.

Do **not** buy a dedicated point-of-use surge protector for the initial workstation.

The previous CyberPower PR1500ELCD and later plug-in surge-protector purchase ideas are superseded.

Short outages are operationally acceptable, and the incremental value of a dedicated surge-protection purchase does not justify its cost for this use case and risk tolerance.

## Baseline power connection

Use:

- a properly earthed 230 V wall outlet;
- if additional sockets are required, a reputable ordinary **16 A Schuko power strip** as a utility item.

The ordinary power strip is not treated as a special protection component in the BOM.

## What a UPS would solve

A UPS can provide:

- ride-through for brief outages;
- time for graceful shutdown;
- reduced interruption to long-running jobs;
- voltage regulation on suitable models.

Those benefits are currently low priority.

## What a dedicated surge protector would solve

A plug-in surge protector can provide an additional sacrificial transient-protection layer. It does not guarantee survival from every electrical event and does not substitute for proper building-level protection or earthing.

The selected PSU already contains normal input/protection circuitry. The project accepts the residual mains risk rather than buying another dedicated device without evidence of a local power-quality problem.

## Outage / power-quality policy

Occasional short outages are accepted. Mitigations remain:

- version control;
- independent backups;
- mature filesystems/applications;
- avoiding firmware/BIOS updates during obviously unstable mains conditions;
- saving work normally.

Revisit external protection only if actual evidence appears, such as repeated unexplained equipment failures, abnormal voltage behavior or outages that materially disrupt VM/database workflows.

## Superseded selections

The following are no longer purchase targets:

- CyberPower PR1500ELCD;
- earlier 1000 W-class UPS candidates;
- sizing a UPS around a hypothetical high-power future workstation;
- buying a UPS mainly for surge protection;
- dedicated plug-in surge protector / surge-protected power strip as a BOM requirement.

## Selected conclusion

- **UPS:** none initially.
- **Dedicated surge protector:** none initially.
- **Continuity requirement:** none.
- **Normal connection:** properly earthed wall outlet; ordinary reputable 16 A Schuko strip only if more sockets are needed.
- **Electrical installation changes:** none required by this project.
- **Future reconsideration:** only if real observed power-quality/outage problems create a concrete need.
