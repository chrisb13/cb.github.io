---
author: chris_bull
comments: true
date: 2015-01-01 00:30:00+00:00
layout: post
slug: vim-netrw
title: Editing files remotely
categories:
- hpc
---

I often find myself wanting to edit a file on a remote machine but ssh is too slow to be running a text editor on the remote machine.. Solution? Vim can use rsync to download a copy of the file and then when you save it, it saves it back to the remote location!

Here's a bash function I wrote to make it all easy....

{% highlight bash %}
function vim_servername() 
{
    if [[ ( $# -eq 0 ) || ( $1 == "--help" ) || ( $1 == "-h" ) ]] ; then
        echo "Usage:   vim_servername [path_to]." 
        echo "Purpose: Allows remote editing of files on servers..." 
        echo "       " 
        echo "Mandatory arguments: " 
        echo "path or file: vim will either edit or open path passed" 
        echo "       " 
        echo "Example." 
        echo "This:" 
        echo "vim_servername /server/path/or/file/"
        echo "       " 
        echo "Becomes:" 
        echo "vim scp://username@server.address.edu.au//server/path/or/file/"

        return 1
    fi

    vim scp://username@server.address.edu.au/${1} 

}
{% endhighlight %}

So, just put these in your [.bashrc](http://superuser.com/questions/49289/what-is-the-bashrc-file) with your relevant server details and you should be good to go! Best to be using [ssh keys](https://www.digitalocean.com/community/tutorials/how-to-set-up-ssh-keys--2), that way you're not typing in your password everytime you save..
