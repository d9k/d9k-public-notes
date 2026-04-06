# #Go

- 2024.07

## :scroll: Go #navigator

- [awesome-go](https://github.com/avelino/awesome-go) by [avelino](https://github.com/avelino)
	- _A curated list of awesome Go frameworks, libraries and software_

## :deciduous_tree: Go projects

### CLI tools

- [fzf: :cherry\_blossom](https://github.com/junegunn/fzf) by [junegunn](https://github.com/junegunn)
	- _A command-line fuzzy finder_

- [lazygit](https://github.com/jesseduffield/lazygit) by [jesseduffield](https://github.com/jesseduffield)
	- _simple terminal UI for git commands_

- [commitizen-go](https://github.com/lintingzhen/commitizen-go) by [lintingzhen](https://github.com/lintingzhen)
		- _The commitizen command line utility, without nodejs._

### embedded

- [gokrazy](https://github.com/gokrazy/gokrazy) by [gokrazy](https://github.com/gokrazy)
	- _turn your Go program(s) into an appliance running on the Raspberry Pi 3, Pi 4, Pi 5, Pi Zero 2 W, or amd64 PCs!_
	- :tv: [Zürich Go Meetup: Run Go programs on your Raspberry Pi with gokrazy! | YT](https://www.youtube.com/watch?v=mv_THRgLRHY)

### #JS tooling

- [esbuild](https://github.com/evanw/esbuild) by [evanw](https://github.com/evanw)
	- _An extremely fast bundler for the web_

### #LAN

- [gogs](https://github.com/gogs/gogs) by [gogs](https://github.com/gogs)
	- _Gogs is a painless self-hosted Git service_

## :jigsaw: Go #lib<span>&hairsp;s</span>

- helpers
	- [goutil: 💪 Helper Utils(700+)](https://github.com/gookit/goutil) by [gookit](https://github.com/gookit)
		- _int, byte, string, array/slice, map, struct, dump, convert/format, error, web/http, cli/flag, OS/ENV, filesystem, system, test/assert, time and more. Go 常用的一些工具函数：数字，字符串，数组，Map，结构体，反射，文本，文件，错误，时间日期，特殊处理，格式化，常用信息获取等等_

- `+` lua
	- [gopher-lua: GopherLua](https://github.com/yuin/gopher-lua) by [yuin](https://github.com/yuin)
		- _VM and compiler for Lua in Go_

- #FP
	- [fp-go](https://github.com/IBM/fp-go) by [IBM](https://github.com/IBM)
		- _functional programming library for golang_

- TDD
	- [goblin](https://github.com/franela/goblin) by [franela](https://github.com/franela)
		- _Minimal and Beautiful Go testing framework_
- gui
	- https://github.com/andlabs/ui - 2300+ commits

## :sparkles: Go features

- [Go features by version](https://antonz.org/which-go/)
	- 1.18 / Mar 2022
		- Generic programming using type parameters.

- _Golang was designed to solve several problems, including **slow build time**, uncontrolled dependencies, effort duplication, difficulty writing automatic tools and cross-language development._

- [Go Developer Survey 2023 H2 Results - The Go Programming Language](https://go.dev/blog/survey2023-h2-results)
	- AI/ML adoption is yet low
	- devs wish more clear errors explanation
	- work more on microservices then monolithic apps. A majority of respondents build microservices in a polyglot of languages, with only about ¼ exclusively using Go.
	- What used for?
		- API/RPC services (non-HTML): 74%
		- CLI: 62%
		- libs: 44%
		- websites/HTML services: 42%
		- #systemScripting: 38%
		- Data processing: 37%
		- Daemons (moniroring): 34%
		- Desktop/GUI apps: 9%
		- Embedded: 7%
		- AI/ML: 4%
		- Games: 4%
		- Mobile apps: 3%

- [ ] :beginner: [Channel Axioms | Dave Cheney](https://dave.cheney.net/2014/03/19/channel-axioms)

- :tv: [THIS Is Why You Should Learn Golang (as a Software Engineer) | Melkey | YT](https://www.youtube.com/watch?v=OCotIc2Ah_0)
	- Ken Thompson is Go developer too
	- 5x more jobs then Rust
	- golang rep has more stars than TS & Rust langs
	- One of the best standart libraries
	- Comments: guy solves Advent of Code with Go

- :tv: [Should you learn Go in 2023? | Dreams of Code | YT](https://www.youtube.com/watch?v=U2PpMZ7hWpg)
	- Robert Griesemer worked at Golang. Before that on V8 engine
	- (basic channels examples)
	- robust standart library

### #systemScripting

- :tv: [We can now write scripts using these languages, but is it worth it? | Dreams of Code | YT](https://www.youtube.com/watch?v=eRHlFkomZJg)
	- good & extensive standart library
	- [scriptisto](https://github.com/igor-petruk/scriptisto) by [igor-petruk](https://github.com/igor-petruk)
		- _A language-agnostic "shebang interpreter" that enables you to write scripts in compiled languages._
		- but written in #Rust

- errors can be easily ignored (no need for `try ... catch` blocks)

### code organisation

- http://stackoverflow.com/questions/9985559/organizing-a-multiple-file-go-project
- http://golang.org/doc/code.html

### polymorphism

- http://golangtutorials.blogspot.ru/2011/06/polymorphism-in-go.html

### debugging

- [delve](https://github.com/go-delve/delve) by [go-delve](https://github.com/go-delve)
	- _Delve is a debugger for the Go programming language._
- :tv: [Deterministic debugging with Delve And the state of Delve | YT](https://www.youtube.com/watch?v=sMnw28M-fMg)

- [ ] :tv: [Start using this Go design pattern.. Consumer Interfaces! | YT](https://www.youtube.com/watch?v=HtMPLiyC8W4&t=4s)

### #WASM

- :speech_balloon: [Running Go in the browser. TinyGo + Wasm + WebGL | /r/golang](https://www.reddit.com/r/golang/comments/1acjtc5/running_go_in_the_browser_tinygo_wasm_webgl/)
- :beginner: [Creating WebGL apps with Go | Gopher Academy Blog](https://blog.gopheracademy.com/advent-2018/go-webgl/)
	- [Whisper Simulation](https://divan.dev/whispervis/)
	- :heavy 8.6 mb `whispervis.js`

## :beginner: Go guides

- [The Zen of Go](https://the-zen-of-go.netlify.app/)

## :arrow_up::arrow_down: Go #WebDev

- [hugo](https://github.com/gohugoio/hugo) by [gohugoio](https://github.com/gohugoio)
	- _The world’s fastest framework for building websites._

- Templ

- :tv: [Golang + Templ Tutorial ( The Basics of go Templ ) #1 | YT](https://www.youtube.com/watch?v=0ZGZyxqa9Og)

- [ ] :tv: [Why We Switched From Svelte Kit To Golang + HTMX | Anthony GG | YT](https://www.youtube.com/watch?v=zB9tEQYLPL4)
	- +Templ
	- Had Svelte Kit SSR, business logic on Go, duplicated Go types in Typescript

- [ ] :tv: [The HATE Stack - Simple and Efficient | YT](https://www.youtube.com/watch?v=bti-bnGbyak)
	- HtmlX
	- Alpine - [Alpine.js](https://alpinejs.dev/)
	- Turso - SQLite
	- Echo - Go web framework

- [ ] #ORM
	- [ ] gorm

- [ ] :tv: [The Truth About HTMX & Golang | YT](https://www.youtube.com/watch?v=MeTj4i4FmVs)

- web framework
	- http://beego.me/
	- json responce
		- http://beego.me/docs/mvc/controller/jsonxml.md

## :toolbox: Go #tool<span>&hairsp;s</span>

- IDE
	- liteide
		- "LiteIDE is fantastic for Debugging."
		- https://code.google.com/p/golangide/
		- http://sourceforge.net/projects/liteide/
- tools
	- http://gvmtool.net/
- version manager
	- https://github.com/moovweb/gvm
- packages version managers
	- https://code.google.com/p/go-wiki/wiki/PackageManagementTools
	- https://github.com/mattn/gom
	- https://github.com/tools/godep

- use C preprocessor
	- http://nirbhay.in/2013/06/preprocessing-go-programs/

## Go #vs

- vs #Rust
	- :horse_racing: [Rust vs Go: Programming Language Duel | YT](https://www.youtube.com/shorts/R19xo9aQ164)
	- [startup-time](https://github.com/bdrung/startup-time) by [bdrung](https://github.com/bdrung)
		- _Measure startup time of different programming languages_
		- 20% faster the #Rust?

		- [1m-go-websockets](https://github.com/eranyanay/1m-go-websockets) by [eranyanay](https://github.com/eranyanay)
			- _handling 1M websockets connections in Go_

- vs #NodeJS
	- :newspaper: [Node vs Go: API Showdown | dev.to](https://dev.to/ocodista/node-vs-go-api-showdown-4njl)
	- :newspaper: [Переходим с Node.js на Go… но это не точно | mkant | Хабр](https://habr.com/ru/articles/890882/)
		- Прикладные API-сервера, для которых чаще всего используют Ноду устроены таким образом, что получить выигрыш производительности переходом на Go довольно трудно, а вот замедлить разработку очень легко.
		- BFF - В этой схеме основную нагрузку несёт система управления базой данных (СУБД). Скорость приёма запросов незначительно влияет на результат и зависит от архитектуры веб сервера
		- Node: код короче, dev-режим запуска, максимально удобная работа с JSON, не нужно "прокидывать" ошибки по всей цепочке функций
		- Golang: бинарный Protobuf удобнее

- vs #Java
	- :tv: [Pros & Cons of Golang (as a Java programmer) | Golang Dojo | YT](https://www.youtube.com/watch?v=mFKwF7m3GuM)

## :microbe: Go disadvantages

- :tv: [HARD truths before switching to Go... | Awesome | YT](https://www.youtube.com/watch?v=UEU4SzBjqrc), 2025
	- repetititve structure envelope
	- repertitive error values handling
	- no function overload

- :tv: [Golang Is Not a Sexy Programming Language | YT](https://www.youtube.com/watch?v=eQbc7cUrKzA)

- :newspaper: [We Need To Talk About The Bad Sides of Go | by Aviv Carmi | Oct, 2022 | Medium](https://web.archive.org/web/20221018104216/https://medium.com/@avivcarmis/we-need-to-talk-about-the-bad-sides-of-go-568a1e5adbc6)
	- :microbe: Symbols starting with an uppercase letter are automatically public and the rest are private. In most other languages, type names, by convention, begin with an uppercase letter, and variable names begin with a lowercase one. This convention means that variables can never shadow types.
	- advices Golang sentinel errors
	- [comments on Reddit | r/programming](https://www.reddit.com/r/programming/comments/ykz7rq/we_need_to_talk_about_the_bad_sides_of_go/)
		- :microbe: _Google has a toxic relationship with the open source community. Google spent YEARS just closing pull requests, discussions, and ideas about generics in Golang. They just change their mind on a whim and refuse to invite discussions simply because something doesn't fit their exact individual decision despite community support._

- http://www.quora.com/Do-you-feel-that-golang-is-ugly/answer/Tikhon-Jelvis
- http://lambda-the-ultimate.org/node/4554
- http://www.quora.com/What-reasons-are-there-to-not-use-Go-programming-language?redirected_qid=1787465

## Why is Go's Garbage Collection so criticized? : r/golang

- https://www.reddit.com/r/golang/comments/z1o2oe/why_is_gos_garbage_collection_so_criticized/?rdt=56407

Takn0711:

_IMHO it's because of the weird place Go is in._

_If you have a low level language, such as C/C++, you want to control everything that's happening, and avoid the overhead of carbage collection: since you are in control of everything, you are supposed to know when to free memory, no need for someone else to scan your memory._

_If you have a high level language, like Python, JS, and Java to a certain extend (I do consider Java as medium-high level), you already have performance overhead by definition, because of the VM/interpreter, so you don't mind having a bit more to delegate the memory handling to someone else and make your code simpler._

## Downsides of Go | /r/golang, 2024

https://www.reddit.com/r/golang/comments/1dxax0m/downsides_of_go/

zer00eyz:
- You have to throw away a lot of muscle memory from other languages. It's pretty easy to move from JS/Ruby/Python ... Go is a shift to how you think and work. Strong standard lib, resist the urge to "grab a package for that" and so on...
- There are some funky edge cases: closed channels is a great example here.
- C integration leaves something to be desired. It works, and works well, but there are dragons there that can bite you in the ass. Escaping to C isn't an easy magic bullet Ala python.
- Plugins are abject misery. The hashicorp lib does a lot to make this livable but it isn't "real" plugins. If you need a pluggable system look elsewhere (or use hashis' api hack)

reflect25:
* It’s not null-safe (in the sense that it does have null values)
* Nils, even if you code is safe from them, somebody else's on the project might not be and it just sucks
Just to explain a bit; it is moderately mitigated with golang's ability for multiple return values and the common pattern of returning (result, err) as well as checking if the err is nil.

Handsomefoxhf: My complaints usually are:
Nils, even if you code is safe from them, somebody else's on the project might not be and it just sucks;
Zero-values instead of defaults, JSON encoding nil-slices as nil, not empty slice;
Lack of standard library components like a generic syncmap, some slice and string operations;
No generic methods on structs, only generic structs.

zirouk: nils are one of Go’s worst features. I don’t think people truly appreciate the cost of not being able to guarantee something isn’t nil. Who on earth wants to handle nils at every layer of their application? Give me a proper algebraic type system any day.

- Handsomefoxhf: For me an even bigger issue is that I see different workarounds for this every time and they're all kind of stupid, I've seen those:
	- Passing everything as values. Works well until you're copying 800-byte structures or passing slices, as they're still "passed by reference"
	- Using some obscure library to represent nil's in structs (null.String) and such.
	- Straight up not checking anything:)

p_bzn:
- Weak abstraction power which limits the expressiveness of the language resulting in “idiomatic reinvent the wheel” all over the place.
- Implicit interfaces and mutations. There is no way to see whether anything method implements an interface or not in a simple declarative way. You don’t know whether reference type is gets mutated / cloned in the method / function.
- Imperative paradigm with no OOP nor FP resulting in awkward software design at scale. Complete lack of FP paradigm makes data processing cumbersome with no alternative.
- Weak type system by design. Generics as an afterthought.
- Error identification at handling stage. Code is awkward with Error.Is when you need to know why, for example, SQL driver returned error. Constrain violation? Field limit check fault? Good luck write code to figure that out.

gomsim: I'm probably too new (a month-ish) to Go have any real gripes with it. Most things mentioned here I just roll with and accept.
What really made me consider tearing out my hair for a second was something as silly as the lack of function overloading. Eg: func Publish(message string) func Publish(message string, id int)
Oh, and I also swore loudly when I realized strings are formatted java style with fmt.Sprintf and lots of %s and variables. I greatly prefer the Kotlin and TypeScript style with in-string varable references.

poggioreal: Go takes a minimalist approach, so it doesn’t offer as many data structures as, for example, C++. For this reason, certain specific data structures need to be reimplemented in Go using a combination of Maps, Slices, and Channels.