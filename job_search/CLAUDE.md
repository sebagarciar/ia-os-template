# job_search: read before touching this project

CV and job applications. If a decision about this folder is written below, do not re-derive it.

- `master-cv.md`: the bullet bank. One line per bullet, tagged, metric-carrying, faithful to what
  was actually done. `tailor-cv` selects from it and never invents.
- `story-bank.md`: the situations behind the bullets. `interview-prep` reads and writes it.
  Numbers must match `master-cv.md` exactly. Nothing here goes on a CV.
- `answer-bank.md`: standard form answers and rules for text answers. Lines marked ASK have no
  confirmed answer: ask, then write it here.
- `tracker.md`: one row per application, newest first. Status `submitted` is set only when I say
  it went out. `built` never means sent.
- `applications/<company-slug>/`: one folder per application (CV pdf, `cv-content.json`,
  `job-description.md`, `notes.md`).
- `daily-scan/`: the job scan run by `find-jobs`. `profile.md` says what I look for,
  `watchlist.json` lists company job boards. Started by hand, never on a schedule.

## Verification rules (the ones that keep the CV honest)

1. **The bank is the only source of facts.** Every claim on a CV or in a form answer traces to a
   bullet in `master-cv.md` (or `story-bank.md` for interviews). Rephrasing is allowed. Facts,
   metrics, scope, titles and dates are not.
2. **Must-haves are checked before building.** If a must-have in the ad has no evidence in the
   bank, say so in two lines before any CV exists. It is a go/no-go and it is my call.
3. **Keyword coverage is checked by a script, not by eye.** `check_keywords.py` compares ad
   keywords with the draft. A miss with evidence in the bank is a selection decision. A miss with no
   evidence is a question for me. What I answer goes into the bank first, never straight into the CV.
4. **Five bullets per role, maximum.** If a role wants a sixth, the selection is not finished.
5. **No client names** on a CV. Describe by sector and size.
6. **Never overwrite an existing application folder.** A new version goes in `-v2`.
7. **Never submit.** The apply skill stops before the last click.

## Versioning

This folder holds personal data in real use. Keep your real copy in a private repo.
