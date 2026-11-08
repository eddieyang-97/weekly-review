# Weekly review

A Codex skill that gathers evidence from your existing connections, then helps you reflect on the week.

1. Open this folder as a Codex project so it can discover the bundled `.agents/skills/weekly-review` skill.
2. Copy the [blank source profile](.agents/skills/weekly-review/references/sources.example.md) to a private location outside this checkout. Fill in the sources and destinations you use. You can also put those details in private project instructions.
3. Start a chat with `$weekly-review Gather this week's evidence`. Point it to your private profile if the chat does not already have it. Connected sources supply the main evidence.
4. When the brief is ready, say **Start reflection**. To resume in another chat, provide the brief or its private link. Approve any proposed external edit by draft and destination.

For a chat without skill support, supply [SKILL.md](.agents/skills/weekly-review/SKILL.md) as workflow instructions. The session needs access to the connectors you plan to use.

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
