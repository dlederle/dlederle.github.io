---
layout: single
title: "Networking in idTech3"
date: 2013-11-07 10:33
comments: false
categories: digra2013
---

(Part 2 of the paper I presented at Digra in August)

#### History of idTech3

The early history of id Software is documented in the nonacademic history book Masters of Doom (David Kushner, 2003). In addition, John Carmack was very open during this time with many of the technical details of day to day development. He posted regularly to a “.plan” file, which other programmers could follow to receive his updates. Using these two resources, combined with interviews and the code itself we can learn a great deal about the development history of the idTech3 engine.
Kushner frames his story in terms of “the two Johns”, Carmack and Romero. In his book, Carmack was the hyper focused technical wizard, while Romero was the free-wheeling design genius. Together they invented the First Person Shooter, but were left behind as other companies took the genre to new heights creatively and commercially. The development of idTech3 was intrinsically tied into the development of Quake III Arena (id Software, 1999). This took place after Romero had left id to start his own company, Ion Storm. The game abandoned any pretense of narrative, and was heavily focused on competitive multiplayer. The engine’s architecture was oriented towards this goal, particularly the networking.

#### Protocol in idTech3

In a popular technical code review of the idTech3 engine, coder Fabien Sanglard declared that “the network model of Quake3 is with no doubt the most elegant part of the engine.” (2012). This pursuit of engineering elegance and excellence, of doing “The Right Thing”, is documented in Masters of Doom as one of Carmack’s driving goals.

Network communication happens over multiple layers of mutually agreed upon protocols, which exist simultaneously. In his book Protocol: How Control Exists after Decentralization (2004) Alexander Galloway thoroughly develops the concept of “protocol” as key to understanding control in a networked society. With his concept of protocological control in mind, the centralized model of idTech3, which I am about to describe, takes on new connotations. Galloway politicized protocol.
Quake III Arena has a client-server model, which allows all of the game state to be handled by a central game server, while thinner clients primarily handle graphics presentation and relay player input to the server. This provides anti-cheat regulation to server owners, allows them to determine which mods can be run, and generally subordinates the players’ clients.

The Quake application level protocol is called NetChannel, and it is tailored for deathmatch. The server sends unreliable packets (Hook, 2006), meaning that it continues to send the data without waiting to confirm that the client has received it. The contents of each packet are the compressed state values that the client will need to render its screen, and a sequence value to keep the packets in order. The server sends the differences between the current state and the last state which the client acknowledged receipt of. In the event of data loss, both the server and the client can make predictions as to what the next frame of the game will be based on the current state.
This prediction allows the client to continue rendering the frame, but can result in jerkiness when the network connection is re-established and the client updates itself to match up with the server. The differences between the clients earlier prediction and the server’s “canonical” state is the the classic visual lagging that anyone who has played networked shooters has experienced.
The client-server model of idTech3 was designed specifically for the fast paced deathmatch genre, which id pioneered and Quake III Arena perfected. This architecture works very well for this type of game, but proves challenging for creating single player experiences. I expand on the implications this had for modders and licensees in the section “Protocological Impact”.

#### Networking Implementation

Galloway observes that the regulation provided by protocol must “always operate at the level of coding”. In the case of idTech3, the code governing this protocol has been opensourced, and is available for study. Using analytical tools from Mark Marino’s Critical Code Studies (Marino, 2006) we can unpack the implementation of the protocol.

The project is large, with approximately 1,110 unique files, 241,000 lines of C, 1,100 lines of assembly and small amounts of a few other languages. Diving into a large software project can be overwhelming, particularly if you are unfamiliar with the domain. I had no prior experience with game engines, and am indebted to Fabien Sanglard’s “Quake 3 Source Code Review” series (Sanglard, 2012). It outlines the code’s high level architecture, with some details of each section.

In general the code did not yield to code studies well. It turns out that infrastructural code is fairly dry. Game code seems much more fruitful. This code is terse, but confusing parts are commented, and everything seems to follow a similar style. In short, it is fairly boring. However, I’ll share one brief selection.

