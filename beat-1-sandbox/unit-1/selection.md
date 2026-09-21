# Unit 1 — Issue Selection

Path: `beat-1-sandbox/unit-1/selection.md`

---

## Selected issue

**Issue link**

https://github.com/codepath/pathreview-ai301-fa26-s1/issues/69

**Verdict output**

Live-mode run on three candidates (#69, #53, #72). The skill accepted all three and
ranked #69 first on fit; #69 is the first object in the closing JSON block, with
`"verdict": "accept"`.

````
issue-select: grade these candidate first issues: https://github.com/codepath/pathreview-ai301-fa26-s1/issues/69 https://github.com/codepath/pathreview-ai301-fa26-s1/issues/53 https://github.com/codepath/pathreview-ai301-fa26-s1/issues/72

All three candidates are inside the scoped repo (codepath/pathreview-ai301-fa26-s1). Gathering repo-level facts and the three issue threads.

Repo-level facts (shared by all three, measured against 2026-09-21): codepath/pathreview-ai301-fa26-s1 is not archived; last 5 main commits are all by human collaborator Aburke225, newest 2026-09-16 (5 days ago); no releases, last push 2026-09-16; docs/CONTRIBUTING.md (189 lines), the PR template, and the repo root contain no AI-usage policy at all. So maintainer-active, repo-shipping, and ai-policy-ok pass for every candidate.

Ranked read-out

Accepted (in fit order)

1. #69 - Output parser crashes on a top-level JSON array fallback - all 5 required pass, both preferred pass. Fit: it lives in the RAG subsystem (rag/generator/output_parser.py), which is the area you named as a growth goal, and it is exactly your preferred shape: a bug with a named file, a named xfail test (manifest H-02), and a reproduced traceback (AttributeError: 'list' object has no attribute 'items'). Note a classmate (jacho15, association NONE) posted a claim + repro on 2026-09-19; under the Path Review house rule that does not block, so unclaimed passes.
2. #72 - verify_password raises UnknownHashError instead of returning False - all 5 required pass, both preferred pass. Fit: Python backend (api label, core/security.py) with a named xfail test (H-05), and it overlaps your security-internship background (fail-closed auth), so it is the lowest-risk of the three; ranked second only because it exercises a strength more than a growth area. The only linked activity is a closed PR in a student's own coursework repo and a fork commit - nothing open in this repo.
3. #53 - PII scrubber fails to redact parenthesized US phone numbers - all 5 required pass, both preferred pass. Fit: Python with four named failing tests in tests/unit/test_pii_scrubber.py, but it is a regex fix in the safety layer, least connected to your stated goals (FastAPI/SQLAlchemy backend, RAG retrieval/eval).

Rejected: none.

```json
[
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s1/issues/69",
    "checks": [
      {"name": "maintainer-active", "grade": "pass", "evidence": "Last 5 main commits all by human collaborator Aburke225, newest 2026-09-16T21:42Z (5 days before 2026-09-21)"},
      {"name": "repo-shipping", "grade": "pass", "evidence": "archived: false; no releases; last push 2026-09-16T21:48Z (5 days, within 60)"},
      {"name": "scope-bounded", "grade": "pass", "evidence": "Bug with one deliverable: rag/generator/output_parser.py calls .items() on a list -> 'AttributeError: list object has no attribute items'; expected: fallback handles array responses; xfail test H-02 named"},
      {"name": "unclaimed", "grade": "pass", "evidence": "assignees: none; linked PRs: none; only claim is classmate jacho15 [NONE] on 2026-09-19 ('I'd like to attempt this'), which the Path Review house rule says does not block"},
      {"name": "ai-policy-ok", "grade": "pass", "evidence": "docs/CONTRIBUTING.md, PR template, and repo root state no AI policy (no AI_POLICY/AGENTS files, no disclosure checkbox)"},
      {"name": "newcomer-label", "grade": "pass", "evidence": "labels: bug, good first issue, rag, tier-1"},
      {"name": "maintainer-filed", "grade": "pass", "evidence": "opened by Aburke225 [COLLABORATOR]"}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s1/issues/72",
    "checks": [
      {"name": "maintainer-active", "grade": "pass", "evidence": "Last 5 main commits all by human collaborator Aburke225, newest 2026-09-16T21:42Z (5 days before 2026-09-21)"},
      {"name": "repo-shipping", "grade": "pass", "evidence": "archived: false; no releases; last push 2026-09-16T21:48Z (5 days, within 60)"},
      {"name": "scope-bounded", "grade": "pass", "evidence": "Bug with one deliverable: core/security.py lets passlib UnknownHashError escape on malformed hashes; expected: return False (fail closed); xfail test H-05 in tests/unit/test_security.py named"},
      {"name": "unclaimed", "grade": "pass", "evidence": "assignees: none; no formally linked PRs; only cross-refs are a CLOSED PR in foojanbabaeeian/ai301-coursework-Fozhan and a fork commit; zero comments"},
      {"name": "ai-policy-ok", "grade": "pass", "evidence": "docs/CONTRIBUTING.md, PR template, and repo root state no AI policy (no AI_POLICY/AGENTS files, no disclosure checkbox)"},
      {"name": "newcomer-label", "grade": "pass", "evidence": "labels: bug, good first issue, api, tier-1"},
      {"name": "maintainer-filed", "grade": "pass", "evidence": "opened by Aburke225 [COLLABORATOR]"}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s1/issues/53",
    "checks": [
      {"name": "maintainer-active", "grade": "pass", "evidence": "Last 5 main commits all by human collaborator Aburke225, newest 2026-09-16T21:42Z (5 days before 2026-09-21)"},
      {"name": "repo-shipping", "grade": "pass", "evidence": "archived: false; no releases; last push 2026-09-16T21:48Z (5 days, within 60)"},
      {"name": "scope-bounded", "grade": "pass", "evidence": "Bug with one deliverable: phone regex in safety/pii_scrubber.py; observed 'Call me at (555) 123-4567 or [REDACTED]' and detect() -> []; expected: parenthesized format redacted; four named failing tests in tests/unit/test_pii_scrubber.py"},
      {"name": "unclaimed", "grade": "pass", "evidence": "assignees: none; linked PRs: none (only a commit reference from fork Evin009/ai301-coursework); zero comments"},
      {"name": "ai-policy-ok", "grade": "pass", "evidence": "docs/CONTRIBUTING.md, PR template, and repo root state no AI policy (no AI_POLICY/AGENTS files, no disclosure checkbox)"},
      {"name": "newcomer-label", "grade": "pass", "evidence": "labels: bug, good first issue, safety, tier-1"},
      {"name": "maintainer-filed", "grade": "pass", "evidence": "opened by Aburke225 [COLLABORATOR]"}
    ],
    "verdict": "accept"
  }
]
```
````

---

## Eval iterations

**Run history**

Two runs before any of these errored out with `claude exited 1` on every item and
produced no agreement score. Both causes were environmental rather than rubric results:
an expired OAuth session on my machine (fixed with `claude auth login`), and a Windows
cp1252 crash when the harness piped the prompt to the CLI (fixed by running it as
`python -X utf8`). Neither produced a score, so neither is listed below. The scored runs,
in order:

1. `--limit 3` smoke run: **2/3**. `issue-01` disagreed — gold `accept`, my rubric
   `reject` on `scope-bounded`.
2. `--only issue-01,issue-05,issue-10` after my first `scope-bounded` revision: **3/3**.
   `issue-05` and `issue-10` were canaries rather than disagreements: they are the two
   gold `reject` umbrella issues that a looser umbrella rule could have let through.
   Neither moved.
3. Full 20-issue run: **18/20 scored items (bar: 18/20: PASS)**, categories
   `claimed 4/4  clear-accept 6/8  dead-repo 3/3  policy 1/1  scope 4/4`. Both
   disagreements — `issue-04` and `issue-19` — were gold `accept` rejected by
   `scope-bounded`, and both sat in `clear-accept`, so I revised rather than stopping at
   the bar.
4. `--only issue-01,issue-04,issue-05,issue-10,issue-15,issue-19,issue-20` after my
   second `scope-bounded` revision: **7/7**. That set is every item in the eval whose
   verdict depends on `scope-bounded`, so one partial run tested the fix and guarded
   every regression at once: `issue-04` and `issue-19` flipped to `accept`, `issue-01`
   held at `accept`, and `issue-05`, `issue-10`, `issue-15` and `issue-20` held at
   `reject`.
5. Full 20-issue confirming run: **20/20 scored items (bar: 18/20: PASS)**, categories
   `claimed 4/4  clear-accept 8/8  dead-repo 3/3  policy 1/1  scope 4/4`. This is the run
   committed as `eval-run.txt`.

**Issue analysis**

`issue-04` (zxcalc/zxlive#555, "Missing several basic rule previews"). My rubric decides
**accept** and the gold label is **accept**, but it took two revisions of `scope-bounded`
to get there, and the reason it originally failed is the more useful half of the story.

In my run 3 the check rejected it, with this evidence line: "Body: 'Including remove
identity, fuse spiders, remove self loops, etc.' — trailing 'etc.' leaves the deliverable
open-ended/unenumerated." Two clauses I had written produced that. Leg (a) required a
bug's body to state "the current behavior (an error message, wrong output, or a named
file/line) and the expected behavior", and the entire body of `issue-04` is one sentence
that names no error message, no file, no line, and never states expected behavior
explicitly. Separately, I had added an "open-ended or incremental invitation" fail
condition to stop umbrella issues like `issue-05` passing, and it caught the trailing
"etc." in what is really a list of example rewrite rules.

Both readings follow my check as literally written and both are wrong about the issue.
`RazinShaikh (COLLABORATOR)` filed it and it carries `good first issue` beside
`Type: bug` and `Category: Proof mode`, so a maintainer had already judged its size, and
the "etc." sits inside one bounded bug rather than spreading work across a codebase.
`references/evidence-guide.md` says this outright — "Short is not the same as
unscoped... Grade the size of the work being asked for, not the polish of the writeup" —
and my pass condition had not encoded it beyond one sentence ("A short body is not a fail
by itself") that the two stricter clauses above simply overrode.

So I fixed the check rather than the verdict. Leg (a) now also accepts "a named
malfunctioning symptom or missing element when a maintainer filed the issue or it carries
a newcomer label", lets expected behavior stay implicit where the symptom is plainly a
malfunction, and exempts an illustrative example list inside an otherwise bounded bug. On
run 5 the same issue passes, and the check now reports its reasoning as: "maintainer-filed
(COLLABORATOR) + 'good first issue' label; body 'Including remove identity, fuse spiders,
remove self loops, etc.' matches rubric's own non-open-ended illustrative-list example."

The identical defect had cost me `issue-19`, where the check fired because a maintainer
listed two suspected causes for a UI freeze. That thread has zero comments, so there was
never an unsettled design debate in it — only the maintainer's own diagnosis.

**Check rationale**

The check is `scope-bounded`, weighted `required`. Its pass condition, as currently
written in the `rubric.md` uploaded to `tools/issue-select/`:

> Pass only if the issue names ONE primary deliverable -- a single named artifact or behavior change (a page or file to add, a named function or line to fix, a described behavior to change) that one PR can finish -- and: (a) for a bug, the body identifies the current wrong behavior -- an error message, wrong output, a named file/line, or a named malfunctioning symptom or missing element when a maintainer filed the issue or it carries a newcomer label -- and the expected behavior, which may be left implicit where the symptom is plainly a malfunction (a crash, a freeze, or a missing element implies it should not crash, freeze, or be missing); (b) for a feature or docs change, the body or a maintainer comment names the specific change, AND the request is maintainer-endorsed (opened by a maintainer, OR carries a maintainer triage label such as good first issue / help wanted / an area or type label, OR a maintainer comment approves it). Several sub-items do NOT fail this check when every sub-item serves that one primary deliverable (e.g. add the new page, then update the existing pages that should point to it): grade the finish line, not the bullet count. Fail when the issue has no single finish line: a tracking/umbrella/"mega" issue whose body is mainly a list of other issue references; an open-ended or incremental invitation (the body invites many PRs, or asks for more of X across the codebase without naming which parts); a pure usage question; or a thread where a maintainer questioned WHAT the change should do or whether it belongs at all ("what should this do?", "not sure this belongs", a maintainer asking the reporter to justify or specify the target behavior) and no later maintainer comment settled it with a concrete decision, which a long thread or past abandoned attempts (closed unmerged PRs) confirm. A maintainer naming suspected causes, mechanisms, or implementation options for a symptom everyone agrees is wrong is diagnosis, not an unsettled spec: latitude in HOW to fix an agreed bug does not fail this check. An illustrative list of examples inside an otherwise bounded bug ("including A, B, C, etc.") is not open-ended. A short body is not a fail by itself: where a maintainer filed the issue or it carries a newcomer label, a maintainer has already judged its size, so grade the size of the work requested, not the polish of the writeup.

Every clause in it is there because a specific issue defeated a simpler version.

My first draft asked whether the issue "asks for ONE concrete change that a single PR can
deliver." On that wording the check rejected `issue-01` (conda/conda#16475) against a gold
`accept`, because that body lists five bullets — add a new task page, then update
`manage-pkgs.rst`, `pip-interoperability.rst`, `new-features.md`, and possibly
`troubleshooting.rst` — and five bullets read as an umbrella. Reading it against the two
gold `reject` umbrella issues showed the distinction I had missed. `issue-10` is a body of
roughly fifty bare issue references, each its own separate PR. `issue-05` says "PRs are
welcome both big and small" and asks for type annotations in "parts of the codebase where
it makes sense", naming no target at all. `issue-01` names one artifact — a new
"Installing PyPI packages with conda" page — and its other four bullets only update
existing pages to point at that page. The property separating them is not how many bullets
a body has but whether the work has a single finish line, so the check is now built around
"ONE primary deliverable", says explicitly that sub-items serving that deliverable do not
fail it ("grade the finish line, not the bullet count"), and names the two shapes that
genuinely have no finish line instead of gesturing at "umbrella".

The second revision came from `issue-04` and `issue-19`, above. It widened leg (a)'s
evidence list for triaged bugs, and it narrowed the unsettled-spec clause to a maintainer
questioning **what** the change should do or whether it belongs — adding that a maintainer
naming suspected causes or implementation options for an agreed symptom "is diagnosis, not
an unsettled spec: latitude in HOW to fix an agreed bug does not fail this check." That
narrowing is what lets `issue-19` through while `issue-15` still rejects, and on run 5 the
check's own words for `issue-15` were that a maintainer "noted Slack's updated
interactivity API differs from the legacy payload esamson demonstrated, and that
discrepancy was never settled with a concrete maintainer decision; confirmed by the
97-comment thread and two closed-unmerged linked PRs (#20840, #23123)."

**Trade-offs**

The check now grades boundedness and says nothing about difficulty, and `issue-19` is the
case where I can see the cost. It passes as one bounded symptom — the UI freezes when you
select large subgraphs — but the maintainer's own suggested fixes are multiprocessing,
selective matching, and moving rewrite application onto a separate thread. That is
concurrency work in a codebase I would be new to, and my rubric calls it a good first
issue because the *ask* is single, not because the *work* is small. I am keeping it that
way: "how long will this take me" is what the fit profile in `scope.md` is for, and
folding difficulty into a required check is how I would start rejecting sound issues for
being unfamiliar.

The second thing it gives up is deliberate. Leg (a)'s symptom path only opens "when a
maintainer filed the issue or it carries a newcomer label", so a one-line bug report from
an untriaged reporter with no labels still fails, even when the bug is real. I accept that
miss because in that case nothing has vouched for the size of the work, and the whole
point of the check is to stop me guessing.

Nothing else moved, and I checked rather than assumed. Before the confirming run I
re-ran `--only issue-01,issue-04,issue-05,issue-10,issue-15,issue-19,issue-20` — every
item in the set whose verdict depends on `scope-bounded` — using `issue-05`, `issue-10`,
`issue-15` and `issue-20` as canaries, since those are the four gold `reject` issues a
looser scope rule could have let through. That run returned 7/7 with all four canaries
still rejecting, and the full run afterwards confirmed it at `scope 4/4` and
`clear-accept 8/8`. Widening leg (a) was safe by construction as well: no gold `reject`
item in the set depends on leg (a) failing, because `issue-02`, `issue-07` and `issue-17`
reject on repo liveness, `issue-03`, `issue-08`, `issue-13` and `issue-18` on claims,
`issue-12` on the AI policy, and the remaining four on the umbrella and unsettled-spec
clauses I left in place.

---

## Selection rationale

**Selection rationale**

**1. Fit to my interests and to the time available.** #69 sits in the RAG subsystem
(`rag/generator/output_parser.py`), which is where I most want to improve. I have built
LLM and agent systems before — including a desktop app that runs coding agents in
parallel and parses their build and test output to hand failures back — but I built them
without much test discipline, and this repo is a FastAPI/SQLAlchemy/pytest codebase. The
bug itself is close to something I have already written by hand: parsing an LLM response
that does not come back in the shape you expected. So I am not learning the domain and
the tooling at the same time. It is labelled `tier-1` at an estimated 2–4 hours, and the
fix has a named file and a named `xfail` test (manifest H-02) to flip, which fits the
week I have before Unit 2 needs it reproduced.

**2. What the verdict identified correctly, and what I weighed that the rubric could
not.** The verdict was right that all five required checks pass on evidence rather than
on the friendly label: the repo is alive on human commits five days old, it is not
archived, `CONTRIBUTING.md` and the PR template state no AI policy at all so my
AI-assisted workflow is allowed, and the issue is one bounded change with a named file, a
named test, and a reproduced traceback. It also correctly applied the Path Review house
rule to `jacho15`'s claim comment instead of treating it as the blocker it would be on
real GitHub.

What the rubric could not weigh is how far along `jacho15` actually is. They did not just
claim the issue — they posted a specific diagnosis of the fall-through in
`parse_review_output` plus a full environment report, so someone is genuinely mid-fix. My
rubric has no check for another contributor's progress, and the house rule tells it not
to care. I chose #69 anyway because course credit attaches to the PR I open rather than
to whether it merges, and because #72 sits behind it as an equally clean fallback: all
five required checks pass, zero comments, and no open work in this repo.

**3. Anticipated difficulty in claiming it.** Low on mechanics, moderate on overlap. The
issue has no assignee and no open linked PR in this repo, so nothing procedural is in the
way, and the house rule means I do not need permission to work a shared issue. The real
difficulty is social rather than technical: `jacho15` has already published their reading
of the bug, so my claim comment in Unit 2 has to acknowledge that work honestly instead
of writing over it, and my PR has to stand on its own if theirs lands first. The fix is
small enough that the risk is duplicated effort, not the code.
