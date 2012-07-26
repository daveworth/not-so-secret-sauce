---
layout: topic
title: Best Practices and Patterns
---

README
------

A README is always a great place to start a new project. The README should be
sufficient for anyone to get the app up and running in 'development' or
'production' without having to ask any questions. As you add new moving parts
to a project; be sure to update the README

Rake Tasks
----------

Rake task for populating data so that a developer can run one command and be
able to click around everywhere in the app.

Tests
-----

Your code needs tests, and all tests need to pass. Also your tests should follow these guidelines:

* 80% or better C0 code coverage (rcqa or cover_me or simplecov gems). 
* Before you push, 'rake test' or 'rake spec' or something
* You probably should have more lines of code than lines of tests. run `rake
  stats` to get these numbers
* A good testing pattern to follow is minitest(?spec/?shoulda) unit tests of
  your models and capybara integration tests
* Be fast

### Continuous Integration

All developers are encouraged to use [Continuous
Integration](http://en.wikipedia.org/wiki/Continuous_integration) to run test
suites automatically, routinely, and often. Hosted options include
[Tddium](http://www.tddium.com), which can be configured to automatically
trigger builds and send build status email notifications each time you push to
Github.

Tools and patterns we like
--------------------------

### Background Jobs

Anything that may take more than a few hundred milliseconds (e.g.,
communicating with an external web service or sending email) should probably be
done asynchronously using a job queue.

* [Sidekiq](https://github.com/mperham/sidekiq)
* [DelayedJob](https://github.com/collectiveidea/delayed_job)

Rails 4.0 will support a [generic queuing mechanism](https://github.com/rails/rails/commit/602000be90e9935f4f4ee5acc096725d7b7c33e5).

### Code Coverage Tools 

* [SimpleCov](https://github.com/colszowka/simplecov)
* [CoverMe](https://github.com/markbates/cover_me)

### [Rails Best Practices](https://github.com/railsbp/rails_best_practices) 

whitespace, formatting, code patterns, etc

### Authentication 

Messing up authentication by rolling your own can be really bad news. Stick to
using open-source solutions that have been battle tested.

* [has_secure_password](http://railscasts.com/episodes/270-authentication-in-rails-3-1)
* [Devise](https://github.com/plataformatec/devise)
* [Authlogic](https://github.com/binarylogic/authlogic)

There is a [tech talk](http://vimeo.com/39498553) on why the lighter weight
`has_secure_password` may be sufficient to many applications.

### Feature Flags

* [Setler](https://github.com/ckdake/setler) 
  ([blog post](http://highgroove.com/articles/2011/08/22/introducing-setler-for-feature-flags.html))

### Javascript

* [jQuery](http://jquery.com/)
* [CoffeeScript](http://coffeescript.org/)

Other frameworks like YUI and Prototype may be useful sometimes, but jQuery
seems to be much more well-known and supported these days.

### Templates/Views

* [Slim](http://slim-lang.com/) ([tech talk](http://vimeo.com/33802242))
* [HAML](http://haml-lang.com/)

### File attachments 

* [Carrierwave](https://github.com/jnicklas/carrierwave)

### Testing

* [rspec/rspec-rails](https://github.com/rspec/rspec-rails) or
  [minitest](https://github.com/seattlerb/minitest)
* [factory_girl](https://github.com/thoughtbot/factory_girl_rails): creating
  instances of objects in tests
* [forgery](https://github.com/sevenwire/forgery): creating unique data in
  factory-created objects
* [mocha](https://github.com/floehopper/mocha) or
  [rspec-mocks](https://github.com/rspec/rspec-mocks): mocking and stubbing
  (recommended reading: [Mocks Aren't Stubs](http://www.martinfowler.com/articles/mocksArentStubs.html) and 
  [Mock Roles, Not Objects](http://www.mockobjects.com/files/mockrolesnotobjects.pdf))
* [VCR](https://github.com/myronmarston/vcr): stubbing network traffic during
  integration tests
* [Spork](https://github.com/sporkrb/spork): a non-ideal, but sometimes
  pragmatic, solution to slow tests

### The Cloud

* [Heroku](http://www.heroku.com/): application hosting
* [asset_sync](https://github.com/rumblelabs/asset_sync): host assets on S3
  ([blog post](http://ckdake.com/content/2011/rails-31-assets-on-s3-with-https.html))

### Security

* [Brakeman](https://github.com/presidentbeef/brakeman): static analysis for
  security issues, check out this [video](http://vimeo.com/35766582)

### Performance

* [bullet](https://github.com/flyerhzm/bullet): SQL performance issues

### Systems Programming

* [Dante](https://github.com/bazaarlabs/dante/): Turn your ruby program into a
  deamon easily.

### Development

* [Foreman](https://github.com/ddollar/foreman): manage all the processes your
  app needs to run

### Other

* [kaminari](https://github.com/amatsuda/kaminari): pagination
* [high_voltage](https://github.com/thoughtbot/high_voltage): static pages
