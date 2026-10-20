# Senior Engineer Agents

A portable `AGENTS.md` and three optional skills for careful, practical software engineering with AI coding agents.

The central workflow is: define success, establish a reproducible case, diagnose, implement, verify, review, repair, and repeat affected checks until the evidence supports completion.

## Use AGENTS.md in a project

1. Read [AGENTS.md](AGENTS.md) and adapt it to your team's constraints.
2. Copy it to the root of a project. If that project already has instructions, merge the useful rules and resolve conflicts before replacing anything.
3. Add the actual project commands, supported versions, architecture constraints, and branch/release policy. Keep the general workflow intact where it fits.
4. Commit the resulting instructions so other contributors can use them. Check whether your agent discovers `AGENTS.md` automatically; configure it when required.
5. Start a session and ask the agent to summarize the applicable instructions and relevant verification commands. Use a small representative task to check the resulting behavior.

[AGENTS.md is an open convention](https://agents.md/), and support differs by tool. Codex reads project instructions from the repository root toward the working directory and supports scoped overrides. Its combined project-instruction size limit defaults to 32 KiB, so keep project guidance concise. [Official Codex instructions guide](https://learn.chatgpt.com/docs/agent-configuration/agents-md)

### What to customize

Add only the information that a contributor needs for this project:

- Setup, lint, type-check, build, and test commands; required environment and fixtures.
- Supported runtimes, package managers, dependency/lockfile conventions, and important module boundaries.
- Domain rules, public compatibility promises, data ownership, migrations, and deployment constraints.
- Commit, branch, review, publishing, and approval policies.

Use nested instructions for area-specific rules if your agent supports them. Keep commands accurate and make examples clearly distinguishable from requirements.

## Optional skills

These are original, instruction-only workflows in the [Agent Skills format](https://agentskills.io/specification). They have no package dependencies or bundled executable scripts.

| Skill | Use it for |
| --- | --- |
| [engineering-research](skills/engineering-research/SKILL.md) | Investigating technical questions with cited primary sources |
| [systematic-debugging](skills/systematic-debugging/SKILL.md) | Reproducing failures and testing competing explanations |
| [feature-review](skills/feature-review/SKILL.md) | Reviewing a feature diff against requirements and project standards |

Install only the workflows you need. For Codex, copy a skill directory into `.agents/skills/` in the target repository, or into `~/.agents/skills/` for personal use. Each directory must retain its `SKILL.md` file. Review existing directories before copying so you do not overwrite another skill. Codex discovers the metadata first and reads the full instructions when selected. Other hosts may use different locations or installation steps. [Official skill setup guide](https://learn.chatgpt.com/docs/build-skills)

After installing, invoke a skill explicitly when useful, for example:

```text
Use engineering-research to compare the supported migration approaches.
Use systematic-debugging to investigate this intermittent failure.
Use feature-review to review the changes since <base-commit>.
```

If your tool supports Codex-style skill invocation, use `$engineering-research`, `$systematic-debugging`, or `$feature-review`. Restart the session if your tool does not discover newly installed skills.

## Scope and limits

This repository shares engineering instructions and workflows. It does not install models, third-party plugins, connectors, credentials, permissions, or your project's build tools. The three included skills are original material; they do not redistribute third-party skill packages.

Instructions guide behavior; results still depend on the model, its context, tools, permissions, and the project. Verify generated changes before relying on them. Sandboxing, access controls, CI, branch protection, and human ownership remain separate controls. [OWASP guidance](https://cheatsheetseries.owasp.org/cheatsheets/LLM_Prompt_Injection_Prevention_Cheat_Sheet.html)

The workflow scales to the task: a wording edit needs a focused documentation check; a data migration or security-sensitive change needs stronger evidence. It encourages reuse when there is a demonstrated need and keeps speculative architecture out of routine fixes.

## Research and maintenance

Read the [cited research and design rationale](docs/research.md) for the decisions behind this template. Keep additions actionable and broadly applicable. Add a rule when observed behavior reveals a real gap, and prune rules that become redundant or stale.

## License

Original material in this repository is available under the [MIT License](LICENSE). Linked documentation and third-party packages retain their own licenses. You may copy, adapt, and share this template under the license terms.
