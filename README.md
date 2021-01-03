# Project Vector Documentation Wiki

This is a prototype of  documentation for a  Project Vector Documentation Wiki.
A prototype  should be viewable at [https://randym32.github.io/Anki.Vector.Documentation](https://randym32.github.io/Anki.Vector.Documentation) for review

The Project Vector Documentation Wiki is generated via the [Material for mkdocs Documentation
Generator](https://github.com/squidfunk/mkdocs-material). It can be scripted to pull changes
from github or other git repository.

It has enough to sketch out the idea, but it isn't complete.

The thought is after shaking out the prototype is to put this into an main project github
repo (like https://github.com/GooeyChickenman/victor), and build the docs for project-victor.org
from there. Possibly using a script that checks for git repo changes.?
The documentation git repo can be forked ad infinitum, and changes -- such as those with lots
of files --  can be sent upstream with pull requrests.
The contributions folder wll describes how this works, as we shake it out..

One thing to decide is what the main project github repo will be:

* https://github.com/GooeyChickenman/victor has been a good goto place.
* The drawback is that https://github.com/GooeyChickenman/victor has the problem that only
  a few people have access to contribute or approve directly, and we can't authorize people.
  Ideally we could expand the approvers, contributers so that any changes go smoothly, with little bottleneck.

(Todo need to ensure it places nice with rest of site)

I'm also using this to explore as a small playbox/prototype template for source-code base
repositories that will come up -- things like the home server code base, OSKR, various modules,
etc etc etc

I am aware that a wiki style can produce lots of memos/notes that don’t feel cohesive when put together.
But it is not practical to put all into a single cohesive work, and not everything needs it.  Perhaps
we can get cohesive larger works later from these.

## Creating the HTML and PDF files

The source documentation text files can be found [documents
directory](./documents). The built out files
will be placed within a [site] directory.

To install:

    pip3 install mkdocs-material
    pip3 install mkdocs-localsearch

To build the html site:

    mkdocs build

The view can click on the edit icon and edit the files in github.
You can, of course, fork the git repo, update until your satisfied
and then push upsatem.
The goal is to write a script and pull updates, do a test build of the html,
and if it passes, make it the live site.

### Building a PDF file as well
You can also try to build

    pip3 install mkdocs-with-pdf

There is some further installation, see the following link for more details:
https://pypi.org/project/mkdocs-with-pdf/

Rename the "mkdocs.yml" file
Then rename "mkdocs-pdf.yml" to "mkdocs.yml"

To build is the same as before

    mkdocs build


### Browser configuration notes
The documentation, when browsed from a local filesystem, may require tweaking
the browser.  If you run into problems here are some tips:

#### Firefox
Go to about:config and make change to the following:
* security.fileuri.strict_origin_policy set to false
* privacy.file_unique_origin  set to false


## Getting help
Being a new library, there is not yet an established usage pattern, clear place
and patterns for getting help.  Try

* [**Official Anki developer forums**](https://forums.anki.com/)
* [**Anki Vector developer subreddit**](https://www.reddit.com/r/ankivectordevelopers)
* [**Anki robots Discord chat**](https://discord.gg/FT8EYwu)

## Contributing
View the [Anki.Vector.Documentation GitHub Project](https://github.com/randym32/Anki.Vector.Documentation)
for information on contributing.

## Grateful Acknowledgements and Special Thanks

The [Gatsbyjs](https://gatsby.dev/) project is a real exemplar on documenting
how a community should work.
