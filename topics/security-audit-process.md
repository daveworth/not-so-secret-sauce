# Overview

At Highgroove we take application security very seriously.  The good news is
that Ruby on Rails does as well and if developers follow the well documented
[best-practices](http://guides.rubyonrails.org/security.html) in the field it is
very difficult to introduce the majority of security vulnerabilities that plague
other platforms and frameworks.  There are trade-offs of course, and as
applications become more sophisticated the more powerful the tools that are
brought to bear on the problem.  With that sophistication comes more potential
for subtle security bugs to creep in.  To prevent that we perform standard
security audits to catch such subtleties before they are put into production.

## High-level audit process:
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
  use issues which may have been missed by Brakeman.

* Audit authentication and authorization-controls
  * If the application is using an unfamiliar control mechanism become familiar
    with it.

  * Authentication:
    * If the project uses `has_secure_password` we're pretty.
    * If the project is using Devise or another system, analyze its use for
      common security issues.

  * Authorization:
    * If the application is using CanCan make sure cascading `cannot`s override
      existing `can`s.

* Audit extra-ORM datastores (such as S3/scribd/etc) for security concerns
  which may affect the business needs of the customer.  We are not experts in
  the regulatory side of things (HIPAA, FERPA, etc.) but will endeavor to engage
  experts in that field if needs-be.

* Audit sessions for their use within the app.

* Report. We focus on openness regarding the results of our audits and inform
  the customer(s) immediately of any results.  If there are any questions please
  just ask!

  * Address each phase of the audit above
  * Address non-security issues noticed during the review.  This phase is
    fairly similar to the Highgroove [code-review process](http://not-so-secret-sauce.highgroove.com/topics/code-reviews-howto.html)

* Any bugs discovered in any audit tool or libraries discovered during the
  audit, are reported to the authors and sometimes patched.  Highgroove
  takes its responsibility to open-source very seriously and we work to
  improve the tools we use when we can.  This work is not done on client
  time but rather as part of our internal iteration at Highgroove.
