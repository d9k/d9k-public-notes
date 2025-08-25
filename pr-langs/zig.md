# Zig

## Links

- [Zigistry: A package registry and manager for Zig | Find & Share Zig Packages](https://zigistry.dev/)
- [awesome-zig](https://github.com/zigcc/awesome-zig) by [zigcc](https://github.com/zigcc)
	- _A collection of some awesome public Zig programming language projects._
- [News ⚡ Zig Programming Language](https://ziglang.org/news/)
- [Devlog ⚡ Zig Programming Language](https://ziglang.org/devlog/2025/)

## Zig Language | Thoughts After 2 Years | codingjerk, 2025

- https://www.youtube.com/watch?v=TCcPqhRaJqc

Zig obvious fine control examples.
Robust explicitness.
Friendly community of professionals.

- Comments: :speech_balloon: [Why I love Zig (after using it for two years) | /r/Zig](https://www.reddit.com/r/Zig/comments/1jxun9r/why_i_love_zig_after_using_it_for_two_years/?%24deep_link=true&post_fullname=t3_1jxun9r&post_index=0)

## Zig in 100 Seconds | Fireship |  YT

- https://www.youtube.com/watch?v=kxT8-C1vmd4

2016

No hidden memory allocations.
Obvious allocators.

comptime - code runs on compile time instead of runtime

defer - automatically run when going out of scope

no exception. function must return error value.

Supports c/c++ cross-compilation with LLVM.

## Go is blazingly faster than Zig? | ThePrimeagen

- https://www.youtube.com/watch?v=RSY85SLXzwk

Zig is prerry fun lang to work with but was encumbered by segfaults.

Store requests in queque not older then 10 seconds.

JS on Bun - 1 hour.

## #video

- :tv: [Creator of Ghostty talks Zig over Go | YT](https://www.youtube.com/watch?v=YQnz7L6x068)
	- Smaller: :tv: [Why Ghostty is written in Zig (not Rust or Go) | YT](https://www.youtube.com/watch?v=dJ5-41u-e7k)
	- 25:29 Ghostty developer: When reads & writes Rust just not having fun.
	- He didn't like jumping back and forth implementing traits with Rust.
	- PrimeAgen: no interfaces in Zig confused me.
		- Mitchell: At first tried to watch every Zig talk about using dynamic dispatch and vtables instead of interfaces. Then realised you don't always need an interface. Then realized Zig comptime makes static dispatch similar to interfaces possible.
	- Doesn't want to return to Go, even PHP seems more interesting. But loves Go community.
		- 3rd person: I don't get the same feelings of Joy when writing Go like I do with other languages. But it's good for working with other people!
	- Go was not a choise because wanted to own every single allocation.
	- Talks with Zig author. Excellent community.

- :tv: [Why does everyone hate Go? | YT](https://www.youtube.com/watch?v=VVb65xABTWw)
	- 1:00 Zig creator criticizes Go.
	- 2 types of language users:
		- Doesn't care: just ship, `$$$`, want users
		- Programming purist: Associates their self worth with the language. Hyper-fixates on complex programming solutions. "Above" the simpletons

- :tv: [Why learn Zig? | Kodaps Academy | YT](https://www.youtube.com/watch?v=wKAsZImDtak), 2024
	- Interoperability with C: Zig can use C libraries. Incremental adoption
	- 2:00 Errors are part of type system. Managing errors is required
	- 3:20 Rust tries to eliminate errors by design. Rust tracks variables lifetime.
	- 4:00 Comptime instead separate C macro language
	- 4:50 Cross-compilation. Toolchain is a part of the language. Integrated TDD
	- 5:10 Zig concurrency is a native language feature
	- 6:10 [Exercism](https://exercism.org/) ad (algo tasks and test assignments tasks (like build own SQLite))


## :balloon: #project<span>&hairsp;s</span> on Zig

- [bun](https://github.com/oven-sh/bun) by [oven-sh](https://github.com/oven-sh)
	- _Incredibly fast JavaScript runtime, bundler, test runner, and package manager – all in one_
- [yorhel/ncdu | Blicky.net Git Host](https://code.blicky.net/yorhel/ncdu/)
	- NCurses Disk Usage
- [tigerbeetle](https://github.com/tigerbeetle/tigerbeetle) by [tigerbeetle](https://github.com/tigerbeetle)
	- _The financial transactions database designed for mission critical safety and performance._

## #speed

- :tv: [Rust vs Zig vs Go Performance | Anton Putra | YT](https://www.youtube.com/watch?v=3fWx5BOiUiY), 2024

- :tv: [Deno vs. Node.js vs. Bun: Performance Comparison 2025 | Anton Putra | YT](https://www.youtube.com/watch?v=DpDHPoStZZ8&list=PLiMWaCMwGJXmcDLvMQeORJ-j_jayKaLVn&index=10)
	- #Bun written with Zig

- :tv: [Go (Golang) vs. Bun: Performance (Latency - Throughput - Saturation - Availability) | Anton Putra | YT](https://www.youtube.com/watch?v=ECnlX00YcPI), 2024

## No interfaces?!

- :speech_balloon: [What's the idiomatic design in zig when there is no interfaces/traits? - Explain - Ziggit](https://ziggit.dev/t/whats-the-idiomatic-design-in-zig-when-there-is-no-interfaces-traits/7817)

- :speech_balloon: [Why Zig doesn't have/want Go-like interfaces? | /r/Zig](https://www.reddit.com/r/Zig/comments/1i1y5x4/why_zig_doesnt_havewant_golike_interfaces/)
	- SweetBabyAlaska: runtime dynamic dispatch is not free.
		- `@Validate(type, otherType)`
		- `@hasDecl()`
		- :speech_balloon: [Proposal: User definable type constraints on polymorphic parameters | issue #1669 | zig](https://github.com/ziglang/zig/issues/1669)

- :speech_balloon: [Interfaces in Zig gives me the vibe of Object Orientation in JavaScript - Brainstorming - Ziggit](https://ziggit.dev/t/interfaces-in-zig-gives-me-the-vibe-of-object-orientation-in-javascript/5650)

- [Zig interfaces | ethanfrei.com](https://ethanfrei.com/posts/zig-interfaces.html)
	- `Dog` example
- [Zig Interfaces | openmymind.net](https://www.openmymind.net/Zig-Interfaces/)
	- `Writer` example
- [Zig Interfaces for the Uninitiated, an update - Zig NEWS](https://zig.news/kilianvounckx/zig-interfaces-for-the-uninitiated-an-update-4gf1), 2022
	- `Iterator` example

## Zig cookbook: collection of simple Zig programs that demonstrate good practices | Hacker News

https://news.ycombinator.com/item?id=38837807

flohofwoe: In short: Zig can (and does) fix C warts from the ground up because it doesn't need to be backward compatible with C, while still getting the essence of what makes C useful (many other new languages don't get this important part). The biggest advantage over C for day-to-day coding is probably the much more complete and useful stdlib. You also don't need to "switch", mixed C/Zig projects are well supported by the Zig language and build system. Having said that, I still write most new code in C (C99 designated init is still superior to what Zig has to offer for struct initialization), but at least there's now a worthwhile alternative on the horizon to switch to in the future.