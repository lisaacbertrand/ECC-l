# Projects

Self-contained Claude Code projects. Each folder has its own `CLAUDE.md` plus agents and skills under `.claude/`. Copy a folder out, or open it as its own working directory, to use it on its own.

| Project | Agents | Skills | Purpose |
|---------|--------|--------|---------|
| [finance-coach](finance-coach/) | improvement-coach | cfa-coach, interview-coach, skill-coach | Close the gap between you and the finance job you want |
| [life-upgrade](life-upgrade/) | accountant, upgrade-strategist, travel-planner | budgeting, taxes, investment-planning | Budget, taxes, and free cash flow → life upgrades, investing, travel |

## Agent vs. Skill

- **Agent**: one-shot work in its own context that reads lots of files or does web research and returns a single artifact (a roadmap, a snapshot, an itinerary). Subagents can't talk back and forth with the user.
- **Skill**: reusable know-how or an interactive loop (quizzing, mock interviews, budget sessions). Skills run in the main conversation, and agents can preload them through the `skills:` frontmatter field.
