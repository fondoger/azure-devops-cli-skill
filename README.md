# azure-devops-cli-skill

This skill is converted from the [Azure DevOps CLI Skill by Github](
https://github.com/github/awesome-copilot/blob/main/skills/azure-devops-cli/SKILL.md#best-practices).

## Structure

The original monolithic `SKILL.md` (2,466 lines) has been split into a compact main file with on-demand reference files to save tokens.

```
skills/azure-devops-cli/
├── SKILL.md                              (93 lines - basics + routing table)
└── references/
    ├── repos-and-prs.md                  (Repositories, PRs, Git refs, branch policies)
    ├── pipelines-and-builds.md           (Pipelines, runs, builds, releases, artifacts)
    ├── boards-and-iterations.md          (Work items, area paths, iterations)
    ├── variables-and-agents.md           (Pipeline variables, variable groups, agents)
    ├── org-and-security.md               (Projects, teams, users, permissions, wikis, admin)
    ├── advanced-usage.md                 (Output formats, JMESPath queries, global args)
    └── workflows-and-patterns.md         (Workflows, best practices, scripting patterns)
```

Only `SKILL.md` is loaded when the skill triggers. Reference files are read on demand based on the user's task.

## Token Estimation

Estimated using ~1 token per 4 characters (English text approximation).

| Scenario | Loaded content | ~Tokens |
|---|---|---|
| Before (monolithic) | Full SKILL.md (55KB, 2,466 lines) | ~14,000 |
| After (always loaded) | Compact SKILL.md (3.9KB, 93 lines) | ~1,000 |
| After (typical task) | SKILL.md + 1 reference file | ~2,500 - 4,500 |

Most tasks only need 1-2 reference files, saving **60-90%** tokens compared to loading everything upfront.