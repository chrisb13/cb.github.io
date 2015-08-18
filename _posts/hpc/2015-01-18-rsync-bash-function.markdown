---
author: chris_bull
comments: false
date: 2015-08-18 00:30:00+00:00
layout: post
slug: bash-function-rsync
title: Bash function for painless rsync.
categories:
- hpc
---

My life consists of three problems...

1. I work on many different machines.
1. I spend a lot of time moving files around.
1. I can never remember the right rsync flags and my fingers are lazy.

The third problem means I never want to deal with the first two.. Sound familiar? 

Here's some bash functions to help you push and pull files from a remote location. 

We have one bash function for pulling files....

{% highlight bash %}
function servername_pull()
{
    if [[ ( $# -eq 0 ) || ( $1 == "--help" ) || ( $1 == "-h" ) ]] ; then
        echo "Usage:   servername_pull [path_from] [path_to]." 
        echo "Purpose: rsync function to pull files from servername." 
        echo "       " 
        echo "Mandatory arguments: " 
        echo "path_from: Path on server to Rsync from" 
        echo "path_to:   Path on local to Rsync to" 
        echo "       " 
        echo "Example." 
        echo "This:" 
        echo "servername_pull /home/server/path/*.py ./temp"
        echo "       " 
        echo "Becomes:" 
        echo "rsync -avz --progress server_username@server.address.edu.au:/home/server/path/*.py ./temp"

        return 1
    fi
    rsync -avz --progress server_username@server.address.edu.au:$* 
}
{% endhighlight %}

And another (slightly more complicated) bash function for pushing files....

{% highlight bash %}
function servername_push()
{
    if [[ ( $# -eq 0 ) || ( $1 == "--help" ) || ( $1 == "-h" ) ]] ; then
        echo "Usage:   servername_push [path_from] [path_to]." 
        echo "Purpose: rsync function to push files to servername." 
        echo "       " 
        echo "Mandatory arguments: " 
        echo "path_from: Path on server to Rsync from" 
        echo "path_to:   Path on local to Rsync to" 
        echo "       " 
        echo "Example." 
        echo "This:" 
        echo "servername_push ./temp/* /home/server/path/"
        echo "       " 
        echo "Becomes:" 
        echo "rsync -avz --progress ./temp/* server_username@server.address.edu.au:/home/server/path/"

        return 1
    fi
    #grabs last passed argument..
    for last; do true; done

    #grabs all arguments but the last one...
    #echo ${@:1:$(($#-1))}

    rsync -avz --progress ${@:1:$(($#-1))} server_username@server.address.edu.au:$last
}
{% endhighlight %}

So, if you put these in your [.bashrc](http://superuser.com/questions/49289/what-is-the-bashrc-file) with your relevant server details you should be good to go! Feel free to change the switches if you prefer something else, do get in touch if you improve these, it's impractical to currently pass include/exclude statements at present for instance...

Also, life is a lot more smooth if you're using [ssh keys](https://www.digitalocean.com/community/tutorials/how-to-set-up-ssh-keys--2).

