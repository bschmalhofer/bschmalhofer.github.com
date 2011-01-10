---
layout: default
title: Rewriting Pipp tests in PHP
---

<p>Pipp is Parrot's PHP and it has small test suite that lives alongside the code in the Parrot repository. Most of the test scripts are written in Perl 5 using the Parrot::Test modules.
So usually I tell Pipp to run some PHP code and check whether the expected result is printed.
This works fine but is not very exiting.
</p><p>
More exciting, for some definition of exciting, is to run PHP scripts and emit TAP with a testing lib implemented in PHP. So Pipp this needs
</p><ol>
<li>user defined functions with param passing</li><li> <b>global</b> for keeping track of the running test count</li><li>module loading</li></ol><p>
Stealing from Rakudo I now got most of that.
<b>global</b> is still missing, so currently I pass in the current test number and increment it outside the testing functions.
</p><p>
Over the next days I plan to port a selection of the easier scripts to PHP. Things like TODO, SKIP and regex matching have to wait for later. Takers welcome!
</p>
