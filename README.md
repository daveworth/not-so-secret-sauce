# Not So Secret Sauce

We realized that at [Highgroove](http://highgroove.com), some of the
documentation we provide to developers that helps them do their jobs better
wasn't really our "secret sauce."

This repository, and its deployed counterpart at
<http://not-so-secret-sauce.highgroove.com/> is the result of making that
material public. We hope it helps you be a better developer!

## Site Quickstart

### Ruby

The site runs on Ruby 1.9.2. If using rvm ...

    rvm install 1.9.2

The site is configured to use a gemset; create one and switch to it ...

    rvm gemset use 1.9.2@not-so-secret-sauce --create

### Jekyll

The site uses the [Jekyll static site
generator](https://github.com/mojombo/jekyll) installed via bundler.  Install bundler 
and update your bundle:

    gem install bundler
    bundle


Run a local version of the site that automatically updates as files are added
or changed ...

    bundle exec jekyll --auto --server

The site runs by default at <http://localhost:4000/>

### Git

This repository does not have a `master` branch like most git repositories;
instead, commits are added to the `gh-pages` branch so the site deploys
correctly to [GitHub Pages](http://pages.github.com).

### GitHub

As a Highgroover ...

1. Clone the repository
2. Make changes (add a topic, touch some styling, etc.)
3. Commit to the `gh-pages` branch
4. Push changes back up

As an open source contributor ...

1. [Fork the repository](http://help.github.com/fork-a-repo/)
2. Branch off of or commit directly to the `gh-pages` branch
3. [Send a pull request](http://help.github.com/send-pull-requests/)

## Contribution Guidelines

How do we decide what goes on the page?

### Should I add _content_ to this collection?

To decide if a contribution belongs here, or in a blog post, or in a private
document there are a few questions to be asked:

Does the content give Highgroove, or a contributor's employer/company, a
business advantage over other companies or does the content simply make the life
of a developer or other developer better?  In the prior case add the
documentation to the intranet to keep business rolling.  In the latter case add
it to this collection.  Over time intranets can and should be reviewed, and
content can be moved here at your leisure.

Once data is contributed here it should be removed from any private source from
which it sprang, perhaps with a reference to this collection when it is moved.

### I should add this but there is some private data coupled to it!

If you find you have content, the bulk of which belongs in this collection, but
has some coupled proprietary (customer-centric, internal businessy) data as well
sanitize it.  Ask yourself the question "Could this hurt ourselves or our
customers, even by helping their competitors?" before adding anything here.  If
there is too much of that type of data see the prior question.

### Style and Markup Guidelines

Following the [Rails API Documentation Guidelines](http://guides.rubyonrails.org/api_documentation_guidelines.html),
where applicable, makes for good writing as well.  Active voice, brevity, and
clarity are as important as content.  If there is code inline make sure your
gist is of the correct language type so that syntax highlighting makes the most
of your contribution.

In places where content is Highgroove, or contributor, -specific use your best
judgement in terms of whether or not to name them in the content or omit them by
replacing their name with a generic pronoun.

## Site Details

### Twitter Bootstrap 2.0

The site is styled by [Twitter Bootstrap 2.0](http://twitter.github.com/bootstrap/).

### Adding a New Topic

Create a new markdown file in the `topics/` directory:

    rake new title='Your awesome title'

You'll want to add the appropriate metadata to the header of your new topic,
which will probably look similar to this:

```
---
layout: topic
title: Highgroove Code Reviews HowTo
description: How Highgroovers give back to the open-source community
---
```

If you have an image in the topic's page, you may also want to add an
`image_hint_url` attribute.

Once the header is in place, finish writing your page in Markdown.

Once you're done and ready to integrate your topic into
the website, add an item to the sidebar in `_layouts/default.html`
that looks like so:

```
<li>
  <a href="/">
    <i class="icon-book"></i>
    Home
  </a>
</li>
```

The list of available icons can be found [here](http://twitter.github.com/bootstrap/base-css.html#icons).
Try to choose one that reflects the navigation item.

Finally, commit your changes and push. GitHub pages will take care of the rest.
