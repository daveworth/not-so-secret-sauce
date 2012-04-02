---
layout: topic
title: Onboarding Process for Designers
---

Working with Highroove Studios means you’ll be working with an established
team of experienced developers on new and ongoing projects. As we learn and
expand our experiences, we constantly improve our process.

However, we have found a standard suite of tools that has made jumping from
one project to another and contributing to most of them almost trivial. There
are gotchas at every turn due mostly to the complexity of what we do, but
we’ve made strides to avoid them as much as possible.

## Prerequisites

Highgroove does all of our development on Mac OS X. We’ll assume you’ll be
doing likewise.

In order to get started, you must be able to compile various libraries and
tools. XCode is the essential piece that allows you to do this.

[Download Xcode](https://developer.apple.com/xcode/). Choose the “Mac Dev
Center”. You should be able to log in with your existing Apple account, but
you may be required to sign up for a free Apple account if you do not have
one. XCode is also available on the DVD that came with your computer if you
still have that!

## Initial Setup

In the past we’ve had to install many dependencies, tools, and libraries by
hand. Now, we have automated systems to make this painless.

[Cinderalla](http://www.atmos.org/cinderella/) is just such a tool.

Open the Terminal application found in /Applications/Utilities/ and paste the
following snippet in then press Enter to make sure it starts:

    curl https://github.com/atmos/cinderella/raw/master/bootstrap.sh -o - | sh

This process can take about 45 minutes to an hour and a half, and sometimes
more.

This will install standard tools like Ruby, Rails, MySQL, RVM, and Homebrew.

## Accessing Projects

Projects we work on are hosted at [GitHub](http://github.com). This means that
our source code is revisioned using Git, a tool for tracking all changes on a
repository over time. You too will be using Git to manage your changes.

GitHub has excellent [Help documentation](http://help.github.com/) for getting
started and solving problems. The “Getting started with Git and GitHub”
section on that page will help you get set up. I will document the minimum
steps necessary:

First, you will need to install Git. Open Terminal up again and paste this in
to run:

    brew install git-core

Once this is done, you will be able to use Git. You will need a [GitHub
Account](http://github.com/account) in order to access our projects. Create an
account there then follow the [instructions to set your username and email in
Git](http://help.github.com/set-your-user-name-email-and-github-token/) on
your machine (so your commits will belong to you).

Finally, you’ll need to [setup SSH keys](http://help.github.com/mac-set-up-
git/) so that your computer can talk to GitHub.

## Running An App

More than likely you will already have at least one project you are working
on. If you don’t already have the source code on your machine, you’ll need to
copy (or clone) it to your computer. Try this in Terminal:

    git clone git@github.com:highgroove/your_project.git
    cd your_project

You’ll need to replace your_project with the name of the project you’re
working on.

*TODO: Write a simple test application with bundler, migrations, et al to go
through simplified process and make sure minimums are setup. (MySQL!)*

## Working on Projects

*TODO: Document making changes, committing them, and pushing them up.*

## Glossary

Here are a few terms you’ll want to know:

* RVM: Ruby Version Manager - simplifies managing different versions of Ruby and Gems related to specific projects
* Homebrew - installs software dependencies, like MySQL and git
* Git - a system for managing versions and the history of your source code
* [GitHub](http://github.com) - a hosting and collarboration service for your Git repositories
* Ruby - the language that Rails is written with
* Rails - a web application framework, used to simplify building complicated business apps
* RubyGems - a bundle of code such as a library or tool written in Ruby
* Terminal - a tool for running commands and interfacing with the filesystem (used for Git among many other things)
