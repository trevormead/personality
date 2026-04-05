# personality — Claude Code Skill

A skill for quantitatively managing 120 variables that shape how Claude communicates. Adjust tone, verbosity, humor, formality, and more using natural language ("decrease sarcasm by 5") or command prompts. Variables are grouped into 32 parent categories with ~3-5 consitutent varibles each, can adjust an entire group at once or fine tune each variable individually. Changes are saved to `~/.claude/personality.json` and applied via `CLAUDE.md` automatically. You can save personality profiles as named presets. Personality settings persist across Claude Code chats. Personality settings can be enabled in claude.ai and mobile - `publish` to collapse the most impactful variable settings into a prompt to manually copy into your Account > Settings > Custom Instructions / Personal Preferences.

## Install

```bash
git clone https://github.com/trevormead/personality ~/.claude/skills/personality
```

Restart Claude Code. The `/personality` command is immediately available.

## Usage

```
  (no args) / show     Display all current values
  help                 Full command reference
  set <var> <n>        Set variable to absolute value (0–100)
  adjust <var> ±n      Adjust by delta  (e.g. humor +10)
  reset <var>          Reset one variable to its default
  reset all            Reset all variables to defaults
  define <var>         Full variable description, spectrum, constituents
  fine-tune <var>                    Show constituent values
  fine-tune <var> <constituent> <n>  Set/adjust one constituent directly
  preset list          List built-in and saved presets
  preset apply <name>  Apply a preset
  preset save <name>   Save current state as a preset
  preset delete <name> Delete a user preset
  history              Recent changes
  diff                 Changes since last publish
  publish              Generate Claude.ai Custom Instructions text
```

Natural language also works:
```
"make responses shorter"
"be more direct"
"dial up humor by 10"
```

## Variables

32 variables across two sets:

**Custom Instructions set** (top 15 — syncs to Claude.ai via `/personality publish`):
Wordiness · Agreeableness · Structural Formatting · Assertiveness · Intellectual Tone · Formal Tone · Advisory Style · Comedic Tone · Interpersonal Style · Answer Depth · Excitement · Initiative Level · Technical Level · Relational Tone · Opinion Expression

**Extended set** (Claude Code only):
Intellectual Depth · Curiosity & Creativity · Illustration · Precision & Rigor · Teaching Approach · Collaboration · Error Handling · Disagreement · Prose Style · Transparency · Self-Reflection · Cultural References · Inclusivity · Values Expression · Sarcasm & Edge · Refusal Style

## Built-in Presets

| Name | Description |
|---|---|
| `default` | Factory defaults |
| `concise_professional` | Low wordiness, high directness, formal |
| `collaborative` | High curiosity, warmth, proactiveness |
| `blunt_expert` | Low agreeableness, high directness, high opinion expression |
| `casual` | High humor, high warmth, very low formality |

## Syncing to Claude.ai

Run `/personality publish` to generate a condensed Custom Instructions block, then paste it into claude.ai → Settings → Custom Instructions. Keeps your Claude.ai and mobile session personality in sync with your Claude Code settings.
