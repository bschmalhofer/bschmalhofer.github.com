---
layout: post
title: embedded databases for Parrot
---

In the last weeks, I have been looking into dynamic PMCs in Parrot. They are not very different from Parrot core PMCs.Users just have to look up the dynamic ID, before they can create a instance.

As an example I worked on the <b>GDBMHash PMC</b>. This is a binding the GNU dbm, a file dictionary. The basic implementation was straightforward. The configuration is somewhat akward. I need to check wether 'libgdbm.so' exists. Currently I have added this check to the core Parrot configuration. It would be nicer to have a seperate configuration step for Parrot extensions. It would be cool to do that in PIR, as Parrot already exists when extensions are added.

Looking back, using 'gdbm' for the example was propably not the best choice. Berkely DB seems to be much more widely used. As far as I remember, Bio::Index::Fasta is based on Berkeley DB.

A more interesting dynamic PMC would be access to Piddles.
Piddles are the basis data structure of the Perl Data languages, <a href="http://pdl.perl.org/" rel="nofollow">http://pdl.perl.org/</a>.
But before digging into that, I propably should tidy up the 'Parrot YAML' and rework 'Parrot m4'.

