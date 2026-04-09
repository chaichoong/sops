# Operations Director — SOPs

Standard Operating Procedures for all Claude skills used by Kevin Brittain / Operations Director.

Live site: https://chaichoong.github.io/sops

---

## Repo structure

```
index.html              ← Team SOP dashboard (auto-lists all SOPs)
sop-template.html       ← Template Claude fills in when a new skill is created
GENERATE-SOP-PROMPT.txt ← Prompt to paste into Claude to generate a new SOP
README.md               ← This file

sops/
  transaction-reconciler.html
  cash-flow-forecast.html
  contractor-job-creator.html
  ... (one file per skill)
```

---

## How to add a new SOP

1. Open Claude (claude.ai or Cowork)
2. Open `GENERATE-SOP-PROMPT.txt` and copy the contents
3. Replace `[PASTE SKILL NAME HERE]` and the skill file path with the new skill
4. Paste into Claude and run
5. Claude outputs a complete HTML file
6. Save the file into the `sops/` folder in this repo (e.g. `sops/my-new-skill.html`)
7. Open `index.html` and add an entry to the `SOPS` array:

```js
{
  id: "my-new-skill",
  title: "My New Skill",
  desc: "One sentence description of what this skill does.",
  category: "ops",        // finance | property | tenant | comms | ops | content | system
  icon: "&#x1F527;",      // pick a relevant emoji HTML entity
  version: "1.0",
  updated: "2026-04-09",  // today's date
  file: "sops/my-new-skill.html"
}
```

8. Commit and push. GitHub Pages deploys within ~60 seconds.

---

## Categories

| Category | Used for |
|----------|----------|
| finance  | Transactions, forecasts, loan agreements, costs |
| property | Contractor jobs, schedule of works |
| tenant   | Onboarding, complaints, documents, UC47, tenancy end |
| comms    | Gmail, post, meeting manager |
| ops      | Task creation, weekly check-ins, daily schedule |
| content  | Runpreneur content machine, copywriting |
| system   | Airtable scripts, PDF processing, utility tools |

---

## GitHub Pages setup (one-time)

1. Push this repo to `chaichoong/sops` (or any repo under the chaichoong account)
2. Go to Settings → Pages
3. Set Source: Deploy from branch → `main` → `/ (root)`
4. Site will be live at `https://chaichoong.github.io/sops`

---

Owner: Kevin Brittain  
Generated SOPs are auto-produced by Claude using the template in this repo.
