---
title: Release
has_children: false
nav_order: 7
---

## Release and versioning

The released software is a desktop application, available to everyone just by simply following the next sections (Deployment, User Guide) that cover the installment and usage of it. The application is released directly on github via commits and push, everything after thorough control of errors and functioning requirements.

With the use of semantic versioning along with the template given us the controls are strict. Everything needs to be automatically controlled every new commit (subsequently every release) by GitHub Actions. We added this functionality towards the end of the project but it added a layer of precision while committing the last versions of the project.

Semantic versioning was used to correctly commit new feature or fixes in this project, along with convential commits they both can help tremendously in the automatization of the project development. Conventional commits are used to have a common ground between developers to explain and have a way of understanding each others work. Semantic Versionaning is used to distinguish every release from the other, giving us a way to release major versions, minor modifications and patches to known problems, as the semantic versioning number explain (MAJOR.MINOR.PATCH).

### Choice of the license

We chose the Apache 2.0 license. It is one of the most permissive licences available for software projects, it gives permission to everyone araound the globe to use our code without fearing problems of any sorts, the second choice was the MIT License, very similar but with one minor difference, if someone modifies and use the code shown in our application in some sort of way they would need to explicitly state that modifications were applied. This puts a clear cut separation between the work done and who did it. Essential in online open source projects.
