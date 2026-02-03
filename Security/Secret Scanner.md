
# (Draft) Secret Scanner

A Secret Scanner is critical part of your DevSecOps (Development, Security, Operations) strategy. it is an automated tool that detects hardcoded sensitive data (like API keys, passwords, tokens) in code, repositories, and infrastructure.  The goal is to prevent accidental leaks, stopping secrets from reaching production, and improving overall application security by integrating into the CI/CD pipeline to find and remediate them early. 

**Examples of Tools:**

- [GitHub Secret Scanning](https://docs.github.com/en/code-security/secret-scanning/introduction/about-secret-scanning): Built-in for public repos, mandatory for advanced security on private ones.
- [Datadog Secret Scanning](https://www.datadoghq.com/product/sensitive-data-scanner/): Part of a broader code security platform.
- [Git-secrets](https://github.com/awslabs/git-secrets): A command-line tool for scanning commits and pushes.

A Secret Scanner acts as a critical security layer, scanning commits, branches, and full history to block unauthorized access and breaches before they happen, ensuring secrets are managed and rotated effectively.

## GitHub Secret Scanning

This feature is built into public repositories by default.

![Screenshot of GitHub configuration](screenshot-github-secret-scanning.png)

## Pre-Commit Hook

GitHub's native secret scanning runs on the server side.  Another tool will need to be used to detect a secret before the sensitive information is part of a `push` command, which is used to upload your local commits to a remote repository (e.g., GitHub, GitLab). You can review open source tool like [git-secrets](https://github.com/awslabs/git-secrets),  [detect-secrets](https://github.com/Yelp/detect-secrets) or [Gitleaks](https://gitleaks.io/).

A pre-commit hook runs locally before a commit is finalized, allowing it to scan the changes and block the commit if a secret is found, preventing it from ever reaching the remote repository.

- `pre-commit` runs _before_ any commit (standard or merge) to check changes,
- `pre-merge-commit` runs _only_ after a successful, automatic merge (no conflicts) but _before_ Git creates the final merge commit




## Online Resources

These are additional resource that you can reference to learn more about this topic:

 - Matthew Hudson, "Git Hooks", https://githooks.com/.
 - Ketan Pradhan, "Secure Your Git Repository with Gitleaks and Pre-commit Hooks", August 26, 2023, https://medium.com/@ketanpradhan/secure-your-git-repository-with-gitleaks-and-pre-commit-hooks-5f37bb03429b.

