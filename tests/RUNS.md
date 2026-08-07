# Run record

**4 blind runs, 3 cases.** Cases 01 and 02 **20/20** each. Case 03 has been run twice: once
against the original key, which it proved wrong, and once again against the corrected key, which
it also proved wrong — in a different place.

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

## Case 03, run twice

The second run agreed with the corrected key on **17 of 20** assertions outright, including every
one the case was built to test: the 5D-over-null tie-break stated and applied, the venue's
published rate used as the input the null is tested against rather than as background, the
directional-bias analysis worked through in the direction that *strengthens* the finding, and
**Provisional** held anyway because the panel-integrity cap binds on structure rather than on
strength. Two assertions matched partially.

The twentieth could not be scored, because the key contradicts itself. `Must assert` requires
**"Primary cause is 5D, competitive triage"**; `Must not` requires **"Does not name any cause as
primary."** Both cannot hold. The `Must not` line was inherited from a pure-null case template and
survived the 5D correction, which updated the assertion and never swept the prohibition — the same
fix-the-instance-don't-sweep-the-class failure the Step 1 routing defect was. Both lines are now
corrected.

This is the value of re-running a repaired key. The first run corrected the key; the key then
agreed with that run by construction. Only a second blind run could show that the repair had left
a contradiction behind, and it did.

## What is still open

- **Cases 01 and 02 have not been re-run against their corrected keys.** They still agree with the
  runs that corrected them by construction. Case 03 is now the only case in this folder whose key
  has survived a run it did not shape.
- **No retrospective field validation.** Every case here is a constructed teaching case. None is a
  real rejection with a known outcome, and nothing in this folder has been checked against one.

`tests/` is deliberately excluded from what you upload into a Claude Project. See the README.
