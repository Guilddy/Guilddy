# Code Guide

## Coding Style

The coding style of this project is pretty simple:

```TypeScript
import * as fs from 'fs';
import { SomeOtherModule } from './some-other-module';
import SomeInterface from './some-interface';

public class SomeModule extends SomeOtherModule, SomeInterface {
    public static SomeStaticProperty : string = "I'm static";

    public SomeInstanceProperty : string = "I'm in an instance";
    protected SomeProtectedInstanceProperty : string = "I'm still in an instance, bot I am also protected.";
    private SomePrivateInstanceProperty : string = "I'm still in an instance, bot I am also private.";

    public constructor(){
        // TODO: Review necessity of reading files here
        fs.readFileSync('./some-unused-text-file.txt');
    }

    public static GetStaticProperty() : string {
        return SomeModule.SomeStaticProperty;
    }

    public static CreateNew( newInstanceProperty : string, newPrivateInstanceProperty : string ) : string {
        let newModule = new SomeModule();
        newModule.SomeInstanceProperty = newInstanceProperty;
        newModule.SetSomePrivateInstanceProperty(newPrivateInstanceProperty);
        return newModule;
    }

    public GetSomePrivateInstanceProperty() : string {
        return this.SomePrivateInstanceProperty;
    }

    public SetSomePrivateInstanceProperty( newPrivateInstanceProperty : string ) : void {
        // FIXME: Check new value before setting value to avoid #xx
        this.SomePrivateInstanceProperty = newPrivateInstanceProperty;
    }
}
```

### File Names

File names are their class name in `kebab case` which is lowercase with dashes (`-`) before a capital letter of the class name. File names always start and end with a letter. There may be no other punctuation in module file names. Numbers are treated as capital letters in this section.

Following that rule, a module with the class name `SomeModule` would be placed in a file called `some-module.ts`.

However, there is a special case. That is when you have a series of capital letters as in an abbreviation. In that case, the whole series of capital letters are considered one word and therefore not separated by dashes except where necessary to emphasize the actual meaning of an abbreviation.

Therefore, a module with the class name `SomeRESTConnector` would be placed in a file named `some-rest-connector.ts` and a module with the class name `SomeConnectorREST` would be placed in `some-connector-rest.ts`. Where an abbreviation might require some more clarification (like `SMTP2FTPConnector`, which would be `smtp-2-ftp-connector`), or there are hybrid words in your module names (like `RESTful`, which would be `restful`) this rule may be bent in favor of clarification.

Of course, it would be better to just avoid this where possible. Maintainers or reviewers may go ahead and ask you to rename your module if rule bending could have been avoided.

### Class Names

Classes are named in `upper camel case` and, if extending an existing class, must follow their super class' naming scheme.

Classes are named in a way that represents their functional responsibility. That means that a connector has `Connector` in its name and an action has `Action` in its name.

When building a module structure where modules used are grouped, modules should be named in a way that their function is in the same position within the same module group. E.g. if the first member of a module group is called `RESTConnector`, the next one that connects to some FTP service is called `FTPConnector` and the module that converts the REST output to general purpose data is called `RESTConverter`, while an import tool might have an interpreter to automatically execute CRUD actions on database entities called `RESTInterpreter`.

### Types

#### Type Names

Type naming follows the module naming scheme.

#### Type Definition

Types are defined in different ways depending on how they are intended to be used:

1. Types that are intended to be used within a single module, class or module group, are placed in:
    - the same file, inbetween the import section and the class definition, if there are no more than two types to be placed in that file or
    - a file whichs name corresponds to that of the module they belong to (so types for a module `RESTController` that sits in `rest-controller.ts` will be placed in `rest-controller-types.ts` next to it) if there are three ore more types that are affected by this rule
2. Types that are intended to be used outside the module group are placed in a `types` directory inside the module group directory and the file name corresponds to their origin module's file name.
3. Types that are intended for co-usage outside their own module group also follow rule number 2, but their `types` directory is a module on its own to enable bulk import on co-used types.

### File Layout

A code file follows this outline (in order):

