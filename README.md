# Weekly review

A weekly review workflow in the [Agent Skills format](https://agentskills.io/specification). It gathers evidence, then helps you reflect on the week. Each session uses the sources and tools it can access.

1. Load the `weekly-review` skill using the setup for your agent below.
2. Copy the [blank profile](.agents/skills/weekly-review/references/sources.example.md) to a private location outside this checkout. Fill in your sources and output pointers. You can also put those details in private project instructions.
3. Ask the agent to **Gather this week's evidence**. Point it to your private profile if needed. The agent starts with the sources it can access and flags gaps in the brief.
4. When the brief is ready, say **Start reflection**. To resume in another chat, provide the brief or its private link. Approve any proposed external edit by draft and destination.

## Agent setup

The canonical skill folder is `.agents/skills/weekly-review`. Keep `SKILL.md` and its `references/` folder together when installing or copying it.

| Environment | Setup |
| --- | --- |
| Codex | Open the repository as a project and invoke `$weekly-review`. [Codex skill discovery](https://learn.chatgpt.com/docs/build-skills) |
| ChatGPT Chat or Work | Prefer an installed plugin containing the skill. Alternatively, supply [SKILL.md](.agents/skills/weekly-review/SKILL.md) as chat or project instructions; the review workflow still works, but the optional `references/sources.example.md` profile template must be supplied separately if needed. [ChatGPT skill availability](https://learn.chatgpt.com/docs/build-skills) |
| Claude Code | Symlink `.claude/skills/weekly-review/` to the canonical skill folder to avoid stale copies (command below), then invoke `/weekly-review`. Copy the folder instead if symlinks are unavailable, and refresh that copy after updates. [Claude Code skills](https://code.claude.com/docs/en/skills) |
| GitHub Copilot in VS Code | Use `.github/skills/weekly-review/` as the recommended project skill location (copy or symlink the canonical folder). VS Code local agent sessions that discover `.agents/skills/` can use this repository's folder directly. [VS Code skill locations](https://code.visualstudio.com/docs/agent-customization/agent-skills) |
| Claude.ai / Claude app | Upload the skill ZIP through **Customize → Skills**. See [Private plugin setup](docs/private-plugins.md#claude-on-the-web). |
| Other agents | Install the complete skill folder using the agent's supported location. Alternatively, supply `SKILL.md` alone as instructions: the core workflow works, but the optional reference profile template will not be available unless supplied separately. |

For Claude Code in this repository, create a symlink from the project root on macOS/Linux:

```bash
mkdir -p .claude/skills
ln -s ../../.agents/skills/weekly-review .claude/skills/weekly-review
```

This points to the canonical skill, so later edits take effect without recopying it. On systems where symlinks are inconvenient, copy the folder and recopy it after changes. Installed ChatGPT/Claude plugins are separate packaged releases and **do not update automatically** when the GitHub source changes.

Connector access, local files, persistence and document editing depend on the session. You can finish the review in chat and copy out the draft if your session lacks storage or editing tools.

See [Private plugin setup](docs/private-plugins.md) to package this skill for your own ChatGPT or Claude account.

## Personal output pointers

Use the **Outputs** section of the private profile to set a destination for each kind of output. For a document, include its link and the target tab or section if applicable. For a local file, give its path or the folder for new files. You can choose chat for the evidence brief and weekly overview, and leave the longer reflection blank if you prefer. The skill shows the draft and destination before any external write and waits for your approval.

## Optional local evidence

Keep screenshots, notes, exports and excerpts outside the Git checkout, alongside your private source profile. One simple layout uses the review week's start date:

```text
private-weekly-review/
  sources.md
  local-evidence/
    YYYY-MM-DD/
      screenshot.jpg
      notes.md
```

Record the evidence folder in your private profile, or give the skill a folder path or attachments for a particular review. You can use any existing folder naming scheme if you point to the correct week. If you add files after the brief is ready, ask the skill to incorporate the new files into that brief. The skill gathers from connected sources even when the folder is empty or missing.
