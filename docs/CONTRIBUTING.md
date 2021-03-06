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

To submit a bug or problem report, please refer to our [guide on issues](./contribution/issues.md), especially the [Bug Reports section](./contribution/issues.md#bug-reports).

## Request a Feature

To submit a feature request, please refer to our [guide on issues](./contribution/issues.md), especially the [Feature Requests](./contribution/issues.md#feature-request).

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

### Testing

We use [mocha](https://mochajs.org/) for testing. Please write unit tests for code you write. Pull requests might not be approved if the test coverage is too low.

### Pull Request

When submitting a pull request, make use of our `Pull Request` template and fill in as much information as possible into your pull request's body so your code can be reviewed properly.

If your pull request is still a work in progress, use our `Draft Pull Request` template, please make sure it is a `Draft` instead of an open pull request. You may have your `Notes` section either as the top-most or bottom-most section in your draft pull request's body.

Please remove the `Notes` section when making your draft an open pull request and make sure you put all information that might be interesting when reviewing the pull request into your `Remarks` section.

## Developer's Certificate of Origin 1.1

By making a contribution to this project, I certify that:

- (a) The contribution was created in whole or in part by me and I have the right to submit it under the open source license indicated in the file; or
- (b) The contribution is based upon previous work that, to the best of my knowledge, is covered under an appropriate open source license and I have the right under that license to submit that work with modifications, whether created in whole or in part by me, under the same open source license (unless I am permitted to submit under a different license), as indicated in the file; or
- (c) The contribution was provided directly to me by some other person who certified (a), (b) or (c) and I have not modified it.
- (d) I understand and agree that this project and the contribution are public and that a record of the contribution (including all personal information I submit with it, including my sign-off) is maintained indefinitely and may be redistributed consistent with this project or the open source license(s) involved.