- Imports
  - System imports (NodeJS internal module imports)
    - Bulk imports (`import * as ABCDEF from 'abcdef'`)
    - Selective imports (`import { a, b, c } from 'abcdef'`)
    - Default imports (`import ABCDEF from 'abcdef'`)
  - External imports (node_module imports)
    - Bulk imports (`import * as ABCDEF from 'abcdef'`)
    - Selective imports (`import { a, b, c } from 'abcdef'`)
    - Default imports (`import ABCDEF from 'abcdef'`)
  - Internal imports (project module imports)
    - Bulk imports (`import * as ABCDEF from './abcdef'`)
    - Selective imports (`import { a, b, c } from './abcdef'`)
    - Default imports (`import ABCDEF from './abcdef'`)
- Types
  - public types
  - private types
- Class
  - Properties
    - Static Properties
      - Public Static Properties
      - Protected Static Properties
      - Private Static Properties
    - Instance Properties
      - Public Instance Properties
      - Protected Instance Properties
      - Private Instance Properties
  - Constructor **(as a separate block, surrounded by single blank lines)**
  - Methods **(methods are separated by a single blank line)**
    - Static Methods
      - Public Static Methods
      - Protected Static Methods
      - Private Static Methods
    - Instance Methods
      - Public Instance Methods
      - Protected Instance Methods
      - Private Instance Methods

Each of the top level properties in this list is an individual block. These blocks are seperated by a blank line.

### Class Properties and Methods

Class properties and methods are named in `upper camel case`. And must have an explicit accessibility modifier and type definition. Type definitions with multiple types (such as `object | string`) are always in the following order:

- Classes (alphabetically sorted)
- Types (alphabetically sorted)
- Interfaces (alphabetically sorted)

If the type can not be determined exactly, the closest anticipated type is used. E.g. as data returned by a method may have properties that can not be determined at the time of implementation, that method has a defined return type of `object`. If the method could also return a string, the type of that method becomes `object | string`. The type `any` may only be used if necessary or where the type would be `bigint | boolean | function | number | object | string | symbol | undefined`.

### Braces

Opening braces are placed in the same line with a preceeding space. Block content and closing braces are placed based on their content's line count:

- **Multi-line content**: The content starts in the line after the opening braces. Closing braces are on their own line, in the same column as the first non-whitespace character on the opening braces line. (see example code in [Coding Style](#coding-style))
- **Single-line content**: The content may be treated as a Multi-line block or hav opening braces, content and closing braces placed in the same line, separated by a single space. (`{ value : string }`)
- **No content / Empty braces**: Opening and closing braces are on the same line, separated by a single space. (`{ }`)

### Parenthesis

### Brackets

### Line Breaks

Line breaks are UNIX standard line breaks (CR / `\n`) in the repository.

It's up to you to use other line endings in your working directory but files need to be committed using UNIX standard `\n` line breaks only.

Any file committed to the repository must also end with a new line.

### Local Variables

## Contribution Roles

This project has a set of roles for contributors other than just the maintainers and main developers who are responsible for this project. There are 4 different contribution roles for this project.

- Reporter (people who submit bug reports, problem reports or feature requests)
- Fiddler (people who forked the repository to fiddle for their own guild, game or for whatever other purpose with the intent of using it or contributing to the main repository later-on)
- Contributor (people who have submitted at least one legitimate merge request)
- Moderator (people who are here to reiew code and issues; these people are actually being picked by maintainers and have to be accepted in order to get this role)

The list above does not directly indicate a ranking by list item position and does not necessarily correspond to the project's Discord server roles.

## Code Review

There are different ways on how to get a merge for your submitted code (see [Contribution](#contribution) for information on how to submit code and which rules to follow when doing so) accepted. In order to get your code accepted, it must be reviewed in one of the following ways:

- by at least one maintainer (a maintainer may not merge their own code) or
- two main developers or
- two moderators and a main developer

## Contribution

> In case you want to contribute to this project, pick a role from [Contribution Roles](#contribution-roles) first and then read up all information on how to contribute in your role in the contribution document.

### Code

#### Dependencies

If your code introduces any dependencies or if you are adding a new module that uses dependencies from the main project or any of the submodules, add them to your pull request so it is more clear which addition introduces which dependency and whether or not the dependencies are put where they need to be.

#### Writing Code

You are required to adhere to the rules specified in the [Coding Style](#coding-style) section.

If there is a reason you can not adhere to any of these rules, please provide an explanation in your pull request according to the [Pull Request](#pull-request) section.

> Remeber: Code needs to be documented and tested. Code that does not have tests is treated as WiP and not reviewed until you notify a maintainer of having finished your pull request.

#### Pull Request

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
