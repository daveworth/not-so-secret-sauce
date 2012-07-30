---
layout: topic
title: Onboarding Process for Designers
---

Working with us means you'll be working with an established team of experienced
developers on new and ongoing projects. As we learn and expand our experiences,
we constantly improve our process.

However, we have found a standard suite of tools that has made jumping from one
project to another and contributing to most of them almost trivial. There are
gotchas at every turn due mostly to the complexity of what we do, but we've
made strides to avoid them as much as possible.

## Prerequisites

We do all of our development on Mac OS X. We'll assume you'll be doing
likewise.

## Initial Setup

### RailsInstaller

Download and install [RailsInstaller](http://www.railsinstaller.org/). It will
install most of the tools we use.

Be sure to watch the [introductory video](http://vimeo.com/43823464). While
not everything may yet make sense, it will help make sure you understand
the basics of what you're installing.

### Postgres

Most of the applications we build are backed by the PostgreSQL database.

Download and install [Postgres.app](http://postgresapp.com).

## Accessing Projects

Our projects use the Git source control system to manage changes. We use
[GitHub](http://github.com) to host a Git repository that all developers
and designers working on the project can access.

RailsInstaller (above) already installed Git for you, but there are a few more
steps involved to getting setup with GitHub. Read over and complete the steps
for [setting up git](https://help.github.com/articles/set-up-git), except *you
don't need to install Git as it's already been installed by RailsInstaller*.

## Running An App

To make sure everything worked, try checking out our demonstration repository:

    git clone https://github.com/highgroove/tacostand.git

Now you have a copy of the app `tacostand` on your computer. The application
contains a `README.md` file, this file contains the all the instructions needed
for getting the application running. You can view this file with any text
editor. Take a look at this file and follow its instructions.

Any project you work on should have a similar `README` file that you can use to
get an application working.

If everything goes smoothly you should be able to get the application running.
If you have trouble on any step, you should recieve some sort of error message
describing what is failing. This will likely point back to some part of the
technology stack that might not be set up properly. With this information a
developer should be able to help you solve your problem.

## Working on Projects

It's important to make sure you stay up to date. Before you start work, make
sure you have the latest code by typing this in Terminal:

  git fetch origin

When working on design things it is often best to work in your own branch.
Continuing with our tacostand example from above, assuming you are in your
`tacostand` directory type:

    git checkout -b "adding_styling_for_screens" origin/master

With this command you have created a new branch and checked it out. If type

    git branch

you will see all your branches and it will show you which branch you are
working on.

Let's make things prettier! How about adding a CSS file with some new styles?
Let's say you created a file called `screen.css` and added that to the
`app/assets/stylesheets` folder. Since our project uses the [asset
pipline](http://guides.rubyonrails.org/asset_pipeline.html), we don't have to
worry about specifily including this file in the markup.

Now that your are happy with your are changes, they are ready to be added the
production version of the application.

First let's commit this file to our `adding_styling_for_screens` we are
currently working on:

    git add app/assets/stylesheets/screen.css
    git commit -a "Adds some awesome new styles"

When you're done adding styling, "push" your branch to GitHub (in this case
Git knows GitHub as the "origin" repository):

    # Note that this won't actually work on tacostand because you will not
    # have authorization to push to that repository
    git push origin adding_styling_for_screens

Finally, create a "pull request" on GitHub. A pull request will notify other
developers that you want to add changes to the main branch. They will review
it and "merge" in your changes after making sure everything looks good.
Instructions on how to open a pull request are available [in the GitHub
documentation](https://help.github.com/articles/using-pull-requests). Note that
we use the "shared repository model."

## Glossary

Here are a few terms you'll want to know:

* RVM: Ruby Version Manager - simplifies managing different versions of Ruby
  and Gems related to specific projects
* Homebrew - installs software dependencies, like MySQL and git
* Git - a system for managing versions and the history of your source code
* [GitHub](http://github.com) - a hosting and collarboration service for your
  Git repositories
* Ruby - the language that Rails is written with
* Rails - a web application framework, used to simplify building complicated
  business apps
* RubyGems - a bundle of code such as a library or tool written in Ruby
* Terminal - a tool for running commands and interfacing with the filesystem
  (used for Git among many other things)
