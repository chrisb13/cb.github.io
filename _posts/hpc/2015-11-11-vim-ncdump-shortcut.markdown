---
author: chris_bull
comments: true
date: 2015-11-11 00:30:00+00:00
layout: post
slug: vim-shortcut-ncdump
title: Vim and netCDF files.
categories:
- hpc
---

I often finding myself wanting basic information about netCDF files when writing scripts that read/write netCDF files... 

The following ncdump command provides a useful overview. The mapping grabs the clipboard register and opens the corresponding netcdf header in a new vim vertical split..

{% highlight vim %}
nnoremap <leader>nc :vnew<Bar>0r!ncdump -c <C-R>+<CR>
{% endhighlight %}

What about if you want to have a quick look at a plot of one of the variables? Works with ncview too!

{% highlight vim %}
nnoremap <leader>ncv :exec '!ncview <C-R>+'<CR>
{% endhighlight %}

Speaking of working with netCDF files, here's a handy [snippet](https://github.com/sirver/ultisnips) for the python library...

{% highlight python %}
snippet loadnetcdf
from netCDF4 import Dataset
infile='/path/to/netcdf4/file.nc'
ifile=Dataset(infile, 'r')
varone=ifile.variables['']
endsnippet
{% endhighlight %}

