# Scoring Guide — 5×5 Likelihood × Impact Matrix

The arithmetic is not the hard part. Choosing the numbers is. Every score in your register needs a written reason, because the reason is what gets challenged in the gallery walk.

## The scales

### Likelihood — probability the vulnerability is exploited in a given year

| Score | Band | Written descriptor |
|---|---|---|
| 5 | Almost certain | Expected to occur several times a year, or has already happened |
| 4 | Likely | Expected once or more per year; a plausible single incident |
| 3 | Possible | Could occur, but no history and no strong driver; needs a second event |
| 2 | Unlikely | Would require unusual conditions or a sequence of failures |
| 1 | Rare | Requires an adversary with significant capability *and* a specific opening |

### Impact — consequence if it happens

Use the units that matter for this asset: NT$ lost, wafers scrapped, days of downtime, records exposed, safety exposure. Pick one unit and stay on it for that row.

| Score | Band | Written descriptor |
|---|---|---|
| 5 | Severe | Multi-week line stop, fab-wide IP loss, or a safety/environmental release |
| 4 | Major | Line stop of days, or loss of a process line's output for a cycle |
| 3 | Moderate | Single-day disruption, loss of a bounded asset, recoverable cost |
| 2 | Minor | Contained loss; a shift's work or a limited set of records |
| 1 | Negligible | Trivial cost; discovered and corrected within the hour |

## The matrix

Inherent Risk = Likelihood × Impact. Read the cell, then ask whether the colour band matches your intuition — if it does not, your likelihood or impact is wrong, not the matrix.

| L \ I | 1 | 2 | 3 | 4 | 5 |
|---|---|---|---|---|---|
| **5 — Almost certain** | 5 | 10 | 15 | 20 | **25** |
| **4 — Likely** | 4 | 8 | 12 | **16** | **20** |
| **3 — Possible** | 3 | 6 | 9 | 12 | **15** |
| **2 — Unlikely** | 2 | 4 | 6 | 8 | 10 |
| **1 — Rare** | 1 | 2 | 3 | 4 | 5 |

Risk bands:

| Score | Band | Expected response |
|---|---|---|
| 20–25 | **Critical** | Must be treated now. Treatment or a written, time-bound acceptance by an owner who can pay for it. |
| 12–16 | **High** | Treat this cycle. If deferred, say why in writing. |
| 6–9 | **Medium** | Treat on the normal capital cycle. |
| 1–5 | **Low** | Monitor. Re-score annually. |

## Residual risk — doing the arithmetic honestly

Residual Risk = Likelihood × Impact *after* the control is in place.

- A control that changes **only one axis** is the normal case, and it is correct. Say which axis and why.
  - A detective control (logging, monitoring, alarms) reduces **likelihood of going undetected**, not likelihood of occurrence — so on this register it often does *not* move the score at all. Be honest about that: a camera is a real control and it may not reduce the risk number.
  - A preventive control (a lock, an ACL, a credential change) reduces **likelihood**.
  - A physical/environmental control (a flood barrier, a backup generator) usually reduces **impact**.
  - Nothing reduces **impact** of a fab-line stop below 3. Do not pretend it does.
- **Residual identical to inherent** means either the control genuinely does nothing to this risk, or the group did not do the arithmetic. Either is acceptable *if* it is stated. Score zero credit, not a deduction, when there is no explanation.
- **State the control's limits.** "MFA on the OT jump hosts" reduces the chance of a stolen credential working. It does nothing about an insider with legitimate credentials, and it does nothing about the phishing email that got the credential in the first place.

## Choosing a control that actually reduces the risk

Ask three questions before you write the control into the row:

1. **Does it touch the named vulnerability?** This is the single most common error. A control aimed at the asset in general does not reduce the risk of the specific weakness you named. "Turn on MFA" is not a control for "the recipe share has no access logging."
2. **Can you state its cost, owner, and timeline?** "Better security" is not a control. "Install badge readers at both stairwell doors, NT$180,000, facilities team, 6 weeks" is. The register is a list of promises, and promises need names and dates.
3. **What is it blind to?** Every control has a failure mode. Write it in the residual-risk cell.

### Treatment vocabulary

| Treatment | Meaning | Moves the score? |
|---|---|---|
| **Mitigate** | Add a control that reduces likelihood or impact | Yes — this is the one that moves the number |
| **Avoid** | Stop doing the activity that creates the risk | Yes, often to 1 |
| **Transfer** | Shift the financial consequence to a third party (cyber insurance, outsourcing contract, SLA with penalties) | Not likelihood, not impact — it changes who pays. Say so explicitly. |
| **Accept** | Deliberately live with the risk, in writing | No. And that is a legitimate choice. |

## On "accept" — a legitimate choice, not a cop-out

Some risks genuinely should not be treated. A typhoon-season roof membrane replacement on a building with a 3-day repair lead time may cost more than the expected annual loss. Accepting that is an *analyst's* decision, not a failure to do the work.

But accept only when you write all three:

1. **The justification** — why the cost of treatment exceeds the expected loss, in numbers where you can.
2. **The acceptor** — a named person or role with the authority to accept it. Not "IT."
3. **The review date** — when someone will look again.

"Accept" with a blank justification cell is the cop-out, and it scores nothing. A well-justified acceptance scores full marks on control and residual risk, because you have shown you know when *not* to spend money.
