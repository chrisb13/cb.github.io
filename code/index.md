---
author: chris_bull
comments: false
date: 2015-12-17 07:35:12+00:00
layout: page
slug: code
title: code
---

The following is some code I've writen or contributed to, all on [GitHub](http://www.github.com/chrisb13):

 * [mkmov](http://www.github.com/chrisb13/mkmov) is designed to make a movie from a NetCDF file or stitch together a series of *.png files. Interface is by command line and everything is done in one line! [Documentation is here](http://christopherbull.com.au/mkmov).

 * [eddytracking](http://www.github.com/chrisb13/eddytracking) is a  Chelton et al. (Prog. Ocean., 2011) style, eddy tracking package I contributed to. Originally written by [Eric Oliver](http://www.github.com/ecjoliver/eddytracking).
	
 * [MkPaper](http://www.github.com/chrisb13/mkpaper) creates a figure document in 3 + n lines of code, where n is the number of figures you have! Check out the blog post I wrote on it [here](http://christopherbull.com.au/python/python-package-mkpaper/).

 * [plthacks](http://www.github.com/chrisb13/plthacks) Plthacks is a Python package that wraps Matplotlib to make common (tedius) tasks faster, currently, it can create a grid of an arbitrary number of plots from an ordered dictionary, there's a blog post about it [here](http://christopherbull.com.au/python/superfast-griddedsubplots/).

 * [Imgtrkr](http://www.github.com/chrisb13/imgtrkr) Ever wondered which file produced that beautiful plot you're looking at? Have you spent an embarrasing amount of time looking for said script? Imgtrkr is a tiny python package that wraps the PIL python library so you can write useful metadata to your png files. (Personally, I write the file that created it, the time and the machine but it's whatever you like!) You can also pass a list of *.png files that imgtrkr has 'tagged' to the command line and it will print your metadata! There's a movie of how it all work [here](https://asciinema.org/a/9w3vq3y6ehmuyko60fsckcjna).
