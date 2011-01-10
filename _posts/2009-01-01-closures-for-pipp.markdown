---
layout: default
title: Closures for Pipp
---

<p>
In the last days I have been working on supporting closures for Pipp. Yes, you've read correctly. The next version of PHP will support real closures. See
<a href="http://www.ibm.com/developerworks/opensource/library/os-php-5.3new2/index.html?ca=drs-tp5008" rel="nofollow">http://www.ibm.com/developerworks/opensource/library/os-php-5.3new2/index.html?<nobr>c<wbr></nobr> a=drs-tp5008</a> for a nice writeup.
</p><p>
Closures are connected with lexical variables, so I had I had to rethink the way I handle variables in Pipp. Initially I had the variables outside functions as package variables. Since this doesn't play well with closures, and as there are problems with included files, I changed those to lexical variables. This was the major part of the work. Thanks to Patrich Michaud for advising me where I should define the lexicals.
</p><p>
After switching to lexicals everywhere I followed my usual approach and tried to do the same as Rakudo does. This worked without hassle for a simple case.</p><blockquote><div><p> <tt>&lt;?php<br> <br>&nbsp; function gen_indentor ( ) {<br>&nbsp; &nbsp; &nbsp; $indention = '+';<br>&nbsp; &nbsp; &nbsp; $indentor = function ($line) use ($indention) {<br>&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; echo $indention . $line . "\n";<br>&nbsp; &nbsp; &nbsp; };<br> <br>&nbsp; &nbsp; &nbsp; return $indentor;<br>&nbsp; }<br> <br>&nbsp; $sub_1 = gen_indentor();<br> <br>&nbsp; $sub_1('one plus');<br> <br>?&gt;</tt></p>
