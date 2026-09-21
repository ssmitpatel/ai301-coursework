# Scope: where to look, and who is looking

<!--
This file is the skill's field of view. The rubric (rubric.md) decides
whether an issue is GOOD; the scope decides which issues are candidates
at all, and whose hands the issue would land in. It applies in live mode
only: in eval mode the bundle is the whole world and this file is
ignored.

Two parts. Staff wrote the first; you write the second.
-->

## Where candidates come from

Only issues in the course's Path Review repository are candidates:

- Repo: `codepath/pathreview-ai301-fa26-s1`

Do not search, fetch, or grade issues from any other repository, however
promising. The wider GitHub comes later in the course; for now the field
is Path Review.

**Path Review house rule.** Path Review is a classroom, and your
classmates are not strangers. Ignore the usual claim signals here: other
students' claim comments (and there may be several on one issue) do not
block an issue, and finding some on the issue you want is normal. Claim
anyway: course credit attaches to the pull request you open, not to
whether it merges, so a shared issue costs nobody anything. Everything
else in the rubric applies as written.

## Your fit profile

<!-- YOU write this part: a few sentences about you. What languages and
tools you have actually used, what you want to get better at, anything
you want to avoid. The skill uses this only to RANK the issues your
rubric accepts, never to change a verdict: fit cannot rescue an issue
your rubric rejects, and cannot sink one it accepts. -->

I am an MS Computer Science student with about two years of professional and
freelance experience building web applications. I am strongest in TypeScript and
JavaScript with React and Next.js -- that is the stack I could debug unaided. I
use Python comfortably for data and ML work (SQL and pandas pipelines, PyTorch)
and am fluent enough to work in a FastAPI / SQLAlchemy / pytest codebase. I have
recent hands-on experience with LLM and agent systems: I built a desktop app that
runs multiple coding agents in parallel, parses their build and test output, and
feeds failures back to the agent, and an on-device meeting assistant that streams
audio into a local Whisper model and queries an LLM over the live transcript. I
also did a security internship doing vulnerability assessment, fixing SQL
injection and XSS, and hardening login flows. Working knowledge of Rust, Java,
C++, C#, SQL, Docker, and Postgres/SQLite.

What I want to get better at: Python backend work in a production-shaped codebase
(FastAPI, SQLAlchemy, pytest), and the retrieval and evaluation side of RAG
systems -- chunking, ranking, and faithfulness checking -- since I built my own
LLM projects without much test discipline.

What I would rather avoid: heavy DevOps, CI, and infrastructure configuration
(deployment pipelines, Kubernetes), and large frontend redesign or visual-design
work. I would rather take a bug with a named file and a failing test than an
open-ended feature with a product decision still inside it.