```c
// using the stringizing operator to save typing...
#define NETF(x) #x,(int)&((entityState_t*)0)->x

netField_t  entityStateFields[] =
{
{ NETF(pos.trTime), 32 },
{ NETF(pos.trBase[0]), 0 },
{ NETF(pos.trBase[1]), 0 },
{ NETF(pos.trDelta[0]), 0 },
{ NETF(pos.trDelta[1]), 0 },
{ NETF(pos.trBase[2]), 0 },
{ NETF(apos.trBase[1]), 0 },
{ NETF(pos.trDelta[2]), 0 },
{ NETF(apos.trBase[0]), 0 },
{ NETF(event), 10 },
{ NETF(angles2[1]), 0 },
{ NETF(eType), 8 },
{ NETF(torsoAnim), 8 },
{ NETF(eventParm), 8 },
{ NETF(legsAnim), 8 },
{ NETF(groundEntityNum), GENTITYNUM_BITS },
```

In code/qcommon/msg.c: Here we can see the player_state variables that are passed between the server and the client. This is potentially useful information for a developer, but from a code studies point of view, what interests me is the comment and small helper function at line 1098. Its an example of code written for humans rather than machines. It is perhaps less performant, but much more readable. The famous introductory computer science textbook, Structure and Interpretation of Computer Programs states in its introduction that “programs must be written for people to read, and only incidentally for machines to execute.” (Abelson, et al). This is the essence of code studies. This code is terse, infrastructural library code, which is typically abstracted even from other developers. Still, even here we find traces of the human authors’.

#### Materiality of the Network

Networking code provides an interesting lense to view the fickle nature of physical hardware, as well as the challenges of protocological implementation details which may not fully abstract away the network’s materiality. Transporting bits around the world forces programmers to recognize the physical limits of computing, and the gaps between protocol and reality.

An incident from the post-release support of Quake II (id Software, 1997) is illustrative of this phenomenon. In a .plan entry that Carmack posted at 4:40 AM, December 31, 1997, he explains a complex and obscure bug caused by a players’ router mishandling the less common UDP datastream. The router was making assumptions that the data would be TCP, or acknowledged UDP.

Carmack solved the problem with a few extra bits per packet, but it irked him.

> I think that this is a rather evil thing for a router to do.
> You wouldn't be able to tell a difference, but its the principle of it...

This incident is fascinating for several reasons. The first is the unhealthy and fanatical work ethic he had at this time. Carmack was working extremely late on New Years, solving a bug that only affected a few users.
The other issue it illustrates is the difference between the abstract, interoperable protocol and the messy reality of physical routers. Carmack’s application protocol should function on all routers if they properly implement the UDP standard. However, certain routers’ optimizations or engineering tradeoffs caused his unusual approach to break. This disconnect between the clean, logical, abstract protocol and the stubborn materiality of computing is important to understanding computing in general.

#### Protocological Impact

> The explicit split of networking into a client presentation side and the server logical side was really the right thing to do. We backed away from that in Doom 3 and through most of Rage, but we are migrating back towards it. All of the Tech3 licensees were forced to do somewhat more work to achieve single player effects with the split architecture, but it turns out that the enforced discipline really did have a worthwhile payoff.

> John Carmack interview with Fabien Sanglard, 2012

This client/server split allowed clean code, and was an appealingly simple architecture. However, it caused problems for licensees and modders. Carmack prioritized his needs and desire to do the engineering “Right Thing” over the needs of other developers.

In a .plan entry from November 3, 1998 Carmack explains some difficulties of his client/server split:

> There are two crucial problems with shipping the game this way: security and portability.

The security challenge is that game mods would now execute code on the client, rather than just the server. This meant that everyone, not just server owners would need to assess the safety of a mod. Similarly, with client side mod code, “less popular systems would find that they could not connect to new servers because the mod code hadn’t been ported.” His solution was the interpreted C virtual machine. This is an important technical decision, and a significant amount of engineering effort, all to support game mods.

When I started this investigation I was following up on an idea I had seen repeated many times in fan forums for id games. id’s games are just tech demos for their engines, and the games themselves are secondary. This is used as an excuse for their lack of design innovation. However, after a deep dive into this engine I found that to be simply not true. All of the engineering decisions made in the networking module are to support the optimal Quake III Arena experience. It is not a flexible architecture, and makes single player experiences harder to craft.

> It's interesting when you look back at our technology licensing -- it was never really a business that I wanted to be in.

> John Carmack interview with Gamastura, 2011

This quote strikes at the core of id’s fall from prominence, and the changing direction of the genre in later years. They stopped focussing on licensing their technology, and allowed other players like Valve and Epic to take over the market.
