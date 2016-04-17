---
author: chris_bull
comments: false
date: 2013-07-30 07:35:12+00:00
layout: page
slug: python-resources
title: Python Resources
wordpress_id: 180
---

There are loads of python blogs on the internet. The aspiration of this blog is to provide useful tips on using Python for data analysis for climate science. To start, here are some Python resources I have found useful.
	
  * Johnny Lin's book [_A Hands-On Introduction to Using Python in the Atmospheric and Oceanic Sciences_](http://www.johnny-lin.com/pyintro/) is a friendly introduction. He also runs a Python climate science user [mailing list](http://pyaos.johnny-lin.com/) and [has a list of climate science python tutorials](http://pyaos.johnny-lin.com/?page_id=217). More recently, there's this book: [Python Programming and Visualization for Scientists](http://www.sundogpublishing.com/shop/python-programming-and-visualization-for-scientists-alex-decaria/).

  * Wes McKinney's book [Python for Data Analysis](http://shop.oreilly.com/product/0636920023784.do) is another good primer with chapters devoted to Numpy, Pandas and matplotlib. Wes McKinney has a finance background and is the original author of the Pandas library, as a result, examples from the book are of less interest to climate scientists.
	
  * [Pandas](http://pandas.pydata.org/) is an excellent python tool for manipulating 2d data sets. There is an overview of Pandas [here](http://vimeo.com/59324550).

  * [PyData](http://pydata.org/) is a twice annual conference on using Python for scientists, engineers, and data analysts. You can watch some of the presentations from the March 2012 conference [here](http://pyvideo.org/category/18/pydata). The videos are a great way to get an [overview](http://catchagain.wordpress.com/tag/scipy/) and learn about the ragedy edge in our [favourite](http://pyvideo.org/video/960/python-in-big-data-with-an-overview-of-numpy-sc) modules.

  * The 'ARC Center of Excellence for Climate System Science' has a [code repository on github](https://github.com/coecms/climatescripts). The repository includes Python scripts. The idea is to provide a common space where all the [CCRC](http://www.ccrc.unsw.edu.au/)/[ARC CoECSS](http://www.climatescience.org.au/) staff/students share functions, scripts and programs that might be useful for people working on climate science problems.
	
  * [netcdf4-python](https://code.google.com/p/netcdf4-python/) is now the standard python interface [netCDF](http://www.unidata.ucar.edu/software/netcdf/). There's a list of other Python netCDF paraphernalia [here](http://www.unidata.ucar.edu/software/netcdf/software.html#Python) and [here](http://pyaos.johnny-lin.com/?page_id=20).

  * [Pip](https://pypi.python.org/pypi/pip) or [Conda](http://conda.pydata.org/docs/) and [IPython](http://ipython.org/) will make your python life a million times more pleasant. Use it. Speaking of pleasant, [make IPython use Vi editing](http://stackoverflow.com/questions/10394302/how-do-i-use-vi-keys-in-ipython-under-nix) and automatic indenting (in particular [where it turns tabs into spaces](http://wiki.python.org/moin/Vim)).

  * Want to just start hacking from examples? [Check out these gems](http://earthpy.org/) and these [gems](http://oceanpython.org/).

  * Need some [great practical tips](http://docs.python-guide.org/en/latest/) on best practice?
	
  * [Pdb](http://docs.python.org/2/library/pdb.html) is a handy built-in debugger. There's a quick tour [here](http://www.youtube.com/watch?v=bZZTeKPRSLQ).

  * [Python logging](http://docs.python.org/2/library/logging.html) is worth the effort (i.e. it really is better than print statements).

  * Since we want our results to be transparent and reproducible, there's really no excuse for not using version control. [Bitbucket and Git](http://blog.bitbucket.org/2011/10/03/bitbucket-now-rocks-git/) work wonderfully.

  * [Felipe Fernandes writes an interesting blog](http://ocefpaf.github.io/) not dissimilar to this, he has tips and examples for using Python in oceanography.
	
  * [Stackoverflow](http://stackoverflow.com/questions/tagged/python).


Plotting using matplotlib:
  * Two good primers ([1](http://www.loria.fr/~rougier/teaching/matplotlib/) and [2](http://nbviewer.ipython.org/urls/raw.github.com/jrjohansson/scientific-python-lectures/master/Lecture-4-Matplotlib.ipynb)) with examples.

  * Basemap ([1](http://matplotlib.org/basemap/users/examples.html), [2](http://peak5390.wordpress.com/2012/12/08/matplotlib-basemap-tutorial-installing-matplotlib-and-basemap/) and [3](http://www.geophysique.be/tutorials/) and [4](http://wiki.scipy.org/Cookbook/Matplotlib/Maps))

Coming from matlab? The following two links are a [cheat sheet](http://mathesaurus.sourceforge.net/) and instructions on [how to import .mat files](http://docs.scipy.org/doc/scipy/reference/tutorial/io.html).

If there are other resources you think are great, send me an [email](mailto:christopher.y.bull@student.unsw.edu.au) and I'll look into it.
