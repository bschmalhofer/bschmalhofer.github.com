---
layout: default
title: Back to YAML/Parser/Syck.imc
---

YAML is again on top of my ever changing Parrot project list. I'd like to get YAML working, before continuing with m4, PDL and ECMAScript.

Initially I had started with libsyck 0.42. However, libsyck is now at 0.45. In order to be on the bleeding edge, I checked out the CVS version. First I couldn't built a shared libsycks.so from the CVS sources. This changed after I applied the complete patch of my changes. I had forgotten to set up the shared libs in Makefile.am.

After a long session with 'ddd' I got libsyck to call the Parrot callback when there is a new node encountered. The next step is to set up the appropriate data structure in the Parrot interpreter. The idea is to use the Siva PMC for that.

The current state of YAML/Parser/Syck.imc can now be tracked on the  <a href="http://yaml.kwiki.org/index.cgi?ParrotDev" rel="nofollow">YAML Kwiki</a>

