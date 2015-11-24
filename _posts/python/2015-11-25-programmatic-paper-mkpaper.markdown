---
author: chris_bull
comments: true
date: 2015-11-25 00:30:00+00:00
layout: post
slug: python-package-mkpaper
title: Programmatic paper writing with MkPaper
categories:
- python
---

MkPaper creates a figure document in 3 + n lines of code, where n is the number of figures you have! 
{: .notice}

Have you ever wished a machine would write your paper for you? 

Wish no more, the future is here!* I've created a Python package that will compile a LaTeX or word document of figures. Basically, you feed the package a path to a figure and a caption and then it will create either:

1. a PDFLaTeX document or a
1. Word Document 

*with those figures and captions inserted*! I've tried to make it as simple and painless to install as possible (just clone the repo'); dependencies are kept to a minimum, specifically:

1. python 2.x
1. pdflatex (optional)
1. python-docx (optional)

Without pdflatex, the package still works (you can create the tex file and not compile). To create a Word document you need python-docx (installable with Anaconda). 

To install the package:
{% highlight python %}
git clone https://github.com/chrisb13/mkpaper.git
{% endhighlight %}

And then, suppose you want to create a word doc, usage looks like...

{% highlight python %}
import mkpaper as mp

#get a list of your figures in PNG format...
import glob
ifiles=sorted(glob.glob(path_to_pngplots + '*.png' ))
assert(ifiles!=[]),"glob didn't find anything!"

#alternatively, we could be more explicit
#ifile[0]=path_to_doc+'penguin1.png'
#ifile[1]=path_to_doc+'penguin2.png'

#instantiate WordFigureDoc class:
#arguments are: path/to/put/figuredocs and name of figure doc..
figobj=mp.WordFigureDoc(path_to_doc,'penguinfigs')
figobj.add_figure(ifiles[0],'first penguin')
figobj.add_figure(ifiles[1],'second penguin')
#etc

#insert the tail of the doc
figobj.end_doc()
{% endhighlight %}

Want to get started? Head over to the [GitHub project here.](http://github.com/chrisb13/mkpaper). Full working examples in [here](https://github.com/chrisb13/mkpaper/tree/master/examples), so you should be up and running in no time!

Feedback and pull requests welcome!

*A touch of hyperbole here ;)
