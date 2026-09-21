# Rubric: is this a good first issue?

<!--
Every recency threshold below is measured against the bundle's capture
date in eval mode, and against today in live mode. "Maintainer" means a
commenter whose author_association is OWNER, MEMBER, or COLLABORATOR.
"Human" means an account whose name does not end in `[bot]` and is not a
project automation account (e.g. minikube-bot, dependabot). The four
required checks map to the four lecture families; ai-policy-ok covers the
fifth surface from references/evidence-guide.md.
-->

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| maintainer-active | Repo facts: the "last 5 default-branch commits" list (date + author), the "latest release" line, and the "maintainer first-response sample". | Pass if at least one of the last 5 default-branch commits is dated within 90 days of the capture date AND is either authored by a human or is a bot merge of a PR whose branch belongs to a human (e.g. `Merge pull request #N from <human>/...`). If every commit in the window is bot-authored bot work (dependabot, automated version bumps), fall back to: pass if the latest release is within 180 days of capture OR any issue in the first-response sample got a maintainer comment within 30 days. Otherwise fail. | required |
| repo-shipping | Repo facts: the "archived:" flag on the repo line, the "latest release" line, and the "last push to any branch" line. | Fail immediately if `archived: yes`. Otherwise pass if the latest release is dated within 365 days of capture, OR (the repo has no releases / the release is older) the last push to any branch is within 60 days of capture. Fail otherwise. | required |
| scope-bounded | Issue title, body, labels, and who opened it (author_association); maintainer comments in the thread. | Pass only if the issue names ONE primary deliverable -- a single named artifact or behavior change (a page or file to add, a named function or line to fix, a described behavior to change) that one PR can finish -- and: (a) for a bug, the body identifies the current wrong behavior -- an error message, wrong output, a named file/line, or a named malfunctioning symptom or missing element when a maintainer filed the issue or it carries a newcomer label -- and the expected behavior, which may be left implicit where the symptom is plainly a malfunction (a crash, a freeze, or a missing element implies it should not crash, freeze, or be missing); (b) for a feature or docs change, the body or a maintainer comment names the specific change, AND the request is maintainer-endorsed (opened by a maintainer, OR carries a maintainer triage label such as good first issue / help wanted / an area or type label, OR a maintainer comment approves it). Several sub-items do NOT fail this check when every sub-item serves that one primary deliverable (e.g. add the new page, then update the existing pages that should point to it): grade the finish line, not the bullet count. Fail when the issue has no single finish line: a tracking/umbrella/"mega" issue whose body is mainly a list of other issue references; an open-ended or incremental invitation (the body invites many PRs, or asks for more of X across the codebase without naming which parts); a pure usage question; or a thread where a maintainer questioned WHAT the change should do or whether it belongs at all ("what should this do?", "not sure this belongs", a maintainer asking the reporter to justify or specify the target behavior) and no later maintainer comment settled it with a concrete decision, which a long thread or past abandoned attempts (closed unmerged PRs) confirm. A maintainer naming suspected causes, mechanisms, or implementation options for a symptom everyone agrees is wrong is diagnosis, not an unsettled spec: latitude in HOW to fix an agreed bug does not fail this check. An illustrative list of examples inside an otherwise bounded bug ("including A, B, C, etc.") is not open-ended. A short body is not a fail by itself: where a maintainer filed the issue or it carries a newcomer label, a maintainer has already judged its size, so grade the size of the work requested, not the polish of the writeup. | required |
| unclaimed | Repo facts: the "this issue: assignees:" and "linked PRs:" line; the comment thread (author, date, text). | Pass only if assignees is `none`, AND no linked PR is in state `open`, AND no comment dated within 180 days of capture claims the issue ("I'll take this", "working on this", "/assign", "can I work on this") or announces/links a PR for it. A claim or PR mention older than 180 days with no follow-up from that person is stale and does not block; a claim of any age is cleared if a maintainer later invited new takers or said the claim was abandoned. Closed/merged linked PRs do not block on their own. | required |
| ai-policy-ok | Repo facts: the "contribution policy" line (quoting CONTRIBUTING.md / AI policy files / templates). | Pass if the policy line states no policy, or states conditions only (disclose AI use, personally understand and test every change, human review required, "fully AI-generated not accepted but assistive use allowed"). Fail only on an outright ban on AI-generated or AI-assisted contributions ("we do not accept AI-generated code"). | required |
| newcomer-label | Issue labels. | Pass if the issue carries a newcomer label: good first issue, help wanted, easy, beginner, or an equivalent. Used only to rank accepted issues. | preferred |
| maintainer-filed | The issue's opener (author_association). | Pass if the issue was opened by a maintainer (OWNER, MEMBER, or COLLABORATOR): maintainer-filed issues are already triaged and rarely get rejected on scope. Used only to rank accepted issues. | preferred |

## Verdict rule

Accept only if every `required` check is `pass`. A single `fail` on any
required check rejects the issue. `unclear` on a required check counts as
`fail`: a first issue whose evidence you cannot verify is not a first issue
you should take. `preferred` checks never change the verdict; among accepted
issues, rank the ones with more preferred passes higher.
