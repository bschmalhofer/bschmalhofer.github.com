---
layout: default
title: First steps with ANTLR and Python
---

<p>
I'm still trying to find the ultimate tool for implementing languages on Parrot. Never having to take a compiler construction class, and not really needing it at work, I'm not familiar with any of common parsing tools.
</p><p>
For now I'm getting down with ANTLR, trying to bring 'bc' to Parrot. 'bc' is actually a neat little language, I like it much better than 'm4'. The main purpose of 'bc' is of course the evaluation of arithmetic expressions. But there are also variables and subroutines. So 'bc' might be nice sandbox for playing with the PAST interface of Parrot.
</p><p>
ANTLR looks very good to me. Like with lex/yacc a syntax definition is transformed into code for lexers and parsers. The pros are
</p><ul>
<li>Mature, with lots of documentation and examples
</li><li>Lexers and parsers in a variety of languages
</li></ul><p>
The cons are:
</p><ul>
  <li>No Perl5 backend</li><li>No Perl6 backend</li></ul><p>
The nice thing is that Abstract Syntax Trees are easily constructed. With a little syntactic sugar, on can specify which tokens are to be ignored and which tokens introduce subtrees. The generated AST can be processed with TreeParsers.
</p><p>
With ANTLR 2.7.5 Python code generation has been added. So I decided to do some baby talk in Python. The Python syntax is very regular and easy to learn, but I miss the human touch from Perl and Ruby. The whole indentation business makes me feel rather confined. I like hitting '%' in vim!
</p><p>
So ANTLR is thumbs up, and Python is thumbs down.
</p>