# CESM Skill

A progressive-disclosure skill for the [Community Earth System Model](https://github.com/ESCOMP/CESM) (CESM), NSF NCAR's coupled Earth-system modeling framework.

> **Maintainer of CESM:** NSF NCAR / Climate and Global Dynamics Lab and the ESCOMP community
> **Skill author:** Koutian Wu (ktwu01@gmail.com)
> **Skill version:** 0.1.0-scaffold

## What This Is

A self-contained knowledge package that teaches AI agents (and humans) how to download, build, configure, run, customize, debug, and contribute to CESM as a coupled Earth-system framework. For deep work inside a single component (CAM, CTSM, MOM6, CICE, etc.), this skill routes into the relevant component-specific skill.

Progressive disclosure:
- `SKILL.md` is the routing hub: decision tree, repo layout, quick start, critical rules
- `reference/*.md` are deep-dive docs loaded on demand

## Contents

- `SKILL.md`, entry point with decision tree
- `reference/getting-started.md`, clone, externals, prerequisites
- `reference/architecture.md`, components, CMEPS mediator, coupling
- `reference/running-a-case.md`, `create_newcase` to `case.submit`
- `reference/compsets-and-grids.md`, compset/grid selection
- `reference/output-and-archiving.md`, history files, archiving
- `reference/debugging.md`, common failures
- `reference/contributing.md`, PR workflow into ESCOMP
- `TODO.md`, open items for future depth

## Status

**Scaffold (v0.1.0-scaffold).** Structure and source-grounded surface verified against the cloned `ESCOMP/CESM` tree. Operational depth (specific namelist values, machine ports, compset gotchas) being filled in iteratively.

## Related skills in this org

- [cam-skill](https://github.com/Earth-Space-Modeling-skills/cam-skill), atmosphere
- [ctsm-skill](https://github.com/Earth-Space-Modeling-skills/ctsm-skill), land
- [mom6-skill](https://github.com/Earth-Space-Modeling-skills/mom6-skill), ocean
- [cice-skill](https://github.com/Earth-Space-Modeling-skills/cice-skill), sea ice
- [waccm-skill](https://github.com/Earth-Space-Modeling-skills/waccm-skill), whole-atmosphere variant
- [waccmx-skill](https://github.com/Earth-Space-Modeling-skills/waccmx-skill), extended whole-atmosphere variant

## License

MIT (skill content). The CESM code itself is governed by its own license; see https://github.com/ESCOMP/CESM/blob/main/LICENSE.txt.
