
| id                               | hubs              | source                                         |
| -------------------------------- | ----------------- | ---------------------------------------------- |
| 202410251335_Convention Comments | [[hubs/git\|git]] | https://www.conventionalcommits.org/en/v1.0.0/ |
It provides an easy set of rules for creating an explicit commit history; which makes it easier to write automated tools on top of.
The commit message should be structured as follows:
```ls
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```
the commit contains the following structural elements,to communicate intent to the consumer of your library:
1. `fix` :a commit of type `fix` patches a bug in your code base
2. `feat`: a commit of the type `feat` introduce a new feature to the codebase 
3. `BREAKING CHANGE` a commit that has a footer `BREAKING CHANGE`, or append a after the type/scope, introduce a breaking API change.A BREAKING CHANGE can be part of commits of any _type_
4. _types_ other than `fix:` and `feat:` are allowed, for example [@commitlint/config-conventional](https://github.com/conventional-changelog/commitlint/tree/master/%40commitlint/config-conventional) (based on the [Angular convention](https://github.com/angular/angular/blob/22b96b9/CONTRIBUTING.md#-commit-message-guidelines)) recommends `build:`, `chore:`, `ci:`, `docs:`, `style:`, `refactor:`, `perf:`, `test:`, and others.
5. _footers_ other than `BREAKING CHANGE: <description>` may be provided and follow a convention similar to [git trailer format](https://git-scm.com/docs/git-interpret-trailers).
Additional types are not mandated by the Conventional Commits specification, and have no implicit effect in Semantic Versioning (unless they include a BREAKING CHANGE). A scope may be provided to a commit’s type, to provide additional contextual information and is contained within parenthesis, e.g., `feat(parser): add ability to parse arrays`.
