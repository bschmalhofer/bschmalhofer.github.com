---
layout: default
title: Quine, wisdom teeth pulled
---

This month I didn't get much done on the ANTLR3 front. Instead I did some directory renaming in the Parrot tree, did a quine in PIR and brought the long awaited HQ9+ to Parrot.

Doing a quine in PIR was fun. The first attempt ended up quite cheatingly with a dynamic op 'q' in myops.ops. Then, thanks to google, I found the standard recipe for quines and did 'quine_ord.pir'.
The '_ord' comes from that I use the 'ord' opcode to encode part of the quine code in a data section.

This weekend I finally built up nerves for ANTLR3.
There is now support for testing an ANTLR3 implementation in the 'Parrot bc' test suite. And I started on a dummy grammar for 'bc' with Java as  a backend.

This afternoon I also had two of my wisdom teeth pulled. It went better than expected, and I feel almost up to par right now.

