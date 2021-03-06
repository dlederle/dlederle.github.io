--- 
title: Poking Around in Passage
layout: single
---

Written as a blog checkpoint for [engl376, Electronic Literature](http://elit.umwblogs.org/) with Dr. Whalen.

One of the first games we played in this class was *Passage*, by Jason Rohrer.
In this post I'm going to take a look at the source code of the game as a paratext which can aid our interpretation of the work.
This approach is heavily influenced by Critical Code Studies, from [Mark Marino](http://www.electronicbookreview.com/thread/electropoetics/codology), and a continuation of [work I did last semester](http://dlederle.com/2012/01/30/introduction-reading-code/) on a different Rohrer game, *Gravitation*.

The code for this game can be found on [Rohrer's website.](http://hcsoftware.sourceforge.net/passage/)
Download the Unix Source, and start poking around with any text editor.

In the "gamma256/gameSource/" directory we find the meat of this particular game.
Most of the files are supporting libraries for "game.cpp," the main file for *Passage*.
Diving into a new code base can be intimidating, and I do not have a perfect way to understand what's going on.
In this case, I began scrolling down, reading comments and variable names, looking for anything out of the ordinary.

The first interesting piece I found was this:

Lines 524-526:

``` c
    // track whether we ever met the spouse
    // separate from World's haveMetSpouse()
    char knowSpouse = false;
```

The "spouse" is monumentally important in Passage, being the only character other than your own avatar.
This seemed like a good starting point, so I searched for everywhere in the file with the word "spouse."
This particular code segment is two lines of comments, denoted by the slashes, and one variable declaration.
The comments are somewhat like notes in the margins to remind Rohrer, or any other reader of this code, what the next line does.
What it does, is keep track of whether you have met your spouse yet.

It is interesting to note that Rohrer calls this character your spouse, rather than partner, wife, girlfriend, or any other adjective we could think of.
You are married to this person, immediately.
In fact, we can pinpoint where in the code that happens.

Lines 1203-1214:

``` c
        if( ! haveMetSpouse() && 
            ! isSpouseDead() && 
            distanceFromSpouse < 10 ) {
            
            meetSpouse();
            
            knowSpouse = true;
            
            startHeartAnimation( 
                (int)( ( spouseX - playerX ) / 2 + playerX ),
                (int)( ( spouseY - playerY ) / 2 + playerY ) - 2 );
            }
```    

This code segment looks much more intimidating, but is very straight forward.
The first three lines are the logical if statement.
The "!" can be read as "not".
So all told it can be translated as approximately "If you have not met your spouse AND your spouse is not dead AND you are less than 10 units away from your spouse" then the piece of code inside the curly braces is executed.
If any of those conditions are false, then the computer skips the inside part.

The inside part of course, is where you meet your wife after the "meetSpouse()" function is called.
We could go track down the particular logic of that function, but from the name it is clear what it does.
Somewhere in "meetSpouse()" and "knowSpouse" becoming true, you are married.
How romantic.

Being married does have consequences.
Here is one interesting bit.

Lines 1229-1234:

``` c
        int spouseExploreFactor = 2;

        if( haveMetSpouse() ) {
            // exploring worth more
            exploreDelta *= spouseExploreFactor;
            }
```

After you get married, you get double points for wandering around.
This is clearly a part of the message of the game.
Rewarding you with points for exploring at all is a message, although it is up for debate how significant these points even are.

"Go West Young Man" and seek your fortune.
In Passage, the act of seeking is its own reward.
Seeking with a partner, is doubly rewarding.

There are of course emotional consequences for becoming married.

Lines 1167-1172:

``` c
        if( age >= 0.85 ) {
            dieSpouse();
            }
        if( age >= 0.95 ) {
            diePlayer();
            }
```

This is the most famous, emotionally manipulative part of Passage.
Those six lines are basically the reason we study this game at all.
They are completely black and white.
At a certain age, you and all of your loved ones will die, and theres nothing you can do about it.
In Passage, no matter what you do, you will outlive your spouse.        

There are some interesting consequences of this.
Here are two seperate, but related pieces of code.

Lines 578-579:

``` c
    // use to slow player motion after spouse has died
    char movingThisFrame = true;
```

Lines 951-956:

``` c
        if( knowSpouse && isSpouseDead() ) {
            
            // player moves slower
            // toggle motion on this frame
            movingThisFrame = ( frameCount % 2 == 0 );
            }
```

To me, this is exciting.
It excites me because I have played Passage several times in the last several years, and never noticed that you slow down after your spouse dies.
Perhaps I'm just not very observant, or perhaps I still get emotionally involved by her death, but by reading the code I learned something new about the game in question.
