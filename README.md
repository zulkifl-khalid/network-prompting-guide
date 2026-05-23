# Advanced Prompting Guide for Network Engineers

A self-contained, interactive guide with **15 structured prompting patterns**  
covering the full network lifecycle — requirements through operations.

**No install. No dependencies. No Claude account needed.**  
Open `index.html` in any browser and it works.

---

## How to Use

### Open locally
```bash
git clone <this-repo-url>
# Then simply open the file:
open index.html          # macOS
start index.html         # Windows
xdg-open index.html      # Linux
```
Or drag `index.html` into any browser window.

> **Note:** The guide loads fonts from Google Fonts. If your corporate network  
> blocks external CDNs, it will fall back to system monospace fonts gracefully —  
> all functionality still works.

---

## Sharing with Your Team

1. Clone or download this repo
2. Open `index.html` in a browser — no server needed
3. Click any prompt card to view the full pattern
4. Use the **copy** button on the DO prompt and paste into any AI tool  
   (ChatGPT, Copilot, Gemini, Claude, Mistral, etc.)
5. Replace all `[BRACKETED PLACEHOLDERS]` with your actual values

---

## How to Add New Prompts

All prompts live in **one clearly marked section** inside `index.html`.  
You do not need to know React or JavaScript — just edit the data.

### Step-by-step

1. Open `index.html` in any text editor (VS Code, Notepad++, vim, etc.)

2. Find this comment (around line 120):
   ```
   /* ── ADD NEW PROMPTS BELOW THIS LINE ─────────── */
   ```

3. Copy the template below and paste it **above** the closing `];`

4. Fill in all fields and save the file

5. Refresh your browser — the new card appears automatically

### New Prompt Template

```javascript
{
  id: 16,                          // increment from the last prompt's id
  phase: "Troubleshooting",        // must match one of the phases listed below
  title: "Your Prompt Title",
  difficulty: "Mixed",             // "Senior" | "Mixed" | "Mid-level"
  mode: "Chat",                    // "Chat" | "Agentic"
  tagline: "One-line card description",
  why: "One paragraph explaining why this prompting pattern exists and what problem it solves.",
  dont: "The vague, bad version of this prompt.",
  do: `The structured, good version of this prompt.

Use backticks for multi-line prompts.
Use \\n for explicit newlines if needed.
Use [PLACEHOLDERS] for values the user must fill in.`,
  keyDiffs: [
    "First key difference between dont and do",
    "Second key difference",
    "Third key difference",
  ],
},
```

### Valid Phase Values
```
"Requirements"       → blue
"Architecture"       → purple
"Design"             → indigo
"Implementation"     → green
"Config Generation"  → amber
"Validation"         → red
"Troubleshooting"    → orange
"Security"           → pink
"Operations"         → cyan
```

To add a **new phase**, add it to both `LIFECYCLE_COLORS` and `PHASE_ORDER`  
at the top of the `<script>` section in `index.html`.

---

## Prompt Coverage

| # | Phase | Title | Level | Mode |
|---|-------|-------|-------|------|
| 01 | Requirements | Constraint-Graph Requirements Elicitation | Senior | Chat |
| 02 | Architecture | Dual-Architecture Self-Check | Senior | Chat |
| 03 | Architecture | Protocol Selection Rubric-Then-Design | Mixed | Chat |
| 04 | Design | IP Addressing & Summarisation Plan-and-Apply | Mixed | Chat |
| 05 | Design | Failure-Mode-First Network Design | Senior | Chat |
| 06 | Config Generation | Diff-Only Configuration Generation | Mixed | Chat |
| 07 | Config Generation | Adversarial Config Template Validator | Senior | Chat |
| 08 | Implementation | Repository-Aware Multi-Device Change Plan | Senior | Agentic |
| 09 | Validation | Pre/Post Change Validation Generator | Mixed | Chat |
| 10 | Validation | Dual-Path Reachability Self-Check | Senior | Agentic |
| 11 | Troubleshooting | OSI-Layer Failure-First Troubleshooting | Mixed | Chat |
| 12 | Troubleshooting | Protocol State-Machine Simulation | Senior | Chat |
| 13 | Security | Security Posture Review with Constraint Graph | Senior | Chat |
| 14 | Operations | Reversible Network Migration Prompting | Senior | Chat |
| 15 | Operations | Intent-to-Runbook Documentation Generator | Mixed | Chat |

---

## Contributing New Prompts

1. Add your prompt following the template above
2. Test it: open `index.html` in a browser and verify the card appears correctly
3. Open a Pull Request with:
   - The updated `index.html`
   - A short description in the PR body of what the prompt solves and which  
     network domain it targets
   - The AI tool you tested it with

Please keep prompts **vendor-agnostic** unless the prompt is explicitly  
documenting a vendor-specific technique (in which case, add the vendor name  
to the title and tag it clearly).

---

## Offline Use

If your corporate network blocks Google Fonts or CDN resources, the guide  
still works — fonts fall back to system defaults. All logic is self-contained.

For a **fully offline version** with no external requests at all, replace the  
three CDN `<script>` tags in `index.html` with locally downloaded copies:

```
https://unpkg.com/react@18/umd/react.production.min.js
https://unpkg.com/react-dom@18/umd/react-dom.production.min.js
https://unpkg.com/@babel/standalone/babel.min.js
```

Download these three files into a `lib/` folder and update the `src` paths  
in `index.html` accordingly.

---

*Vendor-agnostic · No Claude required · Works in any browser*
