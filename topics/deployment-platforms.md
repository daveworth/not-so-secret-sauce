---
layout: topic
title: Deployment Platforms
published: true
description: Deciding where to deploy your app
---

When we develop web applicaitons the majority of our focus is on building
the features that we need. We focus on which gems provide us the functionality
we want, which database is best suited to the application, but not about where
we deploy our applications. There are several deployment platforms that are
available today that provide a range of services depending on the needs of
your application. This page is meant to provide a brief overview of some of
the more popular deployment options.

# Heroku

## Price

Heroku does offer a free tier for applications, and they have several other tiers
depending on how much of a load the site is under. However many optional
functionalities are add-ons so that can make an instance more expensive. Price
is per application.

## Security

Heroku's physical infrastructure is hosted and manages in Amazon's secure data
centers. Amazon constantly manages risk and uses recurring assessments to ensure
that they are compliant with industry standards. They also use third party security
consulting firms in order to perform penetration testing and vulnerability assessments.
They have environmental safeguards in place to prevent against things such as power
loss, or fire. Network security is achieved through the use of firewalls, DDoS mitigation,
spoofing and sniffing protections, and prohibiting port scanning. A full list of the
security practices can be found at: http://policy.heroku.com/security

## Ease of use

Heroku is very easy to use and an application can be up and running in
minutes. The servers are hosted on Amazon EC2 but there is no server
configuration needed since heroku handles this themselves. While this
makes heroku very easy to use, you do lose some control over the
environment. Heroku also relies heavily on command line tools for
management.

## Cloud-ness

Heroku applications are hosted on Amazon EC2 instances. However, your
application will not be allotted to an entire server. You receive a virtual slice
of the computing resources, a 'sandbox', in which your application must reside.
The file system of the server does not allow you to write to it so you must find
another way to store files if you need to. One of the more common ways of doing
this is to use Amazon S3 to store files from the application.

# Engine Yard

## Price

Engine Yard's cheapest option runs about $80 a month, but this gets you a server
that you can put as many applications on as you want. The server is hosted on
Amazon EC2

## Security

Engine Yard provides enterprise-grade security by continually updating their 'stack'
to ensure that all security updates are implemented in a timely manner. They provide
VLAN segmentation, fully configurable firewalls, two-factor authentication, IDS/IPS
services, log aggregation, and event correlation.

## Ease of use

Engine yard is also fairly simple to use and it provides a great deal of control
over the system. However this happens at the expense of rapid configuration
and deployment. Engine Yard provides an extensive dashboard to manage
your servers.

## Cloud-ness

Engine Yard applications are hosted on Amazon EC2 instances. However,
unlike Heroku which gives you a slice of the computing resources, Engine Yard
allocates the entire allotment of the Amazon computing resources. Engine Yard
provides the base platform, but the rest is up to you.

# Rails Machine

## Price

Railsmachine cost is based on what resources your application requires. On the core
plan the costs start at $150 per month for the smallest server. They also have the
option to add additional resources to the server incrementally. For example, to add
an extra GB of memory to the machine would cost an extra $100 per month. All of the
cost factors are laid out here: http://railsmachine.com/support/upgrades/
For this service it is up to you to manage the server and add resources as necessary.
They also offer managed hosting where they watch your account and have
recommendations about how to manage your server.

## Security

Once Rails Machine gets your server up and running it will be up to you to secure
it. They do have a getting started guide on their website, but it still involves setting
up different user accounts on the system. Rails Machine also implements and follows
industry standard security procedures..

## Ease of use

Rails Machine is involved in each step of setting up your application. They will
study your application and recommend an initial configuration of your system.
Once you decide on your server configuration they deploy your application.
Once it is up and running it will be scaled by adding additional resources as
needed.

## Cloud-ness

Rails machine provides virtual servers configured for your application. They offer fast
hands-on response to emergency application issues 24/7. This service is very expensive,
but it guarantees that someone will respond to your emergency very quickly. They also
monitor your application availability around the clock, and they perform daily and off-site
backups.
