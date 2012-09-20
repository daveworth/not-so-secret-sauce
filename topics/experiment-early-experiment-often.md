---
layout: topic
title: Experiment Early, Experiment Often
published: true
description: Run experiments, fail fast.
---

Experiments are the way to try things out when the outcome is uncertain. They go very well with a "bias towards action" and let us "fail fast" if something isn't working well.  To sum things up: Be Bold! Take Risks! But remember:

  "If you are not measuring, you are not engineering."

and if you are trying to effect change but you are not engineering, then you're not going to have a good time.

# SMART Experiments

First up, what are you trying to accomplish? Hopefully it is <a href="http://en.wikipedia.org/wiki/SMART_criteria">SMART</a> (to you at least). Experiments should test an idea in a SMART way.

* Specific - What exactly are we trying to do?
* Measurable - How will we know if this worked?
* Attainable - Is this reasonable to use everyone's time on?
* Relevant - Does this improve a problem we have or make us better?
* Time based - When will we know if this worked?

# Some Past Experiments

Failing an experiment is as good as, if not better than, 'succeeding'. If everything went well all the time and every experiment was successful, we would never learn anything.

## The Great Campfire Experiment

* S - Let's see if Campfire works for us for group chat instead of Skype. Other companies that we like use Campfire.
* M - After using Campfire instead of Skype for a week, we'll gather feedback and use a consensus.
* A - Chat doesn't take up much of our time, but there is a chance that Campfire will save us a bit of time and frustration so the time spent experimenting with it for a week may be worth it.
* R - Skype transcript search is super annoying, and building a bot for a Skype room is hard.
* T - We'll try out Campfire for a week and see!

Success! We used Campfire for a week, the pros outweighed the cons, and we stuck with campfire. It's easier for us to use, and working with our bot is much easier.

## Code Reviews

* S - Code reviews supposedly improve code quality, let's get regular code reviews as part of our routine if they are helpful for us.
* M - If some code reviews identify issues and help people learn, we should keep doing them.
* A - Asking people to spend an hour each week reviewing someone else's code is a reasonable request both to experiment with, and to run every week in the long term.
* R - We're always working to improve code quality, and more eyes on all code helps.
* T - We'll try this out for a week or two and see what people think.

Success! We did random pairings of code reviews for a week, and the feedback was overwhelmingly positive. Developers enjoy reading other developers' code, and everything from style suggestions to architectural decisions made it both ways through the code reviews. This was a while ago, and we still do these every week.

## Full-Mesh pairing

* S - Pairings supposedly improve code quality, let's get regular pairings as part of our routine if they are helpful for us.
* M - If pairings are a good use of time and improve quality, we should keep doing them
* A - Asking people to spend an hour each week reviewing someone else's code is a reasonable request both to experiment with, and to run every week in the long term.
* R - We're always working to improve code quality, and more eyes on all code helps.
* T - We'll try this out for a week or two and see what people think.

Failure! While code-reviews can happen asynchronously, pairings meant that each week people had to schedule time with other people to work on some problem. Due to random pairings, this meant each person would have 2 of these to do each week, which was further complicated by everyone working different hours. Additionally, pairings would happen when 'nothing interesting' was going on in a project, and they didn't ad any value. After a few weeks of trying this out, we stopped doing it. This was a relief to everyone.  Instead of the full-mesh pairings, we just encourage people to pair whenever they need some help or are doing anything particularly tricky or sensitive.

## Groceries in Pivotal Tracker

* S - We use Pivotal Tracker for software, so using it for groceries makes sense. Let's get our grocery list in Pivotal Tracker.
* M - If Pivotal Tracker helps us keep our fridge full, it's better than what we are doing currently
* A - We use Pivotal Tracker every day, so putting groceries in there should easily work with our workflows. Our office manager doesn't however, 
* R - We currently run out of food more than we'd like, and this just gets harder as we hire more people
* T - We'll try this out for a month or two and see what it does for the refrigerator.

Failure! Fitting 2 grocery runs per week into an iteration, making sure the right runs happen on the right days, and making sure that the right food is on the right list is hard. People would put items on the wrong lists, and our office manager had to come into the office to check the fridge to see what staples we were out of.  Pivotal Tracker just confused everyone, and didn't make the food situation any better. We've 'fallen back' to a list of staples on the fridge with blank lines for people to add things if they need them, and a notes column for getting things on the 'staples' list or requesting particular brands or flavors. We're still working on this experiment, but it's going a lot better.

## Billable Projections Spreadsheet

* S - We need a way to answer the questions: "What is Developer X working on in 2 weeks" and "Who is the next available developer to work on a project?" and "What should Client Y be billed?"
* M - Can we answer these questions easily without having to do a bunch of work?
* A - We're smart people and we have the data in various places, this should be pretty reasonable.
* R - We have to answer these questions pretty regularly, and they get harder to answer as our number of clients and developers grow.
* T - We'll try making a spreadsheet in a week and see if it works.

Success, then Failure! We made a spreadsheet for this and it answered the questions, but keeping it up to date is pretty hard, especially as developers come and go, go on vacation, and project timelines shift. This spreadsheet worked for a while but started to grow abscesses like arbitrary numbers in parenthesis, color coding, etc. We're now working on a Rails application that enforces some tighter restrictions and does much better reporting and hope to delete the Billable Projections Spreadsheet sometime soon.

## ROWE

* S - We pay developers for building awesome software, so why should we pay them based on how many hours they work?
* M - Can we not make people track hours, and keep our customers happy?
* A - Good developers are internally motivated and mature enough to handle the responsibility of managing themselves, so if we only hire good developers, this should work.
* R - We want to be the best place for developers to work so not tracking time should help.
* T - We'll switch clients over to results based billing, and once they're all off of hours, we'll see what happens next.

Success! We have no clients at this point that are billed hourly, and a blog post on <a href="http://highgroove.com/articles/2011/12/15/tracking-time-the-rowe-way.html">Tracking Time the ROWE way</a> for an explanation of when time tracking does happen. Developers are compensated based on meeting their results, and not meeting results is grounds for dismissal. 

# Future Experiments

Have an idea? Let's try it out! Pick an experiment to run, and let's make it happen. Any idea that can be turned into a SMART experiment should be run.