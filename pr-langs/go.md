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

- _Golang was designed to solve several problems, including **slow build time**, uncontrolled dependencies, effort duplication, difficulty writing automatic tools and cross-language development._

- [Go Developer Survey 2023 H2 Results - The Go Programming Language](https://go.dev/blog/survey2023-h2-results)

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

- vs #Java
	- :tv: [Pros & Cons of Golang (as a Java programmer) | Golang Dojo | YT](https://www.youtube.com/watch?v=mFKwF7m3GuM)

## :microbe: Go disadvantages

- :tv: [Golang Is Not a Sexy Programming Language | YT](https://www.youtube.com/watch?v=eQbc7cUrKzA)

- :newspaper: [We Need To Talk About The Bad Sides of Go | by Aviv Carmi | Oct, 2022 | Medium](https://web.archive.org/web/20221018104216/https://medium.com/@avivcarmis/we-need-to-talk-about-the-bad-sides-of-go-568a1e5adbc6)
	- :microbe: Symbols starting with an uppercase letter are automatically public and the rest are private. In most other languages, type names, by convention, begin with an uppercase letter, and variable names begin with a lowercase one. This convention means that variables can never shadow types.
	- advices Golang sentinel errors
	- [comments on Reddit | r/programming](https://www.reddit.com/r/programming/comments/ykz7rq/we_need_to_talk_about_the_bad_sides_of_go/)
		- :microbe: _Google has a toxic relationship with the open source community. Google spent YEARS just closing pull requests, discussions, and ideas about generics in Golang. They just change their mind on a whim and refuse to invite discussions simply because something doesn't fit their exact individual decision despite community support._

- http://www.quora.com/Do-you-feel-that-golang-is-ugly/answer/Tikhon-Jelvis
- http://lambda-the-ultimate.org/node/4554
- http://www.quora.com/What-reasons-are-there-to-not-use-Go-programming-language?redirected_qid=1787465