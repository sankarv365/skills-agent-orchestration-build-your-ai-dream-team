# Agent team

The Project Pulse dashboard is built by a team of four specialized agents, orchestrated through the GitHub Copilot CLI in a Codespace.

## Agents

### Orchestrator
- **Model**: Claude Opus 4.7 (copilot)
- **Responsibility**: Coordinates Planner, Coder, and Designer agents. Breaks down complex requests into tasks, manages execution phases, and verifies integrated results.
- **Definition**: `.github/agents/orchestrator.agent.md`

### Planner
- **Model**: Claude Opus 4.7 (copilot)
- **Responsibility**: Creates implementation plans by researching the codebase, documentation, dependencies, and edge cases. Produces ordered implementation steps with file assignments and identifies parallel vs. sequential work.
- **Definition**: `.github/agents/planner.agent.md`

### Coder
- **Model**: GPT-5.5 (copilot)
- **Responsibility**: Implements code-oriented tasks with clear structure, explicit errors, and testable behavior. Writes code, fixes bugs, implements logic, and creates support configuration files.
- **Definition**: `.github/agents/coder.agent.md`

### Designer
- **Model**: Gemini 3.1 Pro (copilot)
- **Responsibility**: Handles UI/UX, accessibility, information architecture, interaction flow, and visual design. Creates a polished dashboard with visual affordances and responsive behavior.
- **Definition**: `.github/agents/designer.agent.md`

## Orchestration Model

The GitHub Copilot CLI in a Codespace orchestrates this team by:
1. Gathering a plan from the Planner
2. Parsing work into phases with clear file scopes
3. Running tasks in parallel when file scopes don't overlap
4. Running tasks sequentially when work overlaps or has dependencies
5. Verifying the integrated result hangs together
6. Reporting outcomes clearly to the learner

No agent stages, commits, or pushes changes—the learner controls all git operations through Copilot CLI prompts.
