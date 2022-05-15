# Good to know 🤔

- To get a sense of where the project is heading, or for ideas on where you could contribute, take a look at the
[roadmap](https://aivot.de/roadmaps) of the respective project.
- We only accept Pull Requests for existing issues. Existing issues have been properly discussed and, if not closed,
deemed valuable for the project.
- When in doubt, keep your Pull Requests small. To give a Pull Request the best chance of getting accepted, don't bundle
more than one feature or bug fix per Pull Request. It's often best to create two smaller Pull Requests than one big one.
- By contributing your code to a projects GitHub repository, you agree to license your contribution under the
[MIT license](https://opensource.org/licenses/MIT).

## Resources 📚

This project contains several resources to help you understand the software architecture, coding style as well as the
development and contribution workflows.  
Please refer to these documents if you have any questions regarding these topics.

| Resource                                | Description                                                                                                      |
|-----------------------------------------|------------------------------------------------------------------------------------------------------------------|
| [CODE_OF_CONDUCT](./CODE_OF_CONDUCT.md) | Code of conduct for collaboration in this project and when collaborating in general with Aivot and its community |
| [CONTRIBUTING](./CONTRIBUTING.md)       | How to contribute to a project (this document 🤯)                                                                |
| [SECURITY](./SECURITY.md)               | Patch cycles and how to report vulnerabilities                                                                   |
| [STYLEGUIDE](./STYLEGUIDE.md)           | Coding styles and the truth about tabs vs. spaces                                                                |
| [README](./README.md)                   | Prerequisites, setup and configuration of the project                                                            |
| [Wiki](../../wiki)                      | Software architecture, APIs and anything else needed for development                                             |

# General Workflow 🔁 --> teilweise offen
We follow a workflow so that everything always remains under control and optimal results are achieved.
For this, we rely heavily on the two systems [Github Issues](https://github.com/features/issues)
and [Clickup](https://clickup.com).

| Step | Description                                                                                                                                                                                | Responsibility     | Remarks                                                                               |
|------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------|---------------------------------------------------------------------------------------|
| 1    | A new issue on GitHub is created (if there is none already).                                                                                                                               | Contributor, Aivot | -                                                                                     |
| 2    | A new *feature*, *fix* or *refactor* branch is created. All changes are going to be committed to this branch.                                                                              | Contributor, Aivot | See [branching](./CONTRIBUTING.md#branching) for more information about our branching |
| 3    | A New Pull Request is created. The Pull Request references the solved issue.                                                                                                               | Contributor, Aivot | Use the Pull Request template provided by the repository                              |
| 4    | Aivot is monitoring for Pull Requests. The newly created Pull Request is reviewed by Aivot. We will either merge the Pull Request, request changes to it, or close it with an explanation. | Aivot              | -                                                                                     | 
| 5    | In case the Pull Request is accepted by Aivot: The branch is squashed and rebased by us. A changelog entry is generated as well as a reference to the original contributor.                | Aivot              | -                                                                                     |


**Please make sure to check your code for syntax, linting, spelling and styling errors.** --> Sollte das nicht irgendwo
gesondert vermerkt sein wie styleguide etc. auf den man dan hier verlinken kann?

## Company facing vs. community facing
The two systems in use, Github Issues and Clickup, each have a very specific purpose.
We use Github Issues for the community facing part of the workflow and Clickup for the company facing part of the workflow.

### Community facing
"Community facing" means making tasks available to the community via Github Issues.
Github Issues include tasks that are created and implemented by us as well as tasks that are submitted,
discussed and implemented by the community.
In other words: Without exception, all tasks end up on GitHub Issues for discussion and to indicate whether they are
implemented by us or by the community. This makes GitHub Issues the perfect place for people to submit their ideas.

### Company facing
"Company facing" means that tasks are handled by us and managed with Clickup for this purpose.
This can include tasks such as a complete feature development or the task of a code review of a pull request from a contributor.
In other words: All tasks that are implemented by us from the beginning, or that are contributed to by us
in the course of their existence, end up in Clickup (sooner or later this is every task 😅). This allows us a coordinated
internal approach. Clickup is therefore the ideal place for people who want to see a [roadmap](https://aivot.de/roadmaps)
for the project.

### Behind the scenes of this approach
**Community facing:**  
As a contributor, you create a GitHub issue. From here on there are two ways:
1. if the issue is put up for discussion and therefore not directly assigned to you for implementation, we copy the issue
as a task to Clickup in the status *in technical coordination*. This way we don't lose track of where discussions
are going on. If we take care of the implementation, the task will be dragged through our Clickup board.
It will be "company facing" from the moment the decision is made that we will develop for this issue.
2. If you as a contributor assign the issue to yourself and work on it, nothing happens from our point of view.
Only when you create a Pull Request we get to know about it and the issue becomes "company facing".
We then create a task in Clickup with the status *in review* in order to be able to give you as a contributor feedback
as quickly as possible. If the code review is successful, we squash and merge and your contribution is included in the project.

**Company facing:**  
When an implementation idea comes from us, we create a task in Clickup for it. For each task we create in Clickup,
we also create an issue on GitHub. This way, the community always has an overview of what ideas are already in the world
at the place where the development is documented, namely on GitHub, and duplicates of ideas are avoided.
Viewing the [roadmap](https://aivot.de/roadmaps) of the project is therefore not mandatory.
If the implementation idea comes from us, we usually handle the development for it as well. For this we assign the issue
on GitHub ourselves. Our internal development also follows the [contributing guideline](./CONTRIBUTING.md)
(branching, pull requests etc.) and is being tracked within Clickup.

# Environment 🌍 --> Offen

https://develop.sentry.dev/environment/
Wsl. müssen wir den Part in die lokale Readme des Projektes packen und dann hier die readme verlinken. Derzeit ist
in der readme die headline usage dafür vorgesehen.

# Branching 🌳

We use trunk based development conventions. If you haven't worked with it yet, we recommend reading the
[documentation on trunk based development](https://trunkbaseddevelopment.com/).

Here is a quick overview of the most important aspects:
- There are only for types of branches: *main*, *feature*, *fix* and *refactor*
- All branches of the type *feature*, *fix* and *refactor* always branch off from the *main* branch
- The name of the branch has to follow the kebab-case naming convention
- The name of the branch should follow the pattern /issue/[GITHUB ISSUE ID]-descriptive-feature-name

# Commit Message 💬
https://develop.sentry.dev/commit-messages/
We have very precise rules over how our git commit messages can be formatted.
This leads to more readable messages that are easy to follow when looking through the project history.

## General Formatting Rules --> Nochmals merge vs rebase durchlesen bei sentry
- Separate subject from body with a blank line
- Limit the subject line to 50 characters
- Capitalize the subject line
- Do not end the subject line with a period
- Use the imperative mood in the subject line (e.g. "Make the button color orange")
- Wrap the body at 72 characters
- Use the body to explain what and why vs. how

## Commit Message Format
Allgemeines zum Aufbau HIER WEITERMACHEN

### Type
| Type | Description |
|------|-------------|
| fix  | bla         |

Welche Types haben wir die vorne weggestellt werden wie fix, style etc.?

### Scope
| Scope | Description |
|-------|-------------|
| app   | bla         |

Welche scopes haben wir? App, release etc.? --> scopes kommen in das repo wiki. Hier entsprechend auf das Wiki verweisen.


eventuell irgendwelche tags etc für automatisierungen z.B. Clickup ID (wird von Aivot eingefügt!?)
Wir könnten im Body die Verlinkung zu Github Issues und Clickup issues machen. --> Wenn der branch die IDs beinhaltet,
wird jeder commit automatisch mitgenommen? https://docs.clickup.com/en/articles/856285-github



# Code Review 🧐

https://develop.sentry.dev/code-review/
coding style
alle tests passen

# Dependencies 🔗

Hinweis dass nur open source dependencies verwendet werden dürfen mit lizenzen x, y, z. Zukünftig kann
das automatisch im build mitgetestet werden. Der Hinweis sollte dennoch bestehen bleiben hier in den docs.

# Translations 🇩🇪

Currently there is no support for translations. We plan on adding support in the future.

Translations are handled via Crowdin/Transifex. You don't need to apply any changes to localized versions of our markdown files
i.e. files having a -locale suffix. Crowdin automatically takes care of syncing these changes across the localized versions.
https://develop.sentry.dev/translations/

# Documentation 📝

We at Aivot write any documentation. Be it code documentation or documentation for the end user.
The main reason for this is that documentation is only very good if it is consistent.
In addition, there are sometimes hands-on demos within the documentation. And we don't expect anyone to produce them.

If you are looking for the projects documentation visit our [documentation overview](https://aivot.de/docs) and select
the respective project.

https://develop.sentry.dev/docs/

Inspired by the great development guideline from the team [@getsentry](https://github.com/getsentry)