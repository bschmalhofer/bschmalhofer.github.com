---
layout: post
title: Closures for Pipp
---

In the last days I have been working on supporting closures for Pipp. Yes, you've read correctly. The next version of PHP will support real closures. See
<a href="http://www.ibm.com/developerworks/opensource/library/os-php-5.3new2/index.html?ca=drs-tp5008" rel="nofollow">http://www.ibm.com/developerworks/opensource/library/os-php-5.3new2/index.html?ca=drs-tp5008</a> for a nice writeup.

Closures are connected with lexical variables, so I had I had to rethink the way I handle variables in Pipp. Initially I had the variables outside functions as package variables. Since this doesn't play well with closures, and as there are problems with included files, I changed those to lexical variables. This was the major part of the work. Thanks to Patrich Michaud for advising me where I should define the lexicals.

After switching to lexicals everywhere I followed my usual approach and tried to do the same as Rakudo does. This worked without hassle for a simple case.

    <?php

      function gen_indentor ( ) {
          $indention = '+';
          $indentor = function ($line) use ($indention) {
              echo $indention . $line . "\n";
          };

          return $indentor;
      }

      $sub_1 = gen_indentor();

      $sub_1('one plus');

    ?>

correctly gives:

    +one plus

But when I create a second closure I run into problems.

    <?php

      function gen_indentor ($indention) {
          $indentor = function ($line) use ($indention) {
              echo $indention . $line . "\n";
          };

          return $indentor;
      }

      $sub_1 = gen_indentor('+');
      $sub_4 = gen_indentor('++++');

      $sub_1('one plus');
      $sub_2('four plusses');

    ?>

incorrectly gives:

    ++++one plus
    ++++four plusses

Looks like I need to fiddle some more.
