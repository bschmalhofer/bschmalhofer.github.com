---
layout: default
title: Choosing a license for Plumhead
---

<p>
I have been thinking on how to proceed with Plumhead, that is PHP on Parrot. The problem is that I have neither the ability nor the inclining to write a PHP grammar from scratch. So a template is needed. This brings up the question of licensing.
</p><p>
Johnlim's blog <a href="http://phplens.com/phpeverywhere/?q=node/view/223" rel="nofollow">http://phplens.com/phpeverywhere/?q=node/view/223</a>
got me jumpstarted on which PHP implementations are out there. I have put my finding into the Parrot Wiki, <a href="http://rakudo.org/parrot/index.cgi?plumhead" rel="nofollow">http://rakudo.org/parrot/index.cgi?plumhead</a>.
The projects that look most interesting to me are phc, PHP4Mono and Roadsend. The PHP4Mono and the Roadsend grammars seem to be written from scratch.
Both projects are GPL licensed. The phc grammar is derived from the PHP 5.2 grammar.

</p><p>
PHP 5.2 is licensed under the PHP license, while parts are under the Zend license. Both licenses are BSD-like, which is quite acceptable to me.
</p><p>
So the plan of the day is to derive the Plumhead grammars from the PHP 5.2 grammar. I'm not sure whether that means that I need to put the whole of Plumhead under BSD license, or whether I can stick with Artistic+GPL.
</p>
