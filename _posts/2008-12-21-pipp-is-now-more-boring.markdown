---
layout: post
title: Pipp is now more boring
---

Comparing different parsing and tree transformation techniques was for me
a major reason for starting work on Pipp. Therefore Pipp had until now support for different frontends:

  * Antlr 3: Parsing and tree transformation with Java-based Antlr 3
  * PHC: Take XML-output from phc and transform it with XSLT
  * PCT: Parrot Compiler Toolkit

Lately I found that I only worked on the PCT variant.
So in order to keep it simple, especially for new contributors, I removed
support for Antlr3 and PHC.

So, Pipp is now more boring, but other exciting things are coming.
