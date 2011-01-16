---
layout: post
title: First steps with ANTLR and Python
---

I'm still trying to find the ultimate tool for implementing languages on Parrot. Never having to take a compiler construction class, and not really needing it at work, I'm not familiar with any of common parsing tools.

For now I'm getting down with ANTLR, trying to bring 'bc' to Parrot.
'bc' is actually a neat little language, I like it much better than 'm4'.
The main purpose of 'bc' is of course the evaluation of arithmetic expressions.
But there are also variables and subroutines. So 'bc' might be nice sandbox
for playing with the PAST interface of Parrot.

ANTLR looks very good to me. Like with lex/yacc a syntax definition is transformed into code for lexers and parsers. The pros are
  * Mature, with lots of documentation and examples
  * Lexers and parsers in a variety of languages

The cons are:
  * No Perl5 backend
  * No Perl6 backend

The nice thing is that Abstract Syntax Trees are easily constructed. With a little syntactic sugar, on can specify which tokens are to be ignored and which tokens introduce subtrees. The generated AST can be processed with TreeParsers.

With ANTLR 2.7.5 Python code generation has been added. So I decided to do some baby talk in Python. The Python syntax is very regular and easy to learn, but I miss the human touch from Perl and Ruby. The whole indentation business makes me feel rather confined. I like hitting '%' in vim!

So ANTLR is thumbs up, and Python is thumbs down.

