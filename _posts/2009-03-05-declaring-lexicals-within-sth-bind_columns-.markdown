---
layout: default
title: Declaring lexicals within $sth-bind_columns()
---

Lately I have taken on the maintainance of a legacy Perl 5 script. The script heavily uses the DBI function bind_columns() for retrieving data from a relational database. After some refaktoring I ended up with something like this:<blockquote><div><p> <tt>my $sth = $dbh-&gt;prepare(&lt;&lt;'END_SQL');<br>SELECT color, food, num_legs<br>&nbsp; FROM pet<br>END_SQL<br>my ( $food, $something_else, $color, $num_legs);<br>$sth-&gt;bind_columns( \$color, \$food, $num_legs );</tt></p>
