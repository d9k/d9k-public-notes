# TCL

## The most misunderstood programming language / The Art Of The Terminal / YT, 2025

https://youtube.com/watch?v=PYh6D1NhatY

TCL (Tickle)

Parts of SQLite and Redis were written in TCL.
tcl language is built into Python interpreter.

2:40 Like in LISP, code is data.

3:00 You cam make TCL look and behave like functional or object-oriented language.

3:40 Made in MIT by John Osterhout, co-author of the Raft distributed consensus algorithm. Raft used in MongoDB, RabbitMQ, ClickHouse, Etcd etc

4:10 John Osterhout tried to automate hardware chips design process. Tool Command Language

6:45 Tk GUI

8:45 Tickle shell

11:30 In LISP everything is a list. And in tickle everything is a string. {} - group, [] - evaluate

12:45 foreach, creating a function dynamically

14:30 for interactive UI you need event handling.

15:35 Non-blocking server?

16:00 Sun releases Live Oak, Tcl competitor, as Java

16:45 Tcl browser plugin. Free for personal use.

18:15 Safe interpreter for browser. Limit time, proxy unsafe commands to it.

19:45 1997 release of Tcl 8 with byte-code support.

22:50 tclsh. https://bit.ly/tcl-fileevents
-> https://github.com/vivus-ignis/the-art-of-the-terminal/blob/master/most-misunderstood-proglang/06-concurrency/01_batch_processor_fileevents.tcl

24:00 No GIL. Parallel execution. Separate interpreters. Threads have to communicate sending messages to other threads like in Erlang. Tasks example.

27:20 trace - lets set a callback when a function of your choise invoked or finishes, when variable is read or written.

27:40 Author of redis: TCL reads like a config file

28:00 Everything is a string => ideal for building DSLs. Tk is just a DSL. SQL-like DSL.

29:00 No references => immutability. No concept of null values => no garbage collector.

29:50 FPGA (Field-Programmable Gate Array) scripting.

30:05 Network equipment scripting

30:20 IRC chats. Eggdrop library for bots.

30:40 TDD.

31:00 NavyServer for web dev backend:
https://github.com/naviserver-project/naviserver

32:00 TCL 9 release at 2025.

32:20 The lack of centralised packaging system. ActiveState TCL commercial repository abandoned.

34:00 To code in Rust you need at first to compile and test run your code in your head.

35:20 This complexity flood is so unlike original architecture of Unix. Smalltack syntax fitting in postcard?

35:20 https://colin-macleod.blogspot.com/2020/10/why-im-tcl-ish.html
https://wiki.tcl-lang.org/page/Articles

35:45 "We are destroying software" https://antirez.com/news/145

36:00 lib20: All the times I read anything about Tcl was to bash on it. It seems to me that only complexity
and solutions that are meant to get money from consumers into the industry are promoted. Joe Armstrong one of the creators of Erlang had a good saying that no other industry has promoted jobs so well as computer programming.

But I took a dive and I really love the language because it fits how my brain operates. I don't have to fight the language, don't have to be always searching for syntax rules. Everything is as simple as possible.

| used to program in Python, really loved it at the beginning, but after a couple of projects | really came to dislike it. Simplicity is only apparent. The language of the reptiles, as many things is life, look like something in the surface but being another thing in reality.

37:20 kt24601: I learned to like TCL after a heavy period of using C++. It wasn't my choice, someone pushed it on me, but I quickly grew to like its overly simplistic syntax.

Alan Perliss said, "A language that doesn't affect the way you think about programming, is not worth knowing.” The thing | learned from TCL is how much mental load you get from a complex language. When | write C++ (or any language), | have to roughly parse it in my brain, to make sure | type something that will compile. TCL syntax is simple, so it feels relaxing and easy to type. Like walking through a green field after climbing over rocks.