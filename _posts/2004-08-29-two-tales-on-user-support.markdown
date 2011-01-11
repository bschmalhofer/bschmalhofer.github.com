---
layout: default
title: two tales on user support
---

During last week I had two experiences with user support.

# Tale 1: broken telephone line

*Sunday*: I wanted to do some stuff for Parrot and found that my 56k-modem didn't work.
My phone didn't have a dial tone, but emitted strange noise.
*Monday*: My upstairs neighbor, an elderly lady, told me that the whole block had problems
and that it is supposed to be fixed today. Being lazy, I didn't call the phone company.
In the evening the phone emitted the same strange noise.
*Tuesday*: After more than 10 clicks on the WWW site of the phone company
I found the relevant phone number for their technical customer support.
When calling them the support guys made a remote measurement and couldn't find anything wrong with the line.
Same strange noises in the evening.
*Wednesday*: Called the phone company again and they filed it as a real problem.
Fixed a date for Thursday 16:00, when a technician would check the line.
*Thursday*: At work I got a call from the phone company that my phone should be working again.
In the evening the phone was really OK.
Later my upstairs neighbor told me that she still had problems.
I promised to call the phone company for her.
*Friday*: Called the phone company on behalf of my elderly neighbor,
and was advised to try a different phone. At my neighbors I found that her phone was working well,
but that her hearing aid went berserk, when using the phone.
I advised her to have her hearing aid checked.
*Saturday*: Went to a birthday party of the nice of my girl friend.
*Sunday*: Called the elderly lady from the place of my girl friend.
Everything is fine when she places the telephone receiver further away from the hearing aid.

# Tale 2: DB::Introspector
*Two months ago*: At work I wrote a little migration script for a relational database.
I used DB::Introspector for checking wether a MySQL database table had the needed indexes.
Found a little problem with DB::Introspector, fixed it, and didn't bother to send in a patch.
*Friday*: Needed the mentioned migration script for a software installation on a test machine.
Installed DB::Introspector and ran into the old problem. I remembered my fix from two months ago and applied it.
This time I filed the patch in http://rt.cpan.org.
*Saturday*: Read on use.perl that a new revision of DB::Introspector is out.
When checking on CPAN I found the it took masahji less than two hours
to apply the patch and prepare a new revision.

I don't know what can be learned from the two tales.
For me, tale 1 was much more frustrating than tale 2.
On the other side, problem 1 took one week to be resolved,
while problem 2 lingered for two months because I didn't take 5 minutes for a very simple problem report.
