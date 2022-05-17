# Good to know 🤔
- To get a sense of where the project is heading, or for ideas on where you could contribute, take a look at the
[roadmap](https://aivot.de/roadmaps) of the respective project.
- We only accept Pull Requests for existing issues. Existing issues have been properly discussed and, if not closed,
deemed valuable for the project.
- By contributing your code to a projects GitHub repository, you agree to license your contribution under the
[MIT license](https://opensource.org/licenses/MIT).

## Resources 📚
This project contains several resources to help you understand the software architecture, coding style as well as the
development and contribution workflows (or how we call it: *development view*).  
Please refer to these documents if you have any questions regarding these topics and therefore development.

| Resource                                | Description                                                                                                      |
|-----------------------------------------|------------------------------------------------------------------------------------------------------------------|
| [CODE_OF_CONDUCT](./CODE_OF_CONDUCT.md) | Code of conduct for collaboration in this project and when collaborating in general with Aivot and its community |
| [CONTRIBUTING](./CONTRIBUTING.md)       | How to contribute to a project (this document 🤯)                                                                |
| [SECURITY](./SECURITY.md)               | Patch cycles and how to report vulnerabilities                                                                   |
| [STYLEGUIDE](./STYLEGUIDE.md)           | Coding styles and the truth about tabs vs. spaces                                                                |
| [README](./README.md)                   | Prerequisites, setup and configuration of the project                                                            |
| [Wiki](../../wiki)                      | Software architecture, APIs and anything else needed for development                                             |

Note: If you have questions regarding the *user view* (e.g. how to use feature XY), please refer to our user documentation
for the respective project by choosing the project on our [documentation overview](https://aivot.de/docs).




# General Workflow 🔁
We follow a workflow so that everything always remains under control and optimal results are achieved.
For this, we rely heavily on the two systems [Github Issues](https://github.com/features/issues)
and [Clickup](https://clickup.com).

| Step | Description                                                                                                                                                                                | Responsibility     | Remarks                                                                               |
|------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------|---------------------------------------------------------------------------------------|
| 1    | A new issue on GitHub is created (if there is none already).                                                                                                                               | Contributor, Aivot | -                                                                                     |
| 2    | A new branch is created. All changes are going to be committed to this branch.                                                                                                             | Contributor, Aivot | See [branching](./CONTRIBUTING.md#branching) for more information about our branching |
| 3    | A New Pull Request is created. The Pull Request references the solved issue.                                                                                                               | Contributor, Aivot | Use the Pull Request template provided by the repository                              |
| 4    | Aivot is monitoring for Pull Requests. The newly created Pull Request is reviewed by Aivot. We will either merge the Pull Request, request changes to it, or close it with an explanation. | Aivot              | -                                                                                     | 
| 5    | In case the Pull Request is accepted by Aivot: The branch is squashed and rebased by us. A changelog entry is generated as well as a reference to the original contributor.                | Aivot              | -                                                                                     |

## Company facing vs. community facing
The two systems in use, Github Issues and Clickup, each have a very specific purpose.  
We use Github Issues for the community facing part of the workflow and Clickup for the company facing part of the workflow.

### Community facing
"Community facing" means making tasks available to the community via Github Issues.  
Github Issues includes tasks that are created and implemented by us as well as tasks that are submitted,
discussed and implemented by the community.
In other words: Without exception, all tasks end up on GitHub Issues for discussion and to indicate whether they are
implemented by us or by the community. This makes GitHub Issues the perfect place for people to submit their ideas.

### Company facing
"Company facing" means that tasks are handled by us and managed with Clickup for this purpose.
This can include tasks such as a complete feature development or the task of a code review of a Pull Request from a contributor.
In other words: All tasks that are implemented by us from the beginning, or that are contributed to by us
in the course of their existence, end up in Clickup (sooner or later this is every task 😅). This allows us a coordinated
internal approach. Clickup is therefore the ideal place for people who want to see a [roadmap](https://aivot.de/roadmaps)
for the project.

### Behind the scenes of this approach
**Community facing:**  
As a contributor, you create a GitHub issue. From here on there are two ways:
1. If the issue is put up for discussion and therefore not directly assigned to you for implementation, we copy the issue
as a task to Clickup in the status *in technical coordination*. This way we don't lose track of where discussions
are going on. If we take care of the implementation, the task will be dragged through our Clickup board.
It will be "company facing" from the moment the decision is made that we will develop for this issue.
2. If you as a contributor assign the issue to yourself and work on it, nothing happens on our side.
Only when you create a Pull Request we get to know about it and the issue becomes "company facing".
We then create a task in Clickup with the status *in review* in order to be able to give you as a contributor feedback
as quickly as possible. If the code review is successful, we squash and rebase and your contribution is included in the project.

**Company facing:**  
When an implementation idea comes from us, we create a task in Clickup for it. For each task we create in Clickup,
we also create an issue on GitHub. This way, the community always has an overview of what ideas are already in the world
at the place where the development is documented, namely on GitHub, and duplicates of ideas are avoided.
Viewing the [roadmap](https://aivot.de/roadmaps) of the project is therefore not mandatory as a contributor.  
If the implementation idea comes from us, we usually handle the development for it as well. For this we assign the issue
on GitHub ourselves. Our internal development also follows the [contributing guideline](./CONTRIBUTING.md)
(branching, Pull Requests etc.) and is being tracked within Clickup.




# Environment 🌍
Please refer to the [README](./README.md#Setup) for detailed instructions on setting up this project as well as
developing for it.




# Branching 🌳
We use trunk based development conventions. If you haven't worked with it yet, we recommend reading the
[documentation on trunk based development](https://trunkbaseddevelopment.com/).

Here is a quick overview of the most important aspects:
- There are only four types of branches: *main*, *feature*, *fix* and *refactor*
- All branches of the type *feature*, *fix* and *refactor* always branch off from the *main* branch
- The name of the branch has to follow the kebab-case naming convention
- The name of the branch should follow the pattern /issue/GH-[GITHUB ISSUE ID]-descriptive-feature-name




# Commit Message 💬
We have very precise rules over how our git commit messages can be formatted.
This leads to more readable messages that are easy to follow when looking through the project history.

## General Formatting Rules
- Limit the subject line to 50 characters
- Separate subject from body with a blank line
- Capitalize the subject line
- Do not end the subject line with a period
- Use the imperative mood in the subject line (e.g. "Add Google SSO")
- Wrap the body at 72 characters
- Use the body to explain what and why vs. how (e.g. Add XY because Z vs. Added X and did Y)
- Use the imperative mood in the body

## Merge vs. Rebase
We use a rebase workflow (see trunk based development in the [Branching](./CONTRIBUTING.md#Branching) section).
That means that every commit on its own should be a clear, functional, and stable change.
This means when you’re building a new feature, you should try to pare it down into functional steps,
and when that’s not reasonable, the end patch should be a single commit. Those commits should be squashed, and the
final patch when landed should be rebased.

Remember: each commit should follow the commit message format. Ideally every commit is stable (green build), at least
the final patch has to be!

### Rebase and Merge
The GitHub UI exposes a “Rebase and Merge” option, which, if your commits are already following the commit guidelines,
is a great way to bring your change into the codebase.

Note: This is only relevant for us at Aivot since we are the ones rebasing
(see [General Workflow](./CONTRIBUTING.md#General-Workflow)).

### Squashing
When you are squashing your branch, it’s important to make sure you update the commit message.
If you’re using GitHub’s UI it will by default create a new commit message which is a combination of all commits
and **does not follow the commit message guidelines**. Make sure you follow the commit message guidelines and write
a commit message that is understandable within the context of a changelog.

Note: This is only relevant for us at Aivot since we are the ones squashing
(see [General Workflow](./CONTRIBUTING.md#General-Workflow)).

## Commit Message Format
Each commit message consists of a **header**, a **body**, and a **footer**.  
The general structure is as follows:
```
[TYPE]([SCOPE]): [SUBJECT]
BLANK LINE
[BODY]
BLANK LINE
[FOOTER]
```
A short explanation on the different building blocks of a commit message:

| Building block | Mandatory? | Explanation                                                                                                                                         |
|----------------|------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|
| Type           | yes        | Signals that the change belongs to a defined category. See [Type](./CONTRIBUTING.md#Type) for types used by us.                                     |
| Scope          | no         | The name of the core component affected by the change as perceived by the user. See [Scope](../../wiki/scope) in wiki.                              |
| Subject        | yes        | A succinct description of the change in imperative mood of what is going to be changed by the commit if merged.                                     |
| Body           | yes        | Explanation of what has been done and why it has been done in imperative mood.                                                                      |
| Footer         | no         | Should contain any information about Breaking Changes. If relevant contains a closing reference to a GitHub issue as well as a Clickup task if any. |

Example of a commit message:
```
feat(auth): Add Google SSO as login option

Add the possibility for users to sign in using Google since many
requested this.

Closes GH-1234
Closes CU-1234

BREAKING CHANGE:
Change auth-endpoint from /auth to /app/auth
```

### Revert
If the commit reverts a previous commit, it should begin with `revert:`, followed by the header of the reverted commit.
In the body it should say: `This reverts commit [HASH].`, where the [HASH] is the SHA of the commit being reverted.

### Type
| Type  | Description                                                                                      |
|-------|--------------------------------------------------------------------------------------------------|
| build | 	Changes that affect the build system or external dependencies (example scopes: webpack, npm).   |
| ci    | Changes to our CI configuration files and scripts (example scopes: github).                      |
| docs  | Documentation only changes.                                                                      |
| feat  | A new feature.                                                                                   |
| fix   | A bug fix.                                                                                       |
| ref   | A code change that neither fixes a bug nor adds a feature (refactor).                            |
| test  | Adding missing tests or correcting existing tests.                                               |
| meta  | Some meta information in the repo changes (example scopes: owner files, editor config, funding). |

### Scope
The scope should be the name of the core component affected (as perceived by the person reading the changelog generated
from commit messages). This means it should be the system impacted, not the literal file changed. For example, if the
code primarily affects settings, you’d use the settings scope, even if the changes are in utility files or db schema.  
Since scopes are highly project specific, please refer to the [scope section](../../wiki/scope) within the projects wiki.




# Code Review 🧐
Code review is mandatory at Aivot. This adds overhead to each change, but ensures that simple, often overlooked problems
are more easily avoided. Code review helps build shared context and collective ownership. It is also an opportunity to
collaborate with others. Finally, code review can identify several classes of problems before customers are exposed
to them.

Code review is managed via GitHub’s Pull Requests. Pull Request templates exist.

## Who reviews code
All engineers should be reviewing code. As you gain more experience and context on the products we build and technologies
we use, you can provide valuable feedback to other engineers who may be working in areas that are new to them but
familiar to you.

Code review is an opportunity to improve your mentoring and communication skills. Code review can have the important
function of teaching engineers about the languages, frameworks and technologies we use in a collaborative environment
that is about the changes being made.

Note: This is only relevant for us at Aivot since we are the ones reviewing code
(see [General Workflow](./CONTRIBUTING.md#General-Workflow)).

## Why Pull Requests
Our open source projects are maintained via GitHub and we want to ensure that the barrier to entry for external
contributions is minimal. By using GitHub features when possible, we make it easy for developers familiar with other
projects on GitHub.

### GitHub Teams
We currently have no teams defined in GitHub.

## Code Reviews are for...
### 1. Identifying problematic code
Above all, a code review should try to identify potential bugs that could cause the application to break – either now,
or in the future.

- Uncaught runtime exceptions (e.g. potential for an index to be out of bounds)
- Obvious performance bottlenecks (e.g. O(n^2) where n is unbounded)
- Code alters behavior elsewhere in an unanticipated way
- API changes are not backwards compatible (e.g. renaming or removing a key)
- Complex ORM interactions that may have unexpected query generation/performance
- Security vulnerabilities
- Missing or incorrect Permissions or Access Control

### 2. Improving Design
Reviewers should consider if the interactions of the various pieces in the change make sense together.
Do the changes conflict with other requirements or goals of the project? Could any of the methods being
added be promoted to module level methods? Are methods being passed properties of objects when they could be passed the
entire object?

### 3. Reducing code complexity
Research shows that Lines of Code are correlated with a higher bug count. If reviewers see an easy opportunity to
significantly reduce the amount of code that is submitted, they should suggest a different approach.

For example, if a submitter has written a `for` loop to find an item in an array:
```
for (let i = 0; i < arr.length; i++) {
  if (arr[i] === 'thingiwant') return i;
}
return undefined;
```
It’s fair game to suggest they instead use:
```
return arr.find(x => x === 'thingiwant');
```
This is a mostly objective improvement: there are fewer variables, fewer statements, and fewer branches, and the
method name `find` communicates intent. Suggesting these types of uncontroversial improvements is encouraged.

Reviewers have to be careful though – it’s easy to go down a rabbit hole of re-writing code to be as small as possible,
and in the end winding up with something ultimately more complicated. Reviewers have to be pragmatic and strive to reach
a good balance.  
See also: [Code reviews are not for getting it perfect](./CONTRIBUTING.md#Getting-it-perfect) below.

### 4. Enforcing coding standards
As much as possible, we use automation to enforce code style and test coverage. But there are exceptions that cannot
necessarily be automated (or perhaps more accurately, we haven’t automated yet):

- Variable and file names are sensible, readable, and consistent with existing code
- Migrations have a deployment plan
- Unused or superfluous code isn’t committed accidentally

### 5. Making sure requirement covering tests are in existence
Reviewers make sure there are functional tests, integration tests or end-to-end tests covering the changes. If not
they ask for them. We rely on our test suite to maintain a high quality bar and ship rapidly.

When reviewing tests reviewers double check that the tests cover the requirements of the project or that the tests cover
the defect being fixed. Tests should avoid branching and looping as much as possible to prevent bugs in the test code
from gaining a foothold.

Functional tests that simulate how a user would call our APIs or use our UX are key to preventing regressions and
avoiding brittle tests that are coupled to the internals of the products we ship.

Tests are also the ideal place to ensure that the changes have considered permissions and access control logic.

### 6. Double-checking expected behaviour
The reviewer should make a genuine attempt to double-check that the goals of the Pull Request appear to be satisfied
by the code submitted. This requires the submitter to write a good description of the expected behavior, and why.  
See also: [Guidelines for Submitters](./CONTRIBUTING.md#Guidelines-for-Submitters) below.

### 7. Assessing and approving long-term impact
If you’re making significant architectural, schema, or build changes that will have long-term ramifications to the
software or data, it is necessary to solicit a senior engineer’s acknowledgment and blessing.

- Large refactors
- Database schema changes, like adding or removing columns and tables
- API changes (including JSON schema changes)
- Adopting new frameworks, libraries, or tools
- New product behaviour that may permanently alter performance characteristics moving forward

### 8. Information sharing and professional development
Code reviews are an opportunity for more people to understand forthcoming code changes, so that they might in turn
teach others down the road, and be in a position to fix something if/when the original author is not available.

Additionally, code reviews are an opportunity to learn about new techniques or approaches, and be exposed to code
you might otherwise not have an opportunity to browse.

## Code Reviews are not for...
### 1. Passing responsibility onto the reviewer
It is not the responsibility of the reviewer that your code is correct, bug free, or achieves its goals.  
Reviewers are there to help you, but if something is wrong, it’s your responsibility to correct it.

### 2. Boasting about your programming knowledge
As a reviewer, try to stick to objective improvements and make a best-intent assumption that the submitter has done
their homework.

### 3. Getting it perfect
The goal of code reviews is to reduce risk, not to produce perfect code. It’s okay to ship code in stages, and to commit
to improving something later. If you’re thinking – if we don’t get it correct up-front, we’ll never come back to it –
consider that if it never needs coming back to, perhaps those changes were never necessary in the first place.

Code reviews are expensive. Every time you request a change, you’re probably delaying that Pull Request by 24 hours or
more. This can severely inhibit our ability to move fast. Please be pragmatic, and consider the cost of each incremental
request for changes.

### 4. Introducing long-term architectural changes for the first time
While code reviews are great for discussion on implementation, they’re not the place to introduce large, long-term
changes for the first time. Before dropping a Pull Request that implements those changes, you should definitely open an
issue beforehand to start a discussion in general.

## Guidelines for Submitters
### Try to organize your work in a way that makes it conducive to review
Ideally, a Pull Request is limited to only a single feature or behaviour change.  
This might feel like more work up-front, but it can make code review faster, reduce risk by letting you ship in stages,
and ultimately end up being quicker.

### Describe what your PR does in a few sentences in the description field
Explain **why** you’re making these changes. Reference any GitHub Issues or Clickup tasks that are being addressed.  
If applicable, explain why other approaches were explored but not settled on.  
This gives the reviewer context, and prevents them going down the same rabbit holes that the submitter may have already
explored when creating the code.

### Annotate specific lines in your PR
If you can, give context to specific lines of code that could use elaboration.

### Where appropriate, label in-progress Pull Requests as WIP (work in progress) for early feedback
Labeling your work as `WIP` helps set expectations about the state of the Pull Request.  
Pull Requests labeled with `WIP` are good for having someone check-in to make sure you’re on the right path.
Additionally, this is an opportunity to verify CI passes before involving a reviewer.

### Be your own first reviewer
After you’ve put up your Pull Request on GitHub, walk through the code yourself, before assigning an external reviewer.  
You’ll often catch code mistakes you didn’t see when writing it.  
This is also a good time to leave comments and refresh your memory in order to write a more helpful description.

### Assign no more than 1-3 reviewers
It’s tempting to want to involve as many people as possible, but it can often be distracting, and create a situation
where nobody’s clear on who should actually perform the review.  
Always @mention an appropriate team (or teams) for review instead of individuals.  
If your work spans multiple teams (and thus, many reviewers), consider breaking up your Pull Requests into multiple
compatible patches (e.g. a backend change and a frontend change).

### Avoid rebasing unnecessarily
After a rebase, previous review comments will be orphaned from their now non-existent parent commits, making review
more difficult.  
Rewriting history makes it difficult for reviewers to isolate the scope of their review.

### Let reviewers know that you’ve made changes
Request review again via the "Reviewers" dropdown (There should be a yellow dot next to their name again).  
Don’t rely on reviewers mind-reading skills to know that you’re ready to have them look things over again.  
If you resolve a point of actionable feedback, it's helpful to leave a comment to let the reviewer know that it was
addressed, ideally with a reference to the commit that addressed it.

## Guidelines for Reviewers
Note: This is only relevant for us at Aivot since we are the ones reviewing code
(see [General Workflow](./CONTRIBUTING.md#General-Workflow)).
### Be polite and empathetic
Avoid accusatory and/or judgmental comments like: “You should have done X”.

### Provide actionable feedback
Instead of “This is bad”, try “I feel this could be clearer. What if you renamed variable X to Y?”

### Distinguish between “requires changes” and “nitpicks”
Consider marking a Pull Request as approved if the only requested changes are minor nits, so as not to block the author
in another asynchronous review cycle.

### Respond promptly to code review requests
We’re a community and you need to unblock other developers so that we can all move forward.  
We recommend checking for open code reviews at the start and end of every day.  
[Github's Review Requests tab](https://github.com/pulls/review-requested) can be a helpful place to keep track of these.




# Dependencies 🔗
We rely on open source projects ourselves for development. In order not to violate any rights, we pay very close attention
to which licenses we allow.

| License                                                                                             | Status     |
|-----------------------------------------------------------------------------------------------------|------------|
| [GNU Lesser General Public License version 3 (LGPL)](https://opensource.org/licenses/LGPL-3.0)      | ⚠️ Caution |
| [Mozilla Public License 2.0 (MPL)](https://opensource.org/licenses/MPL-2.0)                         | ⚠️ Caution |
| [Apache License Version 2.0 (Apache)](https://opensource.org/licenses/Apache-2.0)                   | ✅ Use      |
| [MIT](https://opensource.org/licenses/MIT)                                                          | ✅ Use      |
| [Berkeley Source Distribution License (BSD-2-Clause)](https://opensource.org/licenses/BSD-2-Clause) | ✅ Use      |
| [Berkeley Source Distribution License (BSD-3-Clause)](https://opensource.org/licenses/BSD-3-Clause) | ✅ Use      |
| [Unlicense](https://opensource.org/licenses/unlicense)                                              | ✅ Use      |

**We do not allow the use of proprietary licenses under any circumstances.**

A brief explanation of the statuses is given below.

| Status     | Explanation                                                                                                                                                                                                                                          |
|------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ⚠️ Caution | There are specific requirements. A correct implementation of the license conditions is to be checked by us. Please explain in a comment in the Pull Request why only this package is suitable and no other library with a license of "✅ Use" status. |
| ✅ Use      | Nothing to consider. Just use it.                                                                                                                                                                                                                    |

## Automatic license compliance checking
Implementation is planned...




# Translations 🇩🇪
Currently there is no support for translations. We plan on adding support in the future.




# Documentation 📝

We at Aivot write any documentation. Be it code documentation or documentation for the end user.
The main reason for this is that documentation is only very good if it is consistent.
In addition, there are sometimes hands-on demos within the documentation. And we don't expect any external contributor
to produce them.

Code documentation is stored in the project's [GitHub wiki](../../wiki) so that it is as close to the code as possible.

If you are looking for end user documentation visit our [documentation overview](https://aivot.de/docs) and select
the respective project.




---
Inspired by the great development guideline from the team [@getsentry](https://github.com/getsentry)