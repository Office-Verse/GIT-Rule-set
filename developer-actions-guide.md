# ⚙️ Developer Guide: Working with GitHub Actions in This Project

This guide explains how to interact with GitHub Actions when working on this project — including pull requests, reviewing workflows, debugging failed jobs, and common best practices.

---

## 🚀 1. What Triggers GitHub Actions in This Project?

GitHub Actions will automatically run when:

- You **push** commits to `main` or a feature branch  
- You **open**, **update**, or **reopen** a Pull Request (PR)  
- You **merge** a PR into the main branch  

Workflows run automatically — no manual trigger needed.

---

## 🔍 2. Where to View Workflow Results

1. Go to the repository.  
2. Click on the **"Actions"** tab.  
3. Click on the latest workflow to view logs and job results.  
4. For a specific PR, you can also view checks under the **"Checks"** tab in the PR view.

---

## ❌ 3. If a Workflow Fails

If a GitHub Actions job fails:

1. Open the **"Actions"** tab or the PR's **"Checks"** tab.  
2. Click on the failed job.  
3. Read the logs under each step to identify the issue.  
4. Fix the issue in your local branch.  
5. Push the updated code to the same branch — the workflow will rerun automatically.

---

## 🔁 4. Rerunning Workflows

If you want to rerun a failed workflow manually:

- Go to **Actions → Select the workflow → Click "Re-run jobs"** (if enabled).  
- Or, make a small commit or amend and push:

  ```bash
  git commit --amend
  git push --force
  ```

---

## ✅ 5. PR Review & Merge Rules

- Your Pull Request must **pass all required checks** (e.g., linting, tests).  
- At least **2 reviewers must approve** before merging.  
- Once checks pass and approvals are in, the **"Merge"** button will be enabled.

---

## 🔐 6. Secrets & Sensitive Data

- API keys or tokens are managed securely via GitHub **Secrets**.  
- Never hardcode secrets in code or `.env` files.  
- If you need access to a secret variable in a workflow, ask a maintainer.

---

## 💡 7. Best Practices for Developers

- Run linting/tests locally before pushing:

  ```bash
  flake8 .        # Python linting
  npm run lint    # Node/React linting
  npm test        # or pytest / other test framework
  ```

- Use meaningful commit messages.  
- Don't push directly to `main` — always use a feature branch and Pull Request.  
- Keep PRs focused and small when possible.

---

## 📚 8. Helpful Links

- [GitHub Actions Overview](https://docs.github.com/en/actions)  
- [Workflow Logs & Debugging](https://docs.github.com/en/actions/monitoring-and-troubleshooting-workflows)
