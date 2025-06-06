# Feature Branch Flow

| **Author** | **Created on** | **Version** | **Last updated by** | **Last Edited On** | **Level**          | **Reviewer**    |
|------------|----------------|-------------|---------------------|--------------------|--------------------|-----------------|
| Himanshu   | 2025-04-14      | 1.0         | Himanshu            | 2025-04-29         | Internal Reviewer  | Komal Jaiswal   |
| Himanshu   | 2025-04-14      | 1.0         | Himanshu            | 2025-04-29         | L0                 | Imran           |
| Himanshu   | 2025-04-14      | 1.0         | Himanshu            | 2025-04-29         | L1                 | Shashi          |
| Himanshu   | 2025-04-14      | 1.0         | Himanshu            | 2025-04-29         | L2                 | Mahesh Kumar    |


## Table of Contents

- [Introduction](#introduction)
- [Why Use Feature Branch Flow](#why-use-feature-branch-flow)
- [Feature Branch Workflow](#feature-branch-workflow)
- [Key Features](#key-features)
- [Pull Requests (PRs)](#pull-requests-prs)
- [Versioning in Feature Flow](#versioning-in-feature-flow)
- [Advantages and Disadvantages](#advantages-and-disadvantages)
- [Conclusion](#conclusion)
- [Contacts](#contacts)
- [GitHub](#github)
- [References](#references)

## Introduction
Feature Branch Flow is a streamlined Git workflow where each feature is developed in an isolated branch. This ensures a clean main branch, organized development, and efficient collaboration.

## Why Use Feature Branch Flow

- **Isolated Development**: Each feature is developed in its own branch.
- **Parallel Workflows**: Multiple developers can work on different features simultaneously.
- **Stable `main` Branch**: Ensures production remains stable by merging only tested features.
- **Easy Rollback**: If a feature is not ready, its branch can be discarded without affecting others.
- **Better Collaboration**: Encourages code reviews via pull requests before merging.

## Feature Branch Workflow

![image](https://media.geeksforgeeks.org/wp-content/uploads/20240226111114/image-257.webp)


| **Branch**      | **Purpose**                                              | **Origin** | **Merge Into** |
|---------------|--------------------------------------------------|------------|--------------|
| `main`       | Production-ready branch with stable releases.   | ----       | ----         |
| `develop`    | Integration branch for testing new features.     | `main`     | `main`       |
| `feature/*`  | Individual feature development branches.         | `develop`  | `develop`    |



## Key Features

| **Feature**                | **Description**                                      |
|---------------------------|--------------------------------------------------|
| Isolated Development      | Each feature has a separate branch.               |
| Parallel Workflows        | Developers can work on multiple features at once. |
| Code Review & Collaboration | Uses PRs for reviewing and improving code.       |
| Stability Assurance       | Only tested features get merged into `develop`.    |
| Rollback Capability      | Features can be discarded before merging.         |

## Pull Requests (PRs)
Pull Requests (PRs) allow developers to propose, review, and merge changes from a feature branch to `develop`. This ensures better collaboration and code quality before integrating new features.

[ Raise a Pull Request (PR) on GitHub?]

## Versioning in Feature Flow
Versioning is managed by tagging commits when a feature is completed and merged. Example: `v1.1.0-featureX`.

## Advantages and Disadvantages

### Advantages

| **Advantage**             | **Description**                                  |
|---------------------------|------------------------------------------------|
| Organized Development    | Features are tracked separately.                |
| Stable `main` Branch     | Only tested code gets merged.                    |
| Supports CI/CD           | Works well with automated pipelines.            |
| Better Collaboration     | Code reviews improve quality.                   |

### Disadvantages

| **Disadvantage**          | **Description**                                  |
|---------------------------|------------------------------------------------|
| Increased Merge Conflicts | More branches mean more potential conflicts.   |
| Requires Discipline      | Developers must follow workflow properly.       |
| Overhead for Small Projects | Might be unnecessary for minor changes.       |

## Conclusion
Feature Branch Flow is a great workflow for managing isolated feature development, maintaining a stable `main` branch, and enabling smooth collaboration.

## Contacts

| Name              | Email Address                                   |
|-------------------|--------------------------------------------------|
| Himanshu Parashar | himanshu.parashar.snaatak@mygurukulam.co         |


## References

| **Resource**           | **Description**                      | **Link**  |
|------------------------|------------------------------------|---------|
| Git Feature Flow Docs  | Official documentation on feature branches | [Git Flow](https://nvie.com/posts/a-successful-git-branching-model/) |
| GitHub Documentation   | Official GitHub guide on branches  | [GitHub Docs](https://docs.github.com/en/github) |
