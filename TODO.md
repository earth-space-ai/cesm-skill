# TODO, CESM skill

Items to fill in to bring this skill from scaffold (v0.1.0) to full depth (v0.2.0+).

## Tier B (verifiable from official docs / wiki)

- [ ] List all current compsets with one-line descriptions (parse `cime_config/config_compsets.xml`)
- [ ] List all standard grids with their atmosphere/ocean/land resolutions
- [ ] Document `git-fleximod` vs `manage_externals` migration (which CESM tags use which)
- [ ] Machine port table: which `--mach` strings work on which DOE/NSF systems
- [ ] CMEPS NUOPC mediator overview: which fields are exchanged between components
- [ ] Short-term archive vs long-term archive workflow
- [ ] List of XML files a user typically modifies: `env_run.xml`, `env_build.xml`, `env_mach_pes.xml`

## Tier C (needs operational expertise)

- [ ] Common reasons `case.build` fails on a fresh machine port (PIO, MPI, NetCDF version mismatches)
- [ ] How to debug a hang in the coupling layer (CMEPS log file conventions, ESMF logs)
- [ ] When to use `--pecount` shorthand vs hand-tuning `env_mach_pes.xml`
- [ ] Conventions for hybrid runs (initializing from a previous restart)
- [ ] Branch / hybrid / startup distinction in `env_run.xml`
- [ ] SourceMods workflow for one-off code changes without forking

## Cross-component routing

- [ ] For each component, link to the component-specific skill in the `Earth-Space-Modeling-skills` org
- [ ] Document the case layout under `$CASEROOT` and `$RUNDIR` (logs, run/, bld/, archive/)

## Verification

- [ ] Cite the CESM2 paper (Danabasoglu et al. 2020, JAMES, doi:10.1029/2019MS001916) in the right places
- [ ] Cross-check version numbers and tags against current ESCOMP/CESM releases
- [ ] Run Gemini critique on each `reference/*.md` once filled in
