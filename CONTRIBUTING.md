# Web BDE : Contributing guide

This document aims at describing the flow of all sub-projects concerning Web BDE.

## Git workflow

The **main** repository [web-bde](https://github.com/Web-BDE/web-bde) is composed of **submodules**, each submodules concern a particular **micro-service** ([front-web-bde](https://github.com/Web-BDE/front-web-bde) for example is the service that distribute static files). Each micro service project has its own Issues/PR and follow **this workflow**.  
For more information on how to use submodules with git, please follow [this explanation](https://gist.github.com/gitaarik/8735255)

In each repository yo will find 2 types of branch:

- Main branch (ex: `main-v1`) : The main branch is the current development branch
- Feature (or bugfix) branch (ex: `2-contribution`) : Branch related to an opened Issue that will be merged into a version branch through a PR

Main & Version branches are locked, you can only develop on a feature branch. Each feature branch **must** be related to an opened **Issue**, to merge your work you **must** create a **Pull Request** that **must** be reviewed by an administrator. Once the feature is ready to merge and all requirements have been passed the PR will be merged on the main branch

## How to commit

A commit message **must** follow this structure :

```{text}
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

It is composed of :

- The type of the commit (fix, feat, test...)
- An optional scope to link it with a PR/Issue
- A brief description of 50 character maximum
- An optional (but highly recommended) body describing what have you done and why
- An optional footer for additional information like a breaking change

Please be aware of this conventions while committing to your branch. For more information please read the [conventional commits website](https://www.conventionalcommits.org/en/v1.0.0/)

## When and how to make an Issue ?

An Issue has to be opened when a functional needs is discovered, it could be a feature request, bug report, documentation.... You **must** open an Issue before creating a development branch. An issue should not be technical and should describe what the end user will get.

### Issue Title

The title of your Issue should describe the topic.

### Issue Body

You **must** respect the [templates](.github/ISSUE_TEMPLATE/), tow templates are provided : one for Feature/Documentation request, one for Bug report.

Every Issues **must** contain a task list to follow the progress of the Issue :

- [x] Write the contributing.md

### Issue Labels

You **must** provide your Issue with at least 2 labels :

- A major version label (ex: `v1` or `v2`)
- A purpure label (ex: `documentation`)

## When and how to make a Pull Request ?

A PR **must** be created to request a merge of a feature branch into a main branch, you could create PR to merge feature branches together but it's not required. A PR is related to an Issue and aims at describing more technically the subject of this Issue.

### PR Title

The PR title should describe what you've done and be as short as possible.

### PR Body

A PR **must** follow the [template](.github/PULL_REQUEST_TEMPLATE.md).

Your PR **must** implement the same task list as the Issue but with nested, more technical tasks :

- [x] Write the contributing.md
  - [x] Commits part
  - [x] Issues part
  - [x] PRs part
  - [ ] Reviews part

You **must** mention the Issue related to the PR, for example : `Closes #12`

### PR Labels

You **must** provide your PR with at least 2 labels :

- A major version label (ex: `v1` or `v2`)
- A purpure label (ex: `documentation`)

Your PR must be approved by an administrator in order to be merged into the main branch.

## Review a PR

When reviewing a PR please be very aware about code correctness such as logic, conventions or variables names as much as the overall validity of the implemented feature. If you found a bug or you want to say a word, please follow some simple structure for your comment :

```{text}
@Roxxas96

[Bug]

There is a typo in this line
```

Your comment should at least :

- Mention at least the Assignee that wrote the code
- Mention the type of comment (suggestion, bug etc...)
- Be concise and clear

**It is highly recommended to use fixup commits to correct bugs during a draft PR so people can easily follow the PR workflow**.  
For more information on how to use git commit --fixup & git rebase --auto-squash, please see [this explanation](https://www.mikulskibartosz.name/git-fixup-explained/)

Please be polite and be aware that not every one is as strong as you, working as a large team could be annoying but it's also an incredible experience !
