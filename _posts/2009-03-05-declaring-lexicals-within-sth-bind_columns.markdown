---
layout: post
title: Declaring lexicals within $sth-bind_columns()
---

Lately I have taken on the maintainance of a legacy Perl 5 script.
The script heavily uses the DBI function bind_columns() for retrieving data from a relational database.
After some refaktoring I ended up with something like this:

    my $sth = $dbh->prepare(<<'END_SQL');
    SELECT color, food, num_legs
        FROM pet
    END_SQL
    my ( $food, $something_else, $color, $num_legs);
    $sth->bind_columns( \$color, \$food, $num_legs );
