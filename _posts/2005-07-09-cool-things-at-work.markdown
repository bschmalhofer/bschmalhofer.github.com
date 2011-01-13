---
layout: default
title: Cool things at $work
---

My main project at $work is a Mason-based webapplication for keeping track of interesting biological sequences. As a new round of develoment is just starting, I finally took some time to do some refactoring and to beef up my test suite.

Almost all the application logic, interface to the database and connection to the world is wrapped in a set of Perl5 modules. Running the existing test suite with Devel::Cover was dead easy. It immediately showed me missing tests. Even better, it pointed me to some obsolete code. This is very good, as deleted code is guaranteed to be bugfree code.

The next toy was Test::TAP::HTMLMatrix. I think that there is no support from Module::Build yet, but I could avoid coding by fetching a script from <a href="http://www.hutchinsonsoftware.com/misc/run_tap" rel="nofollow">http://www.hutchinsonsoftware.com/misc/run_tap</a>.
There is still some red in the generated HTML, but I blame it on the world, that keeps on changing.

In the left frame of the webapplication there is a project tree, that can contain several hundred nodes. This used to be a homegrown tree, but I replaced it with a COOLjsTree, <a href="http://javascript.cooldev.com/scripts/cooltree/" rel="nofollow">http://javascript.cooldev.com/scripts/cooltree/</a>.
The COOLjsTree has a fairly complete API and certainly looks more professional than my old tree. My old tree only excelled in the speed of opening and closing subtrees, as it was simply a nested unordered list with some CSS and JavaScript.

I also switched to returning instances of Return::Value from some methods. It is nice to have a standardized returnvalue. However I feel somewhat uneasy about the overloaded get_bool() and get_string().

What are the next cool things? Catalyst with HTML::Mason views sound good for the next project.
For web testing I'd like to use HTTP::Recorder and WWW::Mechanize, but I think that I can't do without JavaScript support.

