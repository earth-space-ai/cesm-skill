---
name: cesm
description: >
  Progressive-disclosure skill for the Community Earth System Model (CESM),
  the NCAR/ESCOMP coupled climate modeling framework. Covers the CESM
  superproject (manage_externals + git-fleximod), the cime case-control
  workflow (create_newcase, case.setup, case.build, case.submit), the
  component model layout (CAM, CTSM, MOM6, POP2, CICE, CISM, WW3, MOSART),
  compsets and resolutions, history output, and contribution model.
  Routes into per-component skills (cam-skill, ctsm-skill, mom6-skill,
  cice-skill) for component-specific depth.
version: 0.1.0-scaffold
tags:
  - earth-science
  - climate-model
  - earth-system-model
  - coupled-model
  - cesm
  - cime
  - ncar
  - escomp
  - fortran
---

# CESM (Community Earth System Model) Complete Guide

> **CESM** = Community Earth System Model, NSF NCAR's flagship coupled climate / Earth-system model.
> Maintainer: NSF NCAR / Climate and Global Dynamics (CGD) Lab + ESCOMP community
> Source: https://github.com/ESCOMP/CESM
> Quickstart: https://escomp.github.io/cesm
> Website: https://www.cesm.ucar.edu
> Slack: https://cesm2.slack.com
> Skill author: Koutian Wu (ktwu01@gmail.com)
> Skill version: 0.1.0-scaffold

**What CESM does:** Couples atmosphere (CAM), land (CTSM), ocean (MOM6 or POP2), sea ice (CICE), land ice (CISM), waves (WW3), and runoff (MOSART/RTM/mizuRoute) components into one configurable Earth-system model. Components communicate through the CMEPS NUOPC mediator. CESM has been a primary contributor to CMIP since CMIP3 and underlies many of the Working Group science campaigns at NCAR.

**Who this skill is for:** Agents, students, and researchers who need to download, build, configure, run, customize, debug, and contribute to CESM as a coupled system. For deep work in any single component, route into the component-specific skill.

---

## Quick Decision Tree

```
"What do I need?"
│
├─ 🆕 First time. What is CESM and how do I get the code?
│  └─ Read: reference/getting-started.md
│     (Repo layout, manage_externals, git-fleximod, prerequisites)
│
├─ 🚀 I want to run a CESM case end-to-end
│  └─ Read: reference/running-a-case.md
│     (create_newcase → case.setup → case.build → case.submit)
│
├─ 🧬 I want to understand the component model layout and how they couple
│  └─ Read: reference/architecture.md
│     (Components, CMEPS mediator, compsets, grids)
│
├─ 🔬 I want to switch components, change resolution, or write a new compset
│  └─ Read: reference/compsets-and-grids.md
│
├─ 📊 I need to understand history files, archiving, post-processing
│  └─ Read: reference/output-and-archiving.md
│
├─ 🐛 My case won't build, won't submit, or fails on a specific machine
│  └─ Read: reference/debugging.md
│
└─ 📝 I want to contribute to CESM or any component
   └─ Read: reference/contributing.md
```

---

## Repo Layout (verified from clone)

```
CESM/
├── bin/                        # Helper scripts
├── ccs_config/                 # CESM Case Setup configuration (grids, compsets, machines)
├── ChangeLog                   # Top-level change history
├── cime/                       # Common Infrastructure for Modeling the Earth (case control)
├── cime_config/                # CIME configuration for CESM
├── components/                 # Pulled in via manage_externals: cam, clm, mom, pop2, cice, cism, ww3, ...
├── doc/                        # Sphinx documentation source
├── libraries/                  # Shared libraries (e.g., parallelio)
├── share/                      # Shared CESM source (drv code, mediator hooks)
└── tools/                      # Pre/post processing utilities
```

This repo is a **superproject**. The actual model code for each component is fetched into `components/<name>/` from `ESCOMP/CAM`, `ESCOMP/CTSM`, etc., via `git-fleximod` (and historically `manage_externals`). Cloning this repo alone gets you the framework, you must run the externals tool to get the science code.

---

## Critical Rules

1. **Never edit the `main` branch directly.** CESM uses release branches and feature branches, with strict tagging conventions managed by CSEG. Use `release-cesm2.x.y` or `cesm3_x_y` branches.
2. **Always run `bin/git-fleximod update` after cloning** (or the older `manage_externals/checkout_externals` for older tags). Without this you have an empty `components/` tree.
3. **Use cime tools, not bare Makefiles.** Cases are created and built through `create_newcase`, `case.setup`, `case.build`, `case.submit`, not by invoking compilers directly.
4. **A "compset" is the science configuration. A "grid" is the resolution. A "case" is one instance.** Internalize this vocabulary.
5. **CESM is large.** A full `B1850` case (fully coupled, pre-industrial) needs serious HPC. For development, start with `X` (data atmosphere/land/ocean) or `F` (CAM + CLM, prescribed SST) compsets.

---

## Reference Index

| File | Topic |
|---|---|
| [reference/getting-started.md](reference/getting-started.md) | Cloning, externals, prerequisites |
| [reference/architecture.md](reference/architecture.md) | Components, CMEPS, coupling |
| [reference/running-a-case.md](reference/running-a-case.md) | Full case workflow |
| [reference/compsets-and-grids.md](reference/compsets-and-grids.md) | Compset/grid selection |
| [reference/output-and-archiving.md](reference/output-and-archiving.md) | History files, short-term archive |
| [reference/debugging.md](reference/debugging.md) | Common build/run failures |
| [reference/contributing.md](reference/contributing.md) | PR workflow into ESCOMP |

---

## Status

This skill is at **scaffold** depth. The structure, repo layout, vocabulary, and routing are verified against the cloned source tree. Per-section operational depth (specific namelist values, machine-port quirks, common compset gotchas) is being filled in iteratively. See `TODO.md` for the open items.
