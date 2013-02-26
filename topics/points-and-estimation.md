---
layout: topic
title: Points and Estimation
published: true
image_hint_url:
description: A little bit about what points are and how to use them
---

# Why points?

Many companies bill by hours because that's seems like a good way to "know what
you're getting" or "get your money's worth." We think it's a bad idea because
developers round things up and down and end up wasting time keeping track of
time and worrying about details that aren't relevant to what matters: the
functionality of your project. Additionally, estimating "hours" is a very tricky
thing and every project we've heard of that has been estimated hourly always
goes over budget. With hours, all you know is that in 40 hours, you will have
gotten 40 hours more of 'something'. With points, it is possible to establish a
'velocity' which a client can use to estimate when some functionality will be
ready.

We use points because they specify what exactly it is that you're paying us for,
and we deliver exactly what you need on a schedule that is continually updating
based on your needs.

We can generally complete anywhere from 10 to 32 points in an iteration
(typically 1 week). It may be as low as 0, or as high as 65 for a single
developer, and that's ok! Points reflect new functionality delivered during an
iteration, and an iteration focused on bugs or research may not have much of
that kind of value delivered. Every project is different, every developer is
different, and every client is different. As long as everyone is consistent, our
tools use actual progress to calculate the real velocity, leading to REAL
estimations based on ACTUAL work.

Note that this doesn't mean that you can replace 'hours' with 'points', and
start billing customers for getting done X points per week. The minute that you
start using points for something other than estimating future work, the whole
system starts to fall apart. It's nice to see velocity rise and more points get
done, but if developers are just using larger estimations and spending their
time playing Diablo III instead, you're not getting more value.

# Points based Estimating

We use points to estimate complexity of features. This explains the basics of
how we do this estimation and what points mean:

* 0 points - This is not really work, but still requires delivery and
  acceptance, changing out text in an email template for example.
* 1 points - This takes some code and maybe a very simple test.
* 2 points - This takes some code, a few tests, and maybe a plugin or library
  that is straightforward to use.
* 3 points - This is more difficult and involves code, complex test cases, a lot
  of dialog, or interacting with complex external services or plugins.

It's ok to not follow these guidelines as long as you are consistent. Your
2-point feature and ours may be very different, but as long as whoever is
estimating stories is being consistent, points will be usable for estimating
when work will be complete.

Other organizations use bigger point scales that go higher, but we think that if
something is more complex than a 3-point feature, it needs to be broken into
smaller pieces. In addition to features with associated points there are a few
other types of stories that we work on:

* Chore - These are things that need to happen, but that do not require
  acceptance. It may be a placeholder for future work ("create stories for user
  authentication") or it may be a task for a client ("Provide snapshot file of
  legacy database") or notes from a phone call.
* Bugs - These don't get points because they're something that shouldn't happen!
  Ideally a developer should have enough acceptance criteria on features to
  prevent these, and tests to prevent any defects, but they crop up. Bugs do
  affect the velocity as time spent on them is not spent on features.

The definition of "Velocity" of a project that we use is the 3-iteration average
of points completed per iteration, which lets us estimate when future stories
will be completed by. For example, if we're averaging 20 points per iteration
and there are 40 points in your backlog, your project will likely be complete in
2 Iterations (2 weeks)!

# Sample Stories

Below are some rough sample stories. No story is a perfect example, but these
get the idea across. We'd probably split some of these up into more small
stories.

## 1 Point:

* Visitor visits home page, displays search fields

  * home page displays just the form HTML as outlined in wireframe here:
    example.com/html
  * simply displays two boxes and submits data to server

## 2 Point:

* When user submits Report your Time form, it saves the results for the Office

* When a User selects: screen name, the time, their mood

  * the form shows the current time
  * the application saves the data attached to the provider
  * takes user to details for provider
  * The system saves the results for the provider, tied to the office.

## 3 Point:

* A user can search for offices based on location, provider name, and provider
  type

  * A Sphinx index provides Geolocational searches, filtering by provider
    category, and optional Office and Provider name as search terms
  * New and updates to existing Offices and Providers update the index instantly
    using Delta Indexes
  * Deleted Offices and Providers are removed from the index immediately (using
    Delta Indexes)
  * The full database is reindexed weekly
