# Baselines

The comparison set is what turns an opinion into a diagnosis. This file covers how to read
the panel you were given and how to decide what counts as a signal.

There are no benchmark numbers here on purpose. Acceptance rates, report lengths, review
turnaround, and what counts as an ordinary volume of criticism vary enormously by field,
venue, tier, and year. Any figure quoted as a norm would be wrong for most venues and would be
treated as authoritative anyway. **Every baseline in a diagnosis is computed from the panel and
the venue supplied with the case.**

---

## The comparison set is the panel

This domain differs from every other in the family, and the difference is in the author's
favour. Elsewhere a comparison set has to be assembled and defended: comparable listings,
comparable topics, comparable requisitions, each one an argument about whether it is really
comparable. Here the set arrives already built and it is stronger than anything assembly could
produce.

**One fixed artifact. Several qualified readers. The same moment. No communication between
them.**

The paper does not vary. The readers do. So every difference between the reports is evidence
about how the paper reads, and every agreement is evidence about the paper. That is a
within-case comparison with the artifact held genuinely constant, which is rare enough to be
worth naming as the reason this folder works at all.

What it is not: an experimental control. Reviewers still differ in expertise, available time,
what the editor asked them to weigh, what else they read that month, and what they believe the
venue is for. Agreement is strong evidence about the paper. It is not proof the paper is the
only variable.

---

## Establishing the pattern

Read the panel three ways, in this order.

**1. Do the objections overlap?** Take each report's substantive objections — the ones that
bear on whether the paper should be published, not the requests for another citation. Ask
whether any objection appears in more than one report, in substance rather than in wording.

- **Convergent** — a substantive objection appears in a majority of reports, independently
  arrived at.
- **Divergent** — no substantive objection appears twice. Every report has its own.
- **Polarized** — reports agree about what the paper does and split on whether it belongs.

**2. Do the restatements agree?** Independently of the objections, extract each report's
account of what the paper claims and does. Compare them to each other, and compare them to the
paper. Three outcomes, and they are the Stage 3 discriminator:

- Restatements agree with each other and with the paper → reconstruction is healthy
- Restatements conflict with each other → claim ambiguity
- Restatements agree with each other and differ from the paper in the same direction →
  framing mismatch

**3. What did the editor act on?** The decision letter tells you which reading the venue
adopted. On a polarized panel this is the whole finding: the editor chose, and the choice
reveals the venue's standard more than the paper's quality.

---

## What counts as a signal

Judgment, stated explicitly in the report rather than applied silently.

- **Clear signal** — a substantive objection independently present in a majority of
  substantive reports, or restatements that demonstrably conflict, or an explicit split on
  scope.
- **Ambiguous** — an objection present in two of four reports, or convergence on something
  minor. Note it, do not treat it as the break unless a later stage is clean.
- **No signal** — objections scattered, minor, and of the kind every report contains.

Do not manufacture a pattern by loosening what counts as the same objection until two reports
match. If you have to squint to make two objections the same, they are not the same.

### The count that is not a discriminator

Every one of the three patterns produces a long list of criticisms. Divergent, convergent, and
polarized panels all generate reports full of objections, and the totals are frequently
similar. **The number of weaknesses raised is predicted by all three hypotheses and therefore
separates none of them.** What separates them is whether the objections overlap — a property
of the set, invisible in any single report, and the reason the panel has to be read together
rather than one report at a time.

The same trap appears one level down. Recommendation spread — one reject, one major revision,
one accept-with-changes — looks like polarization and usually is not. Reviewers converge on the
same defect and diverge on whether it is fatal all the time. That is a difference in threshold,
not in reading. **Read agreement on what is wrong, not agreement on what to do about it.**

---

## Panel size

Three or more independent substantive reports is a usable panel. Two is the floor, and at two
you can observe agreement and cannot distinguish a pattern from a coincidence: two readers
agreeing is two readers agreeing, and the probability that two competent people in the same
field independently notice the same obvious thing is not low.

One report is not a comparison set. Report Undetermined.

Above four the pattern is usually already clear and additional reports mostly confirm.

