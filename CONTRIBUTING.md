_👈 back to [README.md](./README.md)_

---

🙏 Thank you for your interest in contribution!

We ask that you please review these guidelines prior to making a PR. Otherwise there are no restrictions on who may contribute to the System.

Long term, Design System is intended to be maintained collaboratively by every engineer and designer at FireHydrant.

---

- [1. Branches](#1-branches)
- [2. Pull Requests](#2-pull-requests)
- [3. Publish](#3-publish)
- [4. Deploy](#4-deploy)
  - [4.1. Storybook](#41-storybook)
  - [4.2. Playroom](#42-playroom)

---

# 1. Branches

| Branch     | Type           | Notes                                                        |
| ---------- | -------------- | ------------------------------------------------------------ |
| `main`     | release        | **Avoid** pushing directly to this branch. Squash-merge PRs. |
| `gh-pages` | auto-generated | Deploys [Playroom ↗️][playroom] to GitHub pages              |
| `next`     | future work    | Reserved. Only work deemed "not for public"                  |

# 2. Pull Requests

Work should be done on branch names generated by Clubhouse (e.g. `<username>/<ch####>/<ticket-name>`).

Pull Requests should target `main` and be squash-merged.

1. File a ticket in [Clubhouse ↗️][clubhouse]
2. Obtain branch name via [Git Helper ↗️](https://help.clubhouse.io/hc/en-us/articles/207540323-Using-Branches-and-Pull-Requests-with-the-Clubhouse-VCS-Integrations)
3. Push to designated branch
4. Open Pull Request in GitHub (PR should target `main`)
5. Obtain necessary review(s)
6. Squash & Merge to `main`

# 3. Publish

1. bump the version in `package.json`
2. update [CHANGELOG.md](./CHANGELOG.md)

```bash
npm run build
npm publish --tag latest
```

# 4. Deploy

In addition to a semantic versioned package, this project also deploys two web applications automatically:

[![Storybook](https://raw.githubusercontent.com/storybooks/brand/master/badge/badge-storybook.svg)][storybook]
[![Playroom](https://img.shields.io/badge/playroom-live-000)][playroom]

## 4.1. [Storybook][storybook]

On push, every branch is configured to automatically build & deploy to [Chromatic ↗️][chromatic] via ["Chromatic" GitHub Workflow](./.github/workflows/chromatic.yml).

## 4.2. [Playroom][playroom]

On push to `main`, Playroom is automatically built to `docs/`, pushed to branch: `gh-pages`, and deployed to GitHub Pages via ["Build & Deploy Playroom" GitHub Workflow](./.github/workflows/playroom.yml).

---

[chromatic]: https://www.chromatic.com/builds?appId=607731addb01d30021caeac2
[clubhouse]: https://app.clubhouse.io/firehydrant/project/18818/design-system
[playroom]: https://firehydrant.github.io/design-system/
[storybook]: https://main--607731addb01d30021caeac2.chromatic.com/