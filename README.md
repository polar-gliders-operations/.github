<p align="center"> <a href="https://obs.polargliders.com"> <img src="https://obs.polargliders.com/img/logos/polar_glider_logo.png" alt="Polar Gliders" height="90"> </a> &nbsp;&nbsp;&nbsp;&nbsp; <a href="https://www.gu.se/en/department-of-marine-sciences"> <img src="https://obs.polargliders.com/img/logos/gu_white.svg" alt="University of Gothenburg" height="90"> </a> </p> <h1 align="center">Polar Gliders</h1>

Research group at the Department of Marine Sciences, University of Gothenburg, studying the Southern Ocean and the air-sea interface with autonomous platforms.

**Live data:** [obs.polargliders.com](https://obs.polargliders.com)

---

## Platforms

| Platform | Prefix | What we use it for |
|---|---|---|
| Wave Glider | `waveglider-` | Surface air-sea fluxes and upper ocean |
| Seaglider | `seaglider-` | Profiling, ADCP, biogeochemistry |
| Sailbuoy | `sailbuoy-` | Long-endurance surface observations |
| X-Spar | `xspar-` | Spar buoy measurements |
| Floats | `float-` | Profiling floats |

New platform? Pick a short lowercase prefix, add it here, and you are done.

---

## Repository naming

Format: `<scope>-<purpose>`, lowercase, words separated by hyphens. No spaces, underscores or capitals.

**Scope** is either a platform prefix from the table above, or one of:

| Scope | Use for |
|---|---|
| `obs-` | Anything feeding the public observation portal |
| `proj-` | A single campaign or project spanning platforms (e.g. `proj-whirls`) |
| `paper-` | Code for one publication (e.g. `paper-ar-heatflux-2026`) |
| *(none)* | Genuinely cross-platform shared code (`toolbox`) |

**Purpose** is one word where possible:

`processing`, `preflight`, `piloting`, `calibration`, `qc`, `dashboard`, `decoder`, `plotting`

### Examples

| Repo | Meaning |
|---|---|
| `waveglider-processing` | NRT and delayed-mode processing |
| `waveglider-preflight` | Dockside and pre-mission diagnostics |
| `seaglider-adcp` | ADCP decoding and processing |
| `sailbuoy-piloting` | Piloting tools and website |
| `xspar-processing` | X-Spar data processing |
| `float-qc` | Float quality control |
| `obs-polargliders` | Data loading and plotting for the obs portal |
| `proj-whirls` | Campaign level code, configs and mission notes |
| `toolbox` | Shared functions used across the group |

### Suggested renames for existing repos

| Current | Suggested | Why |
|---|---|---|
| `sailbuoy` | `sailbuoy-piloting` | Matches the pattern, says what it does |
| `web-portal` | `obs-web-portal` | Groups it with the obs repos |
| `air-sea-interactions` | `air-sea-best-practice` | Name describes the purpose, not just the topic |
| `waveglider-xdata` | `waveglider-xdata` | Already fine |

GitHub redirects old URLs after a rename, but update local remotes with `git remote set-url origin <new-url>`.

---

## Topics (tags)

Add topics to every repo so the org page is filterable. Use the same vocabulary everywhere:

- Platform: `wave-glider`, `seaglider`, `sailbuoy`, `x-spar`, `float`
- Type: `data-processing`, `diagnostics`, `visualisation`, `shared-library`
- Always: `oceanography`, `polar-gliders`

---

## Visibility

- **Public** by default for processing, tooling and shared code.
- **Private** while a repo contains unpublished results, credentials, vendor specific material or anything under embargo. Make it public once published.
- **Never commit** raw data, API tokens, SSH keys or `.env` files. Use environment variables and a `.gitignore`.

---

## Every repo should have

```
README.md        What it does, how to install, a minimal example
LICENSE          GPL-3.0 unless there is a reason otherwise
environment.yml  Conda environment (or requirements.txt)
.gitignore       Data, outputs, notebooks checkpoints
src/ or <pkg>/   Reusable code as importable functions
notebooks/       Exploration only, outputs cleared before commit
config/          YAML configs, no hard coded paths
```

Rule of thumb: if a notebook cell gets copy pasted twice, move it into a function (and if two platforms need it, into `toolbox`).

---

## Working together

- `main` is always working. Do your changes on a branch (`yourname/short-description`) and open a pull request.
- Use issues for bugs, ideas and to-dos, and tag them with the platform.
- Commit messages: short, present tense, say what changed (`Fix pressure offset in glider QC`).
- Clear notebook outputs before committing, they bloat history.

---

## Pinned repositories

Pin the six that new people should see first: `toolbox`, `obs-polargliders`, plus one processing repo per most active platform.

---

## Contact

Questions about the group or repos: *add name / email here*
