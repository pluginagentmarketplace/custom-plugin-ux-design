<div align="center">

<!-- Animated Typing Banner -->
<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=28&duration=3000&pause=1000&color=2E9EF7&center=true&vCenter=true&multiline=true&repeat=true&width=600&height=100&lines=UX+Design+Assistant;7+Agents+%7C+7+Skills;Claude+Code+Plugin" alt="UX Design Assistant" />

<br/>

<!-- Badge Row 1: Status Badges -->
[![Version](https://img.shields.io/badge/Version-2.0.0-blue?style=for-the-badge)](https://github.com/pluginagentmarketplace/custom-plugin-ux-design/releases)
[![License](https://img.shields.io/badge/License-Custom-yellow?style=for-the-badge)](LICENSE)
[![Status](https://img.shields.io/badge/Status-Production-brightgreen?style=for-the-badge)](#)
[![SASMP](https://img.shields.io/badge/SASMP-v1.3.0-blueviolet?style=for-the-badge)](#)

<!-- Badge Row 2: Content Badges -->
[![Agents](https://img.shields.io/badge/Agents-7-orange?style=flat-square&logo=robot)](#-agents)
[![Skills](https://img.shields.io/badge/Skills-7-purple?style=flat-square&logo=lightning)](#-skills)
[![Commands](https://img.shields.io/badge/Commands-4-green?style=flat-square&logo=terminal)](#-commands)

<br/>

<!-- Quick CTA Row -->
[**Install Now**](#-quick-start) | [**Explore Agents**](#-agents) | [**Documentation**](#-documentation)

---

### What is this?

> **UX Design Assistant** is a production-grade Claude Code plugin with **7 specialized agents** and **7 skills** for comprehensive UX design workflows.

</div>

---

## Table of Contents

- [Quick Start](#-quick-start)
- [Features](#-features)
- [Agents](#-agents)
- [Skills](#-skills)
- [Commands](#-commands)
- [Architecture](#-architecture)
- [Troubleshooting](#-troubleshooting)
- [Contributing](#-contributing)

---

## Quick Start

### Prerequisites

- Claude Code CLI v2.0.27+
- Active Claude subscription

### Installation

**Option 1: From Marketplace (Recommended)**

```bash
# Add the marketplace
/plugin add marketplace pluginagentmarketplace/custom-plugin-ux-design

# Install the plugin
/plugin install custom-plugin-ux-design@pluginagentmarketplace-ux-design

# Restart Claude Code
```

**Option 2: Local Installation**

```bash
git clone https://github.com/pluginagentmarketplace/custom-plugin-ux-design.git
cd custom-plugin-ux-design
/plugin load .
```

### Verify Installation

After restart, you should see these agents:

```
custom-plugin-ux-design:01-ux-research
custom-plugin-ux-design:02-ui-design
custom-plugin-ux-design:03-interaction-design
custom-plugin-ux-design:04-prototyping
custom-plugin-ux-design:05-accessibility
custom-plugin-ux-design:06-mobile-ux
custom-plugin-ux-design:07-ux-writing
```

---

## Features

| Feature | Description |
|---------|-------------|
| **7 Production-Grade Agents** | Specialized AI agents with clear responsibilities, I/O schemas, error handling |
| **7 Skills with Retry Logic** | Reusable capabilities with parameter validation, logging, observability |
| **4 Slash Commands** | Quick workflow commands with comprehensive documentation |
| **SASMP v1.3.0** | Full protocol compliance |
| **Troubleshooting Guides** | Debug checklists, failure modes, recovery procedures |

---

## Agents

### 7 Specialized UX Design Agents

| # | Agent | Description | Bonded Skill |
|---|-------|-------------|--------------|
| 1 | **01-ux-research** | User interviews, surveys, personas, journey mapping, usability testing | `user-research` |
| 2 | **02-ui-design** | Visual design, typography, color theory, component systems, design tokens | `ui-design` |
| 3 | **03-interaction-design** | User flows, micro-interactions, state management, behavioral patterns | `interaction-design` |
| 4 | **04-prototyping** | Wireframes, interactive prototypes, user testing, design iteration | `prototyping` |
| 5 | **05-accessibility** | WCAG compliance, screen reader testing, keyboard navigation, inclusive design | `accessibility` |
| 6 | **06-mobile-ux** | iOS/Android patterns, touch gestures, responsive design, platform guidelines | `mobile-ux` |
| 7 | **07-ux-writing** | Microcopy, voice & tone, error messages, CTAs, content design | `ux-writing` |

### Agent Workflow Dependencies

```
01-ux-research
      |
      v
02-ui-design  <-->  03-interaction-design
      |                    |
      v                    v
04-prototyping  <-->  05-accessibility
      |                    |
      v                    v
06-mobile-ux  <-->  07-ux-writing
```

---

## Skills

### Available Skills

| Skill | Description | Invoke |
|-------|-------------|--------|
| `user-research` | Conduct interviews, create personas, map journeys, run usability tests | `Skill("custom-plugin-ux-design:user-research")` |
| `ui-design` | Create visual designs, build component systems, generate design tokens | `Skill("custom-plugin-ux-design:ui-design")` |
| `interaction-design` | Design user flows, create micro-interactions, manage component states | `Skill("custom-plugin-ux-design:interaction-design")` |
| `prototyping` | Build wireframes, create interactive prototypes, run user tests | `Skill("custom-plugin-ux-design:prototyping")` |
| `accessibility` | Run WCAG audits, test keyboard navigation, check color contrast | `Skill("custom-plugin-ux-design:accessibility")` |
| `mobile-ux` | Design for iOS/Android, create responsive layouts, handle offline states | `Skill("custom-plugin-ux-design:mobile-ux")` |
| `ux-writing` | Write microcopy, define voice & tone, create error messages | `Skill("custom-plugin-ux-design:ux-writing")` |

---

## Commands

| Command | Description | Usage |
|---------|-------------|-------|
| `/create-plugin` | Create a new Claude Code plugin with scaffolding and architecture guidance | `/create-plugin my-plugin --scaffold` |
| `/design-ux` | Start UX design process with research, wireframes, prototypes, and testing | `/design-ux my-plugin --research --wireframe` |
| `/market-plugin` | Develop market strategy with research, positioning, and growth tactics | `/market-plugin my-plugin --research --strategy` |
| `/publish-plugin` | Publish and distribute plugin with validation, preparation, and submission | `/publish-plugin my-plugin --validate --submit` |

---

## Architecture

### Production-Grade Features

Each agent and skill includes:

- **Clear Role Boundaries**: What's in scope vs out of scope
- **Input/Output Schemas**: Type-safe JSON schemas for validation
- **Error Handling**: Failure modes with detection and recovery strategies
- **Fallback Strategies**: Graceful degradation when primary methods fail
- **Token Optimization**: Context management and token budgets
- **Retry Logic**: Exponential backoff for transient failures
- **Logging & Observability**: Events, metrics, and alerts
- **Quality Checklists**: Pre-flight checks before completion
- **Troubleshooting Guides**: Debug steps and common issue resolution

### Dependency Graph

```
Agents (7)          Skills (7)           Commands (4)
    |                   |                    |
    +---[PRIMARY_BOND]--+                    |
    |                                        |
    +--------[triggers]---------[hooks]------+
```

### Integrity Verification

```yaml
integrity_check:
  broken_links: 0          # All agent <-> skill references valid
  orphan_skills: 0         # All skills bonded to agents
  ghost_triggers: 0        # All hook triggers have handlers
  circular_dependencies: 0 # No circular agent dependencies
```

---

## Troubleshooting

### Common Issues

| Issue | Symptom | Solution |
|-------|---------|----------|
| Agent not loading | Not in agent list | Check plugin.json path references |
| Skill not invoking | "Skill not found" | Verify skill directory structure |
| Command fails | Error on execution | Check allowed-tools in command YAML |
| Hook not triggering | Action doesn't fire | Verify trigger event name in hooks.json |

### Debug Checklist

1. Verify plugin loaded: `/plugin list`
2. Check agent files exist in `agents/` directory
3. Verify skill YAML frontmatter is valid
4. Check hooks.json syntax is valid JSON
5. Restart Claude Code after changes

---

## Project Structure

```
custom-plugin-ux-design/
├── .claude-plugin/
│   ├── plugin.json          # Plugin manifest
│   └── marketplace.json     # Marketplace metadata
├── agents/                   # 7 production-grade agents
│   ├── 01-ux-research.md
│   ├── 02-ui-design.md
│   ├── 03-interaction-design.md
│   ├── 04-prototyping.md
│   ├── 05-accessibility.md
│   ├── 06-mobile-ux.md
│   └── 07-ux-writing.md
├── skills/                   # 7 skills with retry logic
│   ├── user-research/SKILL.md
│   ├── ui-design/SKILL.md
│   ├── interaction-design/SKILL.md
│   ├── prototyping/SKILL.md
│   ├── accessibility/SKILL.md
│   ├── mobile-ux/SKILL.md
│   └── ux-writing/SKILL.md
├── commands/                 # 4 slash commands
│   ├── create-plugin.md
│   ├── design-ux.md
│   ├── market-plugin.md
│   └── publish-plugin.md
├── hooks/
│   └── hooks.json
├── README.md
├── CHANGELOG.md
├── CONTRIBUTING.md
└── LICENSE
```

---

## Metadata

| Field | Value |
|-------|-------|
| **Version** | 2.0.0 |
| **Last Updated** | 2025-12-30 |
| **Status** | Production Ready |
| **SASMP** | v1.3.0 |
| **Agents** | 7 |
| **Skills** | 7 |
| **Commands** | 4 |

---

## Contributing

Contributions are welcome! Please read our [Contributing Guide](CONTRIBUTING.md).

1. Fork the repository
2. Create your feature branch
3. Follow the production-grade format for new agents/skills
4. Include input/output schemas, error handling, and troubleshooting
5. Submit a pull request

---

## Security

> **Important:** This repository contains third-party code and dependencies.
>
> - Always review code before using in production
> - Check dependencies for known vulnerabilities
> - Follow security best practices
> - Report security issues privately via [Issues](../../issues)

---

## License

Copyright 2025 **Dr. Umit Kacar** & **Muhsin Elcicek**

Custom License - See [LICENSE](LICENSE) for details.

---

## Contributors

| Contributor | Role |
|-------------|------|
| **Dr. Umit Kacar** | Senior AI Researcher & Engineer |
| **Muhsin Elcicek** | Senior Software Architect |

---

<div align="center">

**Made for the Claude Code Community**

[![GitHub](https://img.shields.io/badge/GitHub-pluginagentmarketplace-black?style=for-the-badge&logo=github)](https://github.com/pluginagentmarketplace)

</div>