---

## Independence is the load-bearing assumption

Everything above depends on the readers not having spoken. Check it explicitly rather than
assuming it.

Venues increasingly run a discussion phase in which reviewers see each other's reports and may
revise before the final decision. Where that happened, **agreement may be social convergence
rather than shared reading**, and the convergent branch cannot be read at full strength. The
divergent branch is affected in the opposite direction and survives: if readers who saw each
other's reports still disagreed, the disagreement is more meaningful, not less.

Where reports carry timestamps or version markers, use them. Where the venue's process is
published, read it. Where neither is available, say the independence of the panel could not be
established and treat the convergent branch as capped.

---

## What the comparison set cannot see

Matching is what makes a comparison work and it is also what makes a comparison blind. Every
axis held constant becomes invisible.

Here the artifact is held constant, which is the point — and it means **the panel can tell you
nothing about how the paper would read to a different kind of reader.** If all three reviewers
come from the same subfield, the set cannot detect a framing problem that would be obvious to
someone outside it, because that perspective does not vary across the panel. If all three were
selected by an editor working from the paper's own keywords, the set cannot detect that the
keywords were wrong.

Name the matched axis in the report as a live alternative that this panel is structurally
unable to test, and name what would test it — usually a reading from outside the panel's
shared background. Do not report it as ruled out. A variable held constant has not been
examined.

---

## The venue rate, and what it is for

The venue's rejection rate is not a benchmark and is not compared against other venues. It has
exactly one job: it is **the input the null model runs on**.

A high rate means rejection is the modal outcome and a rejection on its own carries very little
information about a particular paper. A low rate means the opposite. Either way the number is
about this venue, supplied with this case.

Where the rate is published, use it. Where it is not, say the null could not be tested against
its own input, and cap the null at Provisional under the null-grading rung in `rules.md`. Do
not substitute an impression that the reports seemed mild — that is the inference the rung
exists to distinguish from a measurement.

---

## The qualifying revision test

The most useful item in any file where the paper has been submitted before, and the easiest to
over-read.

A prior round is a completed experiment. But an experiment only tests what it was capable of
testing, and most revisions are not capable of testing most mechanisms.

### Step 1: does the revision qualify

All four must hold before the result means anything.

| Condition | Why it matters | Fails when |
|---|---|---|
| **Changed the thing under test** | A revision only tests the stage it acted on. Clarity acts at reconstruction, new evidence at claim support, a different venue at contribution judgment | A clarity rewrite offered as evidence against an evidential gap. A clearer statement of an unsupported claim is still an unsupported claim |
| **Otherwise separable** | Simultaneous changes confound the result | The revision reframed the paper *and* added two experiments, and the second panel's pattern moved. Which one moved it is not recoverable |
| **Independent second panel** | Same reviewers rereading their own prior objections is not a fresh reading | The venue routed the revision back to the original reviewers. Their agreement with themselves is not convergence |
| **Venue bar unchanged** | The comparison must survive | New editor, special issue, or revised scope statement between rounds |

If any condition fails, the revision is **Uninformative**. Say which condition failed and do
not use it as evidence in either direction. An experiment that did not run is not weak evidence
for the null. It is no evidence.

### Step 2: read a qualifying revision

Compare the pattern before against the pattern after, stage by stage.

- **The pattern moved at a stage** — that mechanism was a real constraint. Which stage changed
  identifies it, and that is more valuable than the fact of the change. Record as **Positive**.
- **Reconstruction improved and the outcome did not change** — the revision worked at what it
  was capable of testing, and it fixed a stage that was never the constraint. Two findings, not
  one, and the second is the more useful. The constraint is downstream.
- **Nothing moved** — strong evidence against **the specific mechanism this revision was
  capable of testing**. Name it explicitly. Record as **Negative**.

**Negative and Uninformative are different verdicts and must be labelled differently.** One
means the test ran and the hypothesis lost. The other means no test occurred. Authors read a
second rejection as proof of gatekeeping; that reading is available, and so is the opposite,
and which is correct depends entirely on whether the revision could have tested the break stage
at all.
