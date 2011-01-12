---
layout: default
title: Parrot Abstract Syntax Tree in Scheme-XML
---

As I'm hacking away at Eclectus, Scheme on Parrot in Scheme,
I'm starting to pick some Scheme knowledge.
So before implementing new features I employed my new wisdom
and did some refactoring on my Scheme code.

The most nasty thing in compiler.scm was the generation of PIR
while traversing the to-be-compiled s-expression.
I decided to use XML Infoset as an intermediate representation,
as I already have an XSLT sheet for generating a PIR representation of PAST
from an XML representation of PAST. The nice thing is that
the XML infoset can also be represented as a Scheme s-expression, that is SXML.
The Scheme librarx SSAX-SXML can turn SXML into XML and perform XSLT operations.


For an example let's look at the Scheme form:
    (fx+ (fx+ -10 11) (fx+ (fx+ 4 3) (fx+ 3 3)))
