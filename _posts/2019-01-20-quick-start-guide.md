---
layout: post
title:  "快速入門指南"
author: jhan
categories: [ Jekyll, tutorial ]
image: https://picsum.photos/750/500
---

If you already have a full Ruby development environment with all headers and RubyGems installed (see Jekyll’s requirements), you can create a new Jekyll site by doing the following:

```ruby
# Install Jekyll and Bundler gems through RubyGems
gem install jekyll bundler

# Create a new Jekyll site at ./myblog
jekyll new myblog

# Change into your new directory
cd myblog

# Build the site on the preview server
bundle exec jekyll serve

# Now browse to http://localhost:4000
```

## Options for creating a new site with Jekyll

`jekyll new <PATH>` installs a new Jekyll site at the path specified (relative to current directory). In this case, Jekyll will be installed in a directory called `myblog`. Here are some additional details:

- To install the Jekyll site into the directory you're currently in, run `jekyll new` . If the existing directory isn't empty, you can pass the --force option with jekyll new . --force.
- `jekyll new` automatically initiates `bundle install` to install the dependencies required. (If you don't want Bundler to install the gems, use `jekyll new myblog --skip-bundle`.)
- By default, the Jekyll site installed by `jekyll new` uses a gem-based theme called Minima. With gem-based themes, some of the directories and files are stored in the theme-gem, hidden from your immediate view.
- We recommend setting up Jekyll with a gem-based theme but if you want to start with a blank slate, use `jekyll new myblog --blank`
- To learn about other parameters you can include with `jekyll new`, type `jekyll new --help`.