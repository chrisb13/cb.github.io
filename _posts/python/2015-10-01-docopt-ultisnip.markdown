---
author: chris_bull
comments: True
date: 2015-10-01 00:30:00+00:00
layout: post
slug: docopt-ultisnip
title: Beautiful argument parsing with docopt and ultisnips.
categories:
- python
---

I recently discovered [docopt](https://github.com/docopt/docopt), this super neat command line parser. I've used sys.argv and the argparse module but they've always felt too limited or overly complicated (respectively). What's great about docopt is that it understands what to do based on the POSIX-style doc string you write! This has two advantages...

1. You've likely used enough *nix command-line tools to have a sense of what your doc string should look like (if you do get lost [the docs](https://github.com/docopt/docopt) are great).
1. It forces you to write documentation!

There's a [video](http://docopt.org/) here if you want a demo. Whilst it's not part of core python, one of the neat things is that it is fully self-contained within a single file. Thus, you can 'install' it with: 
{% highlight bash %}
wget https://raw.githubusercontent.com/docopt/docopt/master/docopt.py
{% endhighlight %}

Anyway, I've written a [Vim Ultisnip](http://vimcasts.org/episodes/ultisnips-python-interpolation/) to do all the work for you...
{% gist a1e813302a0c9fbd9759 %}
This is one of the more useful Ultisnip interpolation uses I've found, you read correctly, it'll 'install' docopt for you!

The above is a gist, feel free to comment/fork/pull.
