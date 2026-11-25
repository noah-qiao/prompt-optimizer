# Draft Defect Reference Table (37 entries)

Read this table when diagnosing or repairing a draft; look up only the category that matches the draft's defect, and do not apply the whole table. Put hit items into the seven sections according to "bad example → fix"; defects marked 〔built-in〕 are already covered by the run flow, so only confirm the deliverable has not regressed and no extra rewriting is needed.

Categories follow step 3 of the flow: classify into purpose/fact/assumption/convention/constraint first, then use this table to calibrate the fix.

## Task category

| # | Defect | Bad example → fix |
|---|---|---|
| 1 | Vague verb | "Help me sort out the code" → "Change `getUserData()` to async/await so a null return does not throw" |
| 2 | Multiple goals in one draft | "Fix login and write a sales email" → split into several drafts when the goals differ; merge only when acceptance criteria are shared |
| 3 | No completion marker〔built-in〕 | "Make it a bit better" → "Pass the existing unit tests and do not throw on null input" |
| 4 | Permissions fully open | "Get it done no matter the cost" → write two lists, allowed actions and forbidden actions |
| 5 | Emotional description〔built-in〕 | "Everything blew up, fix it all" → "Throws TypeError on line 43 when `user` is null" |
| 6 | Building the whole site in one breath | "Build my entire App" → split into three: scaffolding / core features / polish |
| 7 | Implicit reference | "Add that thing again" → restate the task fully every time; do not refer to "what we said last time" |

## Context category

| # | Defect | Bad example → fix |
|---|---|---|
| 8 | Assuming earlier turns are remembered〔built-in〕 | "Pick up from last time" → write every settled decision into [Fact Baseline] |
| 9 | No scenario | "Write a cover letter" → "B2B finance PM role, 2 years of SWE moving into product, shipped 3 features" |
| 10 | Tech stack drift | The new draft conflicts with the earlier choice → put the tech stack into [Fact Baseline] and then revise |
| 11 | Inviting fabrication〔built-in〕 | "What do experts think of X" → "Write only what you are sure of; mark what you are unsure of as [Uncertain] and cite no sources" |
| 12 | Unclear audience | "Write it for users" → "Non-technical B2B buyer, decision-making level" |
| 13 | Not mentioning attempted approaches | (empty) → "X was tried and failed because of Y; do not suggest X again" |

## Format category

| # | Defect | Bad example → fix |
|---|---|---|
| 14 | No deliverable format | "Explain this concept" → "3 bullet points, each ≤20 characters, opening with a 1-sentence summary" |
| 15 | Length left to guesswork〔built-in〕 | "Write a summary" → "The summary is exactly 3 sentences" |
| 16 | Missing professional perspective | A professional task with no role → add [Identity] only when the role would change the result |
| 17 | Adjectives as standards〔built-in · vague-words〕 | "Make it more professional" → "Monochrome palette, body text 16px, line height 24px, no decorative elements" |
| 18 | Image prompt without negative terms | "A portrait of a woman" → add "no watermark, no blur, no extra fingers, no text" |
| 19 | Midjourney prompt written as a long sentence | A prose sentence → "subject, style, mood, lighting, composition, --ar 16:9 --v 6" |

## Scope category

| # | Defect | Bad example → fix |
|---|---|---|
| 20 | No boundary | "Fix my app" → "Change only the login validation in `src/auth.js`; touch nothing else" |
| 21 | No technical constraints | "Write a React component" → "React 18, TS strict, no external libraries, Tailwind only" |
| 22 | Agent with no stop condition | "Finish the feature" → write a stop condition + milestones + verification evidence |
| 23 | IDE task without file paths | "Change the login function" → "Change only `handleLogin()` in `src/pages/Login.tsx`" |
| 24 | Template mismatch | GPT prose crammed into Cursor → switch to the seven-section + file-scope style |
| 25 | Pasting the whole repository | Pasting the whole repo every round → give only the relevant functions and files |

## Reasoning category

| # | Defect | Bad example → fix |
|---|---|---|
| 26 | No audit requirement | "Which option is better" → require the conclusion + assumptions + criteria + evidence + verification + residual uncertainty |
| 27 | Asking to hide the chain of thought〔built-in〕 | "Show your thinking process" → delete it; instead ask for the conclusion, the basis, and the verification results |
| 28 | Expecting cross-session memory〔built-in〕 | "You know my project" → resend [Fact Baseline] in every new session |
| 29 | Conflict with earlier decisions | The new draft ignores the settled architecture → write the conflict into [Fact Baseline] and then revise |
| 30 | Factual task without anchors | "Summarize what experts think of X" → "Write only what you are sure of; mark what you are unsure of as [Uncertain]" |

## Agent category

| # | Defect | Bad example → fix |
|---|---|---|
| 31 | No starting point | "Build me a REST API" → "Empty Node project, Express installed, `src/app.js` exists" |
| 32 | No end point | "Add authentication" → "`src/middleware/auth.js` verifies JWT; `src/routes/auth.js` adds `POST /login` and `/register`" |
| 33 | Silent agent | No progress output → "report milestones, blockers, and the final verification result" |
| 34 | File system fully open〔built-in〕 | No file restriction → "Change only files under `src/`; do not touch `package.json`, `.env`, or the configuration" |
| 35 | No human gate | Fully automatic decisions → "ask me before deleting files, adding dependencies, or changing database tables" |
| 36 | Vague agent first round | "Fix the auth bug" with no scope, files, or acceptance → in the first round give the result, the context, the file scope, the constraints, the action boundaries, and the acceptance criteria |
| 37 | Context rot in long sessions | Repeated corrections while the old assumptions remain → start a new session for unrelated tasks; otherwise compress the context according to the current decisions; outsource only independent large investigations |
