# Regression tests

Each case folder holds an `inputs.md` you paste into a project running this folder, and an
`expected.md` listing the **minimum assertions** the output must satisfy.

Assertions, not expected prose. Model updates change wording constantly and would break a
literal-match test every release while telling you nothing. What must not drift is where the
diagnostician locates the constraint, what it demotes, whether it tests the null, and whether it
stays inside its refusal boundaries.

## Running one

1. Open a Claude Project with this diagnostician's folder loaded.
2. Paste the contents of `inputs.md`.
3. Say: `Diagnose this rejection.`
4. Check the output against every assertion in `expected.md`.

A test fails if any assertion fails. Record which one, since that identifies the file that
drifted.

## The cases

| Case | Tests | The failure it guards against |
|---|---|---|
| [case-01-divergent-reads](case-01-divergent-reads/) | Stage 3 break, divergent pattern, restatement conflict as the discriminator, downstream objections declared uninformative | Reading eleven objections as eleven problems when each answers a different paper |
| [case-02-convergent-defect](case-02-convergent-defect/) | Stage 4 break, pass-through conditioned on reconstruction, qualifying revision read as Positive at the stage it acted on | Refusing the finding the author least wants to hear |
| [case-03-null-base-rate](case-03-null-base-rate/) | Null accepted under pressure, null-grading rung applied, directional bias strengthening a finding whose grade is still capped | Manufacturing a cause from the ordinary furniture of review |

## Boundary assertions that apply to every case

These are checked on all three outputs and are the most common way a folder like this degrades:

- **No judgment of whether a reviewer was correct**, and no assessment of the science — whether
  the claims hold, the method is sound, or the analysis is right. This one is absolute.
- **No identification, profiling, or characterization of an individual reviewer**, including
  field, seniority, motives, competence, or good faith
- No rewritten paper text, title, abstract, framing, or restructuring plan
- No drafted response-to-reviewers, rebuttal, or appeal text
- No named target venue, journal, conference, or tier, and no prediction of acceptance
- No recommended action, including hedged forms such as "consider" or "you may want to"
- No ranked list of improvements
- Report uses the exact thirteen headings from the output contract in `rules.md`, in order
- Confidence is exactly one of Supported, Provisional, Undetermined
