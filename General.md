# General contribution guidelines

This is a list of general contribution guidelines which apply to all projects. It also serves as a general example process for software development. 

## Fundamentals

Criteria for all projects.

* Javascript only. Languages which compile to Javascript (Coffeescript, Typescript, Rust etc) come and go. [New features](https://node.green) are being added to Javascript all the time. 
  * Create bindings for other languages in a separate project
* Full test coverage expected.

## Submitting a Pull request

Thanks for helping to improve this project! Guidance when submitting work.

### General

* All Pull Requests are welcome - large or small, complete or not.
* Don't worry about making the PR perfect. A maintainer or team member will help resolve.
  * Even if a PR is not approved it could still have value and influence future direction.

### Before you start

Checklist for those planning to submit changes.

* Ensure you understand the project's mandate and scope - planned work must fit the mandate.
  * It may be preferable to split the work into a separate project.
* The planned work should benefit all users, or at least the majority. Edge-case features used by a niche minority should live in an extension (e.g. a plugin).


### Design decisions

A design decision may be required when implementing a new convention, consideration or methodology.

* Please discuss and agree non-trivial, structural changes with a maintainer first, before implementing.

#### What is a structural change?

* A breaking change to the public API surface (at either code or package level)
* A change to the programming paradigm (e.g. a move away from Object-Orientated programming).
* A change to the software architecture, e.g. a refactoring of software or data structure.
* A change to the way the code is organised, internally (e.g. reorganising project file and folder structure).

## Authoring Style

Style guidelines.

### Code

* Javascript: [standard style](https://standardjs.com/)
* ECMAScript modules for new projects, ECMAScript with a CommonJS distribution for existing projects.
* Node.js versions >= 12.17 are supported so feel free to use the latest features (async generators etc.).

### Commit

* Atomic, reversable commits prefered.
* No commit message convention required. Any commit message is fine so long as it describes the work.

## Conventions

Development principles to follow.

## Philosophy

* Solve and forget
* Defend stability, controller code less regimented.
* mobile-first
* Minimise cognitive overhead. Shouldn't need to learn new concepts or DSLs.


### Path to stability

* Phase 1: first draft
  * Version number < v1.0.0
  * Anything goes, any paradigm. Project status is "disposable".
  * Mature or die. 
  * Death is inevitable, either through neglect or refactor. Reincantated into a stronger beast in Phase 2.
  * Consider phase 2 once MVP is built and it validates the project's value.
  * Phase 1 projects facilitate discussion. 
  * Phase 1 deaths moved to org cemetery.
* Specialised first, generalised later
  * Don't get bogged down in creative planning, thinking how wonderfully generalised you can make the component
  * Better to start with 10 specialised components (e.g. charts) with a lot of common behaviour, a lot of potential for reuse, than be distracted from your main project by becoming obsessed with making the ultimate generalised chart component that satisfies all use cases.

## Architecture

* Aim for long-life, stability and low-maintenance. Keep the public-facing API simple. Keep subjective or occassional features in separate plugins.
* Object-orientated, reusable, extensible. [SOLID](https://en.wikipedia.org/wiki/SOLID).
* Always avoid procedural code. All functionality defined in classes.
  * Even a single, trivial function should be defined in a suitably-named class. It may be trivial now but will grow.
* Minimal - less is more.
  * Aim for the smallest possible API surface. Don't extend it unless you're also prepared to remove API features in a future release, breaking compatibility and weakening stability.
  * Minimise dependency tree bloat. Don't flood the project with third-party opinions.

### Package.json

* Ensure `"engines"` correctly indicates the minimum required Node.js version
* Use a `"files"` array to keep package size down
* Use `npm run` scripts for automated tasks rather than gulp, grunt etc.
* Feel free to add yourself to the `contributors` array, e.g.:
    ```
    "contributors": [
      "Roger Exampleton <roger@example.com> (http://example.com)"
    ]
    ```

## Project toolkit

The standard set of tools and utilities.

### Development tools

* De-lint your work using the [standard command-line tool](https://standardjs.com/) but don't install it into the project. It should be part of your regular command-line toolkit (like `mv` and `ls`), there's no need to copy it into every project. Install it globally: `npm install -g standard`.

### Continuous Integration

* Github CI. Support for 12, 14, 16.
