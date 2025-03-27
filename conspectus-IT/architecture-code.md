# Architecture: code

## Write code that is easy to delete / programming is terrible

- https://programmingisterrible.com/post/139222674273/write-code-that-is-easy-to-delete-not-easy-to

if we wish to count lines of code, we should not regard them as “lines produced” but as “lines spent”.

If we see ‘lines of code’ as ‘lines spent’, then when we delete lines of code, we are lowering the cost of maintenance. Instead of building re-usable software, we should try to build disposable software.

Once you make something a shared API, you make it harder to change.

### Step 1: Don’t write code

### Step 1: Copy-paste code

### Step 2: Don’t copy paste code

(utils)

### Step 3: Write more boilerplate

Boiler plate is a lot like copy-pasting, but you change some of the code in a different place each time, rather than the same bit over and over.

Libraries that require boilerplate are often stuff like network protocols, wire formats, or parsing kits...

We’re trying keep the parts that change frequently, away from the parts that are relatively static.

it’s hard to interweave policy (what a program should do), and protocol (what a program can do) together without limiting the options. \[policy is like providing settings to protocols. Protocols are like templates\]

### Step 4: Don’t write boilerplate

It’s time to wrap your flexible library with one that has opinions on policy, workflow, and state. Building simple-to-use APIs is about turning your boilerplate into a library.

One of the most popular and beloved python http clients, requests, is a successful example of providing a simpler interface, powered by a more verbose-to-use library urllib3 underneath. urllib3 does the pipelining, connection management, and does not hide anything from the user. requests is about popular http adventures, urllib3 is about giving you the tools to choose your own adventure.

I’m not advocating you go out and create a /protocol/ and a /policy/ directory, but you do want to try and keep your util directory free of business logic, and build simpler-to-use libraries on top of simpler-to-implement ones.

This split of concerns allows us to make some users happy without making things impossible for other users.

### Step 5: Write a big lump of code

Business logic is code characterised by a never ending series of edge cases and quick and dirty hacks.

Other styles like ‘game code’, or ‘founder code’ are the same thing: cutting corners to save a considerable amount of time.

Sometimes it’s best just to give up and write a substantial amount of trashy code to hold the rest together.

The reason? Sometimes it’s easier to delete one big mistake than try to delete 18 smaller interleaved mistakes.

If you’re writing your first game: don’t write an engine. Similarly, don’t write a web framework before writing an application. Go and write a mess the first time.

Monorepos are a similar tradeoff: You won’t know how to split up your code in advance, and frankly one large mistake is easier to deploy than 20 tightly coupled ones.

When you know what code is going to be abandoned soon, deleted, or easily replaced, you can cut a lot more corners. Especially if you make one-off client sites, event web pages.

I’m not suggesting you write the same ball of mud ten times over, perfecting your mistakes. To quote Perlis: “Everything should be built top-down, except the first time”. You should be trying to make new mistakes each time, take new risks, and slowly build up through iteration.

It’s quicker to write ten big balls of mud and see where it gets you than try to polish a single turd.

It’s easier to delete all of the code than to delete it piecewise.

### Step 6: Break your code into pieces

Big balls of mud are the easiest to build but the most expensive to maintain.

Instead of breaking code into parts with common functionality, we break code apart by what it does not share with the rest. We isolate the most frustrating parts to write, maintain, or delete away from each other.

We are not building modules around being able to re-use them, but being able to change them.

Also it's often easier to have one awful component with a simple interface, than two components requiring a careful co-ordination between them.

Loose coupling is about being able to change your mind without changing too much code.

HTTP’s error codes are example of loose coupling: common problems across web servers have unique codes. When you get a 400 error, doing it again will get the same result. A 500 may change. As a result, HTTP clients can handle many errors on the programmers behalf.

Erlang/OTP is relatively unique in how it chooses to handle failure: supervision trees. Roughly, each process in an Erlang system is started by and watched by a supervisor. When a process encounters a problem, it exits. When a process exits, it is restarted by the supervisor. The key idea is that it is quicker to fail-fast and restart than it is to handle errors. Error handling like this may seem counter-intuitive, gaining reliability by giving up when errors happen, but turning things off-and-on again has a knack for suppressing transient faults.

Error handling is one of the many ways in which a system can be tightly bound together.

In IMAP almost every each operation is a snowflake, with unique options and handling. Error handling is painful: errors can come halfway through the result of another operation.

By comparison, both file systems and databases make much better examples of remote storage. With a file system, you have a fixed set of operations, but a multitude of objects you can operate on.

Other examples of loose coupling are other systems with middleware, or filters and pipelines.

First we layered our code, but now some of those layers share an interface: a common set of behaviours and operations with a variety of implementations.

The modular bit makes it way more fun to write code, in the same way that Lego bricks are fun because they all fit together. A healthy code base has ... just enough distance between the moving parts so you won’t trap your hands inside.

Code that is loosely coupled is much easier to replace, and much easier to change too.

### Step 7: Keep writing code

Being able to write new code without dealing with old code makes it far easier to experiment with new ideas. It isn’t so much that you should write microservices and not monoliths, but your system should be capable of supporting one or two experiments atop while you work out what you’re doing.

Feature flags are one way to change your mind later. Although feature flags are seen as ways to experiment with features, they allow you to deploy changes without re-deploying your software.

Google Chrome is a spectacular example of the benefits they bring. They found that the hardest part of keeping a regular release cycle, was the time it took to merge long lived feature branches in.

A feature flag isn’t just a command line switch, it’s a way of decoupling feature releases from merging branches, and decoupling feature releases from deploying code.

