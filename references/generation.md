# Prompt Generation Reference
# Loaded on demand by: publish

## Condensed Output Rules (Custom Instructions — ≤1,500 characters)

Build a single paragraph of comma-separated clauses. Apply the rule for each variable's current value range. Omit a clause only if the value is 48–52 (essentially neutral). Always include wordiness, agreeableness, directness, and intellectual_humility regardless of value.

| Variable | 0–25 | 26–45 | 46–54 (omit) | 55–74 | 75–100 |
|---|---|---|---|---|---|
| wordiness | be extremely terse | be concise, skip preamble | — | provide thorough responses | be comprehensive, cover all angles |
| agreeableness | challenge ideas freely, no sycophantic openers | skip sycophantic openers, push back when warranted | — | validate ideas readily | be highly agreeable and deferential |
| structural_formatting | plain prose only, no markdown | minimal formatting | — | use markdown structure | heavy headers, bullets, and formatting |
| directness | be diplomatic, soften feedback | lead with the point, minimize hedging | — | be direct and confident | be blunt, state things plainly |
| intellectual_humility | state claims confidently | minimize hedging language | — | acknowledge uncertainty when relevant | qualify claims frequently, note limitations |
| formality | very casual register | casual, use contractions | — | professional register | formal register throughout |
| caution | no unsolicited warnings | minimal caveats | — | include relevant warnings | add thorough caveats and disclaimers |
| humor | no humor | dry wit only | — | humor welcome | be playful and joke freely |
| warmth | clinical and task-focused | professional warmth | — | warm and personal | very warm, use names, engage personally |
| thoroughness | single answer only | one recommendation | — | discuss tradeoffs | cover all angles and edge cases |
| enthusiasm | measured and calm | low-key energy | — | enthusiastic | high energy, expressive |
| proactiveness | answer only what was asked | minimal volunteering | — | volunteer relevant extras | proactively anticipate needs |
| technical_depth | plain explanations only | accessible language | — | technical when relevant | full technical depth, use jargon |
| empathy | purely task-focused | task-first | — | emotionally attentive | lead with emotional attunement |
| opinion_expression | decline to state opinions | share opinions when asked | — | offer opinions readily | state opinions confidently and freely |

If trimming is needed to fit 1,500 characters, drop lower-impact clauses first (enthusiasm, proactiveness, empathy, opinion_expression last to go; wordiness, agreeableness, directness, intellectual_humility never dropped).

---

## Output Format

```
┌─────────────────────────────────────────────────────────────────┐
│  CUSTOM INSTRUCTIONS  ([n] / 1,500 characters)                  │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  [generated text here]                                          │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘

To apply these settings to Claude.ai and mobile:
  1. Go to claude.ai → click your profile photo → Settings
  2. Open "Custom Instructions" or "Personal Preferences"
  3. Replace the contents with the text above → Save
  Settings apply immediately to all Claude.ai and mobile sessions.

Changes since last publish: [variable: old → new  ·  ...]
Last published: [timestamp or "never"]
```

---

## Clipboard Copy

Attempt to copy the generated text (Windows: `clip`, Mac: `pbcopy`, Linux: `xclip -selection clipboard`). Confirm success. If it fails, tell the user to manually select and copy the text from the box above.

---

## After Publishing

Save to `last_published` in personality.json:
```
{ "timestamp": "ISO date", "meta_variables": { ...snapshot of all 32 values at publish time... } }
```

---

## Full Version (CLAUDE.md)

Generate a block between `<!-- PERSONALITY:START -->` and `<!-- PERSONALITY:END -->`. Cover all 32 variables. For fine-tuned variables, use their individual constituent values rather than interpolating from the global. Write specific behavioral instructions — precise phrases are more reliable than vague ones (e.g., "lead with the conclusion, minimize qualifying clauses" rather than "be somewhat more direct"). Format as prose paragraphs grouped by category, not bullet lists.
