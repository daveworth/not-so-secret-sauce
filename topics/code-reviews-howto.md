---
layout: topic
title: Highgroove Code Reviews HowTo
description: How Highgroovers give back to the open-source community
image_hint_url: http://www.flickr.com/photos/sebastian_bergmann/3991540987/
---

Highgroove team members are tasked with performing Code Reviews every week.

We do these for several reasons:

* Peer Review produces better code
* Sharing knowledge of projects keeps all developers in the know (avoids hit-by-bus scenario)
* Code Reviews exercise the mind and keep us all writing similar, idiomatic code. See: http://napkin.highgroove.com/articles/2011/02/06/cowboy-girl-programmers-dont-live-here

## What's the lightweight process for performing a Code Review?

If you have been assigned a code review for a developer, ask that developer or find out what projects they have been working on. Make sure you have access to the code (usually on github). See section: “What if the code I need to review is not on github?”

Simply go through the history, clicking on commits until you have found commits that either haven’t been reviewed, or you have a sufficient amount. 

Here are some additional things to review:

* README - is it there, documented, does it have any troubleshooting?
* Bootstrapping - is there anything necessary to get the project running?
* Tests - check overall, not just the checked in ones.
* Troubleshooting from any problems / support requests from the week
* Use of new gems (rcov, cover_me, etc.)
* Use of patterns / ways of implementing solutions

## What is a sufficient amount of code to Review?

You should at least quickly glance over every single commit the reviewee made in
the last 7 days or so (since their last review).  This probably means finding
every commit more recent than the last comment on their projects.

Make sure to leave comments that are representative of Highgroove's core values, and don't mention other projects in your comments. Remember, every time you comment, that comment get's sent directly to the client and there is no undo!

## What if the code I need to review is not on github?

It’s easy to create a repository and push remotely to it:

Create the repository on github (under the highgroove organization).
add a “remote” to your git repository, by editing the git config (or adding remote): 

<pre>

[remote "origin"]
fetch = +refs/heads/*:refs/remotes/origin/*
url = git@github.com:clients-private-repo/project-name.git

[remote "highgroove"]
fetch = +refs/heads/*:refs/remotes/origin/*
url = git@github.com:highgroove/project-name.git

[branch "master"]
remote = origin
merge = refs/heads/master

</pre>

*or*

<pre>

git remote add highgroove git@github.com:highgroove/project-name.git
git push

</pre>

You’ll need to ask someone with access to the code to do this for you.

## How can I quickly review code from 1 week ago?

This command gets all commits by "Will" from 1 week ago:

<pre>

git log 'master@{1 week ago}'..master --author='Will' --full-diff -p

</pre>

