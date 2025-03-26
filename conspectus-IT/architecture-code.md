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



## One Big Fluke › What is "founder code"? / Brett Slatkin

- https://www.onebigfluke.com/2015/04/what-is-founder-code.html?m=1

This is code that's in your codebase that was written by a cofounder of the project. The purpose of founder code is to demonstrate the intended outcome of design choices. It goes beyond a requirements or design document because it's exactly specific about how the software is supposed to work.

Founder code is great for illustrating an important architectural choice (e.g., how to make a system scalable).

Founder code is especially helpful in UX design. Complex animations, transitions, and interactions can be hard to describe. Data visualizations take a long time to play with before you discover the right combination that's compelling.

Founder code is fundamentally just another name for prototyping. When a team has grown to the point where other (better) programmers have time to rewrite the original founder code, that's success.

Thus, the ultimate goal of founder code is to become obsolete.

About: author of the book [Effective Python](https://effectivepython.com/). A software engineer at Google. @haxor on Twitter.