# Vector Enhancement Proposals
Memos, cheekily named for Python’s memo system.
At the moment, I see these as proposals for changes to the software and files on a Vector.
(Proposals for changes to the site or documentation, or build tools, etc should go elsewhere.)

This would be relevant for changes, esp substantial changes, that you might like many people to adopt.

File Format:

* I’m going to try to use markdown most often, but
* PDF/HTML export for normal human readers

Common elements, to make it easier to read and management them:

The first part is the markdown front matter: it begins and ends with --- and the lines inside
contain YAML.  This lets other tools extract the basics.

```
---
title: VEP123 - The name of the VEP (only a few words)
summary: An ptional description of the proposal, if the title is too short
authors:
    - Author Name 
date: 2022-07-10
---
```

The title starts with "VEP" and a unique (serial) number.  It is followed by a brief description or topic of the
proposal.  The other fields are self explanatory, and helps track the info

Other outline, organization:

- Description of the changes
- Some Design decisions
- Documentation
- Cavaets
- Status
- References
- Change history synopsis (this is for people)


