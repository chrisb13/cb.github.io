---
author: chris_bull
comments: true
date: 2015-12-02 00:30:00+00:00
layout: post
slug: lightning-netcdf
title: Bash function for super fast loading of netCDF files in Python.
categories:
- python
---

I often finding myself wanting basic information about netCDF files and needing to inspect it in Python *quickly*.

I've written a bash function that takes a passed path of a netCDF file, it then writes a short python script and loads it into a ipython console. The console then prints out basic information about the file and all the variable names, ready for you to hack away!

For this bash function you'll need:

1. python 2.x
1. python netCDF4 library
1. ipython

Here's the function:

{% gist 62b159a374bb0763c569 %}

The above is a [GitHub gists](https://help.github.com/articles/about-gists/), feel free to comment/fork/pull! If you've found this handy, you might also like my [Vim and UltiSnip](http://christopherbull.com.au/hpc/vim-ncdump-shortcut/) for similar stuff.
