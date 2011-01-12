---
layout: default
title: Parrot and libsyck
---


During the last weeks I have been trying to bring <a href="http://whytheluckystiff.net/syck/" rel="nofollow">libsyck</a> to <a href="http://parrotcode.org/" rel="nofollow">Parrot</a>. libsyck is a C-library for parsing <a href="http.//yaml.kwiki.org" rel="nofollow">YAML</a>. It has been designed to work closely together with scripting languages.

At first sight it looks fairly easy. The scripting language tells libsyck about the YAML string. Libsyck parses the YAML string into a parse tree and tells the scripting language whenever it encounters a node. The scripting language receives a node, store the information in a convenient location and tells libsyck where it has put the node. Usually the convenient location is the languages symbol table, and the location returned to libsyck is a symbol id.

The communication from libsyck to the scripting language is done via callback functions, aka handlers. So in order to marry Parrot and libsyck, one needs the Parrot Native Call Interface with callback functions.

Parrot NCI itself is pretty stable. It is easy to load a shared library and call functions in that library. The ops 'loadlib' and 'dlfunc' are your friends there. Arbitrary structs can be read and written to, by putting them into a UnMangagedStruct Parrot Magic Cookie.

For callback functions at least two different things are needed:
  * A function pointer that the external library can call
  * A Parrot subroutine that does the wanted work
In Parrot there is a single callback function for  each supported callback function signature. This is so, because it is hard to create new C-functions without resorting to a C-compiler.
So how does the Parrot interpreter know which subroutine  should be invoked? For that purpose, any PMC, e.g. 'user_data', can be used. The opcode 'new_callback' sticks the sub as a property onto 'user_data'. The external library is given a pointer to 'user_data'. When the external library is calling the callback function, it needs to pass 'user_data' back to the Parrot interpreter. In short, the actual callback function is dumb, all the interesting things are in 'user_data'.

So far the external library can tell the Parrot interpreter to invoke a sub. The remaining questions are at what time the sub is invoked and how the sub passes information back to the external library. Parrot callback function have no return values. This should propably keep the number of function signatures small. However, the callback sub can receive an external data pointer from the external library and write data into the libraries memory.

The question of the timing is more crucial. Right now Parrot places all callback requests from external libraries into an event queue. This is so, because callbacks can in priciple be fired at any time. At least in a single threaded environment, this means that the actual work is done *after* the external library is finished with the callback call. The execution is asynchronous. This is OK for callbacks that should Parrot notify about something, for example key press events in a GUI.
'libsyck' however depends on synchronous execution. The memory that contains data about a YAML node seems to be reused. When  libsyck is parsing, it gives Parrot a pointer to useful data. When Parrot is finally looking at the data, it has long been overwritten.

Presently, I see the lack of synchronous execution of callbacks as the biggest obstacle in bringing libsyck to Parrot. Unfortunately I have no idea how Perl5 and Ruby are handling this. The next thing I want to try, is to put a property 'snchronous_is_ok' on 'user_data' and call the sub synchronously.

