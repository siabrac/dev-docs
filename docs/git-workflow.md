# ⚙️ Git Workflow Guide (Local First + GitHub Flow)

This guide explains how we work with Git for development, feature work, and bug fixes.

---

## 🛠️ 1. Project Setup (Local → GitHub)

**Create project locally:**
```bash
mkdir my-project && cd my-project
git init
```

**Add initial files:**
```bash
touch README.md .gitignore
git add .
git commit -m "Initial commit"
```

**Create empty GitHub repo (no README, .gitignore):**
```bash
git remote add origin git@github.com:your-org/my-project.git
git branch -M main
git push -u origin main
```

---

## 🚀 2. Day-to-Day Development (GitHub Flow)

**Feature or fix something?**
```bash
git checkout -b feature/my-feature   # or fix/bug-description
```

**Do your work:**
```bash
git add .
git commit -m "feat: short summary"
git push -u origin feature/my-feature
```

**Open a Pull Request (PR):**
- Describe what changed
- Link to issue (if any)
- Mark ready when it’s clean and tested

**Merge PR to `main`:**
- Squash merge if appropriate
- Delete branch after merge

**Optional: Tag release**
```bash
git tag v1.2.0
git push --tags
```

---

## 📚 Branch Naming

| Type       | Prefix     | Example                   |
|------------|------------|---------------------------|
| Feature    | feature/   | feature/login-page        |
| Bugfix     | fix/       | fix/null-pointer-crash    |
| Hotfix     | hotfix/    | hotfix/production-crash   |
| Release    | release/   | release/1.2.0             |
| Experiment | exp/       | exp/new-layout            |

---

## 🧹 Tips

- Keep branches short-lived
- Rebase or pull `main` regularly:
  ```bash
  git checkout main && git pull
  git checkout feature/my-feature
  git rebase main
  ```
- Use meaningful commit messages (`feat:`, `fix:`, `refactor:`)
- Review your own PRs before asking others
- Keep `main` always deployable

---

## 🧠 Summary

- Start local -> push to empty GitHub repo
- Use short-lived branches -> PR -> merge to `main`
- Keep `main` clean, stable, and ready to ship
- Clear naming = less confusion
- Keep it simple, automate where possible
