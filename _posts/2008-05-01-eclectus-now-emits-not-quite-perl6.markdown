---
layout: post
title: Eclectus now emits Not Quite Perl6
---

Eclectus is a Scheme-compiler implemented in Scheme.
The compilation target is a Parrot Abstract Syntax Tree, which is being run with the help of the Parrot Compiler Toolkit.

A sideline in Eclectus is the the problem how to tell PCT about the PAST generated in Scheme. Up to now I generated PIR that built up that data structure. This involved nasty dealings with unique ids for Parrot registers.

Generating NQP is much saner. The PAST is now set up with nested PAST::Node constructors.

Even nicer would be to create a YAML representation of PAST. But PCT doesn't support this yet.
