# Private plugin setup

Use [the skill in this repository](../.agents/skills/weekly-review/SKILL.md) as the source. Copy the whole `.agents/skills/weekly-review/` folder when packaging, including `references/sources.example.md`. Keep your filled profile, evidence and reviews in a separate private location. Give the agent access to the filled profile in your review session.

## ChatGPT Chat or Work

If you have the Plugin Creator tool, open this repository in a session that can read it and ask:

> Package `.agents/skills/weekly-review` as a skills-only plugin named Weekly Review. Include the blank reference template and save the plugin privately to my account.

To prepare the ZIP yourself, copy the skill to `skills/weekly-review/` in a staging folder. Add this `plugin.json` next to `skills/`:

```json
{
  "$schema": "https://agent-plugins.org/schemas/1.0.0/plugin.schema.json",
  "name": "weekly-review",
  "version": "0.1.0",
  "description": "Gather weekly evidence, reflect, and draft a review.",
  "extensions": {
    "com.openai": {
      "interface": {
        "displayName": "Weekly Review",
        "shortDescription": "Gather evidence and reflect",
        "category": "Productivity"
      }
    }
  }
}
```

Zip `plugin.json` and `skills/` together at the archive root. Use Plugin Creator to save the archive privately, or use your workspace’s plugin ZIP upload flow if enabled. Open the saved plugin, install it if prompted, then start a new chat and select **Weekly Review** from the composer. Ask it to gather this week’s evidence. When updating, rebuild from the repository, bump the version and update the existing private plugin with the new archive. [Package format](https://developers.openai.com/plugins/build/plugins) · [Workspace upload permissions](https://learn.chatgpt.com/docs/enterprise/apps-and-connectors) · [Use plugins in ChatGPT](https://learn.chatgpt.com/docs/plugins)

## Claude Code

For a local plugin, copy the same skill folder to `skills/weekly-review/` in a staging directory. Put this manifest in `.claude-plugin/plugin.json` within that directory:

```json
{
  "name": "weekly-review",
  "version": "0.1.0",
  "description": "Gather weekly evidence, reflect, and draft a review."
}
```

Start Claude Code with `claude --plugin-dir /path/to/staging-directory`, then invoke `/weekly-review:weekly-review` and ask it to gather this week’s evidence. The flag loads the plugin for that session. For repeated use without a plugin wrapper, put the original skill folder in `.claude/skills/` and invoke `/weekly-review`. [Create a Claude Code plugin](https://code.claude.com/docs/en/plugins/create) · [Claude Code skill locations](https://code.claude.com/docs/en/skills)

## Claude on the web

Zip the `weekly-review/` skill folder itself, with `SKILL.md` and `references/` inside it. In Claude, open **Customize → Skills → Create skill → Upload a skill** and enable the upload. Uploaded custom skills are private to the account until shared. [Claude custom skill packaging](https://support.claude.com/en/articles/12512198-how-to-create-custom-skills) · [Claude skill upload](https://support.claude.com/en/articles/12512180-use-skills-in-claude)

Each agent uses its own connected accounts, file access and document tools. Start with a brief, check that it identifies any unavailable sources, then say **Start reflection** when you are ready. Approve external edits separately by draft and destination.
