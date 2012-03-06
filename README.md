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
generator](https://github.com/mojombo/jekyll). Install it as a gem ...

    gem install jekyll

Run a local version of the site that automatically updates as files are added
or changed ...

    jekyll --auto --server

The site runs by default at <http://localhost:4000/>

### Git

This repository does not have a `master` branch like most git repositories;
instead, commits are added to the `gh-pages` branch so the site deploys
correctly to [GitHub Pages](http://pages.github.com).

### GitHub

As a Highgroover ...

1. Clone the repository
2. Commit to the `gh-pages` branch
3. Push changes back up

As an open source contributor ...

1. [Fork the repository](http://help.github.com/fork-a-repo/)
2. Branch off of or commit directly to the `gh-pages` branch
3. [Send a pull request](http://help.github.com/send-pull-requests/)

## Site Details

### Twitter Bootstrap 2.0

The site is styled by [Twitter Bootstrap
2.0](http://twitter.github.com/bootstrap/).

### Adding a New Topic

Create a new markdown file in the `topics/` directory:

    vim topics/my-new-topic.md

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
