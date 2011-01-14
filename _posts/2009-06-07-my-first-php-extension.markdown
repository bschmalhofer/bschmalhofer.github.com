---
layout: default
title: My first PHP extension
---

PHP Extensions are usually written C and they usually export
at least one constant, function, class, resource type or stream to the PHP userspace.
So they are pretty much the same as XS-Modules in Perl 5.
Extensive information about PHP extension can be found in Sara Golemons book 'Extending and Embedding PHP'.

The several hundred standard functions of PHP are implemented in terms of extensions.
[Pipp](http://pipp.org/) either needs to reimplement this massive count of functions,
or support extensions natively. Being lazy, native support for extensions is the way to go.
So let's see how to create a dummy PHP extension. The following is for Linux and is based on the tutorial
[1021-Extension-Writing-Part-I-Introduction-to-PHP-and-Zend](http://devzone.zend.com/article/1021-Extension-Writing-Part-I-Introduction-to-PHP-and-Zend).
The first step is to build PHP 5.3 with development support.
The source can be checked out from a CVS repository. See <a href="http://www.php.net/anoncvs.php" rel="nofollow">http://www.php.net/anoncvs.php</a> for details and the password for anonymous CVS access.

    mkdir ~/first_php_extension
    cd ~/first_php_extension
    cvs -d :pserver:cvsread@cvs.php.net:/repository login
    cvs -d :pserver:cvsread@cvs.php.net:/repository checkout -r PHP_5_3 php5
