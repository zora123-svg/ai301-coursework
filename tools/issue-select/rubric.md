# Rubric: is this a good first issue?

<!--
THIS IS THE PART YOU WRITE. The skill in SKILL.md executes whatever checks
you define here. It ships empty on purpose: the judgment is your work.

A filled rubric must contain:

1. At least one row in the checks table. Each row needs all four columns:
   - Check: a short name (used in the output JSON).
   - Evidence: exactly what to look at, and where. Name the source
     (repo-facts block, issue body, comment thread, or the locations in
     references/evidence-guide.md). "The repo" is not a source; "the last
     5 default-branch commit dates" is.
   - Pass condition: a condition someone else could apply and get your
     answer. Prefer thresholds with numbers ("a maintainer commented
     within 30 days") over adjectives ("maintainer is responsive").
   - Weight: `required` (a fail here rejects the issue) or `preferred`
     (never changes the verdict; a nice-to-have that helps rank the
     issues you accept).

2. A verdict rule below the table: how the check grades combine into
   accept or reject, including how `unclear` is treated. The verdict
   space is binary. If you write no rule for `unclear`, the skill treats
   it as fail.

Cover what actually kills first contributions. The lecture named four
families: the maintainer is alive, the repo is in use, the scope fits a
newcomer, and nobody else is already on it. A rubric that ignores a family
will fail eval issues designed around that family.
-->

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| maintainer-alive | Commit stream: date of the most recent default-branch commit; issue thread: date of the most recent maintainer/owner/collaborator comment | A maintainer merged a commit or commented on the issue thread within the last 30 days | required |
| repo-in-use | Repo-facts block: latest release date and last-push date | At least one release shipped in the last 6 months, OR a commit landed on the default branch within the last 30 days | required |
| scope-fits-newcomer | Issue body, and the comment thread if the issue body alone doesn't resolve it | The issue describes one specific task or bug with a defined outcome that a newcomer could finish and call done — even if it names multiple causes, touches several closely related files, or lists a few similar sub-items toward that one outcome (e.g. several rule previews, several doc pages for one workflow). Fails when the issue is instead an ongoing program or umbrella inviting an open-ended number of separate contributions (phrases like "PRs welcome, big and small" or "incrementally"), a self-described tracking list/megaissue, or a feature request where the core design/product decision is still unmade and unresolved after any comments. This applies regardless of who authored the issue — an umbrella issue is still an umbrella even when a maintainer opened it | required |
| unclaimed | This issue's current assignee field and linked/referenced PRs, plus the comment thread for any history of prior claims | No assignee is currently set, no PR (formally linked or referenced in the comment thread) already implements the fix, AND the comment thread does not show a pattern of prior contributors claiming this same issue and going quiet (two or more claim-then-abandon cycles, or someone reporting they already opened a PR for it) | required |
| ai-policy-compatible | The contribution policy quoted in the repo-facts block | The policy does not categorically forbid AI-generated code or documentation (e.g. "we do not accept AI-generated code or documentation"). A policy that merely requires the contributor to review, test, and personally understand AI-assisted work still passes — only an outright ban fails | required |

## Verdict rule

Accept if all `required` checks pass. Reject if any `required` check fails.
`unclear` on a `required` check counts as a fail.
