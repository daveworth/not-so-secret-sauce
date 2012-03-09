---
layout: topic
title: Our Open-Source Methodology at Highgroove
description: How Highgroovers give back to the open-source community
image_hint_url: http://farm3.staticflickr.com/2354/2312329520_cd26fbd46d_m.jpg
---

<a href="http://www.flickr.com/photos/saskiavandenieuwenhof/2312329520/" title="Free beer at van Abbe museum by Saskia Heijltjes, on Flickr"><img src="http://farm3.staticflickr.com/2354/2312329520_cd26fbd46d_m.jpg" width="240" height="180" alt="Free beer at van Abbe museum"></a>

Open-Source software makes all of our lives better. It allows us to do our jobs
without reimplementing the wheel each time. It allows us to understand the nuts
and bolts of how the software we use operates ... and even change those
internals if we need to!

Open Source is a two-way street, however. While we aren't legally bound to
contribute back to the software we use, we like to do it out of a sense of
community and because we know how much open source has helped us solve big
problems. It's also good for business, of course, since it increases
Highgroove's visibility if other developers are using software we helped create.


# Motivation

## Scratch an Itch

Many of our developers contribute to open-source projects regularly. Often their
involvement in a given project arose from a need such as a feature lacking in a
toolset upon which they already relied. See the
[Badger Works](http://highgroove.com/badger_works.html) for complete details.

## Fix a Bug

Bugs in software are a reality, but also incredibly frustrating for users of
open-source libraries. If you run across a bug in a library that you are using,
do the community a huge favor by tracking it down, making a bug report, and
  ideally, fixing it!

Follow all of the same guidelines as if you were adding a new feature (see The
Mechanics section below).

If you just happen to have an interest in a project you'd like make better,
check the bug-tracking system or issues wiki (on Github) and fix it; even if it
doesn't help you today, you never know when it will down the road.

## Adopt Abandonware

Does your favorite gem for doing something only support Ruby 1.8 and break
horribly on 1.9? Do its tests fail even if library itself apparently works? Has
the original author apparently moved on, or even explicitly given up support?

This can lead to a tricky situation of many forks, all of which fix different,
or even overlapping bugs, and each of which is vying to become the definitive
new version of an old project. Attempting to coordinate that logistical problem
is beyond the scope of this guide, but is definitely a pitfal to be aware of.

In the event that you'd like to help revive a project and there is at least one
quality fork, contribute to it. If there is not, make one yourself and invite
others who have forked the project to contribute!

Do Something Fun!

Do you have an interest in some field that you can learn more about by
developing tools? Graph-theory, artificial intelligence, mobile apps,
distributed computing, Linux kernel drivers? Hot frameworks and languages like
node.js and erlang?

Take the time, learn the tools, and if you find them lacking ... make a small
contribution! You could even roll your own if you're breaking new ground.

# Example Contributions

## Extraction of General Purpose Libraries from Existing Code

Rails itself was extracted from the code that built the [first version of
Basecamp](http://www.slideshare.net/vishnu/extracting-rails-from-basecamp).
If you find yourself writing some code in a project that feels like it
has general-purpose appeal, try extracting it out into a gem.

For example, the [rector gem](https://github.com/alindeman/rector) was
extracted out of code that parallelized a report for a customer.

The extracted library will be easier to maintain because it is separated from a
specific project. It will also be a welcomed contribution that saves other
developers time. Also, it might save you time if another developer contributes a
feature you need back. And last but not least, it makes you and Highgroove look
awesome!

Building a gem is not a difficult process, so even the smallest of gems will be
welcomed additions to the community. Seek out other Highgroovers who have built
gems before if you want to give this a shot; you might be surprised at how easy
it is.

## Documentation

Many open-source maintainers took their first steps on a project by simply
improving the documentation. Documenting some code or a common task when using
software is great way to learn the internals of the a project. It sounds really
mundane, but if you are using a library and realize its documentation is
lacking, it would be a great service to the community if you contributed
documentation back. You'll help allay a lot of developer frustration and learn a
ton along the way.

To make a documentation contribution, figure out the specifics of how
documentation is handled for a given project. Sometimes documentation lives
within the codebase itself; other times, it lives in an associated Wiki.

Examples:

* The [Rails Guides](http://guides.rubyonrails.org/) are maintained in the
  [lifo/docrails](https://github.com/lifo/docrails) GitHub repository. There is
  an open commit policy: anyone can simply clone the repository directly and
  commit/push to it! This is the easiest way to contribute back to Rails.

* The documentation for the popular authorization library
  [CanCan](https://github.com/ryanb/cancan) is maintained in the associated
  [GitHub Wiki](https://github.com/ryanb/cancan/wiki) for the project. Project
  Wikis can be accessed by finding the project on GitHub and clicking "Wiki"
  toward the top right of the page.

* Documentation for code structures is usually maintained alongside the code
  itself. The Rails API docs are generated from code comments in RDoc format
  (for an example, see [ActionMailer::Base](https://github.com/lifo/docrails/blob/master/actionmailer/lib/action_mailer/base.rb#L9-20) 
  and its [generated form](http://api.rubyonrails.org/classes/ActionMailer/Base.html)).
  Again, anyone can contribute to these docs by committing to [lifo/docrails](https://github.com/lifo/docrails).

# The Mechanics (Existing Projects)

## Github

Ryan Bates' [Railscast #300 on Contributing to Open Source](http://railscasts.com/episodes/300-contributing-to-open-source)
covers all the details on fixing bugs and adding features to projects hosted on
GitHub. It's well worth the 9 minutes!

## Doing it by hand

If the project resides in another versioning and distribution system such as
Sourceforge, or even as a tarball somewhere out there, you'll have to do it the
old fashioned way. There is no forking, only downloading, and if the project
does use revision control but not Git you'll have to change your workflow to
match. In the case that the project uses Subversion you can use the git-svn
bridge locally but keep in mind that the natural workflow of the project owners
will very likely be different from the one to which you are used.

The general workflow is not so different from the Github-centric one above, but
you will have to be in greater command of your tools:

1. Retrieve the code
    * Check it out of an SCM (SVN, Mercurial, CSV, RCS!?)
    * Download the source tarball
2. _Optional_ Import the code into a local Git repository to manage feature branches
3. Make your changes to your local code, along with tests if possible.
4. Contribute your patch:
    * If you don't have commit access to the original SCM (if there is one),
      which is likely during the beginnings of your interaction with a project,
      create a patch using diff that the author can easily analyze for merging.
      Be sure to introduce yourself, include a detailed (but not too detailed)
      explanation of your bugfix or feature, and make yourself available to
      answer any questions the maintainer may have for you.
    * If you do have access then contribute your patch per the process of the
      project. That may involve creating a remote branch for review or other
      project-specific processes. Be aware that if you utilize git locally with
      a bridge to a different SCM, local commits may have non-obvious effects
      (such as creating a new revision number in SVN) that can be prevented by
      rebasing before committing. This is no different than the git
      best-practice you already practice but the effects of missing this step
      here are more obvious than in the git-specific case.
5. Make yourself available, exactly as before.

# Wrap-up

As with any project the key is to make your contributions something well tested,
within scope, and easily understandable by the recipient.  Moreover by being
communicative and available you will find your contributions much more likely to
be accepted by the project one which you worked, then it's time for an
[Open-Source adult beverage](http://freebeer.org/blog/)!

### Git Workflow and Resolving Conflicts (Part 1)
<iframe src="http://player.vimeo.com/video/33165748?title=0&amp;byline=0&amp;portrait=0&amp;color=e61515" width="600" height="375" frameborder="0">
</iframe>
<br/>
<br/>
### Git Workflow and Resolving Conflicts (Part 2)
<iframe src="http://player.vimeo.com/video/33166064?title=0&amp;byline=0&amp;portrait=0&amp;color=e61515" width="600" height="450" frameborder="0">
</iframe>
<br/><br/>

[Show me more videos!](http://vimeo.com/highgroove/videos)
