# cache-STREAM
A benchmark to evaluate the effect of caches on the effective bandwidth.
Inspired by the STREAM benchmark by John D. McCalpin we make some small changes
to the original STREAM mpi benchmark to evaluate the effective bandwidth for vector operations when the problem size is small.

In particular, rather than having an array V of size >> the cache size we investigate the effect of performing the same amount of work, 
but decreaseing the array size, but perform the operation several times. We investigate arrays of size $b^k,b^{k-1},...,b^1,b^0$ running each ADD, SCALE, TRIAD kernel $b^0,b^1,..,b^k$ times.

This prompts us to make certain changes to the original benchmark in order to disallow the compiler from removing our outer loop, in partiuclar we make redundant updates of a, b, c.

