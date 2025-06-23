Git is highly configurable, but to begin you will need to set your name and email so the commits you make can be attributed to you. 

Git configuration can be applied glbally, locally, or via conditional includes which is useful if you work across different environments, or like to separate personal and work projects.

Let's git crackin! 

**1. Configure global defaults via the terminal**

* Enter the following commands with the content of the quotes, substituted with your information (afterall, there's only one me and it's not you) and hit enter after each one:

```bash
git config –-global user.name "Glyn Mooney"
git config –-global user.email "glyn.mooney@capgemini.com"
git config --global init.defaultBranch main
```
**Polite notice:** By default, git is configured to use `master` as the default branch name. This, though the default for the tool, hasn't been the norm for some years now.

You will see repositories with the old and the new branch name convention. Just be aware that in both cases, they reprisent the main line of development for the repository.