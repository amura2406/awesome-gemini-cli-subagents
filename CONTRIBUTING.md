# Contributing to Awesome Gemini CLI Subagents

Thank you for your interest in contributing to this collection!

## 🤝 How to Contribute

### Adding a New Subagent

1. **Choose the right category** - Place your subagent in the most appropriate category folder
2. **Test your subagent** - Ensure it works with Gemini CLI
3. **Update required files** - When adding a new agent, you must update:
   - **Main README.md**: Add your agent to the appropriate category section in alphabetical order
   - **Category README.md**: Add detailed description, update Quick Selection Guide table, and if applicable, Common Technology Stacks
   - **Your agent .md file**: Create the actual agent definition following the template
4. **Submit a PR** - Include a clear description of the subagent's purpose

### Subagent Requirements

Each subagent should include:
- Clear role definition
- List of expertise areas
- Required MCP tools (if any)
- Communication protocol examples
- Core capabilities
- Example usage scenarios
- Best practices

### Agent Template Format

All agents must follow this YAML frontmatter structure:

```yaml
---
name: your-agent-name
description: When and why this agent should be invoked
kind: local
tools:
  - read_file
  - write_file
  - run_shell_command
  - search_file_content
model: gemini-3-pro-preview  # or gemini-3-flash-preview for simple tasks
temperature: 0.1  # See temperature guidelines below
max_turns: 20     # Adjust based on complexity
---
```

### Temperature Guidelines

Choose appropriate temperature based on agent task type:

| Task Type | Temperature | Max Turns | Examples |
|-----------|-------------|-----------|----------|
| Code Generation | 0.1 | 20 | backend-developer, python-pro |
| Debugging | 0.05 | 25 | debugger, error-detective |
| Code Review | 0.15 | 25 | code-reviewer, security-auditor |
| Infrastructure | 0.15 | 20 | devops-engineer, terraform-engineer |
| Architecture | 0.35 | 25 | api-designer, microservices-architect |
| Documentation | 0.35 | 15 | documentation-engineer |
| Research | 0.45 | 20 | market-researcher, trend-analyst |
| Strategy/Product | 0.5 | 20 | product-manager, business-analyst |
| Creative | 0.55 | 20 | ui-designer, content-marketer |

See [TEMPERATURE_OPTIMIZATION_SUMMARY.md](TEMPERATURE_OPTIMIZATION_SUMMARY.md) for detailed rationale.

### Required Updates When Adding a New Agent

When you add a new agent, you MUST update these files:

1. **Main README.md**
   - Add your agent link in the appropriate category section
   - Maintain alphabetical order
   - Format: `- [**agent-name**](path/to/agent.md) - Brief description`

2. **Category README.md** (e.g., `categories/02-language-specialists/README.md`)
   - Add detailed agent description in the "Available Subagents" section
   - Update the "Quick Selection Guide" table
   - If applicable, add to "Common Technology Stacks" section
   
3. **Your Agent File** (e.g., `categories/02-language-specialists/your-agent.md`)
   - Follow the standard template structure
   - Include all required sections

### Adding a Tool

Tools are Gemini CLI skills that enhance the catalog experience (discovery, browsing, management).

1. **Create a folder** in `tools/` with your tool name
2. **Include required files**:
   - `README.md` - Installation and usage documentation
   - Command files (`.md`) - One per command, with YAML frontmatter
   - Helper scripts (`.sh`, `.py`) - Shared utilities if needed
3. **Follow skill best practices**:
   - Use descriptive `name` and `description` in frontmatter
   - Include trigger phrases in descriptions
   - Handle errors gracefully with user-friendly messages
4. **Update the main README.md** - Add your tool to the 🧰 Tools section
5. **Test locally** before submitting

### Code of Conduct

- Be respectful and inclusive
- Provide constructive feedback
- Test contributions before submitting
- Follow the existing format and structure

### Pull Request Process

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/new-subagent`)
3. Add your subagent following the template
4. Update ALL required locations:
   - Main README.md (add to category section in alphabetical order)
   - Category-specific README.md (add description, update tables)
5. Verify all links work correctly
6. Submit a pull request with a clear description

### Quality Guidelines

- Subagents should be well-structured and tested
- Include clear documentation
- Provide practical examples
- Ensure compatibility with Gemini CLI

## 📝 License

By contributing, you agree that your contributions will be licensed under the MIT License.

All subagents in this repository are provided "as is" without warranty. The maintainers do not audit or guarantee the security or correctness of any contribution and accept no liability for any issues arising from their use.