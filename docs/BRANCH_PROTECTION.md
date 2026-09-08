# Protecting `main` 🔒

**Status: needs Aaditi (repo owner) to click this once. ~60 seconds.**

Everything else in this repo is set up. This is the one thing that requires repo-admin
rights, which only [@aaditisinghal](https://github.com/aaditisinghal) has — collaborators
with `push` access (including automation) cannot create protection rules.

The repo is **public**, so this is free. No paid plan needed.

---

## Do this

Go to **[Settings → Rules → Rulesets](https://github.com/aaditisinghal/Job-application-portal/settings/rules)**
→ **New ruleset** → **New branch ruleset**.

> Rulesets are the modern replacement for "Branch protection rules." If you'd rather use the
> old screen, the equivalent settings are listed at the bottom of this file.

### 1. Name and scope

| Field | Value |
|---|---|
| **Ruleset Name** | `protect-main` |
| **Enforcement status** | **Active** ← easy to miss, it defaults to Disabled |
| **Bypass list** | **Leave empty.** This is the whole point — no admin override, no "just this once." |
| **Target branches** | Add target → **Include default branch** |

### 2. Tick these rules

- [x] **Restrict deletions** — nobody can delete `main`
- [x] **Block force pushes** — nobody can rewrite `main`'s history
- [x] **Require a pull request before merging**
  - Required approvals: **1**
  - [x] **Dismiss stale pull request approvals when new commits are pushed**
  - [x] **Require review from Code Owners** *(uses our `.github/CODEOWNERS`)*
  - [x] **Require conversation resolution before merging**
  - Allowed merge methods: **Squash** only — keeps `main`'s history a clean list of changes
- [ ] **Require status checks to pass** — leave off until we actually have CI, then turn it on and add the checks

Leave the rest alone. Signed commits and linear history are nice later; they'll just annoy us now.

### 3. Create

Hit **Create**. Done.

---

## Confirm it worked

From any clone:

```bash
git checkout main
echo "test" >> README.md
git commit -am "test: this should be rejected"
git push origin main
```

You should get:

```
! [remote rejected] main -> main (protected branch hook declined)
```

Then undo the local test commit:

```bash
git reset --hard origin/main
```

If that push **succeeded**, the ruleset is either Disabled or has a bypass list. Go back and check both.

---

## While you're in Settings

Two more one-click things worth doing:

**Settings → Collaborators** — confirm [@kbhatnagar1506](https://github.com/kbhatnagar1506) has **Write** access.

**Settings → General → Pull Requests**
- [x] Allow squash merging *(only this one)*
- [ ] Allow merge commits — off
- [ ] Allow rebase merging — off
- [x] Automatically delete head branches — keeps the branch list from becoming a graveyard

Leave `krishna` and `aaditi` unprotected. They're personal workspaces; you should be able to
force-push your own branch when you make a mess.

---

## If you use the older "Branch protection rules" screen instead

**Settings → Branches → Add branch protection rule**, branch name pattern `main`:

- [x] Require a pull request before merging
  - [x] Require approvals — **1**
  - [x] Dismiss stale pull request approvals when new commits are pushed
  - [x] Require review from Code Owners
- [x] Require conversation resolution before merging
- [x] **Do not allow bypassing the above settings** ← without this, admins can push straight to `main` and the rule is decorative
- [ ] Allow force pushes — leave **off**
- [ ] Allow deletions — leave **off**
