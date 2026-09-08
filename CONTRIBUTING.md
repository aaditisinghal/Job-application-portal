# Contributing to Beeline 🐝

Two people, three branches, one rule. Keep it that simple for as long as we can.

## The one rule

**`main` is protected. Nothing lands there except through a pull request that someone approved.**

No direct pushes. No force-pushes. No "it's just a typo, I'll push it quick." GitHub enforces this, so it isn't a matter of discipline — the push will simply be rejected.

## Branches

| Branch | Purpose |
|---|---|
| `main` | Always working, always deployable. Protected. |
| `krishna` | Krishna's working branch |
| `aaditi` | Aaditi's working branch |

Working on something that'll take more than a day, or might break? Branch off your own branch:

```
krishna/nectar-ranking
aaditi/hive-dashboard
```

Naming: `<yourname>/<short-kebab-description>`.

## The flow

```bash
# 1. Start from current truth
git checkout krishna
git fetch origin
git merge origin/main

# 2. Build

# 3. Commit in small, readable pieces
git commit -m "nectar: rank by seniority delta, not title string"

# 4. Push
git push -u origin krishna

# 5. Open a PR into main. Get an approval. Merge.
```

## Commit messages

Present tense, lowercase, say what changed and why if it isn't obvious:

```
forage: dedupe postings by company + normalized title
scribe: stop hallucinating dates when the resume has gaps
fix: hive crashed on an empty application list
```

Not `update`, `fixes`, `wip`, or `asdf`.

## Pull requests

- **Small.** A PR you can read in ten minutes gets reviewed today. A 2,000-line PR gets reviewed "soon."
- **Explain the why.** The diff shows what changed; the description explains why it needed to.
- **Self-review first.** Read your own diff on GitHub before asking anyone else to. You'll catch the leftover `console.log`.
- **One approval to merge.** We're two people — that means the other one.
- **Stale approvals die.** Push new commits and the approval resets. That's on purpose.
- **Squash on merge** so `main` reads as a list of changes, not a list of keystrokes.

## Reviewing

Review the same day if you can. Being blocked on a review is the most demoralizing state in a two-person project.

Say what kind of comment you're making, so nobody guesses:

- **blocking:** this is wrong and must change before merge
- **suggestion:** I'd do it differently, your call
- **nit:** cosmetic, ignore me freely
- **question:** genuinely asking, not disguised criticism

Approve when it's better than what's on `main`. Not when it's perfect — perfect never merges.

## Things we don't do

- Commit secrets, `.env` files, API keys, or résumés with real personal data. Check `git diff --staged` before every commit.
- Force-push to a branch someone else is working on.
- Merge your own PR without a review, no matter how small.
- Ship anything that lies on a user's behalf. See the non-negotiables in the [README](README.md).
