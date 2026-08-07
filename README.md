# Review Rejection Diagnostician

**v0.1** · Status: built. Not yet exercised by a blind run, and no retrospective field
validation.

A folder you drop into a Claude Project. Claude becomes a diagnostician that works out why a
paper was rejected after review.

It is built for one moment: the reports are open on the desk, the decision is in, and the
explanation forming in the room is that one reviewer did not read it properly. Sometimes that is
true. It is also the reading that requires the least of the author, which is why it arrives first
and survives longest — and it is not decidable from the thing people use to decide it, which is
the tone of the report.

---

## The comparison set you already have is unusually good

Most diagnosis needs a comparison set assembled and defended. Here one arrives already built, and
it is better than anything assembly could produce.

**Several qualified readers encountered one fixed artifact at the same moment, and did not speak
to each other.**

The paper does not vary. The readers do. So every difference between the reports is evidence
about how the paper reads, and every agreement is evidence about the paper. That is close to a
natural experiment, and it is the reason this works at all.

**The agreement pattern is the instrument** — not the tone, not the recommendation, not how many
weaknesses were listed:

| Pattern | Means | Where it breaks |
|---|---|---|
| **Convergent** — independent readers flag the same thing | A real defect in the work | Claim support |
| **Divergent** — each flags something different | The paper is unclear rather than wrong | Reconstruction |
| **Polarized** — they agree what it is, split on whether it belongs | Scope mismatch with the venue | Contribution judgment |

Three very different findings, three different responses, and the rejection letter renders all
three as *reject*.

---

## What it does

Reads the reports against each other, finds the earliest stage where the submission broke, and
names the one cause the evidence supports.

Then it tells you what would prove it wrong.

## What it does not do

- **Evaluate the science.** It is not a fourth reviewer. It cannot tell you whether reviewer 2
  was right. It can tell you whether reviewer 2 read the same paper as reviewers 1 and 3.
- Rewrite the paper, the abstract, the framing, or the title
- Draft your response to reviewers, rebuttal, or appeal
- Identify, profile, or characterize an individual reviewer
- Recommend a venue, or predict acceptance anywhere
- Tell you what to do next

It stops at the cause. What you do about it is your decision, and it is a different conversation
with different inputs.

---

## Setup

1. Create a Claude Project.
2. Upload everything in this folder **except `tests/`** to the project knowledge.

   `tests/` stays out deliberately. It holds the answer keys the regression cases are scored
   against, and a diagnostician that can read its own expected outputs is not being tested by
   them. It belongs in the repo, where a stranger can run the cases and check the result
   against the key themselves. It does not belong in the project, where the folder under test
   would be reading them.
3. Paste this into the project's custom instructions:

   > Follow identity.md and rules.md exactly. Run the diagnostic sequence in rules.md in
   > order and use the output contract at the end of that file. Consult reference/ as
   > needed. Do not recommend actions.

That is the whole install. No dependencies, no API keys, nothing to run.

---

## Running a case

Upload the case materials and say: **"Diagnose this rejection."**

### What you need

Four things. Without all four you will get an Undetermined result rather than a wrong one.

1. **Every report you received, in full, as written** — not a selection, not a summary
2. **The decision letter**, including the editor's remarks
3. **The submitted version** — at minimum title, abstract, claim statements, and the sections the
   reports name
4. **The venue and its stated scope**, plus its rejection rate if published

The first item is the one authors compromise without meaning to. **A selected panel cannot show
divergence.** Keep back the mild report and only convergence can be read, and convergence read
off a selected panel is an artifact of the selection. Summaries destroy it too: the pattern lives
in whether two reports objected to *the same thing*, which needs the actual wording of both.

The fourth item is what stops an ordinary outcome at a competitive venue from looking like a
verdict on your paper.

### What sharpens it considerably

- **The venue's review process** — specifically whether reviewers see each other's reports.
  Independence is the assumption everything else rests on, and a discussion phase changes what
  agreement means.
- **Prior rounds and their reports**, if this has been submitted before. That is a completed
  experiment and it is the most valuable item in the file.
