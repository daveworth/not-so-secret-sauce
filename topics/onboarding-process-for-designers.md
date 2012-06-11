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

In order to get started, you must be able to compile various libraries and
tools. XCode is the essential piece that allows you to do this.

[Download Xcode](https://developer.apple.com/xcode/). Choose the "Mac Dev
Center". You should be able to log in with your existing Apple account, but you
may be required to sign up for a free Apple account if you do not have one.
XCode is also available on the DVD that came with your computer if you still
have that!

## Initial Setup

In the past we've had to install many dependencies, tools, and libraries by
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
started and solving problems. The "Getting started with Git and GitHub" section
on that page will help you get set up. I will document the minimum steps
necessary:

First, you will need to install Git. Open Terminal up again and paste this in
to run:

 brew install git-core

Once this is done, you will be able to use Git. You will need a [GitHub
Account](http://github.com/account) in order to access our projects. Create an
account there then follow the [instructions to set your username and email in
Git](http://help.github.com/set-your-user-name-email-and-github-token/) on your
machine (so your commits will belong to you).

Finally, you'll need to [setup SSH
keys](http://help.github.com/mac-set-up-git/) so that your computer can talk to
GitHub.

## Running An App

More than likely you will already have at least one project you are working on.
If you don't already have the source code on your machine, you'll need to copy
(or clone) it to your computer. Try this in Terminal:

 git clone git@github.com:highgroove/tacostand.git

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

When working on design things it is often best to work in your own branch.
Continuing with our tacostand example from above, assuming you are in your
`tacostand` directory type:

 git checkout -b "pretty_branch"

With this command you have created a new branch and checked it out. If type

 git branch

you will see all your branches and it will show you which branch you are
working on.

Let's make things prettier! How about adding a CSS file with some new styles?
Let's say you created a file called `screen.css` and added that to the
`app/assests/css` folder. Since our project uses the [asset
pipline](http://guides.rubyonrails.org/asset_pipeline.html), we don't have to
worry about specifily including this file in the markup.

Now that your are happy with your are changes, they are ready to be added the
production version of the application.

First let's commit this file to our `pretty_branch` we are currently working
on:

 git add app/assests/css/screen.css git commit -a "Adds some awesome new
styles"

Next we want to get any changes that might have happened while we are working.

 git fetch

Now that we have the changes we need to rebase our branch against any changes
that might have happened in the master branch:

 git rebase master

Now your commits are made and your branch is up to date. What you do next will
vary depending on project to project. Most likely you will want to push your
`pretty_branch` to github and submit a pull request.

 git push origin pretty_branch

Once the branch has been pushed you can visit the branch on github and press
the button to submit a pull request.

However, in some special cases you might need to go ahead an fold those changes
into master and pushed the merged version of master:

 git checkout master git merge pretty_branch git push origin master

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
