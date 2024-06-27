# Git Workflow for CITE

Before development, CITE members and contributors must read this document outlining the **Git Workflow for CITE**. 

The process works in 7 steps:
1. [Create a GitHub Issue](https://github.com/USC-CITE/.github/blob/main/how_to_create_an_issue.md). 
2. Create a `git branch` to address the issue.
3. `git commit` changes to branch.
4. `git push` branch to remote repository.
5. [Create a pull request](https://github.com/USC-CITE/.github/blob/main/how_to_submit_a_pull_request.md).
6. Have your pull request reviewed and tested.
7. Approve pull request for merging to `main` branch. 

> [!NOTE]
> CITE members who are assigned tasks (which are under a project) within Notion can ignore the first step.

## Table of contents

-   [How does CITE name branches?](#how-does-cite-name-branches)
-   [How does CITE name commits?](#how-does-cite-name-commits)
-   [References](#references)

## How does CITE name branches?

```bash
git branch feature/issue-1/add-home-page
git branch bugfix/no-ref/improve-about-page-responsiveness
git branch hotfix/issue-342/button-overlap-form-on-mobile
git branch test/no-ref/refactor-components-with-atomic-design
```

Dissecting the commands above, the format goes as:

```bash
git branch [category]/[issue-reference]/[description]
```

### Branch Category

A git branch should start with a category. Choosing one depends on the issue you are trying to address. 

CITE pinpointed 5 categories you can use:

- `feature` is for adding, modifying, or removing a feature
- `bugfix` is for fixing a bug
- `refactor` is for refactoring a feature or documentation
- `hotfix` is for changing code with a temporary solution and/or without following the usual process (usually because of an emergency)
- `test` is for experimenting outside of an issue

### Branch Issue Reference

After the category, there should be a *"/"* followed by the reference of the GitHub issue you are working on. If there's no reference, just add `no-ref`.

### Branch Description

After the reference, there should be another *"/"* followed by a description which sums up the purpose of this specific branch. This description should be short and "kebab-cased".

By default, you can use the title of the issue/ticket you are working on. Just replace any special character by *"-"*.

## How does CITE name commits?

```bash
git commit -m "Add the Home page"
git commit -m "Cut the search bar from the header"
git commit -m "Fix menu of header janking on mobile devices"
git commit -m "Bump NodeJS to 22.0.1"
git commit -m "Make Apache Server use HTTP instead of HTTPS"
git commit -m "Refactor search bar" 
git commit -m "Optimize search bar queries"
```
> [!NOTE] 
> A commit must describe one change only. If you find it hard (i.e. you did many little changes), describe the most significant change.

Dissecting the examples above, we have the following format:

```bash
git commit -m "[verb] [description]"
```

Verbs to use:
- `Add` = Create a capability e.g. feature, test, dependency.
- `Cut` = Remove a capability e.g. feature, test, dependency.
- `Fix` = Fix an issue e.g. bug, typo, accident, misstatement.
- `Bump` = Increase the version of something e.g. dependency.
- `Change` = Change the build process, or tooling, or infra.
- `Move` = Move a file or folder to somewhere else.
- `Start` = Begin doing something; e.g. create a feature flag.
- `Stop` = End doing something; e.g. remove a feature flag.
- `Refactor` = A code change that MUST only be a refactoring.
- `Reformat` = Refactor of formatting, e.g. omit whitespace.
- `Optimise` = Refactor of performance, e.g. speed up code.
- `Document` = Refactor of documentation, e.g. help files.

The seven rules

- Separate subject from body with a blank line
- Limit the subject line to 50 characters
- Capitalise the subject line
- Do not end the subject line with a period
- Use the imperative mood in the subject line
- Wrap the body at 72 characters
- Use the body to explain what and why vs. how


## References
- [Simplified convention for naming branches and commits in git](https://dev.to/varbsan/a-simplified-convention-for-naming-branches-and-commits-in-git-il4)
- [Git commit message by Knowbl](https://github.com/knowbl/git-commit-message)