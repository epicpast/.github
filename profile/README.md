<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/epicpast/.github/main/assets/banner-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/epicpast/.github/main/assets/banner-light.svg">
  <img alt="Epic Pastures - Where Regenerative Agriculture Meets Open Source Technology" src="https://raw.githubusercontent.com/epicpast/.github/main/assets/banner-light.svg">
</picture>

<div align="center">

# Epic Pastures

**Regenerative Agriculture | Sheep Genetics | Smart Farm Automation**

*Open source tools for farmers who code and coders who farm*

[![Location](https://img.shields.io/badge/Farmville-Virginia-228B22?style=flat-square&logo=googlemaps&logoColor=white)](https://maps.google.com/?q=1853+Cumberland+Rd+Farmville+VA)
[![Savory Institute](https://img.shields.io/badge/Savory-Land_to_Market-8B4513?style=flat-square)](https://www.savory.global/)
[![NSIP](https://img.shields.io/badge/NSIP-Sheep_Genetics-4169E1?style=flat-square)](https://nsip.org/)
[![Instagram](https://img.shields.io/badge/@epicpastures-E4405F?style=flat-square&logo=instagram&logoColor=white)](https://instagram.com/epicpastures)

</div>

---

## About

**Epic Pastures** is a regenerative farm in Virginia's Piedmont region, raising **Katahdin hair sheep** and **pasture-raised poultry** using holistic management principles. We believe that **better technology enables better land stewardship**.

This GitHub organization is where we publish the software we've written to run our farm. If it's useful to us, maybe it's useful to you too.

<table>
<tr>
<td width="50%">

### The Farm

- **Katahdin Hair Sheep** - hardy, parasite-resistant, no shearing
- **Pasture-Raised Poultry** - chickens and ducks on rotating paddocks
- **Regenerative Practices** - EOV-verified soil and ecosystem health
- **Holistic Management** - Savory Institute Land to Market verified

</td>
<td width="50%">

### The Tech

- **Sheep Genetics & EBVs** - NSIP tools for breeding decisions
- **Smart Farm Automation** - Home Assistant + ESPHome sensors everywhere
- **Monitoring & Control** - water levels, barn climate, fence status
- **Simulation & Modeling** - greenhouse and grazing predictions

</td>
</tr>
</table>

---

## Focus Areas

### Sheep Genetics & NSIP

<img align="right" width="120" src="https://img.shields.io/badge/NSIP-Integrated-4169E1?style=for-the-badge&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI+PHBhdGggZmlsbD0id2hpdGUiIGQ9Ik0xMiAyQzYuNDggMiAyIDYuNDggMiAxMnM0LjQ4IDEwIDEwIDEwIDEwLTQuNDggMTAtMTBTMTcuNTIgMiAxMiAyek0xMiAyMGMtNC40MSAwLTgtMy41OS04LThzMy41OS04IDgtOCA4IDMuNTkgOCA4LTMuNTkgOC04IDh6Ii8+PC9zdmc+">

We use NSIP (National Sheep Improvement Program) to make breeding decisions based on actual performance data:

- EBV (Estimated Breeding Value) analysis and visualization
- Breeding decision support systems
- Flock performance tracking and genetics reporting
- Integration with NSIP databases and lamb plans

### Smart Farm Automation

<img align="right" width="120" src="https://img.shields.io/badge/Home_Assistant-Powered-41BDF5?style=for-the-badge&logo=homeassistant&logoColor=white">

**Home Assistant** and **ESPHome** based systems for farm monitoring and control:

- Water tank levels and automatic refill systems
- Barn environment monitoring (temperature, humidity, ammonia)
- Electric fence monitoring and alerts
- Automated lighting schedules for poultry
- Weather station integration for grazing decisions

### Greenhouse & Pasture Simulation

<img align="right" width="120" src="https://img.shields.io/badge/Simulation-Models-32CD32?style=for-the-badge&logo=matlab&logoColor=white">

When to move sheep? How warm should the greenhouse be? We model it:

- Greenhouse climate control simulations
- Pasture growth and recovery modeling
- Stocking density optimization
- Forage quality prediction

### Robotics & Field Automation

<img align="right" width="120" src="https://img.shields.io/badge/Robotics-Automation-FF6B35?style=for-the-badge&logo=ros&logoColor=white">

Farm work is physical. We're building things to help with that:

- Automated feeders and waterers
- Pasture monitoring rovers
- Computer vision for livestock health assessment
- GPS-guided equipment control

---

## Technology Stack

```
┌─────────────────────────────────────────────────────────────────────────────┐
│  FARM AUTOMATION                                                            │
├─────────────────────────────────────────────────────────────────────────────┤
│  Home Assistant  │  ESPHome  │  MQTT  │  InfluxDB  │  Grafana               │
├─────────────────────────────────────────────────────────────────────────────┤
│  DEVELOPMENT                                                                │
├─────────────────────────────────────────────────────────────────────────────┤
│  Python  │  TypeScript  │  Go  │  Rust  │  C++ (embedded)                   │
├─────────────────────────────────────────────────────────────────────────────┤
│  AI & DATA                                                                  │
├─────────────────────────────────────────────────────────────────────────────┤
│  Claude Code  │  GitHub Copilot  │  Pandas  │  scikit-learn  │  NSIP API    │
├─────────────────────────────────────────────────────────────────────────────┤
│  INFRASTRUCTURE                                                             │
├─────────────────────────────────────────────────────────────────────────────┤
│  GitHub Actions  │  Docker  │  Raspberry Pi  │  ESP32  │  LoRa              │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

## Reusable Workflows

Standardized CI/CD for agricultural software projects:

```yaml
# Example: Python project with farm-specific tooling
jobs:
  ci:
    uses: epicpast/.github/.github/workflows/reusable-ci-python.yml@main
    with:
      python-version: '3.12'
      coverage-threshold: 80
```

| Workflow | Description |
|----------|-------------|
| `reusable-ci-python.yml` | Python with uv, ruff, pyright, pytest |
| `reusable-ci-typescript.yml` | TypeScript with pnpm, ESLint, Vitest |
| `reusable-ci-go.yml` | Go with golangci-lint |
| `reusable-security.yml` | Secret and dependency scanning |
| `reusable-homebrew-formula.yml` | CLI tool distribution via Homebrew |

---

## How We Work

**Farm first.** If the sheep need moving, the code can wait. Software serves the land, not the other way around.

**Share what works.** We're not a software company. If something we built helps another farm, great. That's why it's here.

**Good enough ships.** A script that works today beats perfect code next lambing season. We fix things as we go.

**Keep it simple.** The person maintaining this code is probably future-me, tired, at 6am, wondering why the waterer alert didn't fire.

---

## Connect

<div align="center">

| | |
|---|---|
| **Farm Website** | [epicpastures.com](https://epicpastures.com) |
| **Instagram** | [@epicpastures](https://instagram.com/epicpastures) |
| **GitHub Issues** | Project-specific discussions |
| **Pull Requests** | The best way to contribute |

</div>

---

<div align="center">

*"Better eggs come from happy hens. Better farms come from less time fighting software."*

<sub>
Farmville, Virginia | <a href="https://epicpastures.com">epicpastures.com</a> | <a href="https://github.com/epicpast/.github">View Ecosystem</a>
</sub>

</div>
