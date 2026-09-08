# Beeline 🐝 — notes for Claude sessions

## Commit identity — read this before committing

Work on this repo happens from Claude Code sessions. Commits must be **attributed
to the human whose session it is** while staying **signature-verified**.

GitHub attributes the **author** and verifies the **committer**. The session
container's SSH signing key belongs to `noreply@anthropic.com`, so these have to
be different people:

- Set the **author** to the human, with `git commit --author="..."`.
- Leave the **committer** alone — it stays `Claude <noreply@anthropic.com>`.

```bash
git commit --author="KRISHNA BHATNAGAR <186415037+kbhatnagar1506@users.noreply.github.com>" -m "..."
```

GitHub then shows *"KRISHNA BHATNAGAR authored, Claude committed"* — it counts on
the human's contribution graph and keeps the green **Verified** badge.

**Do not** set `user.email` / `user.name` to a human. That makes the *committer* a
human, the signature stops matching the registered key, and every commit shows as
**Unverified**. (A SessionStart hook resets the global identity each session, so
setting it globally doesn't stick anyway.)

| Person | Author string |
|---|---|
| Krishna | `KRISHNA BHATNAGAR <186415037+kbhatnagar1506@users.noreply.github.com>` |
| Aaditi | `Aaditi Singhal <112204267+aaditisinghal@users.noreply.github.com>` |

Commit as whoever's session this is. Never commit as the other person.

## Branches

`main` is protected — PRs only. Work on `krishna` or `aaditi`, or a topic branch
off your own (`krishna/nectar-ranking`). Never commit directly to `main`.

Full conventions in [CONTRIBUTING.md](CONTRIBUTING.md); decisions and their
reasoning in [docs/DECISIONS.md](docs/DECISIONS.md).
