# apcyber-u2-risk-register-lab — Risk Register Lab

AP Cybersecurity Unit 2, Lesson 6. This repo holds the templates, scenario brief, scoring guide, and rubric for building a risk register for a real semiconductor fab.

## Your job

1. **Fork** this repo to your account.
2. Launch **Codespaces** from your fork (or clone locally — this lab is mostly writing, not running).
3. Read `reference/fab_scenario.md` — the brief for the company you are assessing.
4. Copy the template: `templates/risk_register_template.csv` (or the markdown version in `templates/` if you would rather draft offline).
5. **Build a register of 8 or more assets.** Groups of 3–4.
6. For every asset: name a specific vulnerability, score likelihood 1–5 and impact 1–5 with a **written reason for each**, compute inherent risk, propose one **specific and costed** control, and recompute residual risk. Use `reference/scoring_guide.md` for the matrix.
7. Save your finished register in your fork as `risk_register.csv` (or `.md`).
8. Be ready to **defend at least two of your scores** in the gallery walk — other groups will read your register and challenge you.

## The columns

`Asset, Vulnerability, Likelihood, Impact, Inherent Risk, Proposed Control, Residual Risk, Owner`

Asset — the thing with value, named specifically. "Etch tool controller software on Line 3," not "computers."

Vulnerability — the weakness that would be exploited. "Sends unencrypted data" is a vulnerability. "Hacker" is not.

Proposed Control — with a cost and an owner. "Better security" is not a control. "Install badge readers at both stairwell doors, NT$180,000, facilities team, 6 weeks" is.

Residual Risk — likelihood × impact *after* the control. A control that changes only one axis is the normal case; say which one and why. If residual equals inherent, you owe an explanation.

Owner — a named person or role, not "IT."

## The gate

- **8 or more rows.** Fewer than 8 is a 2-point deduction.
- **Assets genuinely distinct.** Eight variations of the same server scores 0 for the asset criterion.
- **Every score carries a written reason.** The reason is what gets challenged; the number alone is not a score.
- **Every control is costed, specific, and addressed to the named vulnerability** — not to the asset in general.
- **Residual risk is recomputed,** with the affected axis identified and the control's limits stated honestly.

See `rubric.md` for the full 20-point breakdown with descriptors, and `reference/scoring_guide.md` for the 5×5 matrix and how to pick a control that actually works.

## Gallery walk cross-review

Each group reads **two** other registers and leaves written feedback on sticky notes:

- (a) one score you think is wrong, and why
- (b) one control that does not actually reduce that risk
- (c) one asset the group should have considered and missed

Question (b) is where the real learning is. A control that does not touch the named vulnerability does not reduce the risk, and it is the most common error in the room.

## A note on "accept"

Choosing to **accept** a risk is a legitimate treatment decision, not a cop-out — but only when you justify it. Saying "accept" with no written reason is the cop-out. If you accept, say why the cost of treatment exceeds the loss exposure, and name who accepted it and when it will be revisited.
