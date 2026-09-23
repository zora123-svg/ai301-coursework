# Unit 1 — Issue Selection

Path: `beat-1-sandbox/unit-1/selection.md`

Record of the issue carried into Unit 2, and of the evaluation runs that produced
`eval-run.txt`. This file is graded at the path above; a copy kept anywhere else in
the repository is not read.

Complete every labelled field below. Each is graded on its own; content placed under the
wrong label is not graded.

---

## Selected issue

**Issue link**

https://github.com/codepath/pathreview-ai301-fa26-s3/issues/40

**Verdict output**

```
## Summary

All three issues come from the scoped repo (`codepath/pathreview-ai301-fa26-s3`) and pass every required check: the repo pushed a commit 6 days ago (2026-09-16) and shows no policy against AI-assisted work, and none of the three issues has an assignee, a linked PR, or any comments showing a prior claim.

**Ranked (all accepted):**

1. **#40 — "Add a Copy link button..."** — Best fit: spans a React frontend file (`ReviewPage.tsx`) and a Python backend route (`api/routes/reviews.py`), directly matching your React + Python experience and your goal of building real full-stack fundamentals, while the requirement (read-only link, 30-day expiry) is already concretely specified.
2. **#47 — "API docs don't include example curl commands"** — Solid, low-risk fit: pure docs task in your wheelhouse (any language), smallest scope (2–3 hrs, tier-1), but less building/engineering practice than #40.
3. **#27 — "Add a feedback tone check..."** — Accepted but ranked last: Python files only, but the work sits inside the RAG/LLM generation pipeline (prompt-based classification, regeneration logic) — a domain outside your stated experience, so the learning curve is higher relative to payoff.

```json
[
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s3/issues/40",
    "checks": [
      {"name": "maintainer-alive", "grade": "pass", "evidence": "Most recent default-branch commit by Aburke225 on 2026-09-16, 6 days before today (2026-09-22)"},
      {"name": "repo-in-use", "grade": "pass", "evidence": "Commit landed on default branch 2026-09-16, within 30 days (no releases exist, but commit-recency clause satisfies the OR)"},
      {"name": "scope-fits-newcomer", "grade": "pass", "evidence": "Body specifies one concrete outcome (shareable, no-login, 30-day-expiry read-only link) across 3 closely-related files, no open design question"},
      {"name": "unclaimed", "grade": "pass", "evidence": "assignee: null, assignees: [], comments_count: 0, pull_request: null"},
      {"name": "ai-policy-compatible", "grade": "pass", "evidence": "docs/CONTRIBUTING.md and PR template contain no AI-usage restriction; silence passes per rubric"}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s3/issues/47",
    "checks": [
      {"name": "maintainer-alive", "grade": "pass", "evidence": "Most recent default-branch commit by Aburke225 on 2026-09-16, within 30 days"},
      {"name": "repo-in-use", "grade": "pass", "evidence": "Commit landed 2026-09-16, within 30 days"},
      {"name": "scope-fits-newcomer", "grade": "pass", "evidence": "Single file (docs/API.md), single defined outcome (add curl examples), labeled good-first-issue + tier-1, 2-3 hr estimate"},
      {"name": "unclaimed", "grade": "pass", "evidence": "assignee: null, assignees: [], comments: 0, pull_request: null"},
      {"name": "ai-policy-compatible", "grade": "pass", "evidence": "No AI restriction found in docs/CONTRIBUTING.md or PR template"}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s3/issues/27",
    "checks": [
      {"name": "maintainer-alive", "grade": "pass", "evidence": "Most recent default-branch commit by Aburke225 on 2026-09-16, within 30 days"},
      {"name": "repo-in-use", "grade": "pass", "evidence": "Commit landed 2026-09-16, within 30 days"},
      {"name": "scope-fits-newcomer", "grade": "pass", "evidence": "Bounded outcome (add a tone-classification/reject-regenerate step) across 2 named files, no open design debate in the issue"},
      {"name": "unclaimed", "grade": "pass", "evidence": "assignee: null, assignees: [], comments_count: 0, pull_request: null"},
      {"name": "ai-policy-compatible", "grade": "pass", "evidence": "No AI restriction found in docs/CONTRIBUTING.md or PR template"}
    ],
    "verdict": "accept"
  }
]
```
```

---

## Eval iterations

Quote source text directly in each field below. Paraphrase does not satisfy them.

**Run history**

1. `agreement: 17/20 scored items  (bar: 18/20: below the bar)`
2. `agreement: 13/20 scored items  (bar: 18/20: below the bar)`
3. `agreement: 16/20 scored items  (bar: 18/20: below the bar)`
4. `agreement: 16/20 scored items  (bar: 18/20: below the bar; category floor unmet: no match in policy)`
5. `agreement: 18/20 scored items  (bar: 18/20: PASS)`
6. `agreement: 19/20 scored items  (bar: 18/20: PASS)`

The last score matches the `agreement:` line in the committed `eval-run.txt`.

**Issue analysis**

`issue-19` (zxcalc/zxlive#517). My rubric's verdict: `reject` (`failed: scope-fits-newcomer`). Gold label: `accept`, with the note *"maintainer-diagnosed performance bug with named causes, unclaimed"*.

The issue body reads: *"There are two potential causes which should be fixed: 1. The matchers are slow... 2. UI update is waiting..."* followed by three "Additional suggestions." My check's pass condition rejects an issue when it shows "multiple competing approaches still undecided," and the model graded the three additional suggestions as exactly that — undecided competing approaches — rather than as optional implementation notes attached to an already-diagnosed bug. Gold treats naming multiple causes of one bug as still bounded, since the causes are diagnosed, not merely proposed; my check's wording doesn't yet distinguish "named causes of a diagnosed bug" from "an open design question with multiple options."

**Check rationale**

`scope-fits-newcomer`, quoted from the uploaded `rubric.md`:

> The issue describes one specific task or bug with a defined outcome that a newcomer could finish and call done — even if it names multiple causes, touches several closely related files, or lists a few similar sub-items toward that one outcome (e.g. several rule previews, several doc pages for one workflow). Fails when the issue is instead an ongoing program or umbrella inviting an open-ended number of separate contributions (phrases like "PRs welcome, big and small" or "incrementally"), a self-described tracking list/megaissue, or a feature request where the core design/product decision is still unmade and unresolved after any comments. This applies regardless of who authored the issue — an umbrella issue is still an umbrella even when a maintainer opened it

This wording went through two earlier drafts. The first version required either a tightly single-scoped issue body or a comment thread that confirmed the scope; that version rejected several gold-`accept` issues (conda#16475, zxlive#555, zxlive#517) that had zero comments but were still clearly bounded. A second draft added a carve-out exempting any issue opened by the repo's own maintainer/collaborator from needing that confirmation — but that carve-out let through sympy#28806, a gold-`reject` "codebase-wide type-annotation umbrella" that also happened to be collaborator-authored. The current wording drops the authorship carve-out entirely and instead names the actual distinguishing feature the gold labels track: a bounded task can span several files or list a few sub-items, but an *open-ended, ongoing program* (an umbrella or tracking list) is rejected regardless of who opened it.

**Trade-offs**

This check still misses `issue-19`, as shown directly in the committed `eval-run.txt`: `issue-19  accept  reject   NO     failed: scope-fits-newcomer`. The wording's "multiple competing approaches still undecided" clause, which correctly rejects real design-debate issues (e.g. `sharkdp/bat#1341` in the calibration set), also catches a diagnosed bug that lists more than one named cause plus optional follow-up suggestions. I accepted this as a known miss rather than loosening the clause further, because loosening it to admit "named causes plus suggestions" risks re-admitting the umbrella issues (`issue-05`, `issue-10`) the same clause was tightened to catch — those also present as lists of "named," seemingly bounded sub-items.

---

## Selection rationale

Graded on whether all three are answered, in your own words. Not on how good the
reasoning is, and not on length — a short honest answer to each earns the full marks.
This is also the basis for the claim comment you write in Unit 2.

**Selection rationale**

1. This issue fits my interest in full-stack development — it spans both the React frontend and the Python backend, which lines up with where I want to grow.
2. The verdict correctly identified my interest and ranked this issue first for fit. I don't think it weighed the time the issue would take to complete.
3. It's labeled tier 2, which I'd call an intermediate level of difficulty — certainly doable by me.

---

Related paths: `eval-run.txt` in this directory; your skill's files in
`tools/issue-select/`.
