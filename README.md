# JLESC2026.github.io

The website and short-link host for the [IT Tech Support Tool Kit](https://github.com/JLESC2026/IT-Tech-Support-Tool-Kit).

## What is in this repository

| File | Source | Purpose |
|---|---|---|
| `index.html`, `404.html` | Edited here | Landing page and not-found page |
| `toolkit`, `assess`, `install` | **Published automatically** from the main repository (`toolkit`, `assess`, `Install.ps1`) | Short-link launchers used from PowerShell |
| `manifest.json`, `version.json` | **Published automatically** by the Release workflow | Release file URLs and SHA-256 hashes the launchers verify; latest version shown on the landing page |
| `.nojekyll` | Edited here | Makes GitHub Pages serve the files as they are |

**Do not edit `toolkit`, `assess`, `install`, `manifest.json` or `version.json` by hand.** The next release overwrites them. Change the launchers in the main repository and publish a release.

## How a release reaches this site

Pushing a `v*` tag in the main repository runs its **Release** workflow (`.github/workflows/release.yml`). It builds the release files, attaches them to a GitHub release, and commits the launchers and the new `manifest.json` / `version.json` here. The workflow needs a secret named `PAGES_DEPLOY_TOKEN` in the main repository: a fine-grained personal access token limited to this repository with "Contents: Read and write".

## GitHub Pages settings

Pages should be set to deploy from the `main` branch, `/ (root)` folder (Settings > Pages). Those settings are not stored in this repository, so check them there.

## Rolling back

Run the Release workflow manually in the main repository with an older tag. It republishes that release's manifest and launchers.

