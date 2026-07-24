# Setup Instructions

This repo is built for GitHub's special **profile README** feature, so it must live at:

```
https://github.com/Shiva134-ui/Shiva134-ui
```

(a public repo with the exact same name as your username). If you haven't created it yet: click **New repository** → name it `Shiva134-ui` → check **Public** → check **Add a README**, then replace its contents with the files here.

## 1. Push these files
```
git init
git remote add origin https://github.com/Shiva134-ui/Shiva134-ui.git
git checkout -b main
git add .
git commit -m "feat: premium animated DevOps profile"
git push -u origin main
```

## 2. Required repository secrets
Go to **Settings → Secrets and variables → Actions → New repository secret**:

| Secret | Used by | Where to get it |
|---|---|---|
| `METRICS_TOKEN` | `metrics.yml` | Create a fine-grained [Personal Access Token](https://github.com/settings/tokens) with `repo` + `read:user` scopes |
| `WAKATIME_API_KEY` | `waka.yml` | Free account at [wakatime.com](https://wakatime.com) → Settings → API Key. If you don't use WakaTime, delete `waka.yml` and the `<!--START_SECTION:waka-->` block in the README |

`GITHUB_TOKEN` is provided automatically by GitHub Actions — no setup needed.

## 3. Enable Actions
**Settings → Actions → General → Workflow permissions** → select **Read and write permissions**, then save.

## 4. Run workflows once manually
Go to the **Actions** tab → select each workflow (`Generate Contribution Snake`, `Generate Profile Metrics`, `Update WakaTime Coding Stats`, `Profile Auto-Refresh`) → **Run workflow**, so the first-generated assets exist before their schedules kick in.

## 5. Verify
- The snake animation pushes to an `output` branch automatically — you don't need to create it.
- `github-readme-stats`, `github-readme-streak-stats`, `github-profile-trophy`, and `skillicons.dev` are all free public services referenced live in the README — nothing to install.

Once secrets are set and workflows have run once, your profile is fully self-updating.
