---
author: chris_bull
comments: true
date: 2013-07-30 06:36:22+00:00
layout: post
slug: using-matplotlib-and-ffmpeg-to-make-movies
title: Bug with Matplotlib when making movies.
wordpress_id: 165
categories:
- python
tags:
- bug
- ffmpeg
- movie
- movies
- python
---

I wanted to make a movie, the plan was to use Matplotlib to make the frames and then stitch them together using ffmpeg. The problem I had was that I'd make about 1000 frames and then it would crash with this rather obtuse error:

{% highlight python %}
RuntimeError: Could not open facefile /share/apps/python/2.7.2/lib/python2.7/site-packages/matplotlib/mpl-data/fonts/ttf/Vera.ttf; Cannot_Open_Resource
{% endhighlight %}

I suspected it was leaking memory and running the script on a bigger machine confirmed it. It turns out you have to be explicit rather than implicit when defining your figure/axes. Bit of annoying bug really. To better explain, basically I had:

    
{% highlight python %}
    for loop_through_picture_maker:
        plt.close('all')
    
        #code that produces a plot using implicit figure and axes
    
        plt.close()
{% endhighlight %}


And what I needed was:

    
{% highlight python %}
    fig=plt.figure()
    for loop_through_picture_maker:
        ax=fig.add_subplot(111)
    
        #code that produces a plot using explicit figure and axes
    
        fig.clf()
        del ax
{% endhighlight %}


My thanks to [Jean-François Exbrayat](http://www.climatescience.org.au/staff/profile/jexbrayat) for pointing out the bug.

NB: this was with Matplotlib 1.1.0.
