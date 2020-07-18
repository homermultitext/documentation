---
layout: page
title:  File layout
parent: Guide for editors
nav_order: 5
---


## Setting up validation

Create a folder named `hmt` on your computer, and inside that folder, clone your editing repository.

Do all of your `git` work (pulling, pushing) in your host operating system (Mac, Windows,...)

Now you can [start the docker container](https://github.com/neelsmith/transmission-evolution/wiki/Validating) from the `hmt` folder.  The contents of your `hmt` folder will appear in the docker container in a folder named `work`.

## Finding files in your two environments

In your host operating system, you start the docker container in `hmt` (colored light brown in the illustration below).  To use git in your repository, you'll need to `cd` into your team's editing repository.

In the docker container, you'll start out in the root of the file system (or `/`, colored light brown in the illustration below). To start up a validation script in your editor's repository, you'll need to `cd` first into `work` (which includes all the contents of `hmt` in your host OS), and then `cd` into your editing repository.


The root of your editing repository is highlighted in blue. The only folders with files you need to edit are highlighted in green. The `scripts` folder (folder) contains the validation script you will run to validate your editing.  The `validation` folder (purple) is where you will find validation reports saved for you to evaluate.








| Host OS  | Docker container |
| --- | --- |
| ![host](https://neelsmith.github.io/transmission-evolution/imgs/host-os-colored.png) | ![docker](https://neelsmith.github.io/transmission-evolution/imgs/docker-files-colored.png) |
