---
layout: default
title: 'make distclean' is not my friend
---

<p>
Over the weekend I have been looking into the Perl Data Language, PDL. Nice! There is ample support for visualisation and the Gnu Scientific Library is there too.
</p><p>
However for the next picture drawing, or number crunching task, I would like to finally get started on R. I think that with R it is much easier to do statistics. Also there seem to exist some bioinformatics packages for R.
</p><p>
Back to PDL:
The basic data structure of PDL is a multidimensional array, usually called 'piddle'. It would be a nice challenge to bring piddles to Parrot as PMCs. Loooking at the docs and the C header files, it shouldn't be too hard. One should be able to load the shared libs that are already generated for Perl5.
</p><p>
For my work on bringing 'libsyck' to Parrot, there is good and bad news. The good news is that synchronous callbacks are now in Parrot. 'libsyck' really needs synchrounous callbacks, as it passes  weak references back to the Parrot interpreter.
</p><p>
The other good news is, that St&#233;phane Payrard started to work on a multifacetted PMC, 'siva'. The 'siva' PMC seems to be ideal for building up a parse tree of a YAML document.
</p><p>
The bad new is, that a couple of weeks ago I did a 'make distclean' on my working copy of the Parrot sources. This sent all my new libsyck files into Nirvana. Luckily I'm doing this for fun.
</p>
