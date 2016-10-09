---
author: chris_bull
comments: true 
date: 2014-01-08 00:30:00+00:00
layout: post
slug: gotcha-in-pandas-using-hdfstore-frame_tables
title: Gotcha in Pandas using HDFStore frame_tables
wordpress_id: 628
categories:
- python
---

Recently, I changed from using regular [pytable HDFStores to fancy frame_tables](http://pandas.pydata.org/pandas-docs/dev/io.html#io-hdf5). The move was mostly for the better as my HDFStores were big. Of course, my old code modifying the dataframes broke because of this little bit of syntax...

{% highlight python %}
In [1]: import pandas as pd
In [2]: p=pd.HDFStore('/path/to/some/hdfstore.h5')
In [3]: p.DF['latitude'][0]=20
In [4]: p.DF['latitude'][0]
Out[4]: -25.0
In [5]: DF=p.select('DF')
In [6]: DF['latitude'][0]=20
In [7]: DF['latitude'][0]
Out[7]: 20.0
In [8]: p                                                                                                                            
Out[8]:                                                                                                                              
                                                                                               
File path: /path/to/some/hdfstore.h5                              
/DF                frame_table  (typ->appendable,nrows->24165608,ncols->7,indexers->[index],dc->[longitude,latitude,depth_m,abstime])
/PARLOC            frame_table  (typ->appendable,nrows->17913,ncols->4,indexers->[index])
In [10]: pd.__version__                                                                                                              
Out[10]: '0.12.0' 
{% endhighlight %}

Of course, the annoying part is that line four doesn't throw an error message!

