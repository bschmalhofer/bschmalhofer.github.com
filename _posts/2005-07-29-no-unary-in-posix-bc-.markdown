---
layout: default
title: No unary '+' in 'POSIX bc'
---

I'm still trying to learn about computer languages, by targeting 'POSIX bc' to Parrot. Currently I'm checking whether I got the precedences of '+', '-', '*', '/' and '%' right.
The harder things are still to come: variables and subroutines.

There is a funny thing I noticed about POSIX bc. POSIX bc has no unary '+', thus '+1' on a line by itself is a syntax error.
</p><blockquote><div><p> <tt>bernhard@ubuntu:~$ bc -s<br>bc 1.06<br>Copyright 1991-1994, 1997, 1998, 2000 Free Software Foundation, Inc.<br>This is free software with ABSOLUTELY NO WARRANTY.<br>For details type `warranty'.<br>1<br>1<br>-1<br>-1<br>+1<br>(standard_in) 3: syntax error<br>0<br>0<br>quit<br>bernhard@ubuntu:~$</tt></p>
