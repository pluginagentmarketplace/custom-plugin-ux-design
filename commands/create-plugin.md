# /create-plugin

Start building a new Claude Code plugin from scratch with expert guidance from the Plugin Architecture Specialist.

## Usage

```
/create-plugin [plugin-name] [--type] [--template] [--scaffold]
```

## Examples

### Create a new plugin
```
/create-plugin my-plugin
```

### Use a specific template
```
/create-plugin my-plugin --template api-integration
/create-plugin my-plugin --template learning-platform
```

### Generate scaffolding
```
/create-plugin my-plugin --scaffold
```

## Plugin Types

### Agent-Based Plugins
Specialized agents that guide users through specific domains.
```
/create-plugin my-plugin --type agent
```

### Command-Based Plugins
Slash commands providing specific functionality.
```
/create-plugin my-plugin --type command
```

### Skill-Based Plugins
Learning skills and knowledge containers.
```
/create-plugin my-plugin --type skill
```

### Integrated Plugins
Complete plugins with agents, commands, and skills.
```
/create-plugin my-plugin --type integrated
```

## Templates

### Learning Platform Template
Ideal for educational and learning plugins.
```
/create-plugin my-plugin --template learning-platform
```
Includes:
- Agent system for expertise
- Skill containers for content
- Progress tracking
- Assessment tools

### API Integration Template
For plugins integrating external APIs.
```
/create-plugin my-plugin --template api-integration
```
Includes:
- API client setup
- Authentication handling
- Error management
- Request/response handling

### Tool/Utility Template
For productivity and utility plugins.
```
/create-plugin my-plugin --template utility
```
Includes:
- Command structure
- Data processing
- Output formatting
- Integration points

### Community Plugin Template
For community-driven plugins.
```
/create-plugin my-plugin --template community
```
Includes:
- User contribution system
- Feedback mechanisms
- Collaboration features
- Community management

## Generation Features

### Automatic Scaffolding
```
/create-plugin my-plugin --scaffold
```

Creates:
- `.claude-plugin/` directory with manifest
- `agents/` directory structure
- `commands/` directory structure
- `skills/` directory structure
- `hooks/` directory structure
- README template
- LICENSE file

### Plugin Configuration
```
/create-plugin my-plugin --scaffold --configure
```

Interactive setup:
- Plugin name and description
- Author information
- License selection
- Version initialization
- Manifest configuration

### Example Files
```
/create-plugin my-plugin --scaffold --examples
```

Includes:
- Sample agent file
- Sample command file
- Sample skill file
- Sample hook configuration

## Plugin Structure Created

```
my-plugin/
├── .claude-plugin/
│   └── plugin.json
├── agents/
│   └── example-agent.md
├── commands/
│   └── example-command.md
├── skills/
│   └── example-skill/
│       └── SKILL.md
├── hooks/
│   └── hooks.json
├── README.md
└── LICENSE
```

## Next Steps

1. **Customize Manifest**
   ```
   Edit .claude-plugin/plugin.json
   ```

2. **Create Agents**
   ```
   Add agent files to agents/ directory
   ```

3. **Build Commands**
   ```
   Create command markdown in commands/ directory
   ```

4. **Define Skills**
   ```
   Create skill containers in skills/ directory
   ```

5. **Configure Hooks**
   ```
   Update hooks.json for automation
   ```

6. **Test Locally**
   ```
   Load plugin in Claude Code: /plugin load ./my-plugin
   ```

## Architecture Guidance

The Plugin Architecture Specialist will guide you through:
- Plugin structure decisions
- Component organization
- Integration patterns
- Performance considerations
- Security best practices
- Scalability planning

## Tips

1. Start with a clear plugin concept
2. Choose the right template
3. Use scaffolding for consistency
4. Follow naming conventions
5. Document as you go
6. Test frequently
7. Gather user feedback early

## Integration with Agents

Use specialized agents for different aspects:
- **Plugin Architect** - Structure and design
- **UX Designer** - Interface design
- **Market Researcher** - Market positioning
- **DevX Engineer** - Developer experience
- **QA Tester** - Testing strategy
- **Growth Strategist** - Growth planning
- **Community Manager** - Documentation

## Build Checklist

- [ ] Plugin name and description finalized
- [ ] Template selected
- [ ] Scaffolding generated
- [ ] Manifest configured
- [ ] Agents created
- [ ] Commands built
- [ ] Skills defined
- [ ] Hooks configured
- [ ] Local testing passed
- [ ] Documentation complete
