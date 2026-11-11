# Embodied Physics Contract

A minimal data contract for physically auditable embodied episodes.

This is **not** a training format. RGB, language, and end-effector actions may exist elsewhere; they do not fill this contract.

**Version:** `gradia.embodied_physics.v1`

- Spec: [`PUBLIC_SCHEMA_v1.md`](PUBLIC_SCHEMA_v1.md)
- Example episode: [`schema.example.json`](schema.example.json)

## Scope

This repository only defines the `gradia.embodied_physics.v1` data contract and a format example.

The reference auditor `audit_episode.py` lives in the local Gradia workbench. It is not published with this repository.

`schema.example.json` is a format example. It is not a reproducible audit pack.

## Audit order

1. Empty `frames` → `NOT_RUN`
2. Schema incomplete → `INVALID`, list the missing fields, **do not** run physics rules
3. Only a legal schema is scored by R1–R3 (teleport, velocity reverse, penetration)

## INVALID

`INVALID` rejects the capture. It is not “safe”. It is not a policy `FAIL`. It is not a physics failure. It only means the log has no computable physical witness.

## Boundary

A `PASS` on the example only shows that the format is readable. It does not show that a real capture pipeline is viable.

The reference auditor lives in the local workbench. **It is not published with this repository.**

## Related

- Product / CEL: [liao-zhizhi/agent-metabolism-os](https://github.com/liao-zhizhi/agent-metabolism-os)
- Paper 7, *The Physical Grounding Fault*: [10.5281/zenodo.24139787](https://doi.org/10.5281/zenodo.24139787)
- Seven-paper series: [liao-zhizhi/causal-evolution-paper](https://github.com/liao-zhizhi/causal-evolution-paper)
