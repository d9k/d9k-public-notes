# Smalltalk

## Why is Smalltalk not popular? : r/smalltalk

- https://www.reddit.com/r/smalltalk/comments/tih472/why_is_smalltalk_not_popular/

interactive coding experience. It's a real eye-opener.

I'm no expert but Smalltalk systems used to be very proprietary and expensive. So people choose free Java instead. I think it's that simple.

The idea of shipping the live image with all the code inside it offended management, when alternatives like Java meant distributing something compiled that was open for extension but not examination. -- And yet here we are, shipping containers to servers. Essentially an image on top of a complex framework -- Everything old is new again! :)

There is Squeak and Pharo, at squeak.org and pharo.org. There is also text-based GNU Smalltalk. My struggle with Pharo(and likely other Smalltalks) is finding the right objects and methods. Obviously, there is a lot of sample code, but I find reverse engineering the classes a big time sucker.

Smalltalk was already losing to C++ when Java arrived. Smalltalk was expensive to buy developer licenses for, slow in production, and the Smalltalk vendors put all their attention into competing against each other. Smalltalk failed for mostly social and economic reasons.

Smalltalk has never been popular with the academy. It came out of an industrial research program. Smalltalk in fact has had robust support for collaborating teams, continuous integration, distributed data stores, and deployment to multi-machine environments for scale and resilience long before anyone dreamed up “web” “applications” in the “cloud”.

## Smalltalk: the Software Industry's Greatest Failure / richardkulisz.blogspot.com

http://richardkulisz.blogspot.com/2011/02/smalltalk-software-industrys-greatest.html

The functional paradigm rejects all notion of modifiable state and orders everything around verbs so that all sentences are verb-object-object. The functional paradigm rejects state and objects so violently that it denies subjects exist. As a direct consequence it is blatantly unnatural to the human brain, contrary to physical reality, and contrary to human consciousness. Only math lovers find the functional paradigm attractive or useful which makes it useless to the rest of humanity.

Java for example doesn't even remotely qualify as object-oriented having been conceived as a deliberately inferior and broken pseudo-OO version of Smalltalk.

The failure of Smalltalk is two-fold. First, the fact that its rules are at least twice as large as they need to be. Because for every general rule of Smalltalk that someone has to assimilate in order to master the language, there is a specific rule (an exception to the general rule) that must ALSO be memorized.

Examples
- the existence of variables is bound early at compile time, not at runtime - if you try to compile a method with an undeclared variable, it triggers a compile time error, not a runtime error (and compile time warning) like it should.
-  there is no infinite object cloner out of the box. You're stuck with deepCopy which is arbitrarily limited.

The second way that Smalltalk is a failure is that it was woefully incomplete when it was standardized and it got extended by incompetent hacks rather than competent systems designers.

the event system is not debuggable.
the UIs are blatantly not OO - Squeak's Morphic is so messed up it doesn't qualify as an OOUI.

The lack of homoiconicity [homoiconic means code is data] in Smalltalk is perhaps its greatest failure since it has meant that many vital extensions to Smalltalk were rendered impossible.

### Comments

Richard Kulisz (https://www.blogger.com/profile/05450367878517586463): Your greatest misconception about software creation is that it is a field. It is not. It is a meta-field.

Creating software isn't like creating automobiles or books. As a programmer your purpose isn't to use, apply or instantiate technology. Your purpose is to create new technology.

You are asking for the field to settle, for well-designed interchangeable parts to appear, for designs to achieve local minima of difficulty and maxima of expressiveness.

The day it happens, programmers will be done with these parts of software and move on to something completely different.

Once you have the ultimate photo-gallery (http://richardkulisz.blogspot.com/2010/11/elements-of-excellent-photo-gallery.html), you don't need to program other ones. That would be stupid.