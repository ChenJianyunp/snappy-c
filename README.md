![snappy-c](http://halobates.de/snappy-c.png)

My change on it
----
This is a modified snappy compression software forked from google. It change the compression algerithm a little while keep the Snappy format. I add a threshhold to update function of hash table, so the hash table will not be updated after every match, thus the copy token will not always copy from the nearest match. From the real test, this change cause almost no reduction on compression ratio, but making the performance of parallel decompression on some data much batter.\
changed file:\
Makefile, snappy.c\



Original README is below
-------

This is a C port of the google snappy compressor (http://code.google.com/p/snappy/)
The compressor is very fast with reasonable compression ratio.
It is mainly useful for projects that cannot integrate C++ code, but want snappy.
Also contains a command line tool, a benchmark, random test code and a fuzz tester.

The compression code supports scather-gather and linear buffers. The scather
gather code is ifdefed (-DSG) and can be removed with unifdef.

API documentation: http://halobates.de/snappy.html

To generate the documentation run

	make html

Requires the kerneldoc script from a Linux kernel source (may need to point
the makefile to it). If you don't have the kernel source lying around
just download it from
https://git.kernel.org/cgit/linux/kernel/git/torvalds/linux.git/plain/scripts/kernel-doc
and point the Makefile to it.




Andi Kleen
