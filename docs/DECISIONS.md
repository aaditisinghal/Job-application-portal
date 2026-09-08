# Decisions

Short log of choices we made and why, so future-us doesn't relitigate them.

---

## 1. The project is called Beeline 🐝

*Decided: 2026-09-08*

A bee finds the thing, goes straight to it, and comes back to tell the hive exactly
where it is. That's the product in one animal.

It also named every subsystem for free — Forage, Nectar, Scribe, Waggle, Hive — which
matters more than it sounds: consistent vocabulary is the cheapest documentation there is.

Considered and rejected: *Otterview* (cute, but the pun locks us to interviews),
*Quokka* (adorable, says nothing about jobs), *Perch* (clean, already taken a few times over).

## 2. `main` is protected; everything lands via PR

*Decided: 2026-09-08*

Two people moving fast is exactly when a repo quietly breaks. One approval is cheap
insurance and forces us to read each other's code, which is how we stay able to work
on each other's files later.

Enforced by GitHub, not by memory — see [BRANCH_PROTECTION.md](BRANCH_PROTECTION.md).

## 3. Squash merges only

*Decided: 2026-09-08*

`main`'s history should read as a list of changes, not a list of keystrokes.
Personal branches can be as messy as we like.
