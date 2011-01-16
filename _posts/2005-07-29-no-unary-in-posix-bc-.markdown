---
layout: post
title: No unary '+' in 'POSIX bc'
---

I'm still trying to learn about computer languages, by targeting 'POSIX bc' to Parrot.
Currently I'm checking whether I got the precedences of '+', '-', '\*', '/' and '%' right.
The harder things are still to come: variables and subroutines.

There is a funny thing I noticed about POSIX bc. POSIX bc has no unary '+',
thus '+1' on a line by itself is a syntax error.

    bernhard@ubuntu:~$ bc -s
    bc 1.06
    Copyright 1991-1994, 1997, 1998, 2000 Free Software Foundation, Inc.
    This is free software with ABSOLUTELY NO WARRANTY.
    For details type 'warranty'.
    1
    1
    -1
    -1
    +1
    (standard_in) 3: syntax error
    0
    0
    quit
    bernhard@ubuntu:~$
