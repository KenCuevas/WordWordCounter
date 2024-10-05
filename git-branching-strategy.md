# Git Branching Strategy

This document outlines the recommended branching strategy for managing our Git repository effectively. Following this strategy will ensure smooth collaboration, organized code management, and efficient delivery.

## 1. Main Branch (`main` or `master`)

- **Purpose**: Contains the stable, production-ready code. Every commit here should be fully tested and ready for deployment.
- **Best Practices**:
  - Protect this branch: No direct commits. Use pull requests for merging changes.
  - Only deployable code should be in this branch.

## 2. Development Branch (`develop`)

- **Purpose**: Contains the latest development version. This is where all new features are merged after testing.
- **Best Practices**:
  - Frequently merge feature branches to avoid large conflicts.
  - Run continuous integration (CI) tests on every push to ensure stability.

## 3. Feature Branches (`feature/{feature-name}`)

- **Purpose**: Each new feature or significant change should have its own branch. This allows for isolated work without affecting others.
- **Naming Convention**: Use descriptive names for feature branches, e.g., `feature/login-authentication` or `feature/ui-redesign`.
- **Life Cycle**: Create from `develop` and merge back when the feature is complete.
- **Best Practices**:
  - Keep changes atomic for easy code reviews and merges.
  
  ```bash
  # Example of creating a new feature branch
  git checkout develop
  git checkout -b feature/new-feature
  ```

## 4. Bugfix Branches (`bugfix/{bug-name}`)

- **Purpose**: Used to fix minor bugs not related to a new feature.
- **Life Cycle**: Created from `develop` or `main` depending on where the bug was found. Merged back into the same branch.
- **Best Practices**:
  - Focus only on solving the bug at hand.

## 5. Release Branches (`release/{version}`)

- **Purpose**: Used to finalize and prepare a new version for production. Minor fixes or final touches are applied here.
- **Life Cycle**: Created from `develop` and merged into both `main` and `develop` after the release.
- **Best Practices**:
  - Use this branch for regression testing and final adjustments before the release.
  
  ```bash
  # Example of creating a release branch
  git checkout develop
  git checkout -b release/v1.0.0
  ```

## 6. Hotfix Branches (`hotfix/{hotfix-name}`)

- **Purpose**: Created to address critical issues in production that need immediate fixes.
- **Life Cycle**: Created from `main`, then merged into both `main` and `develop` to ensure the fix is included in both.
- **Best Practices**:
  - Keep changes minimal and focused only on fixing the issue.

## 7. Pull Requests (PR) and Code Reviews

- Always use **pull requests** for merging branches into `develop` or `main`. This ensures that code is reviewed by at least one other developer, improving quality and catching potential issues early.

## 8. Commit Guidelines

- **Atomic Commits**: Each commit should focus on a single change or task, making it easier to understand and review.
- **Descriptive Commit Messages**: Write clear and concise messages explaining what has been done and why.

## Example Workflow

1. **Create a new feature branch from `develop`**:
    ```bash
    git checkout develop
    git checkout -b feature/new-feature
    ```

2. **Work on the feature and commit changes**:
    ```bash
    git add .
    git commit -m "Implemented new authentication feature"
    ```

3. **Open a pull request to merge into `develop`**:
    After completing the feature, open a pull request for code review and merge into the `develop` branch.