- **Confidential-to-editor sections**, which often carry the fit and novelty commentary.
- **Reviewer areas as declared by the venue** — areas, not identities.

Full intake list in [reference/intake.md](reference/intake.md).

---

## What you get back

A report with fixed headings, in this order:

Failure observed · Comparison set · Comparison-set integrity · Funnel reconstruction · Primary
constraint · Primary cause · Mechanism · Evidence for this cause and against the alternatives ·
Alternatives and why they are demoted · Null model · Confidence · Missing evidence · What would
prove this wrong

The diagnosis comes at three levels rather than one, because flattening them produces a finding
that sounds rigorous and cannot be acted on. **Constraint** is where the submission breaks.
**Cause** is why it breaks there. **Mechanism** is how that cause produces this specific pattern
across these reports.

Three worked examples in [examples.md](examples.md), including one that finds nothing wrong.

---

## The three answers people find surprising

**"Your paper isn't wrong, it's unclear."** When no two reports object to the same thing and each
reviewer's account of your contribution differs from the others', competent readers took
different things from it. The eleven objections on record are then not eleven problems — they are
answers to three different papers, and none of them is usable evidence about your evidence.

**"They're right."** Independent readers who never spoke, arriving at the same objection, is the
strongest signal this domain produces. It is the finding authors least want and the one most
worth having early.

**"This decision doesn't carry information."** At a venue rejecting 85%, an ordinary rejection is
the modal outcome. If the panel agrees on nothing and the letter names no defect, rewriting
addresses nothing, because the decision was not about your paper.

---

## How it decides

Every submission moves through five stages: **desk survival, reviewer engagement,
reconstruction, claim support, contribution judgment.** Find the earliest one that broke. **That
stage is the diagnosis site, and every stage after it is starved and tells you nothing.**

That rule bites harder here than anywhere, because the starved stages still produce text. A
reviewer who misread your paper writes a full, confident, specific objection to your claims — and
that objection is downstream of the misreading and carries no independent information about
whether the claims hold. It looks exactly like evidence.

So the useful figure is never how many reviewers objected to your evidence. It is **how many of
the reviewers who reconstructed your paper correctly objected to your evidence.** Three of three
is a finding. One of three, with the other two objecting from a misreading, is the opposite
finding wearing the same number.

Contribution judgment is a stage rather than a metric because "this is wrong" and "this is right
and not for us" are different findings with different responses, and the rejection letter renders
both as *reject*. Collapsing them is how an author spends six months repairing a paper that had
nothing wrong with it.

Full method in [rules.md](rules.md). Cause taxonomy with evidence signatures in
[reference/failure-modes.md](reference/failure-modes.md).

---

## Files

```
review-rejection-diagnostician/
├── README.md                      this file
├── identity.md                    who it is, what it diagnoses, what it refuses
├── rules.md                       the method and the output contract
├── examples.md                    three worked cases, one of them a null
└── reference/
    ├── failure-modes.md           causes by funnel stage, with evidence signatures
    ├── baselines.md               reading the panel and establishing the pattern
    └── intake.md                  required inputs and missing-evidence handling
```

---

## Scope and honesty

The examples are constructed teaching cases with reports written to make each agreement pattern
legible. They are not real reports and the papers do not exist.

There are deliberately no benchmark figures anywhere in this folder. Acceptance rates, report
lengths, and what counts as an ordinary volume of criticism vary by field, venue, tier, and year,
and any number quoted as a norm would be wrong for most venues while being treated as
authoritative. Every baseline is computed from the panel and the venue supplied with the case.

This diagnoses how a paper was received. It does not assess whether the claims are true, whether
the method is sound, or whether any objection was correct — that question is answered by the
field, over time, and a tool answering it from three reports would be producing confident noise
about the thing that matters most.

Reviewers are numbered, never identified or characterized. Anonymity is a condition of the
process working at all.

Reports are confidential documents in most venues' processes. Whether to place them in a project
is your disclosure decision.
