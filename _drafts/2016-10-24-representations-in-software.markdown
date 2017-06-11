---
title: Notes on Representations In and Of Software
layout: post
----

> It is a matter of representations in and representations out.
> Michael Mahoney (2005)

This post isn't exactly an argument so much as it is notes towards an argument, which I'm still trying to work through.
I'm going to present my rambling notes on two related topics which I've been reading about over the last year (or more).
First is the idea of a software representation.
Different authors use different terminology (which I'll cover in more depth below), but these are predominantly thought of as simulative models, or "putting the world into the computer" as historian Michael Mahoney puts it.
Second is the idea of how to represent software.
The most common way is through source code which describes the operation of the software, but other authors have all tackled this in their own way.
I think these are the two central questions that interest me in software studies, and hope that I can begin to articulate them better through my notes on other scholars work.


Representations beyond Software
===============================

Of course, the study of "representations" extends well beyond software.
For my purposes, I'm particularly interested as it applies to the philosophy of science and technology.
I certainly haven't read enough in this (wide) area, but here are notes on a few sources.

First up is Eugene Wigner on "The Unreasonable Effectiveness of Mathematics in the Natural Sciences" (1960).
I found this article remarkably readable, which was nice since I had very close to no background on the topic.
The main thing I got from it is best summed up in his conclusion: "The miracle of the appropriateness of the language of mathematics for the formulation of the laws of physics is a wonderful gift which we neither understand nor deserve."
Wigner explores the question of why "the language of mathematics" seems to correspond so closely to the functioning of the natural (physical) world.
I don't have anything like a solid physics background, but I wonder what other representational strategies have been tried?

Next is anthropologist Paul Rabinow's "Representations are Social Facts: Modernity and Post-Modernity in Anthropology" (1986).
I have no idea what reference led me to this, which was interesting but a bit far afield from my normal stomping grounds.
Rabinow begins with a section titled "Beyond Epistemology", in which he paraphrases Richard Rorty who notes that "epistemology as the study of mental representations" is a particular historically and culturally situated phenomenon. (p 235)
From this relatively simple observation, Rabinow (likely borrowing heavily from Rorty, though I haven't read the source material) plows through philosophy before concluding that "thought is nothing more and nothing less than a historically locatable set of practices" (p 239).
He continues in "Representations and Society" to present four conclusions drawn from Foucault (p 241).
-   i) Epistemology is an historical event in 17th C. Europe
-  ii) "We do not need a theory of indigenous epistemolgies", instead, we (anthropologists?) should show how people claim epistemologies as their own.
- iii) "Anthropologize the West" and make economic and epistemological conditions "historically peculiar"
- iv) "Pluralize and diversify approaches" or "Occidentalism is not a remedy for Orientalism"

The rest of the chapter is engaging deeply with ethnographic theory that I don't have a strong grasp of, but he concluded with a quote from Stanley Fish on interpretation that I liked: "Disagreements are not settled by the facts, but are the means by which the facts are settled" (255, qting Fish "What Makes an Interpretation Acceptable?")

Frankly, I didn't understand most of this chapter.
It was very clearly important for the discipline of anthropology at that time, but I don't have nearly enough context to follow it.
I think that a general audience version of the same ideas about epistemologies and the societies that produce/are produced by them would be really fascinating and important, but this was a bit too much for me when I read it.

Finally, moving in closer to software, is Phil Agre's *Computation and Human Experience* (1997).
Snippets of this book will fill up most of the next section on Representations in Software, but Agre also does a nice job of surveying other thinkers and applying their work to his own project of interactionist AI.
In Ch 2 "Metaphor in Practice", Agre highlights two philosophers who I should probably read more of eventually.
First, Paul Ricouer, who Agre reads as saying that scientific metaphors are not single words, but systems of metaphors (p 319, note 8).
TODO: Look up
Second is 
Heidegger: "Technical language as such encodes a cultural project of its own: the systematic rediscription of human and natural phenomena" in order to "facilitate rational control" (34)
TODO: Finish
Spurred on by this I also tried to read some of Heidegger's "The Question Concerning Technology", but there was no way I could make good sense of it without some guidance.
Wikipedia says that both of them and Hans-Georg Gadamer are "the major hermeneutic phenomenologists," and perhaps someday I'll be able to dive more deeply into their work.

