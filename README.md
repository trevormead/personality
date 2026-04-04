# personality — Claude Code Skill

A skill for managing 32 variables that shape how Claude communicates. Adjust tone, verbosity, humor, formality, and more — changes are saved to `~/.claude/personality.json` and applied via `CLAUDE.md` automatically.

## Install

```bash
git clone https://github.com/trevormead/personality ~/.claude/skills/personality
```

Restart Claude Code. The `/personality` command is immediately available.

## Usage

```
/personality              Show all 32 variables as a bar chart
/personality help         Full command reference
/personality set <var> <n>         Set a variable (0–100)
/personality adjust <var> ±n       Adjust by delta
/personality fine-tune <var>       Show constituent breakdown
/personality fine-tune <var> <constituent> <n>
/personality preset list           List built-in and saved presets
/personality preset apply <name>   Apply a preset
/personality preset save <name>    Save current state as a preset
/personality publish               Generate Claude.ai Custom Instructions text
/personality history               Recent changes
/personality diff                  Changes since last publish
```

Natural language also works:
```
/personality make responses shorter
/personality be more direct
/personality dial up humor by 10
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

Run `/personality publish` to generate a condensed Custom Instructions block, then paste it into claude.ai → Settings → Custom Instructions. Keeps your Claude.ai and mobile sessions in sync with your Claude Code settings.
