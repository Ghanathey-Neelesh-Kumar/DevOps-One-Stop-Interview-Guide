# Difference Between `git fetch` and `git pull`

## 🧩 Core Difference

| Command | What it Does | Merges into Local Branch? |
|----------|---------------|---------------------------|
| **`git fetch`** | Downloads (fetches) the latest changes from the remote repository (like *origin*) — but does **not** change your working directory or local branches. | ❌ No |
| **`git pull`** | Does a **fetch + merge (or rebase)** — it downloads the changes **and** immediately merges them into your current branch. | ✅ Yes |

---

## 🔍 Example

Say you’re on the `main` branch, and your teammate pushed new commits to the remote `main` branch.

- `git fetch origin main` → brings those new commits into your local Git history (remote-tracking branch `origin/main`), but your local `main` stays the same.  
- `git pull origin main` → does the same **fetch**, then merges those changes into your local `main`.

---

## 🧠 When to Use Each

| Use Case | Recommended Command | Why |
|-----------|--------------------|-----|
| You want to **see what others have changed** before merging | `git fetch` | Keeps your branch clean; lets you review or diff before merging. |
| You’re ready to **update your local branch** with remote changes | `git pull` | Automatically fetches and merges for you. |
| In CI/CD or automated scripts | Usually `git fetch` | Avoids merge conflicts during automation. |
| When working on shared branches (like `main` or `develop`) | Start with `git fetch` + `git diff` | Safer to inspect before pulling. |

---

## 💡 Tip

If you prefer a linear history (no merge commits), you can use:

```bash
git pull --rebase
