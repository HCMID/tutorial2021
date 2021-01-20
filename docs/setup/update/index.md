---
title: "Updating your validation notebook"
layout: page
nav_order: 2
parent:  "Setting up a repository"
grand_parent:  "HC MID tutorial"
---


# How do I update my validation notebook?


You can always find the current version of the MID validator notebook in [this github repository](https://github.com/HCMID/validatormodel).  If the version of the validation notebook in your repository does not match the version listed there, you should update your notebook.

You need to update three files in your project's `notebooks` directory.  Replace these three files with the current versions the the [`validatormodel`](https://github.com/HCMID/validatormodel) repository.

- `notebooks/Project.toml`
- `notebooks/Manifest.toml`
- `notebooks/midvalidator-VERSION.jl`

You may rename `midvalidator-VERSION.jl` to anything you like; `Project.toml` and `Manifest.toml` must have exactly those names.  You do not need to update the `MID.toml` file where your team configures the name and github repository of your project.
