---
layout: topic
title: Code Reviews
---

Every week, every developer is assigned a random developer to perform a Code Review on.

We do these for several reasons:

* Peer Review produces better code
* Sharing knowledge of projects keeps all developers in the know (avoids hit-by-bus scenario)
* Code Reviews exercise the mind and keep us all writing similar, idiomatic code. See: <a href=">http://napkin.highgroove.com/articles/2011/02/06/cowboy-girl-programmers-dont-live-here">cowboy/girl programmers don't live here</a>

## I'm new here!

For your first few code reviews, you should pair with someone else for doing the actual review. Code reviews are extremely important, and aren't something that comes naturally to most people until you've done a few of them. A recorded <a href="/topics/tech-talks.html">Tech Talk</a> on this is coming soon.

## The Process

Each week, you'll be assigned another developer to review. Find out what projects they have worked on, and queue up every commit they have made since the last time they were reviewed (Typically 1 week ago). If you don't have access to their code for some reason, let the developer know and there are likely a few quick buttons that can be pushed.

Take a look at each commit and leave in-line comments for anything you notice including things like:

* "This method is named poorly, is too complex, and is hard to understand. I recommend ..."
* "Wow! I never knew you could do things this way. Nice!"
* "Where are the associated tests for this commit?"
* "You're implementing something I've seen a Gem for, have you seen X?"

In addition to commits, it's good to give the project a quick review for other things that may need improvement:

* Is a README present, thorough, and does it provide everything a new developer might need to get the project up and running?
* Is there a well populated test suite that uses best practices and provides good coverage?
* Is the Gemfile documented with explanations for what any Gems do that you haven't heard of?
* Does the project architecture follow established best practices and patterns?

Be professional. Remember that clients, designers, and everyone else involved on a project can see your comments!

If you have any comments that compare the project you are reviewing to other projects, send these comments via e-mail directly to the developer you are reviewing. Some projects that we work on are confidential.

Our process is extremely similar to the process Dan Kubb describes in [Ruby Rogues 047 - Coding Disciplines](http://rubyrogues.com/047-rr-coding-disciplines/) as he practices at CodeBenders.  His description of using Github and the multiple "layers" of review he performs are well worth the listen (starting at around 29m30s in the podcast).

## Reviewing code that isn't on Github

The easiest way to do this is to get the code on Github. You'll need to ask someone with access to the code to do this for you. Create a new private repository on Github and push the code to it by adding it as an additional remote.  Here are two ways to do this:

<pre>
[remote "origin"]
fetch = +refs/heads/*:refs/remotes/origin/*
url = git@github.com:clients-private-repo/project-name.git

[remote "my-organization"]
fetch = +refs/heads/*:refs/remotes/origin/*
url = git@github.com:my-organization/project-name.git

[branch "master"]
remote = origin
merge = refs/heads/master
</pre>

*or*

<pre>
git remote add my-organization git@github.com:my-organization/project-name.git
git push
</pre>

If the code cannot be pushed to Github, you should get in touch with the developer you are reviewing to schedule a time to go over their commits. You may need to share their screen to connect to a firewall install of Github or some other crazy thing.

## What else?

Quiet, private, code reviews are nice but there are a few other things we like to do occasionally to better achieve the goals at the top of this page:

* 'Pairing Hours' in the conference room:  We'll reserve the conference room for a few hours. Developers are encouraged to stop by with any questions about something they have been working on, or to sit down with other developers to help them out. This is helpful for resolving specific issues.

* 'Code Review: Live':  Occasionally, we'll do a 'live' code review with a bigger audience. The code is projected on the wall or a big-screen TV and anyone in attendance can offer up comments and suggestions. This is helpful for architectural changes and new developers, but usually only makes it through a few commits.

You might notice your inbox filling up with e-mail notifications for comments on things that you may not want to scroll through.  Head over to <a href="https://github.com/settings/notifications">your github 'notication center'</a> and turn off 'Comments on commits in my repositories' and your e-mail inbox should be pretty limited to your actions.

