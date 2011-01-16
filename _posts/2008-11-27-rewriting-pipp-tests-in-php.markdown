---
layout: post
title: Rewriting Pipp tests in PHP
---

Pipp is Parrot's PHP and it has small test suite that lives alongside the code in the Parrot repository.
Most of the test scripts are written in Perl 5 using the Parrot::Test modules.
So usually I tell Pipp to run some PHP code and check whether the expected result is printed.
This works fine but is not very exiting.

More exciting, for some definition of exciting, is to run PHP scripts and emit TAP with a testing lib implemented in PHP. So Pipp this needs
  1. user defined functions with param passing
  2. *global* for keeping track of the running test count
  3. module loading

Stealing from Rakudo I now got most of that.
*global* is still missing, so currently I pass in the current test number
and increment it outside the testing functions.

Over the next days I plan to port a selection of the easier scripts to PHP.
Things like TODO, SKIP and regex matching have to wait for later. Takers welcome!
