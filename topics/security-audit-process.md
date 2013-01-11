---
layout: topic
title: Security Audit Process
published: true
image_hint_url:
description: Our internal security audit process and methodology
---

# Overview

## Process

We take application security very seriously.  The good news is
that Ruby on Rails does as well and if developers follow the well documented
[best-practices](http://guides.rubyonrails.org/security.html) in the field it is
very difficult to introduce the majority of security vulnerabilities that plague
other platforms and frameworks.  There are trade-offs of course, and as
applications become more sophisticated the more powerful the tools that are
brought to bear on the problem.  With that sophistication comes more potential
for subtle security bugs to creep in.  To prevent that we perform standard
security audits to catch such subtleties before they are put into production.

### High-level audit process:
* Audit with [Brakeman](http://brakemanscanner.org/) - this scanner analyzes and
  application and determines if "standard", often rails specific, security
  vulnerabilities are present.

  * Analyze Brakeman results and prioritize; Those vulnerabilities which are
    clearly present are fixed immediately.

  * Manual validation of suspected vulnerabilities - Some reported possible
    vulnerabilities are a function of context and must be manually analyzed
    and either confirmed to be safe or repaired.

* Audit mass-assignment controls for inappropriate use of `attr_accessible` and
  `attr_protected`.

* Audit scopes, and scope "helpers" (such as Squeel/Metawhere), for insecure
  use issues which may have been missed by Brakeman.  If MetaWhere is used,
  audit usage of `assoc_(un)searchable`.

* Audit authentication and authorization-controls

  * If the application is using an unfamiliar control mechanism become familiar
    with it.

  * Authentication:

    * If the project uses `has_secure_password` we're pretty happy.
    * If the project is using Devise or another system, analyze its use for
      common security issues.

  * Authorization:

    * If the application is using CanCan make sure cascading `cannot`s override
      existing `can`s.
    * If the application is using another Authorization system examine its
      controls

* Audit routes for correct HTTP verb usage, particularly in `match` definitions.

* Audit extra-ORM datastores (such as S3/Scribd/etc) for security concerns
  which may affect the business needs of the customer.  We are not experts in
  the regulatory side of things (HIPAA, FERPA, etc.) but will endeavor to engage
  experts in that field if needs-be.

* Audit sessions for their use within the application.

* Audit schema to determine if sensitive data is being stored.

  * Audit logging and verify that sensitive data is filtered before being logged.

* Audit explicit calls to `Object#send` and `Object#__send__` for user controlled parameters

* Misc

  * Report security issues unique to a given project due to their domain.
  * Report technical issues which may not be of a security nature. e.g. lack
    of README or other documentation, a lack of tests, etc.

* Report - We focus on openness regarding the results of our audits and inform
  the customer(s) immediately of any results.  If there are any questions please
  just ask!

  * Address each phase of the audit above

  * Address non-security issues noticed during the review.  This phase is
    fairly similar to our [code-review process](http://not-so-secret-sauce.highgroove.com/topics/code-reviews-howto.html)

* Any bugs discovered in any audit tool or libraries discovered during the
  audit, are reported to the authors and sometimes patched. We also 
  take our responsibility to open-source very seriously and we work to
  improve the tools we use when we can.  This work is not done on client
  time but rather as part of our internal work to contribute back to the
  community.

## Keeping up with Ruby and Ruby on Rails security issues

There are a number of good resources to stay abreast of the state of Ruby, and
Ruby on Rails security.  Both the Ruby and Ruby on Rails communities follow, and
recommend, a responsible disclosure policy such that patches can be delivered
before exploits are publicly available in the wild.

### Ruby on Rails

* We closely monitor the Ruby on Rails [security mailing list](https://groups.google.com/forum/?fromgroups#!forum/rubyonrails-security),
  and recommend that all Ruby on Rails developers do the same.

* [PentesterLab.com](https://www.pentesterlab.com) often releases
  Rails-centric [exercises](https://www.pentesterlab.com/exercises) which help
  Rails developers to understand vulnerabilities at a more granular level.

### Ruby

* The MRI has it's own list of [known security issues](http://www.ruby-lang.org/en/security/).
* JRuby also maintains a list of [known security issues](http://jruby.org/security).
* Rubinus does not have a clear security list they do track security related
  [issues](https://github.com/rubinius/rubinius/issues?labels=security&page=1&state=open) on GitHub.
