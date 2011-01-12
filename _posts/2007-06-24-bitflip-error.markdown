---
layout: default
title: Bitflip error
---

On Friday a colleague @work asked me about an
error in a webapplication. There was a Perl syntax
error in Sys::Hostname. As I saw no reason that anybody should mess with with Sys::Hostname, I checked the time Hostname.pm was last changed.
Confusingly the last change was in 2004, apparently this was the time the server was set up.
A diff with another
Perl 5.8.0 installation showed a single bit change.
The first space, 0x20, of Hostname.pm line 104 has turned into into a '(', 0x28.
The only explanation I can imagine is that a bit has flipped in file cache.

<em>Strange.</em>
