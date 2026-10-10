# streak-bot

A tiny GitHub Actions workflow that makes one commit a day so the contribution graph stays green.

## How it works

`.github/workflows/daily-commit.yml` runs on GitHub's servers twice a day (10:17 and 18:43 UTC). It appends one line to `streak.log`, commits it as you, and pushes. If today's line is already there, the run exits without doing anything. You can also run it by hand from the **Actions** tab (**Run workflow**).

## Setup

1. Create a new repo on GitHub (any name, e.g. `streak-bot`). It must be **your own repo, not a fork**.
2. Add `.github/workflows/daily-commit.yml` and this README to it, and push to the default branch.
3. In the repo go to **Settings → Actions → General → Workflow permissions** and choose **Read and write permissions**.
4. Open the **Actions** tab, pick **Daily streak commit**, and click **Run workflow** once to test. A new `streak.log` should appear in the repo.

## Good to know

- Commits only count on the graph if they land on the repo's default branch.
- For a **private** repo, turn on **Profile → Contributions → Private contributions** (the dropdown above your graph) or the squares won't show.
- GitHub can pause scheduled workflows in repos with long inactivity. If you ever see a banner saying the workflow was disabled, click **Enable workflow** in the Actions tab.
