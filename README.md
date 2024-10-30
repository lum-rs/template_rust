<p align="center">
  <img src="image" width="512">
</p>

# Project

Project description

## Collaborating

Check out [Milestones](milestone), [Board](project), and [Issues](issues)

## TODO

1. Manually run "Build and test" GitHub Action
2. Adapt repo settings (See manual steps below)
3. Adapt README.md
4. Adapt LICENSE
5. Adapt Cargo.toml: Name, Author, Description, Repository, Keywords

## Manual steps

- Turn off Wikis
- Only allow squash merging (Pull request title and commit details)
- Always suggest updating pull request branches
- Allow auto-merge
- Automatically delete head branches
- Include Git LFS objects in archives
- Rulesets:
  - Default branch:
    - Enforce: Active
    - Bypass: Organization Admin, Repo Admin, Maintain Role, Dependabot
    - Target: Default branch
    - Restrict deletions
    - Require linear history
    - Require signed commits
    - Require pull request before merging
      - Required approvals: 1
      - Dismiss stale pull request approvals when new commits are pushed
      - Require conversation resolution before merging
      - Request pull request review from Copilot
    - Require status checks to pass:
      - Require branches to be up to date before merging
      - Do not require status checks on creation
      - Build and test (ubuntu)
      - Build and test (windows)
      - Build and test (macos)
      - Block force push
  - Release branches:
    - Enforce: Active
    - Target: release/\*\*
    - Restrict updates
    - Restrict deletions
    - Require linear history
    - Require signed commits
    - Require pull request before merging
      - Required approvals: 1
      - Dismiss stale pull request approvals when new commits are pushed
      - Require conversation resolution before merging
      - Request pull request review from Copilot
    - Require status checks to pass:
      - Require branches to be up to date before merging
      - Do not require status checks on creation
      - Build and test (ubuntu)
      - Build and test (windows)
      - Build and test (macos)
      - Block force push
- Environments: (Can be ignored, will be automatically created by CI/CD jobs)
  - CRATES_IO
  - GITHUB_RELEASE
  - GITHUB_PRE_RELEASE