Representations in Software
===========================
> "a bit of metaphor lashed to a bit of math" TODO exact quote 
> Phil Agre (1997, p 

Michael Mateas diss ch 7 "Expressive AI: Affordances and Semiotics
Affordances in expressive AI: (124)
  the negotiation of meaning conditioned by *interpretive* affordances
  the internal structure, conditional by architectural affordances
Authorial affordances: "The 'hooks' that an architecture provides for an artist to inscribe their authorial intention in the machine"

Agre Ch 4 "Abstraction and Implementation"
Structures of Computation:
abstraction: the functional definition of artifacts
implementation: their actual (physical?) construction

Agre Ch 5 "The Digital Abstraction"
an abstraction over continuous matter (90)
Labels are supplements: "They are supposed to be innessential to the technical artifact and yet they are necessary to insert the artifact into the order of human meanings" (95)

Dourish and Mazmanian 2011 "Media as Material: Information Representations as Material Foundations for Organizational Practice"
Interested in the "Materiality of Digital Representation"
With an excellent lit review on knowledge representation in general (9)

Kay and Goldberg: Metamedium
Kay and Goldberg: “Every message is, in one sense or another, a simulation of some idea. It may be representational or abstract.” (393)


Kay on Software

NWF/Mateas: Operational logics/playable models

Agre: Representations and representation schemes (318, note 15)

Mahoney: Operative Representations
Mahoney 2008 "What Makes the History of Software Hard"
"The history of software is the history of how various communities of practitioners have put their portion of the world into the computer"

Mahoney: "Software paradox" - software can automate everything but its own production
Mahoney 2004 "Finding a History for Software Engineering"
Software is different. Modeling "real-world" systems is not automateable, and likely never will be (9-10).

Mahoney: "The Histories of Computing" 2005
"It is about modelling the world in the computer, about computational modelling, about translating a portion of the world into terms a comptuer can 'understand'....Any meaning the symbols may have is acquired and expressed at the interface between a computation and the world in which it is embedded. The symbols and their combinations express representations fo the world, which have meaning to us, not to the computer. It is a matter of representations in and representations out. What characterises the representations is that they are operative." (129)
This is perhaps the clearest explanation of what I'm getting at here.

Woolgar "Rethinking Requirements Analysis" (in ch 8 of Requirements Engineering: Social and Technical Issues" 1994)
System as Text: View the user as an active "reader" who interprests the capabilities of the system.
The system is then organized to encourage a particular reading (which fulfills the developers' business requirements)

Wardrip-Fruin: "Digital Media Archaelogy: Interpreting Computational Processes" 2011
"The digital media field must begin to grapple with the ideas embedded in its systems"
This is how they represent

Stuff I haven't read as much of:
--------------------------------

Format studies (MP3 book) or data modeling in general

Knowledge Representation in AI

"Digital Places" by Michael Curry 1998
I read the book review by Daniel Sui (2001) and it sounds quite relevant: "Representation of space in GIS is.. narrowly conceived" and "problematic for representing social reality"
Part two is concerned with the "relationship between the systems and the institutions within which they operate"


Representations of Software
===========================

Frabetti: on code/technical documentation
"I am well aware that any relationship we can etnertain with software is always mediated, and that software might well be 'unobservable'" (xix)

Nofre, Priesetley and Alberts 2014: "When Technology Became Language: The Origins of the Linguistic Conception of Computer Programming"
- "programming language" is an unexamined metaphor
Motivated by achieving "machine independent" compatibility, translation becomes a central metaphor.
They claim that this linguistic shift enabled a machine independent "computer science" (66)

Gingold: Reverse diagrams

de Souza, Froehlich, and Dourish 2005: "Seeking the Source: Software source code as a social and technical artifact"
via Latour the concept of inscription: "The patterns of work become 'inscribed' into the artifacts and representations"...of science

Holmes 2016 "'Can We Name the Tools?' Ontologies of Code, Speculative Techne, and Rhetorical Concealment"

Descriptions of software:

As I conducted the reading for this week I was struck by how challenging it is to describe software.
Describing complex systems in a linear text is challenging no matter what, describing a complex interactive system is nearly impossible, and describing such a thing to an audience that had never experienced anything like it must have been a nightmare.
Many of these authors had to describe novel systems without showing the system itself.

I first noticed this after experiencing a weird familiarity while reading Douglas Engelbart and William English's piece.
It felt like reading the rulebook for a game which is very similar to a game you already know how to play, but not identical.
Many of the features he describes are so close to systems which we use every day.
It’s easy to gloss over things, but the details matter immensely!
The differences in how hypertext was implemented, the differences in input system and the different network environment all surely influenced the overall user experience.
Additionally, it was tough to determine which part of it the authors thought was most important and which a more incidental feature.
Is the core tagging mechanism critical, or is it the chorded input?

In the Software chapter, I felt the mismatch between my priorities and the authors most acutely.
While describing Ted Nelson’s Labyrinth system, the piece leads off by describing the basic interactions such as "the user types F (forward)" (250) instead of the operational logics, the mechanisms or the ways this structures knowledge.
It’s like saying "to begin with, users of *Moby Dick* must open the front cover".
It might be true, but it isn't really the point!
It's nothing like *As we May Think* or even Nelson’s other writing, in their expansive goals of liberating human knowledge and expression.

TODO: Conclusion

Afterward
=========


This messy lit review is just a start.
There are, of course, an enormous amount of questions generated by this reading and directions to inquire after.
One area I didn't cover was software (or the figure of code) as metaphor or representation in some other field.
Wendy Chun's "Programmed Visions" is the definitive work on this.
In general, this doesn't interest me nearly as much as thinking about specific software artifacts.

