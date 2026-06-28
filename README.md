# workflows

Kungfu reusable GitHub Actions workflows.

## v2 baseline

The v2 line is the modernized baseline for Kungfu v4 workflow work:

- Node.js defaults to 24.
- Ubuntu defaults to 24.04.
- first-party GitHub actions are pinned to current major versions.
- reusable workflows call `kungfu-systems/action-bump-version` v4 by default.
- Linux heavy builds are expected to use trusted self-hosted runner labels.
- Docker/container build paths are retired until the Docker mechanism is redesigned.
- legacy AirTable/Monday/release-note/extensions integrations are opt-in.
- legacy collaborator/dependency/auto-approval helpers are opt-in.
- legacy scheduled sync and purge jobs are retired by default and require manual
  `workflow_dispatch` confirmation.

The lightweight validation path should use `.release-verify.yml` with
`build-container-enabled: false` and explicit trusted runner labels. Fork pull
requests must not enter self-hosted build jobs.
