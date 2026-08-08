# Run record

**6 blind runs, 3 cases.** Every case has now been run twice: once against the key as originally
written, and once again against the key after the first run corrected it. That second pass is the
one that matters, and it is described at the bottom under *Closing the circularity*.

| Case | First run | Re-run against the corrected key |
|---|---|---|
| 01 — divergent reads | 20/20 | **18/20** · 1 partial, 1 missed assertion |
| 02 — convergent defect | 20/20 | **21/21** · clean |
| 03 — null / base rate | key proven wrong, corrected | **17/20** · found the corrected key contradicting itself |

## How these were run

Each case was run in a **fresh session that had never seen this folder**, by someone who did not
build it. The session was given the folder and the case inputs and explicitly forbidden from
opening any `expected.md`. It returned a diagnosis. Only afterwards was that diagnosis scored,
line by line, against the assertions written before the run.

That order is the point. An answer key written from the spec tests whether the folder is
self-consistent. A key scored against a blind run tests whether it is *right*, and the way you
find out it wasn't is that a run disagrees and turns out to have the better argument.

## What the runs actually changed

Most defects these runs found were in an answer key, a fixture, or a worked example — the layer
that *demonstrates* the rules rather than the layer that states them. An example teaches by
demonstration and a rule constrains by assertion, and demonstration wins, so an example that
breaks its own rule is worse than no example at all.

**But not all of them, and an earlier version of this file said otherwise.** It claimed the runs
had found zero defects in any `rules.md`. That was true when it was written and false within a
day, and it stayed on `main` after the commits that falsified it. Two `rules.md` defects have
been found, both routing:

- **Step 1 terminated before the taxonomy could fire**, which made 5D unreachable — every case
  meeting 5D's conditions also met the screen's, so the screen answered first and the taxonomy
  entry became dead text.
- **The same termination, in four of the five products in this family**, found when a blind
  re-run hit it in a second product. Fixed everywhere it was carrying.

That correction matters more than the clean number it replaced. A run that can only ever find
fault with the demonstration layer is not reaching the layer that governs. These two show the
runs reach it.

## Closing the circularity

Every corrected key in this folder has now been re-run blind. Three results, and they are three
different kinds:

**Case 02 came back 21/21.** Every assertion, including the three the case exists to catch: the
recommendation split refused as polarization rather than promoted to Stage 5, the venue-problem
framing the request asks for refused on the evidence, and the round-1 revision graded **Positive
at Stage 3** with the two-findings reading — the revision worked at the one thing it could test,
and clearing that break revealed the next one rather than resolving it. This is the strongest
result in the folder, because the key it satisfied was one a previous run had already corrected.

**Case 03 proved the corrected key wrong a second time, in a new place.** The key required
"Primary cause is 5D, competitive triage" under `Must assert` and "Does not name any cause as
primary" under `Must not`. Both cannot hold. The prohibition had been inherited from a pure-null
case template and survived the 5D correction, which updated the assertion and never swept the
prohibition. Both lines are now fixed. Only a run that did not shape the key could have shown
this, which is the whole argument for re-running.

**Case 01 came back 18/20 on a key that had scored 20/20.** The run held every load-bearing
assertion — constraint at Stage 3, the divergence pattern, framing mismatch demoted on the
agreement discriminator rather than the misreading count, Stages 4 and 5 declared starved, and
the folk cause refused explicitly ("*A reviewer did not read it.* Not supported"). What it
dropped was the assertion requiring the author's count of eleven objections to be **addressed and
refused as a basis**. The run never mentioned the count. It did not rank or triage the
objections either, so the drift signal did not fire — it simply declined to engage the author's
framing rather than refusing it out loud.

That gap is a finding about the method, not only about the run. **The output contract has no
heading where "your count of objections is not a measure of anything" belongs.** The assertion is
satisfiable — the first run satisfied it — but whether it appears depends on the run rather than
on the contract, and an assertion the method never cues is one the method cannot be relied on to
produce.

It has deliberately **not** been patched. Editing `rules.md` to satisfy a key hours after a run
exposed the gap, without re-running, rebuilds exactly the circularity this record exists to track.
It is written down instead.

## What is still open

- **The case-01 contract gap above.** Named, not fixed, and not fixed on purpose.
- **No retrospective field validation.** Every case here is a constructed teaching case. None is a
  real rejection with a known outcome, and nothing in this folder has been checked against one.
  This is the largest thing missing and no amount of blind running substitutes for it.

`tests/` is deliberately excluded from what you upload into a Claude Project. See the README.
