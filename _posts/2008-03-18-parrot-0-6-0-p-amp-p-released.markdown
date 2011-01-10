---
layout: default
title: Parrot 0.6.0 "P&amp;P" released
---

<p>On behalf of the Parrot team, I'm proud to announce Parrot 0.6.0
&quot;P&amp;P.&quot; <a href="http://parrotcode.org/" rel="nofollow">Parrot</a>
is a virtual machine aimed at running dynamic languages. This release is a milestone release featuring the revamping of Parrot Magic Cookies.</p><p>Parrot 0.6.0 can be obtained via <a href="http://search.cpan.org/dist/parrot" rel="nofollow">CPAN</a>
(soon), or <a href="http://parrotcode.org/source.html" rel="nofollow">follow the download instructions</a>.
For those who would like to develop on Parrot, or help develop Parrot itself,
we recommend using <a href="http://subversion.tigris.org/" rel="nofollow">Subversion</a>
or <a href="http://svk.bestpractical.com/" rel="nofollow">SVK</a>
on <a href="https://svn.perl.org/parrot/trunk/" rel="nofollow">our source code repository</a>
to get the latest and best Parrot code.</p><p>Parrot 0.6.0 News:</p>

    - Specification
      + launched pdd18_security.pod
      + updated pdd17_pmc.pod
      + launching draft of pdd28_character_sets.pod
    - Documentation
      + cleanup of IMCC documentation
    - Configuration
      + add step auto::gettext
      + add step auto::crypto
    - Compilers
      + PCT:
        . Fix '-e' option
        . Phase out P6Regex in favor of Perl6Regex
      + IMCC:
        '.local Array my_arr' is illegal now
    - Languages
      + C99: reimplementation with PCT
      + lolcode:
        . various updates
        . add support for functions with params
        . add math functions
      + Rakudo:
        . support for 'say'
        . first cut at smart matching
        . indirect method calls
        . support for Pairs
        . added methods 'grep' and 'first'
        . implement auto{increment,decrement}
        . initial implementation of 'perl6doc'
      + Lua:
        . various updates
        . add base64 library
      + Cardinal: basic support for functions with parameters
      + Pheme: various updates
      + Ecmascript: various updates
      + Tcl: now targeting tcl 8.5.1, no more expected failures in test suite.
        (No, this doesn't mean everything's implemented. =-)
      + Eclectus: various updates
      + WMLScript: various updates
    - Implementation
      + PDD17 (PMCs)
      + Add library YAML::Dumper
      + Add the MD2, MD4, MD5, RIPEMD160, SHA & SHA1 PMC, as a wrapper
         around libcrypto
    - Miscellaneous
      + various bugfixes, code cleanups and coding standard fixes
      + consting
      + remove external Perl 5 modules from the Parrot distribution

<p>
Thanks to all our contributors for making this possible, and our sponsors for supporting this project.
</p>
<p>
Enjoy!
</p>
