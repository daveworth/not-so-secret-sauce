---
layout: topic
title: Best Practices and Patterns
---


README
------

A README is always a great place to start a new project. The README should be sufficient for anyone to get the app up and running in 'development' or 'production' without having to ask any questions. As you add new moving parts to a project; be sure to update the README


Rake Tasks
----------

Rake task for populating data so that a developer can run one command and be able to click around everywhere in the app.


Tests
-----

Your code needs tests, and all tests need to pass. Also your tests should follow these guidelines:

* 80% or better C0 code coverage (rcqa or cover_me or simplecov gems). 
* Before you push, 'rake test' or 'rake spec' or something
* You probably should have more lines of code than lines of tests. run `rake stats` to get these numbers
* A good testing pattern to follow is minitest(?spec/?shoulda) unit tests of your models and capybara integration tests
* Be fast

    
Tools and patterns we like
--------------------------

### Delayed Jobs 

Anything that takes more than a few hundred milliseconds should be done as using a job queue. [DelayedJob](https://github.com/tobi/delayed_job), [Resque](https://github.com/defunkt/resque), [RabbitMQ](http://www.rabbitmq.com/), etc

### Code Coverage Tools 

[SimpleCov](https://github.com/colszowka/simplecov), [CoverMe](https://github.com/markbates/cover_me)

### [Rails Best Practices](https://github.com/railsbp/rails_best_practices) 

whitespace, formatting, code patterns, etc

### Authentication 

Don't do your own authentication, use the built-in support in Rails (has_secure_password), [Authlogic](https://github.com/binarylogic/authlogic), [Devise](https://github.com/plataformatec/devise), or something else. Here is a [video](http://vimeo.com/39498553) that can help you decide what to use.

### Feature Flags

[Feature Flags are awesome](http://highgroove.com/articles/2011/08/22/introducing-setler-for-feature-flags.html) use [Setler](https://github.com/ckdake/setler)

### Javascript

Use [jQuery](http://jquery.com/) and [CoffeeScript](http://coffeescript.org/), don't use YUI, Prototype, etc.


### Templates/Views

* [Slim](http://slim-lang.com/), checkout this [video](http://vimeo.com/33802242)
* [HAML](http://haml-lang.com/)

### File attachments 

* [Carrierwave](https://github.com/jnicklas/carrierwave)

### Testing
* [factory_girl](https://github.com/thoughtbot/factory_girl_rails) - Creating instances of objects in tests
* [mocha](https://github.com/floehopper/mocha) - Mocking out method calls (Any interfaces with external APIs) in tests
* [VCR](https://github.com/myronmarston/vcr) - use "real" data but don't require the network for every test
* [forgery](https://github.com/sevenwire/forgery) - Creating unique data in factory-created objects
* [Spork](https://github.com/sporkrb/spork) - speed up various integration tests

  
  
### The Cloud

* [jammit-s3](https://github.com/railsjedi/jammit-s3) - package up assets and serve them from S3
* [Heroku](http://www.heroku.com/) - Application hosting
* [asset_sync](https://github.com/rumblelabs/asset_sync)  - Allows you to use S3 to host your assets for your Heroku Rails 3.1+ applications, check out this [blog post](http://ckdake.com/content/2011/rails-31-assets-on-s3-with-https.html)

### Security

* [Brakeman](https://github.com/presidentbeef/brakeman) - static analysis for security issues, check out this [video](http://vimeo.com/35766582)

### Other
  
* [kaminari](https://github.com/amatsuda/kaminari) - Pagination
* [bullet](https://github.com/flyerhzm/bullet) - Detecting SQL issues
* [Foreman](https://github.com/ddollar/foreman) - startup everything you need at once