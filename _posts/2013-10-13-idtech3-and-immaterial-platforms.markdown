---
layout: single
title: "idTech3 and Immaterial Platforms"
date: 2013-10-13 16:41
comments: false 
categories: digra2013
---

(Part 1 of the paper I presented at Digra in August)

Watch the beginning of these two clips:

<iframe width="420" height="315" src="//www.youtube.com/embed/k_Mc4ClRIXY" frameborder="0" allowfullscreen></iframe>

<iframe width="420" height="315" src="//www.youtube.com/embed/_S_T2GJS-iY" frameborder="0" allowfullscreen></iframe>

While these games have quite different aesthetics, they both share a significant amount of code.
They are both built on id Software’s idTech3 engine.
id’s earlier engines were widely licensed and formed the basis for other companies’ games, as well as other engines, most notably Valve’s GoldSrc (the engine that powered Half Life 1).
idTech3 had more competitors.
Other engines, like Unreal and Source, ultimately had more games built on them, but idTech3 was behind several influential or critically acclaimed games, which shaped the next decade of First Person Shooters.

John Carmack, the CTO of id Software and the primary developer on all of their games, is an important figure in the history of the shooter.
His technical preferences and engineering decisions have shaped the entire genre.
While the slower, more realistic style of Valve and others won over id’s fast twitch, arcade shooter, a complete picture of the genre must take id’s games, and their engines, into account.
idTech3 is particularly interesting for me, as it is a turning point where id Software began to retreat from mainstream popularity.
As other companies began developing competing visions of what a shooter could be, id’s Quake III Arena continued pursuing extremely fast paced, cartoon-like gameplay, without a single player story mode.

idTech3 is also an interesting example of what I will call “immaterial platforms”, software platforms that shape and constrain further development in the same way that game consoles do.
The game engine is the key immaterial platform for computer games.
Today, I’ll closely examine idTech3’s networking component on several levels.
While there are many interesting parts of the engine, this tight focus allows me to trace its impact on several key communities, and is a lense to view the broader place of id Software in the genre.

### Immaterial Platforms

From the very beginning, Bogost and Montfort include software platforms in the scope of inquiry.
This is their definition from 2007:

> A platform is a computing system of any sort upon which further computing development can be done. It can be implemented entirely in hardware, entirely in software (which runs on any of several hardward playforms), or in some combination of the two.

However, the first books to come out of the MIT book series have all focused on physical, commercial game systems.
While platform studies is not constrained exclusively to this book series, it is the most significant outlet for platform studies work.
Dale Leorke has criticized the series for becoming formulaic, and prompted platform studies scholars to expand their methodology and scope (2012).

Following Friedrich Kittler’s observations on software obscuring or abstracting away hardware concerns, immaterial software platforms are those which hide the operations of a physical, material platform which does the real computational work.
Many games are not tied to a single hardware platform, but are instead targeted to a general software platform, which can then be executed on a variety of physical platforms, with as little modification as possible.
The daily engagement of game developers with these software platforms brings them closer to the surface of player experience, and their generality makes them a worthwhile platform to study.

Immaterial platforms occupy an inbetween space in [this five layer stack](http://platformstudies.com/levels.html).
They are a platform for further development, but are made up of code.
It is important to make the distinction between game code, which encodes the form of the game, and the infrastructural platform code that underlies it.
This is a messy, liminal space that is not clearly defined.
If we place immaterial platforms as a halfway point between “code” and “platform” they become a useful lense with which to investigate the intersection of those layers.

#### Game Engine as Platform

The most important immaterial platform for any game is its engine.
They emerged as a way to reuse code between games which shared many of the same core requirements.
2D or 3D graphics, networking, sound, and realistic physics simulations are typically easier to reuse than reimplement, as is interacting with hardware.

A game engine can help mitigate the challenges of developing for multiple physical computing platforms.
Using an engine allows the developer to program to that engine, treating it as the primary platform, rather than the computing system which runs both the engine and game.
To the developers, the engine can be a more important substrate than the computer hardware.

Andrew Hutchinson has called working inside of these technological limits the “pragmatic expression” of games.
In a paper contrasting the aesthetics of two 1993 games, Doom and Myst, Hutchinson notes that both games had similar goals, but, due to the technological limits of their time, both were forced to make compromises.
The engines of these games were specifically tuned for two radically different aesthetics.
It is impossible to make a game as visually immersive as Myst on the Doom engine, just as it is impossible to make a fast paced game on the Myst engine.
The engine is not just important for developer experience, it determines what they can possibly create for the player.
