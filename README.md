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
| ChatGPT Chat or Work | Use the skill through an installed plugin that bundles it, or supply [SKILL.md](.agents/skills/weekly-review/SKILL.md) as chat or project instructions. [ChatGPT skill availability](https://learn.chatgpt.com/docs/build-skills) |
| Claude Code | Copy the skill folder to `.claude/skills/weekly-review/` in your project and invoke `/weekly-review`. [Claude Code skills](https://code.claude.com/docs/en/skills) |
| GitHub Copilot in VS Code | Open the repository in a local chat session that discovers `.agents/skills/`. For sessions using `.github/skills/`, copy the same skill folder to `.github/skills/weekly-review/`. [VS Code skill locations](https://code.visualstudio.com/docs/agent-customization/agent-skills) |
| Other agents | Use the agent's skill installation path or give it the instructions from `SKILL.md`. |

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
