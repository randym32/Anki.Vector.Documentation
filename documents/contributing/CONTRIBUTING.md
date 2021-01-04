# Contributing

Thanks for being interested in contributing! We're so glad you want to help!

We want contributing to Project Victor to be fun, enjoyable, and educational
for all.  We love receiving contributions from our community, all contributions
are welcome.

There are many ways to contribute.  You can also help us by:

* Answering questions people have have in the forums
* Helping us build and design our website
* Cleaning up our existing documentation, polishing it, fixing our spelling or
  grammar mistakes, and so on
* Create new documentation
* Create an example of some changes / fixes/ hacks
* Creating blog posts, and tutorials about one of Vector's many features
* Reviewing submissions
* Contributing bits that can be incorporated into this or related projects.

Below you will find tips on how to get the most out of your contributing
experience, including GitHub management tips, setup instructions for docs and
code contributions, and more.

<a name="contact"></a>
## Not sure how to start contributing?

If you are worried or don't know where to start, 
you can reach out with questions to anyone from the
Project Victor team on

* [**Official Anki developer forums**](https://forums.anki.com/)
* [**Anki robots Discord chat**](https://discord.gg/FT8EYwu)
* [**GitHub Discussions**](https://github.com/randym32/Anki.Vector.Documentation/discussions)
  is directly integrated with the repository.  You can use this to ask for help
  or share ideas related to improving the documentation or deploying it.

## Pair programming

Other projects offer free [pair programming sessions](https://gatsby.dev/contributing/pair-programming.md)
to the community.  I think that might be a neat idea, if there's something
others would like to work on together......


## How to start contributing and our code of conduct
Below you'll find guides on our community, code of conduct, and how to get
started contributing:

- [Code of Conduct][0]: Read about what we expect
  from everyone participating to make it the most friendly and welcoming
  community.
- [Style Guide][1]: The art of contributing, a.k.a.
  the detailed requirements that will make it more likely your contribution is
  accepted with minimal changes.


> By participating in this project, you agree to abide by our [Code of Conduct][0].
> We expect all contributors to follow the [Code of Conduct][0] and to treat
> fellow humans with respect.


## Important Resources

The important documents and links are on the [front page of the wiki.](../index.md)

## Improving Documentation

If you have a suggestion for the documentation, I would recommend that you take
a stab at making the changes to the documentation.  Simple changes can often be
made without a sophisticated pull release.

For large fixes, please build and test the documentation before submitting the
pull-request to be sure you haven't accidentally introduced any layout or
formatting issues.

### Templates
To help get started with creating a new entry, the document-templates folder
includes some start files that can be used as templates when creating new
documents:

* A template for [how to documents](/documents/document-templates/how-to.md)
* A [generic template](/documents/document-templates/template.md) for other files


### How to Create the HTML and PDF files

The source documentation text files can be found
[documents directory](/documents). The built out files will be placed within a
[site] directory.

First, install the documentation tools:

    pip3 install mkdocs-material
    pip3 install mkdocs-localsearch


Then you can build the html site simply by:

    mkdocs build

### Building a PDF file as well
You can also build the PDF.  First install the tools:

    pip3 install mkdocs-with-pdf

There is some further installation, see the following link for more details:
[https://pypi.org/project/mkdocs-with-pdf/](https://pypi.org/project/mkdocs-with-pdf/)

Rename the "mkdocs.yml" file
Then rename "mkdocs-pdf.yml" to "mkdocs.yml"

To build is the same as before

    mkdocs build


### Whitespace Cleanup

Don't mix code or documentation changes with whitespace cleanup! If you are
fixing whitespace, include those changes separately from your code changes. If
your request is unreadable due to whitespace changes, it will be rejected.

> Please submit whitespace cleanups in a separate pull request.

## Reorganizing Filesystem / directory tree

Don't mix rearranging the location and names of files with code or documentation
changes! If you are rearranging the file system, please include those changes
separately from your code changes. 

> Please submit file system changes in a separate pull request.

<a name="pull-request-process"></a>
## Pull Request Process

Please see the [pull requests page](pull-requests.md) for the process of
submitting your changes to the prooject and incorporating feedback.
are happy with your changes first!


[0]: code_of_conduct.md
[1]: style-guide.md
[2]: https://egghead.io/series/how-to-contribute-to-an-open-source-project-on-github
[3]: http://makeapullrequest.com/
[4]: http://www.firsttimersonly.com
[5]: https://gist.github.com/Chaser324/ce0505fbed06b947d962
[7]: http://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html


_Credits: This page was adapted from an [EmbeddedArtistry template](https://github.com/embeddedartistry/embedded-resources/blob/master/docs/CODE_OF_CONDUCT_template.md)_
