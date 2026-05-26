# CESM Skill

A progressive-disclosure skill for the [Community Earth System Model](https://github.com/ESCOMP/CESM) (CESM), NSF NCAR's coupled Earth-system modeling framework.

> **Maintainer of CESM:** NSF NCAR / Climate and Global Dynamics Lab and the ESCOMP community
> **Skill author:** Koutian Wu (ktwu01@gmail.com)
> **Skill version:** 0.1.0-scaffold

> ⚠️ **Disclaimer — please read before using this skill.**
> This skill is **not a gold-standard reference**. It is a helper that lowers
> the barrier for new users to **get their hands dirty** with the model. AI
> agents (and the humans drafting this material) make mistakes; commands, file
> paths, namelist options, and physics explanations here can be wrong,
> incomplete, or out of date. **Always cross-check with the official model
> documentation, the source code, and a human expert before trusting any
> output for research, publication, or operational use.**

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

- [cam-skill](https://github.com/earth-space-ai/cam-skill), atmosphere
- [ctsm-skill](https://github.com/earth-space-ai/ctsm-skill), land
- [mom6-skill](https://github.com/earth-space-ai/mom6-skill), ocean
- [cice-skill](https://github.com/earth-space-ai/cice-skill), sea ice
- [waccm-skill](https://github.com/earth-space-ai/waccm-skill), whole-atmosphere variant
- [waccmx-skill](https://github.com/earth-space-ai/waccmx-skill), extended whole-atmosphere variant

## Acknowledgments

**Gold-standard references for CESM** (use these to cross-check anything in this skill):
- ESCOMP/CESM repository: https://github.com/ESCOMP/CESM
- CESM Quickstart: https://escomp.github.io/CESM/release-cesm2/
- CESM2 description paper: Danabasoglu et al. 2020, JAMES, doi:10.1029/2019MS001916
- CIME documentation (case control system): https://esmci.github.io/cime/

This scaffold exists only because of the work of other people, and any value
it has is borrowed from theirs.

- **NSF NCAR / Climate and Global Dynamics Lab** and the **ESCOMP
  community** for building and maintaining
  [ESCOMP/CESM](https://github.com/ESCOMP/CESM), the CIME case-control
  system, the public Sphinx documentation, and the coupled-modeling
  framework this skill teaches users to drive.
- The **CMEPS mediator** developers (NCAR + NOAA) for the coupling
  architecture this skill routes through.
- The maintainers of every component model that ships inside a CESM
  configuration: CAM, CTSM, MOM6, CICE, MOSART, RTM, WACCM, WACCM-X.
  Each has its own sibling skill that this one routes into.
- **Zesen Huang** for [laps-skill](https://github.com/huangzesen/laps-skill),
  the progressive-disclosure layout this repo borrows.

Any errors, oversimplifications, or out-of-date claims in this skill are the
skill author's responsibility, not the upstream community's. This is a
scaffold; operational depth is being filled in iteratively.

## License

MIT (skill content). The CESM code itself is governed by its own license; see https://github.com/ESCOMP/CESM/blob/main/LICENSE.txt.
