# Rubric — Risk Register Lab (20 points)

Print this, hand it back with the register. Score each criterion against the descriptor that matches the work.

## Criterion 1 — Assets (4 points)

| Points | Descriptor |
|---|---|
| **4** | 8 or more assets. Genuinely distinct — a file server, its backup disk, its removable-media distribution, and the test stations are four different risks, not one asset written four ways. Each asset named specifically enough that someone could find it on a floor plan ("the EUV lithography tool bay," not "computers"). |
| **3** | 8 or more assets, but two or more are near-duplicates, or several are named generically ("the network," "employee data"). |
| **2** | 6–7 assets, or the register is recognisably eight variations of two or three systems. |
| **1** | Fewer than 6 assets, or the assets are categories rather than things ("hardware," "people," "the internet"). |
| **0** | No register, or fewer than 4 rows. |

**Automatic −2** applies to any group whose register has fewer than 8 rows. The deduction is on top of the criterion score, not instead of it.

## Criterion 2 — Scores (4 points)

| Points | Descriptor |
|---|---|
| **4** | Every row carries a written reason for likelihood *and* for impact. Impact reasons use real units for that asset (NT$, wafers scrapped, days of downtime, records). Inherent risk arithmetic is correct in every row. Scores within a band are defended by the reason, not by the number. |
| **3** | Arithmetic correct throughout, but reasons are present for only some rows, or impact reasons are stated in vague terms ("very bad," "big loss") rather than units. |
| **2** | Arithmetic is correct in some rows and wrong in others, or reasons are almost entirely absent. |
| **1** | Inherent risk is a number that does not correspond to likelihood × impact in most rows. |
| **0** | No scores, or a single number per row with no likelihood/impact split. |

## Criterion 3 — Controls (6 points)

This is the heaviest criterion. The control must be **specific, costed, and addressed to the named vulnerability.**

| Points | Descriptor |
|---|---|
| **6** | Every control is specific, carries a cost, an owning team, and a timeline, and addresses the *named vulnerability* rather than the asset in general. Each control's blind spot is acknowledged. |
| **5** | Controls are specific and costed with a timeline, but at least one addresses the asset rather than the named vulnerability, or omits the owner. |
| **4** | Controls are specific and address the right vulnerability, but most lack a cost or a timeline — e.g. "install MFA on the OT jump hosts" with no number attached. |
| **2–3** | Controls are generic. "Better security," "more training," "turn on MFA" with no scope, cost, owner, or timeline. |
| **1** | Controls are aspirational and would not survive a procurement conversation. |
| **0** | No controls proposed. |

Reference points from the lesson: *"Turn on MFA" scores 1. "MFA on fab OT jump hosts via a separate RADIUS server, NT$600,000, 10 weeks" scores 3 on its own contribution.*

**A justified "accept" scores full marks.** Acceptance is a legitimate treatment when it comes with the numbers, the named acceptor, and a review date. "Accept" with a blank justification scores nothing.

## Criterion 4 — Residual risk (4 points)

| Points | Descriptor |
|---|---|
| **4** | Residual risk recomputed correctly in every row, the axis changed is identified, and the control's limits are stated honestly — including an explicit note where a detective control does not move the score. |
| **3** | Residual risk recomputed correctly, axis identified, but limits are stated thinly or not at all. |
| **2** | Residual equals inherent with no explanation in some or all rows — the arithmetic was not done. *(2 points if residual equals inherent with no explanation.)* |
| **1** | Residual scores are arbitrary, or reduced on both axes at once by a control that could only touch one. |
| **0** | Residual column empty. |

## Criterion 5 — Defensibility (0 points, but gating)

Every group will be asked to **defend at least two of their scores** in the gallery walk. A group whose scores cannot be defended with the written reason they submitted has not met the lab's actual objective, even if the arithmetic is right. The gallery walk cross-review feeds the debrief, not the 20 points — but a group that cannot answer the challenge should expect to be asked again.

---

**Total: 20 points**

| | Criterion | Max |
|---|---|---|
| 1 | Assets | 4 |
| 2 | Scores | 4 |
| 3 | Controls | 6 |
| 4 | Residual risk | 4 |
| 5 | Defensibility | 0 |
| | **Total** | **20** |
| | Less automatic −2 deduction if fewer than 8 rows | −2 |
