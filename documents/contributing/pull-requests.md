# Pull Requests

This document describes what you needed to know about the pull request process.

A pull request is how you submit your changes to the project.
Before you make any changes, please read the [contributing page](CONTRIBUTING.md)
for information regarding contributions to project overall.  This will help you
in making your changes fit within the project and its style; as well as the
steps you must do before creating a pull-request.


## What is a Pull Request (PR)?

As described above, a pull request is how you submit changes to this project.
It is a _request_ that the project pull in your changes.  Here's how the folks
at GitHub [define a pull request][0]:

> Pull requests let you tell others about changes you've pushed to a branch in
> a repository on GitHub. Once a pull request is opened, you can discuss and
> review the potential changes with collaborators and add follow-up commits
> before your changes are merged into the base branch.

The pull request allows others to review the changes, test them, and provide
feedback -- including requests to makes to the changees, so that they better
fit into the project.

<a name="pull-request-process"></a>
## Pull Request Process

Once you have completed the changes on your local development environment,
tested them, and so fprth, the next steps is to create a pull request.
Be sure to check the [contributing guide](CONTRIBUTING.md) for additional
steps and tips to ensure that your changes will fit with the project.

> When you are ready to generate a pull request, either for preliminary review,
> or for consideration of merging into the project you must first push your
> local topic branch back up to GitHub:

```
git push origin newfeature
```



> Once you've committed and pushed all of your changes to GitHub, go to the
> page for your fork on GitHub, select your development branch, and click the
> pull request button. If you need to make any adjustments to your pull
> request, just push the updates to your branch. Your pull request will
> automatically track the changes on your development branch and update.

1. Ensure any install or build dependencies are removed before the end of the
   layer when doing a build.
2. You may merge the Pull Request in once you have the sign-off of two other
   developers, or if you do not have permission to do that, you may request the
   second reviewer to merge it for you.

### Review Process

After a pull request has been sent to the repository, the team and community
may suggest modifications to the changes you have submitted.

Many pull requests are likely to open for several days, until the core team
can approve them in Github.  In some cases, multiple people will have the
chance to review/comment. 

Please check your pull request for comments, feedback, and suggested changes:

- Review the suggested changes using the "View changes" button.
- [Commit](https://help.github.com/en/articles/incorporating-feedback-in-your-pull-request#applying-suggested-changes) the suggestions.
- [Discuss suggestions](https://help.github.com/en/articles/about-conversations-on-github) to ask questions about the suggested changes.
- Incoprorate the [suggestions to your changes](https://help.github.com/en/articles/incorporating-feedback-in-your-pull-request)


### Addressing Feedback

Once a PR has been submitted, your changes will be reviewed and constructive
feedback may be provided. Feedback isn't meant as an attack, but to help make
sure the highest-quality workmanship makes it into our project. Changes will be
approved once required feedback has been addressed.


If a maintainer asks you to "rebase" your PR, they're saying that a lot of
files has changed, and that you need to update your fork so it's easier to
merge.

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

If too much code has changed for git to automatically apply your branches
changes to the new master, you will need to manually resolve the merge
conflicts yourself.

Once your new branch has no conflicts and works correctly, you can override
your old branch using this command:

```
git push -f
```

Note that this will overwrite the old branch on the server, so make sure you
are happy with your changes first!


## Additional resources

- [Creating a pull request](https://help.github.com/en/articles/creating-a-pull-request) from GitHub
- [Configuring a remote for a fork](https://help.github.com/en/articles/configuring-a-remote-for-a-fork)
- [Which remote URL should I use?](https://help.github.com/en/articles/which-remote-url-should-i-use)
- [Git Branching and Merging](https://git-scm.com/book/en/v2/Git-Branching-Basic-Branching-and-Merging)
- [Feature Branching and Workflows](https://git-scm.com/book/en/v1/Git-Branching-Branching-Workflows)
- [Resolving merge conflicts](https://help.github.com/en/articles/resolving-a-merge-conflict-on-github)


[0]: https://help.github.com/en/articles/about-pull-requests
[1]: http://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html


_Credits: This page was adapted from an [EmbeddedArtistry template](https://github.com/embeddedartistry/embedded-resources/blob/master/docs/)_
_and adapted from the
[Gatsbj.js project](https://github.com/gatsbyjs/gatsby/blob/master/docs/contributing/)_
