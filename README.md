# ia-os-template

A personal operating system for [Claude Code](https://claude.com/claude-code), built around a job
search. Skills do the repeatable work. A memory file turns each correction into a rule. A
verification layer keeps every CV claim tied to a fact bank.

This is a clean template of the system I use every day. All personal data is replaced by a
fictional person (Alex Example). It is shared as-is.

## How it fits together

```
  job ad ──> apply ──> go/no-go ──> tailor-cv ──> form answers ──> tracker row
                          │              │               │
                          │      check_keywords.py       │
                          ▼              ▼               ▼
                    master-cv.md  (the only source of facts)
                          ▲
  interview-prep ─────────┘      find-jobs ──> ranked HTML report ──> apply

  you correct Claude ──> wrap-up ──> MEMORY.md / writing_style.md / a SKILL.md
```

## The pieces

| Piece | What it does |
|---|---|
| `job_search/.claude/skills/apply` | Job ad in: go/no-go, tailored CV, form answers, tracker row, optional form fill in Chrome. Stops before Submit. |
| `job_search/.claude/skills/tailor-cv` | Picks bullets from the bank for one ad and renders a one-page ATS-safe PDF. |
| `job_search/.claude/skills/find-jobs` | Collects jobs posted in the last 24 hours, ranks them against your CV, builds an HTML report. Runs by hand, never on a schedule. |
| `job_search/.claude/skills/interview-prep` | Researches a company, writes a stage-by-stage brief, runs a mock. |
| `.claude/skills/wrap-up` | Reviews a session for lessons and proposes them one by one. Writes only what you approve. |
| `.claude/skills/write-as-me` | Loads your writing style before anything goes out in your name. |
| `.claude/skills/business-case` | Case brief in, one deck and one model out, with a review checklist. |
| `CLAUDE.md`, `MEMORY.md`, `context/` | The rules Claude loads every session, and where each new lesson is filed. |

## Design choices

- **The bank is the only source of facts.** `master-cv.md` holds one tagged line per achievement.
  Skills select and rephrase. They never invent a number, title or date.
- **Verification is a script, not a promise.** `check_keywords.py` compares the ad's keywords
  with the draft and splits the misses: "evidence in the bank" is a selection decision, "no
  evidence" is a question for the human. The answer goes into the bank first.
- **Must-haves are checked before any CV is built.** A missing must-have is a go/no-go, raised
  in two lines, and it is the human's call.
- **The human presses the last button.** No skill submits, sends or publishes.
- **Memory with a routing table.** Every correction becomes a rule, and `lesson-routing.md`
  decides whether it goes in memory, a style guide, a folder's rules or a skill.
- **A button or a command, never a scheduler.** Personal tools run when you start them.

## Try it

1. Install Claude Code and open this folder.
2. Read `examples/applications/acme-ops-manager/`: one fictional application end to end, with
   the CV PDF the scripts produced.
3. Replace `context/about-me.md`, `job_search/master-cv.md` and `job_search/answer-bank.md`
   with your own facts. Keep the real copy in a private repo.
4. Paste a job ad and say "apply to this".

The PDF builder needs Python 3 and Google Chrome (it prints the PDF through headless Chrome). The
Chrome path is set at the top of `job_search/.claude/skills/tailor-cv/scripts/build_cv.py`.

To use another city, edit the city lists at the top of
`job_search/.claude/skills/find-jobs/scripts/scan.py` and the city strings in `sources.py`.

More at my site, `sebasgarcia.dev`.
