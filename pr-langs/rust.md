# Rust

- :sparkles: Лучшие консольные утилиты
- :sparkles: Программирование микроконтроллеров
- :microbe: Сложная кривая обучения

## Rust в ядре Linux: Грег Кроа-Хартман о будущем без багов

https://proglib.io/p/eto-vyigrysh-dlya-vseh-pochemu-klyuchevoy-razrabotchik-linux-bolshe-ne-hochet-pisat-na-c-2025-02-26, 2025

- Грег Кроа-Хартман, один из ключевых разработчиков и сопровождающих ядра
- большинство багов в ядре (по количеству, а не по серьезности) связаны с «глупыми незначительными крайними случаями в C», которые полностью отсутствуют в Rust. Речь идет о таких вещах, как переполнение буфера, пропуск проверки кодов возврата и ошибки типа use-after-free.
- C++ не даст нам аналогичных преимуществ, а проблемы с комитетом по стандартизации указывают на то, что _«всем лучше отказаться от этого языка как можно скорее, если они хотят иметь кодовую базу, которую можно поддерживать в течение длительного времени»_.

## Considering Rust | Jon Gjengset | YT

https://www.youtube.com/watch?v=DnT-LUQgc7s, 2020

## :speech_balloon: Why and Why not Rust? - The Rust Programming Language Forum

https://users.rust-lang.org/t/why-and-why-not-rust/98354, 2023
	- jbe:
		- sometimes prone to boilerplate code or verbose syntax due to some limitations of the type system (e.g. regarding [method delegation](https://users.rust-lang.org/t/implementing-trait-by-forwarding-all-trait-methods-to-inner-value/63725))
		- async has been added to the language at a later stage, so async integration sometimes feels limited and [complex](https://users.rust-lang.org/t/pin-unpin-sometimes-feels-slapped-on-top-of-an-existing-language/65944) (pinning, lifetime issues, etc.)
		- error handling sometimes feels like having a lot of friction (one thing I ran into can be [found here](https://users.rust-lang.org/t/error-cannot-be-sent-shared-between-threads-safely/91455), [another example there](https://users.rust-lang.org/t/error-cannot-be-sent-shared-between-threads-safely/91455))
		- complexity of the language leads to inevitable design flaws in std (e.g. [this one](https://internals.rust-lang.org/t/semantics-of-asref/17016?u=jbe)) which are probably [impossible to fix](https://internals.rust-lang.org/t/rusts-complexity-rusts-stability-policy/16946?u=jbe)

## Rust - очень вредный язык программирования? | Миша Ларченко | YT

https://www.youtube.com/watch?v=U8GS5ZB1CG0

Главный разработчик Rust For Linux ушёл с проекта. не хватает энтузиазма, чтобы побороть нетехнические глупости.

Люди работающие с Rust долгое время, склонны к выгоранию.

jyn514: "the number of people who have left the rust project due to burnout is shockingly high. the number of people in the project who are close to burnout is also shockingly high". / https://jyn.dev/the-rust-project-has-a-burnout-problem/

### Комментарии

@gtr-o-dimm: Вы Миша на Раст не базарьте, просто зайдите в си-комьюнити и скажите слово раст, очнетесь на костре как еретик и сразу поймёте от чего устает раст разработчик

## Rust: зачем выбирать этот язык в 2025 году? | Дмитрий Коваленко | #29

https://vkvideo.ru/video-224967259_456239083

Rust читабельный.

Fulltime не нравился, пока не нашёл работу на Rust.

Сначала думали делать OCaml-подобный язык с Garbage-коллектором.

Borrow checker - работа со статическими анализаторами вроде Valgrind - почему бы не встроить в язык.

Servo - движок на Rust.

Инструментарий переписывается на Rust. Компиляторы, linter'ы, редакторы.

Rust кажется не сложнее Go и явно интереснее.

Перейти с TS на Rust легче, чем на C или Zig.

Продуманная стандартная библиотека, которой очень легко что-то распарсить.

Изоляция unsafe-кода.

После Rust проще писать на функциональных языках.

Str - указатель на кусочек String с длинной. Компилятор проверяет, чтобы данные, на которые ссылается Str, всегда существовали.

## Rewriting Bun in Rust / bun.com

https://bun.com/blog/bun-in-rust

We could have kept fixing these kinds of bugs one-off in perpetuity, but we owe it to our users counting on us to do better than that, and systematically prevent these kinds of bugs from recurring.

What we were already doing
- We patched the Zig compiler to add Address Sanitizer support. We run our test suite with ASAN on every commit.
- fuzz Bun's runtime APIs 24/7 using Fuzzilli, the JavaScript engine fuzzer used by V8 & JavaScriptCore
- a lot end-to-end memory leak tests

For Bun, correctly handling the lifetimes of garbage-collected values and manually-managed values has been a major source of stability issues - most often small memory leaks and occasionally, crashes. Every memory allocation has to be meticulously reviewed. Where do these bytes get freed? How do we ensure it only gets freed once? Did we check for JavaScript exceptions properly? Is this garbage-collected pointer visible to the conservative stack scanner? Is this garbage collected memory or manually managed memory?

 I don't blame Zig for that - other users of Zig don't have the bugs we had, and mixing GC with manually-managed memory is an uncommon enough thing for software to need that no language really designs for it.

Zig does not have constructors/destructors, and most cleanup is expected to be written out explicitly at each call site with defer.

Our current approach is a mix of:
- arena lifetimes, where the scope of when it's accessible is clear (parser state doesn't escape the calling function and so AST nodes are a good choice there)
- reference-counting
- pay really close attention

Many projects opt to answer these kinds of questions through a style guide. TigerBeetle's TigerStyle is an example in Zig and Google's 31,000 word C++ style guide is another.

How do you make sure the style guide is followed? code review, linters & static analyzers.

A large percentage of bugs from that list are use-after-free, double-free, and "forgot to free" in an error path. In safe Rust, these are compiler errors and RAII-like automatic cleanup with Drop. Compiler errors are a better feedback loop than a style guide.

About 20% of Bun's code is written in C++ and Bun embeds several C/C++ libraries:

C++ instead of Zig would be a reasonable choice for Bun. We would get constructors & destructors. We could delete lots of extern "C" wrapper code.

We added Rust-inspired smart pointers to Bun's codebase. But honestly, I didn't want to do it. Homegrown smart pointers offer worse ergonomics than Rust, with none of the guarantees.

The least risky approach to getting something shippable would be a mechanical port from Zig to Rust, with the minimal number of behavioral changes, using the exact same test suite we already use for testing Bun.

//. . . . .