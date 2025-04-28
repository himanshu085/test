
# Naming Conventions Documentation

## Author

| **Author** | **Created on** | **Version** | **Last updated by** | **Last Edited On** | **Level**          | **Reviewer**    |
|------------|----------------|-------------|---------------------|--------------------|--------------------|-----------------|
| Himanshu   | 2025-04-14      | 1.0         | Himanshu            | 2025-04-28         | Internal Reviewer  | Komal Jaiswal   |
| Himanshu   | 2025-04-14      | 1.0         | Himanshu            | 2025-04-28         | L0                 | Imran           |
| Himanshu   | 2025-04-14      | 1.0         | Himanshu            | 2025-04-28         | L1                 | Shashi          |
| Himanshu   | 2025-04-14      | 1.0         | Himanshu            | 2025-04-28         | L2                 | Mahesh Kumar    |

## Table of Contents

- [Introduction](#introduction)
- [Branch Naming Conventions](#branch-naming-conventions)
- [Tag Naming Conventions](#tag-naming-conventions)
- [Commit Message Conventions](#commit-message-conventions)
- [Benefits of Naming Conventions](#benefits-of-naming-conventions)
- [Conclusion](#conclusion)
- [Contacts](#contacts)
- [References](#references)

## Introduction

This documentation serves as a comprehensive guide to the naming conventions for branches, tags, and commit messages in our project. By following these conventions, the development team can maintain a consistent and organized workflow, improve clarity in code management, and enhance collaboration. Clear naming practices make it easier to understand the purpose of changes, streamline reviews, and ensure everyone is aligned throughout the development process.

## Branch Naming Conventions

Branches are used to encapsulate specific features, fixes, or other workstreams. Consistent branch naming makes it easier to understand the purpose and scope of each branch at a glance.

### General Structure

```
<type>/<ticket-number>-<short-description>
```

### Types

- feat: New features
- fix: Bug fixes
- chore: Maintenance or non-feature updates (e.g., refactoring, dependency updates)
- docs: Documentation updates
- test: Testing additions or updates
- hotfix: Critical fixes that need to be merged immediately

### Examples

- feat/1234-add-user-login
- fix/5678-fix-login-bug
- chore/91011-update-dependencies
- docs/1213-update-readme
- test/1415-add-login-tests
- hotfix/1617-fix-critical-login-issue

## Tag Naming Conventions

Tag naming conventions provide a standardized way to label specific points in a repository's history, typically following semantic versioning. Tags are primarily used to mark releases or milestones in the project.

### General Structure

```
v<major>.<minor>.<patch>
```

### Examples

- v1.0.0: Initial stable release
- v1.1.0: New feature added in a backwards-compatible manner
- v1.1.1: Bug fix in a backwards

## Commit Message Conventions

Commit messages are crucial for understanding the history and context of changes. A consistent format helps maintain clear project history and facilitates easier code reviews.

### General Structure

```
<type>(<scope>): <subject>

<body>

<footer>
```

| Section | Description |
|---------|-------------|
| Scope | Provides context about the section of the codebase affected by the change. Should align with the module or component being modified. |
| Subject | A concise summary of the change:<br>- Written in imperative, present tense: "change" not "changed" or "changes."<br>- No more than 50 characters long.<br>- Should not end with a period. |
| Body | Includes:<br>- A detailed explanation of what the commit does.<br>- The motivation for the change and its context.<br>- Any relevant information to help understand the change. |
| Footer | Contains:<br>- Information about breaking changes (e.g., "BREAKING CHANGE: type is removed").<br>- References to issues (e.g., "Closes #1234"). |

### Examples

```
feat(login): add login feature

Implement login functionality using OAuth2. This includes the creation of login page, integration with backend API, and unit tests.

Closes #1234
```

```
fix(auth): fix token refresh logic

Correct the token refresh mechanism to handle expired tokens properly. This ensures the application maintains session state correctly.

Closes #5678
```

```
docs: update contributing guidelines

Add more details about the branching and commit message conventions to the contributing guidelines to help new contributors.

Closes #91011
```

## Benefits of Naming Conventions

- Improved collaboration across teams.
- Simplified navigation in large repositories.
- Consistent CI/CD pipeline configurations.
- Enhanced readability and maintainability.

## Conclusion

In conclusion, Implementing branch access policies in the OT Microservice project ensures code quality, security, and efficient collaboration. By enforcing GitHub's branch protection rules, updates to critical branches like main require pull requests with tests and code reviews, preventing unauthorized changes and maintaining a clean codebase.

## Contacts

| Name              | Email Address                                   |
|-------------------|--------------------------------------------------|
| Himanshu Parashar | himanshu.parashar.snaatak@mygurukulam.co         |

## References

| Topic                | Link                                                                 | Description                                               |
|----------------------|----------------------------------------------------------------------|-----------------------------------------------------------|
| Naming Conventions Guide | [https://dev.to/shinjithdev/git-good-best-practices-for-branch-naming-and-commit-messages-oj4](https://dev.to/shinjithdev/git-good-best-practices-for-branch-naming-and-commit-messages-oj4) | This link explains the naming conventions. |
