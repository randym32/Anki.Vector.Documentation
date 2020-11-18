# Contributing

We want contributing to Project Victor to be fun, enjoyable, and educational
for all.  We love receiving contributions from our community, all contributions are welcome, including:

* issues (bug reports),
* new documents
* updates and tweaks,
* blog posts,
* workshops
* etc

There are many ways to contribute, including submitting bug reports, improving documentation, submitting feature
requests, reviewing new submissions, or contributing bits that can be incorporated into the project.

## Not sure how to start contributing?

If you are worried or don't know where to start, 
you can reach out with questions to anyone from the
Project Victor team on

* [**Official Anki developer forums**](https://forums.anki.com/)
* [**Anki robots Discord chat**](https://discord.gg/FT8EYwu)


## Pair programming

Other projects offer free [pair programming sessions](https://gatsby.dev/contributing/pair-programming/)
to the community.  I think that might be a neat idea, if there's something others
would like to work on together......


## Code of Conduct

> By participating in this project, you agree to abide by our [Code of Conduct][0]. We expect all contributors to follow the [Code of Conduct][0] and to treat fellow humans with respect.


## Important Resources

The important documents and links are on the [front page of the wiki.](../index.md)

## Improving Documentation

If you have a suggestion for the documentation, I would recommend that you take a stab at making the chnages to the
documentatin.

For large fixes, please build and test the documentation before submitting the pull-request to be sure you
haven't accidentally introduced any layout or formatting issues.

```
Provide instructions on building and viewing documentation
```

## Contributing Code

This section is used to get new contributors up and running with dependencies, development, testing, style rules, formatting rules, and other things they should know.

If you have a label for beginner issues, talk about that here so they know where to look:

> Unsure where to begin contributing to Atom? You can start by looking through these beginner and help-wanted issues: Beginner issues - issues which should only require a few lines of code, and a test or two. Help wanted issues - issues which should be a bit more involved than beginner issues.

Working on your first open source project or pull request? Her are some helpful tutorials:

* [How to Contribute to an Open Source Project on GitHub][2]
* [Make a Pull Request][3]
* [First Timers Only][4]

### Getting Started

Install these dependencies:

```
with some examples
```

Provide some instructions for your workflow (e.g. fork the repository)

> You will need to fork the main repository to work on your changes. Simply navigate to our GitHub page and click the "Fork" button at the top. Once you've forked the repository, you can clone your new repository and start making edits.

> In git it is best to isolate each topic or feature into a “topic branch”. While individual commits allow you control over how small individual changes are made to the code, branches are a great way to group a set of commits all related to one feature together, or to isolate different efforts when you might be working on multiple topics at the same time.

> While it takes some experience to get the right feel about how to break up commits, a topic branch should be limited in scope to a single issue

```
# Checkout the master branch - you want your new branch to come from master
git checkout master

# Create a new branch named newfeature (give your branch its own simple informative name)
git branch newfeature

# Switch to your new branch
git checkout newfeature
```

For more information on the GitHub fork and pull-request processes, [please see this helpful guide][5].

### Finding an Issue

The list of outstanding feature requests and bugs can be found on our on our [GitHub issue tracker][6]. Pick an unassigned issue that you think you can accomplish and add a comment that you are attempting to do it.

Provide notes on different kinds of issues or labels

> `starter` labeled issues are deemed to be good low-hanging fruit for newcomers to the project
> `help-wanted` labeled issues may be more difficult than `starter` and may include new feature development
> `doc` labeled issues must only touch content in the `docs` folder.


### Style Guidelines

If your code has any style guidelines, add them here or provide links to relevant documents. If you have an automated checker, make sure to provide instructions on how to run it.


### Whitespace Cleanup

Don’t mix code changes with whitespace cleanup! If you are fixing whitespace, include those changes separately from your code changes. If your request is unreadable due to whitespace changes, it will be rejected.

> Please submit whitespace cleanups in a separate pull request.


## Pull Request Process

Do you have any labelling conventions?

Add notes for pushing your branch:

> When you are ready to generate a pull request, either for preliminary review, or for consideration of merging into the project you must first push your local topic branch back up to GitHub:

```
git push origin newfeature
```

Include a note about submitting the PR:

> Once you've committed and pushed all of your changes to GitHub, go to the page for your fork on GitHub, select your development branch, and click the pull request button. If you need to make any adjustments to your pull request, just push the updates to your branch. Your pull request will automatically track the changes on your development branch and update.

1. Ensure any install or build dependencies are removed before the end of the layer when doing a
   build.
4. You may merge the Pull Request in once you have the sign-off of two other developers, or if you
   do not have permission to do that, you may request the second reviewer to merge it for you.

### Review Process

The process is likely to be lite for many changes.

Many pull requests are likely to open for several days, until the core team can apporve them in Github.
In some cases, multiple people will have the chance to review/comment. 


### Addressing Feedback

Once a PR has been submitted, your changes will be reviewed and constructive feedback may be provided. Feedback isn't meant as an attack, but to help make sure the highest-quality code makes it into our project. Changes will be approved once required feedback has been addressed.

If a maintainer asks you to "rebase" your PR, they're saying that a lot of files has changed, and that you need to update your fork so it's easier to merge.

To update your forked repository, follow these steps:

```
# Fetch upstream master and merge with your repo's master branch
git fetch upstream
git checkout master
git merge upstream/master

# If there were any new commits, rebase your development branch
git checkout newfeature
git rebase master
```

If too much code has changed for git to automatically apply your branches changes to the new master, you will need to manually resolve the merge conflicts yourself.

Once your new branch has no conflicts and works correctly, you can override your old branch using this command:

```
git push -f
```

Note that this will overwrite the old branch on the server, so make sure you are happy with your changes first!

## How people can contribute

* You can help us answer questions our users have 
* You can help build and design our website
* You can help clean up our existing documentation, polishing it and so on
* You can help create new documentation

* Create an example of some changes / fixes/ hacks

[0]: code_of_conduct.md
[1]: style_guidelines.md
[2]: https://egghead.io/series/how-to-contribute-to-an-open-source-project-on-github
[3]: http://makeapullrequest.com/
[4]: http://www.firsttimersonly.com
[5]: https://gist.github.com/Chaser324/ce0505fbed06b947d962
[6]: link/to/your/project/issue/tracker
[7]: http://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html
