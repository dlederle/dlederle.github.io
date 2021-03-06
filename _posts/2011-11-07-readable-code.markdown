--- 
title: Readable Code
category: engl457
layout: single
---

> We want to establish the idea that a computer language is not just a way of getting a computer to perform operations but rather that it is a novel formal medium for expressing ideas about methodology. Thus, programs must be written for people to read, and only incidentally for machines to execute. 
> Abelson and Sussman, Preface of [*Structure and Interpretation of Computer Programs*](http://mitpress.mit.edu/sicp/full-text/book/book.html)

This is the essence of what makes code studies a viable methodology. While many uses of the word 'code' imply obfuscation or the hiding of meaning, well written computer code should do the opposite.
It should clearly communicate its purpose and underlying workings to any reader with programmatic literacy.
Carried out logically this leads towards some variation on [literate programming](http://en.wikipedia.org/wiki/Literate_programming) as developed by Donald Knuth.
Of course, this is just one definition of 'good code'.
Other views of computer programming might hold that any program which works for its end users is good.
In software engineering, there are many practical concerns about readability of a computer program.
It allows easier collaboration with others, it is more maintainable, and it just looks better.
However, from a code studies perspective, clearly readable code draws attention to the unique property of computer code, that it exists on two communicative layers.
On one it speaks to a computer, by way of a compiler or interpreter, and on the other to a human.

One amusing example of this in my own life comes from a friend of mine in my computer science classes who consistently tries to name his variables something more interesting than 'i' for an iterator or 'n' for a number.
For example, he names his characters 'char mander', 'char meleon', and 'char zard'.
Only programs which require three character variables get to fully evolve.
These conventions don't alter the runtime characteristics of his program, but they do endear him to his classmates (and exaperates some of his professors).
When struggling through a late night debugging session, seeing 'bool [tentabool](http://bulbapedia.bulbagarden.net/wiki/Tentacruel)' is much funnier than it probably should be, and eases some stress.

In their paper, *A Box Darkly: Obfuscation, Weird Languages, and Code Aesthetics*, Michael Mateas and Nick Montfort explore the idea that code exists on both of these planes, and that clear communication is not always the goal.
They describe obfuscation contests, such as [the International Obfuscated C Code Contest](http://www0.us.ioccc.org/main.html) which aims among other things "To show the importance of programming style, in an ironic way."
The archives contain some truly incomprehensible abuses of the language, which are still compilable and runnable programs.
The very existence of a contest dedicated to (bad) programming style indicates that writing a computer program is not solely an engineering task.
I hope that through further code study I can learn more about the good, the bad, and the ugly hidden in the source code of programs which may seem innocous on the surface.
