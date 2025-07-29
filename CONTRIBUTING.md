# Contribution Guidelines

Thank you for your interest in contributing to ClearURLs! To keep our codebase secure, maintainable, and reviewable, please follow these guidelines when submitting Merge/Pull Requests.

## Table of Contents

1. [Getting Started](#getting-started)
2. [Branching and Pull Requests](#branching-and-pull-requests)
3. [Modifying Rules](#modifying-rules)
4. [Adding New Rules](#adding-new-rules)
5. [Testing Your Changes](#testing-your-changes)
6. [Merge Request Size and Organization](#merge-request-size-and-organization)
7. [Commit Messages](#commit-messages)
8. [Security Considerations](#security-considerations)
9. [Review Process](#review-process)

---

## Getting Started

1. Fork the repository and create a new branch for your work.
2. Sync with the upstream `master` branch regularly to avoid merge conflicts:
   ```bash
   git fetch upstream
   git checkout master
   git merge upstream/master
   ```
3. Create a topic branch with a descriptive name:
   ```bash
   git checkout -b add-new-tracking-rule
   ```

## Branching and Pull Requests

- Use feature branches for each logical set of changes.
- Don’t work directly on `master`.
- Open a Merge Request (MR) / Pull Request (PR) against `master` when your feature branch is ready.

## Modifying Rules

> **Important:** Do **not** move, delete, or heavily modify existing rules in a single MR.

- Existing rules in `rules.json` and `rules.min.json` must remain untouched. This prevents accidental removals and helps reviewers focus on new content.
- If you need to refactor or clean up existing rules, create a dedicated MR for that purpose.

## Adding New Rules

1. **Append only:** Add new rules at the *end* of the file. Do not interleave with existing rules.
2. **Rule format:** Follow the JSON schema and naming conventions exactly. See also https://docs.clearurls.xyz/latest/specs/rules/
3. **Documentation:** For each new rule, include:
   - A short description of its purpose.
   - An example URL containing the tracking parameter(s) you intend to remove.
   - (Optional) A brief note on any edge cases or limitations.

## Merge Request Size and Organization

- **Keep MRs small and focused.** Aim for fewer than 200 lines of net additions per MR.
- **One topic per MR:** Group related rules together (e.g., all rules for a given domain).
- If you have a large number of rules to add, split them into multiple MRs.

## Commit Messages

- Write clear, imperative commit messages.
- Reference issue numbers when applicable: `Add rule for example.com (#123)`.

## Security Considerations

- ClearURLs is distributed as a browser extension and integrated into multiple applications, so any faulty or malicious rule could impact hundreds of thousands of users worldwide.
- **Avoid large, unreviewable diffs:** split your changes into focused MRs so reviewers can thoroughly inspect each rule and prevent potential security issues.

## Review Process

- After opening an MR / PR, it will be assigned to a maintainer for review.
- Respond promptly to review comments and clarify any questions.
- Once approved and all CI checks pass, your MR will be merged.

---

We appreciate your contributions and efforts to keep ClearURLs secure and efficient! If you have any questions, feel free to open an issue or ask in the discussion channels.

