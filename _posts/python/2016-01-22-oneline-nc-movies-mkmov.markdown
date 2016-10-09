---
author: chris_bull
comments: true
date: 2016-01-22 00:30:00+00:00
layout: post
slug: oneline-movies-mkmov
title: Python package for one-line creation of movies from netCDF files.
categories:
- python
---

**Update 10.10.2016**. MkMov 0.4 now supports a bunch of other outputs, see [usage](http://christopherbull.com.au/mkmov/usage.html) for details.

MkMov is a Python package that creates a movie from a netCDF file with a single line, interface is command line (no python knowledge needed)! 
{: .notice}

I reguarly find myself making movies for sanity checks on model runs, other times I'll want a movie for a talk or perhaps to look at how some diagnostic plot varies over time. Suffice to say a few people have asked me how I create movies from netCDF files, such questions spurred the development of...

[MkMov](https://github.com/chrisb13/mkmov), a python package for making movies. In can be used in two ways:

1. from a netCDF file
1. from a list of png files (use --stitch option)

Examples tell a thousand words, [here's a movie (AVISO global allsat madt, output is daily and variable is adt)](https://youtube.com/embed/JEMj05o-KA4)

Created with a single line command, namely

{% highlight bash %}
python mkmov.py 2d adt --lmask -214748 --cmap Set3 -o /srv/ccrc/data42/z3457920/mkmovmovies4/AVISOdt_global_allsat_madt_Set3.mov /srv/ccrc/data42/z3457920/RawData/AVISO/RawData/dt_global_allsat_madt/ftp.aviso.altimetry.fr/global/delayed-time/grids/madt/all-sat-merged/h/*/*.nc &>  /srv/ccrc/data42/z3457920/mkmovmovies4/15.log &
{% endhighlight %}

More examples with their respective run commands [here](http://christopherbull.com.au/mkmov/examples.html). Official [docs are here](http://www.christopherbull.com.au/mkmov). [Contributions](http://www.christopherbull.com.au/mkmov/contributing.html) are most welcome.

You might be wondering what this tool offers over something like ncview and a screen grabber program. 

Pros:

1. bash scriptable
1. customisable output (e.g. --clev, --cmap [etc](http://christopherbull.com.au/mkmov/usage.html))
1. can take multiple files as input
1. can wrap ffmpeg to stitch together any png files

Cons:

1. slow in comparison to ncview 
1. need to install dependencies

