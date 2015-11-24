---
author: chris_bull
comments: true
date: 2015-09-05 00:30:00+00:00
layout: post
slug: bash-function-clipit
title: Grabbing paths straight to the clipboard.
categories:
- hpc
---

Do you remember the moment when you realised in Linux that clicking the mouse wheel pasted selected text? I had a similar reveleation when I discovered xclip recently, a handy utility for pushing text into the clipboard. I'm forever copying and pasting paths from SSH sessions so here's a bash function that does the work for you...

{% highlight bash %}
function clipit() #clipit path 
{
    if [[ ( $# -eq 0 ) || ( $1 == "--help" ) || ( $1 == "-h" ) ]] ; then
        echo "Usage: clipit FILENAME_PATHNAME" 
        echo "Purpose: gets full path of file or path and places in clipboard." 
        echo "       " 
        echo "Requires: xclip" 
        echo "       " 
        echo "Mandatory arguments: " 
        echo "FILENAME_PATHNAME: path to folder or file" 
        echo "       " 
        echo "Example." 
        echo "clipit filename.txt" 
        echo "       " 
        echo "becomes:       " 
        echo "readlink -e filename.txt|tr -d '\n'|xclip -selection c"

        return 1
    fi
  readlink -e ${1}|tr -d '\n'|xclip -selection c
}
{% endhighlight %}

If you're got apt-get and sudo rights, then you can install xclip with:
{% highlight bash %}
sudo apt-get install xclip
{% endhighlight %}

If you don't have either of the above, then you can compile from source with (defaults to the slow but likely available GNU compiler):
{% highlight bash %}
cd 
wget wget http://downloads.sourceforge.net/project/xclip/xclip/0.12/xclip-0.12.tar.gz
tar -xvf xclip-0.12.tar.gz
mv xclip-0.12 xclip
cd xclip
./configure --prefix=$HOME/xclip
make
{% endhighlight %}

Seems like a bit of work but it's pretty quick. And then, once compiled, add the following to your ~/.bashrc...
{% highlight bash %}
#add xclip to the end of bash path
PATH=$PATH:~/xclip/
{% endhighlight %}

This assumes that you compiled in ~/xclip/ as above. Happy speedy copy/pasting!
