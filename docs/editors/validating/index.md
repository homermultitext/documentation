---
layout: page
title:  How to validate
parent: Guide for editors
nav_order: 4
---



## One-time setup

Organize your workspace like this:

- make a folder called `hmt` someplace convenient (maybe your Desktop or Documents folder)
- from a bash shell, `cd` into your `hmt` folder.  (Use `pwd` to verify that you're in the right place.)
- clone your editing repository


Here's a [comparison of where you'll find files in your host OS and Docker container](https://github.com/neelsmith/transmission-evolution/wiki/File-system-layout).

## Starting the Docker container

First make sure Docker is running. Then `cd` into your `hmt` folder (which in turn contains your editing repository), and start the container:

- in Mac OS:

    docker run -ti --rm -v $(pwd):/work neelsmith/hmteditor:1.0.0

- in Windows 10:

    winpty docker run -ti --rm -v /$(pwd):/work neelsmith/hmteditor:1.0.0


This will start the Docker container and put you in a bash shell in the Docker environment.


## Running the validation script

- The directory named `work` in your Docker container is shared with the directory where you started the container.  If you started the container in `hmt`, its contents appear in Docker as `work`.  To `cd` into your editing repository, first `cd work`, the `cd` into your editing repository.
- Run `sbt console`
- In the `sbt console`, run `:load scripts/mom2020.sc`.  (Notice the leading colon!)
- Use the `validate` method to write validation reports.
- In your host OS (Mac OS, Windows), read the validation reports, fix any errors, revalidate, until you have no remaining errors.

When you are done, type `:quit` to exit the `sbt console`. (Again, leading colon.)

Now you should be back at the bash shell in your Docker container.


## Exiting the Docker container

Type `exit`.  This will stop the Docker container, and put you back at either your Terminal (Mac) or QuickStart Terminal (Windows) prompt.
