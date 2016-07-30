Text from the [original web-page](http://www.tiac.net/~sw/2008/10/Hilbert/moore/):


> ##Fast Hilbert Curve Generation, Sorting, and Range Queries
>
> Hilbert curves are one of a class of space filling curves - continuous, nonsmooth curves that pass arbitrarily close to every point in space of arbitrary dimension - and much information about planar Hilbert curves is on the web - see here for example - but little information on efficient generation of Hilbert curves and related activities like Hilbert sorting, Hilbert range queries, and so on, is available.  The common recursive generation of planar Hilbert curves does not easily lead to fast nonrecursive algorithms for related problems, nor to higher-dimensional generalizations. A rather opaque description of a nonrecursive algorithm by Butz ("Alternative Algorithm for Hilbert's Space-Filling Curve", IEEE Trans. Comp., April, 1971, pp 424-426) led to an implementation by Spencer Thomas that appeared in Graphics Gems and has been widely circulated on the net.
>
>I began with his implementation, and began rearranging it to eliminate the need for various precomputed tables.  In the process, I found that the basic index-to-point and point-to-index calculations could be made quite terse, without any supplementary tables.  I extended those algorithms to allow the comparison of two points to see which falls first on a Hilbert curve.  Although this comparison can be achieved by converting each point to its integer index and comparing integers, there can be a problem with regard to the size of the resulting integers overflowing conventional integer types.  My implementation of the comparison is less sensitive to this problem.  Further extensions led to algorithms for finding the first vertex of a box to appear on the Hilbert curve, finding the first point (not necessarily a vertex) of a box to lie on the curve, and for finding the first point after a given point to lie in the box.
>
>The purpose of this work is to enable efficient multidimensional searches and to associate spatial locality in searches with spatial locality in the ordering of items in a B-tree based database.  With the ability to find the first point in a box after a given point, it is possible to enumerate all the points in the database within a box without examining every point in the database.   Likewise, it would be possible to compute efficiently "spatial joins" - that is, all pairs of points that both lie in some small box.
>
>At this point, I can explain the algorithms best by offering the source code, so here is the C [source](hilbert.c) and here is the corresponding [header](hilbert.h) file.
>
>Please let me know if you find this implementation of nonrecursive multidimensional Hilbert curve methods useful or entertaining.
>
>Doug Moore 
>(dougm@...edu)

####License
From the [code](hilbert.c):
```
/* LICENSE
 *
 * This software is copyrighted by Rice University.  It may be freely copied,
 * modified, and redistributed, provided that the copyright notice is 
 * preserved on all copies.
 * 
 * There is no warranty or other guarantee of fitness for this software,
 * it is provided solely "as is".  Bug reports or fixes may be sent
 * to the author, who may or may not act on them as he desires.
 *
 * You may include this software in a program or other software product,
 * but must display the notice:
 *
 * Hilbert Curve implementation copyright 1998, Rice University
 *
 * in any place where the end-user would see your own copyright.
 * 
 * If you modify this software, you should include a notice giving the
 * name of the person performing the modification, the date of modification,
 * and the reason for such modification.
 */* 

```