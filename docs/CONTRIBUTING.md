# Contribution

> In case you want to contribute to this project, pick a role from [Contribution Roles](#contribution-roles) first and then read up all information on how to contribute in your role in the corresponding documents.

## Contribution Roles

This project has a set of roles for contributors other than just the maintainers and main developers who are responsible for this project. There are 4 different contribution roles for this project.

- Reporter (people who submit bug reports, problem reports or feature requests)
- Fiddler (people who forked the repository to fiddle for their own guild, game or for whatever other purpose with the intent of using it or contributing to the main repository later-on)
- Contributor (people who have submitted at least one legitimate merge request)
- Moderator (people who are here to review code and issues; these people are actually being picked by maintainers and have to be accepted in order to get this role)

**Disclaimer**: This list does not indicate a ranking by list item position.

## Report a Bug or Problem

To submit a bug or problem report, please refer to our [guide on issues](./contribution/issues.md), especially the [Bugs and Problems section](./contribution/issues.md#bugs-and-problems).

## Request a Feature

To submit a feature request, please refer to our [guide on issues](./contribution/issues.md), especially the [Features section](./contribution/issues.md#features).

## Code Review

There are different ways on how to get a merge for your submitted code (see [Pull Request](#pull-request) for information on how to submit code and which rules to follow when doing so) accepted. In order to get your code accepted, it must be reviewed in one of the following ways:

- by at least one maintainer (a maintainer may not merge their own code) or
- two main developers or
- two moderators and a main developer

## Contributing Code

### Writing Code

You are required to adhere to the rules specified in the [Coding Style](./contribution/code-guide.md#coding-style) section.

If there is a reason you can not adhere to any of these rules, please provide an explanation in your pull request according to the [Pull Request](#pull-request) section.

> Remeber: Code needs to be documented and tested. Code that does not have tests is treated as WiP and not reviewed until you notify a maintainer of having finished your pull request.

### Pull Request

When submitting a pull request, make use of this template or at least answer everything in this template so your code can be reviewed properly.

```MD
## Purpose

[Specify the purpose of your pull request. This includes which feature request or issue this tries to resolve.]

## Functionality

### Changes

[Describe the changes your pull request makes to the functionality of existing components in detail]

### Implemented

[Describe the new functionality your code introduces in detail]

### Dependencies

[List the dependencies your code uses to enable more precise dependency management]

## Remarks

[Add any information that you may want (or - maybe due to other rules or conventions - need) to be in your pull request here]
```

If your pull request is still a work in progress, please flag it as a work in progress (also called a `draft` on GitHub), please make sure it is a `Draft` instead of a full pull request. You may have your `Notes` section either as the top-most or bottom-most section in your pull request's body marked with the corresponding header:

```MD
## Notes
```
