## Who I am

@context/about-me.md

## Read when the task needs it

These files do not load on their own. Read the one that matches before you start.

- When I correct you, or on `/wrap-up`: `context/lesson-routing.md` (where the lesson goes).
- Before writing anything in my name: `context/writing_style.md` (the `write-as-me` skill loads it).

## Folders

- `context/`: who I am and how I sound.
- `job_search/`: CV bank, applications, tracker, daily job scan. Has its own `CLAUDE.md`.
- `examples/`: one fictional application, end to end, so you can see what the skills produce.

Each folder's rules are in its own single `CLAUDE.md`.

## Job skills from a root session

Folder skills only load when the session starts in that folder. From a root session: when I paste a
job ad and want to apply, read `job_search/.claude/skills/apply/SKILL.md` first (it runs
`tailor-cv` inside it); when I mention an interview, read
`job_search/.claude/skills/interview-prep/SKILL.md`; when I ask for today's new jobs, read
`job_search/.claude/skills/find-jobs/SKILL.md`. Run scripts from the repo root.

## How I like to work

1. **Plan first.** For anything bigger than a quick fix, show me a short plan before you build.
2. **Prove it works.** Never tell me something is done without showing me it working.
3. **Do it properly.** If a fix feels hacky, redo it the right way. Finish the whole job.
4. **Plain English.** Short sentences, one idea each, common words.
5. **Keep it tidy.** Every project lives in its own folder.

## Memory: you get smarter every week

@MEMORY.md

When I correct you, write the lesson down as a new rule. Where it goes is decided by
`context/lesson-routing.md`. Check `MEMORY.md` and `context/writing_style.md` before every task.
