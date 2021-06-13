---
title: "Hugo and github pages setup"
date: 2021-06-13T13:48:24-07:00
---

# Hugo?

In which I try to set up github pages using Hugo.

- Following instructions from [github pages startup](https://pages.github.com/) up to step 3   
- Instructions from [hugo](https://gohugo.io/getting-started/quick-start/), although replacing step 3 with the alternate instructions from the [geekdoc theme](https://geekdocs.de/usage/getting-started/#option-1-download-pre-build-release-bundle)
- Edited `./config.toml` to include the line `publishDir = "docs"`
- `hugo -D`
- push to github
- and we are live.



## Wrong turns:

### Automatic build on commit

- Considered, but discarded the idea [here](https://gohugo.io/hosting-and-deployment/hosting-on-github/), might revisit later to eliminate the hugo building step before pushing to master.

### git submodule for theme
I initially did not follow geekdocs instructions and tried to do the github suggested approach of making a submodule, and that created many useless files in my repo.  Following [this](https://stackoverflow.com/questions/1260748/how-do-i-remove-a-submodule) suggestion, I managed to get rid of the dependency, and then followed the directions [here](https://geekdocs.de/usage/getting-started/#option-1-download-pre-build-release-bundle) again:
