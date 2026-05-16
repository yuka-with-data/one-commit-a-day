# OSS Contribution Playbook 2026
A practical guide for understanding and contributing to open source repositories

## Why This Guide Exists
Every open source repository has its own:
- workflow
- tooling
- expectations
- hidden automation
- contribution culture

For beginners, these rules are often scattered across:
- README files
- CONTRIBUTING.md
- GitHub Actions workflows
- `pre-commit` configulations
- issue templates
- PR templates

This guide organizes the common patterns and modern OSS contribution practices into a reusable workflow.

## Universal OSS Contribution Structure
### 1. Understand the Project
Before contributing:
- Read the README carefully
- Understand the project's purpose
- Identify the main tech stack
- Explore open issues and discussions
- Observe recent commits and pull requests

Questions to ask:
- Is the project active?
- What type of contributions are welcomed?
- Is the maintainer responsive?
- Is the project beginner-friendly?

### 2. Locate Contribution Rules
Most OSS repositories store important rules in multiple places.

Common files and directories to inspect:
```txt
README.md
CONTRIBUTING.md
.github/
LICENSE
CODEOWNERS
```
Inside `.github/`, check for:
- issue templates
- pull request templates
- GitHub Actions workflows

These files often reveal the real contribution expectations.

### Setup the Local Development Environment
Typical setup steps:
1. Fork the official repository
2. Clone your fork locally
3. Add the upstream remote
4. Install dependencies
5. Run the project locally
6. Run tests before making changes

Common environment-related files:
```txt
requirements.txt
pyproject.toml
package.json
Makefile
docker-compose.yml
.pre-commit-config.yaml
```

## Understanding Hidden OSS Rules
Many important repository rules are not explained directly in the `README`.

### CI/CD (Continuous Integration/Continuous Delivery) Workflows
Check:
```txt
.github/workflows/
```
These workflows may enforce:
- formatting
- linting
- tests
- type checking
- branch validation
- PR title conventions

Sometimes CI errors themselves become the best documentation.

### Pre-Commit Hooks
Some repositories use:
```txt
.pre-commit-config.yaml
```
This file defines automated checks that run locally before a commit is created.

The goal is to:
- catch problems early
- enforce consistent formatting
- reduce CI failures
- maintain code quality across contributors

Common tools executed through pre-commit include:
- black
- ruff
- flake8
- prettier
- eslint
- mypy

Typical workflow:
```txt
git commit
    ↓
pre-commit hooks run automatically
    ↓
checks pass or fail locally
```
**This is different from GitHub Actions or CI pipelines.**
- `pre-commit` runs locally on the contributor's machine
- CI workflows run remotely on GitHub after code is pushed

Many modern OSS repositories use both systems together.

Recommended practice:
- install `pre-commit` if the repository uses it
- run hooks locally before pushing changes
- treat `pre-commit` failures as helpful feedback, not errors to fear

### PR and Commit Expectations
Some repositories require:
- Conventional Commits
- linked issues
- small PR sizes
- screenshots
- changelog updates

Always inspect:
- previous merged PRs
- PR templates
- contribution guidelines

## Recommended First Contributions
Good beginner contributions:
- typo fixes
- documentation improvements
- examples
- small bug fixes
- test improvements

Helpful issue labels:
- `good first issue`
- `help wanted`
- `documentation`