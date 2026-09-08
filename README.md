<div align="center">

# 🐝 Beeline

**The shortest path to the right job.**

*A job-application agent built by two people who applied to a few hundred jobs, got bored out of their minds, and decided to automate the soul-destroying half.*

[![Status](https://img.shields.io/badge/status-early%20days-yellow)]()
[![Branch policy](https://img.shields.io/badge/main-PRs%20only-blue)]()
[![License](https://img.shields.io/badge/license-MIT-green)]()

</div>

---

## The problem

Getting the right job in front of the right person at the right time is absurdly hard — and almost none of that difficulty is about whether you can do the work.

Here's what the process actually looks like:

- You find a role you're good for **eleven days after** it was posted, when the shortlist is already drawn up.
- You paste the same work history into a fifth different applicant tracking system, because every company bought a different one.
- You rewrite the same cover letter for the twentieth time, changing one company name and pretending it's bespoke.
- You send it into a void. No reply. No rejection. Nothing you can learn from.
- You do this two hundred more times.

The bottleneck was never the candidate's ability. It's that job hunting is a **search, ranking and logistics problem** dressed up as a personality test — and it's being solved by hand, by exhausted people, at the exact moment in their life they have the least energy to spare.

We know because we did it. We applied to hundreds of jobs between us, got very bored, and realized we were doing badly at a task a machine should be doing for us.

So we're building the thing we wanted to exist while we were in the middle of it. For us first. For everyone else right after.

## What Beeline does

The goal: **you describe yourself once, and Beeline keeps working while you don't.**

| | |
|---|---|
| 🌸 **Forage** | Continuously pulls openings from job boards and company career pages, deduped and normalized into one clean feed. |
| 🍯 **Nectar** | Ranks every role against your actual profile — skills, trajectory, visa status, comp floor, how much you'd hate the commute. Not keyword matching. |
| ✍️ **Scribe** | Drafts a tailored resume and cover letter per role, from your real history. You approve; nothing goes out behind your back. |
| 🐝 **Waggle** | Submits and tracks the application, then watches for the reply so you're not refreshing your inbox at midnight. |
| 🏠 **Hive** | One dashboard: everything applied to, its stage, what's gone quiet, and what to do next. |

**Timing matters more than anything.** A great application on day 1 beats a perfect one on day 12. Speed is the feature.

### Non-negotiables

- **No lying.** Beeline never invents experience, degrees, or dates. It presents what's true, well.
- **Human in the loop.** Nothing is submitted without your say-so — at minimum a batch approval you actually saw.
- **Your data is yours.** Your history, your résumé, your rejections. Exportable, deletable, never sold.

## Why "Beeline"

A bee finds the thing, goes straight to it, and comes back to tell the hive exactly where it is. No wandering. That's the entire product in one animal.

It also gave us free names for everything, which is the real reason.

## How we work

Three branches, one rule.

| Branch | Who | What it's for |
|---|---|---|
| `main` | 🔒 nobody, directly | The truth. Always working. **Protected — pull requests only.** |
| `krishna` | Krishna | Krishna's working branch |
| `aaditi` | Aaditi | Aaditi's working branch |

**The rule: nothing reaches `main` except through a reviewed pull request.** No direct pushes, no force-pushes, no exceptions — the rule is enforced by GitHub, not by us remembering.

Day to day:

```bash
git checkout krishna          # or aaditi — your branch
git pull origin main          # start from current truth
# ...build something...
git commit -m "add nectar ranking v0"
git push -u origin krishna
# open a PR into main, get one approval, merge
```

For anything bigger than a quick fix, branch off your own branch (`krishna/nectar-ranking`) so a broken experiment never blocks you.

See [CONTRIBUTING.md](CONTRIBUTING.md) for the full flow and [docs/BRANCH_PROTECTION.md](docs/BRANCH_PROTECTION.md) for the exact settings guarding `main`.

## Roadmap

- [x] Repo, branch policy, and a README that explains why we bothered
- [ ] Pick the stack and get a skeleton app running
- [ ] Profile model — the "describe yourself once" schema
- [ ] Forage: first job-board ingestion, deduped
- [ ] Nectar: ranking that beats scrolling LinkedIn by hand
- [ ] Scribe: tailored resume + cover letter generation
- [ ] Hive: the dashboard
- [ ] Waggle: submission and reply tracking
- [ ] Use it on ourselves. Get jobs. Prove it works.

## The hive

| | |
|---|---|
| **Krishna** | [@kbhatnagar1506](https://github.com/kbhatnagar1506) |
| **Aaditi** | [@aaditisinghal](https://github.com/aaditisinghal) |

## Status

Very early. The repo is younger than most of our unanswered applications.

---

<div align="center">
<sub>Built out of spite, boredom, and roughly four hundred rejection emails. 🐝</sub>
</div>
