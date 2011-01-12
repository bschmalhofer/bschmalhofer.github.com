---
layout: default
title: HQ9+ reimplemented with PCT
---

Klaas Jan's excellent "Parrot Compiler Tools" - Tutorial inspired me to go back and reimplement HQ9+ with PCT. The result is in <a href="http://svn.perl.org/viewvc/parrot/trunk/languages/hq9plus/" rel="nofollow">http://svn.perl.org/viewvc/parrot/trunk/languages/hq9plus/</a>.

As HQ9+ is not really a hard language, it all went fairly smooth. 'mk_language_shell.pl' created me a stub in 'languages/hq9plus'. Then I copied some reusable files from the old implementation in 'languages/HQ9plus'. This was fine under Linux, but caused pain for folks on case-insensitive file systems. Sorry, next time I try to think before committing!

For looking up snippets of PAST I used the old trick: write a snippet of Perl 6 and look at the PAST that Rakudo generates.

The last problem was whitespace handling. For that I only needed a simple change in the grammar. Replace all 'rule's by 'token's and sprinkle some '\s*'s.

The next thing on my agenda is for Plumhead and Eclectus. I want to switch from 'generate PIR that sets up PAST' to 'generate NQP that sets up PAST'.
