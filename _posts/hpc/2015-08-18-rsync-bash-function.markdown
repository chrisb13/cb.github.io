---
author: chris_bull
comments: true 
date: 2015-08-18 00:30:00+00:00
layout: post
slug: bash-function-rsync
title: Bash function for painless rsync.
categories:
- hpc
---

My life consists of two problems...

1. I work on many different machines and the files I want are invariably on the wrong machine.
1. I can never remember the right rsync flags for the different machines I use and my fingers are lazy.

The second problem means I never want to deal with the first two.. Sound familiar? 

Here's some bash functions to help you push and pull files from a remote location. 

We have one bash function for pulling files....
{% gist 7ea4e9620cbce4a80bfd %}

And another (slightly more complicated) bash function for pushing files....

{% gist 432eade90ec68629d03a %}

So, if you put these in your [.bashrc](http://superuser.com/questions/49289/what-is-the-bashrc-file) with your relevant server details you should be good to go! Feel free to change the switches if you prefer something else, do get in touch if you improve these, it's impractical to currently pass include/exclude statements at present for instance... The above are [GitHub gists](https://help.github.com/articles/about-gists/), feel free to comment/fork/pull!

Also, life is a lot more smooth if you're using [ssh keys](https://www.digitalocean.com/community/tutorials/how-to-set-up-ssh-keys--2).