### Conclusion

It is not so much you are building modules to re-use, but isolating components for change. Handling change is not just developing new features but getting rid of old ones.

Good code isn’t about getting it right the first time. Good code is just legacy code that doesn’t get in the way.

## Small Functions considered Harmful | by Cindy Sridharan | Medium

- https://copyconstruct.medium.com/small-functions-considered-harmful-91035d316c29

Raymond Hettinger, a core Python developer, has a fantastic talk called Beyond PEP8: Best practices for beautiful, intelligible code. This talk is a must-watch, not just for Python programmers but for anyone interested in programming or who programs for a living, because it very incisively lays bare the fallacies of a dogmatic adherence to PEP8, which is the Python style guide many linters implement.

The main problem with DRY is that it coerces one into abstractions — nested and premature ones at that.

The fabulous Rubyist Sandi Metz has a famous talk called [All The Little Things](https://www.youtube.com/watch?v=8bZh5LMaSmE&feature=youtu.be).

Abstract ONLY when you know all details. Since you can't be humble and flexible. Our carefully handcrafted artisanal “perfect” abstraction is only one business requirement or bug report away from being consigned to the status of “wrong”.

Context switches are expensive, whether they are CPU context switches or a programmer having to mentally switch context while reading code.

\[too many levels of abstraction are hard to grasp\]

Smaller the functions, longer the names.

Some say that small functions force stack calls list be more readable.

When thinking about how to abstract, it greatly helps to be cognizant of the fact that the code we’re building might probably only be a few hours away from dying (being modified).

the code we’re building might probably only be a few hours away from dying (being modified). Thus optimizing for ease of modification of code tends to work better than trying to build topdown narratives of the sort proposed in Clean Code.

The more the number of classes/interfaces/packages, the harder it is to “take it all in” in one fell swoop, which does zilch to justify the maintenance cost of these various classes/interfaces/packages we’ve built.

Explosion of small functions, especially one line functions, makes the codebase inordinately harder to read.

"A Philosophy of Software Design" by John Ousterhout

What I’m really hoping for during the times I venture into uncharted territory is to make the least number of mental hops and context switches while trying to find the answer to a given question. 

The best modules are those that provide powerful functionality yet have simple interfaces. I use the term deep to describe such modules. A shallow module is one whose interface is relatively complex in comparison to the functionality that it provides. Splitting to smallest possible classes often doesn't help with writing deep modules.

Mocks are an artificial simulation of some result. Mocks are also very likely to get out of sync from the real service they stand-in for. The way network I/O is tested is by, well, not actually testing it. I find limiting the surface area of mocks to the least amount of code to work best. Should be a function with no more than 1–2 lines

Mocks also work best when there is just a single instance of every particular mock and every test uses the same mock.

Property based testing: each time many passes with randomly generated tests: (Haskell) QuickCheck, (Scala) ScalaCheck, (Python) Hypothesis.

## One Big Fluke › What is "founder code"? / Brett Slatkin

- https://www.onebigfluke.com/2015/04/what-is-founder-code.html?m=1

This is code that's in your codebase that was written by a cofounder of the project. The purpose of founder code is to demonstrate the intended outcome of design choices. It goes beyond a requirements or design document because it's exactly specific about how the software is supposed to work.

Founder code is great for illustrating an important architectural choice (e.g., how to make a system scalable).

Founder code is especially helpful in UX design. Complex animations, transitions, and interactions can be hard to describe. Data visualizations take a long time to play with before you discover the right combination that's compelling.

Founder code is fundamentally just another name for prototyping. When a team has grown to the point where other (better) programmers have time to rewrite the original founder code, that's success.

Thus, the ultimate goal of founder code is to become obsolete.

About: author of the book [Effective Python](https://effectivepython.com/). A software engineer at Google. @haxor on Twitter.

## The harsh reality of good software / ThePrimeTimeagen

- https://www.youtube.com/watch?v=NiljDyzAOcI

Author: if I have to sum up my coding skills after 15 years of software development I would probably go with something like "average". A lot of devs feel the same regardless of years of experience.

Primeagen: usually you need to learn many things at the beginning of project. But once you do it, the interest goes down.

Primeagen: People don't care how hard you worked. If you didn't sleep several days and deploy feature that breaks everything you'll be upset.

Nobody besides your team really cares about DDD or how much layers of abstractions and design patterns you preemptively added to the project.

As long as a software works nobody outside dev team will prioritise fixing it.

Primeagen: software must be properly tested. There is no such thing as clean readable code. There are degrees of shitty code.

Code must be clean, concise, planned, maintainable, secure, performant. Fight abstractions, understand the domain, follow standards, know your tech, refactor with caution.

Fight abstractions - assume unexpected changes when you write code.

All problems in computer science can be solved with another level of indirection except the problem of too many levels of indirection. / David Wheeler \[Isn't AI debugging is such a problem?\]

The problem of too many abstractions can be easily solved with... talking to other people.

Primeagen: first build atomic pieces of whatever you need. Next make a couple of things with these atomic pieces. Then abstract over these tiniest amount.

Sonarqube static analyser, supports TypeScript

18:45 Primeagen: small functions codebase requires so much hopping around to figure out what the function does. You don't want code that is hard to follow. Eyeshot development - context must be within eyeshot. It must be obvious what function does.

20:20 The best tool for the job is the tool you know best. 43% of all sites are still built on WordPress.

24:30 Programming is.. you failing on a sword of somebody else's shortcut.

27:05 Just enjoy what you're doing. If you find a way to not look at a problem as inconvenient but as an opportunity to learn and get better your life will significantly be better.