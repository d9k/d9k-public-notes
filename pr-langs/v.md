# V programming language

- [v](https://github.com/vlang/v) by [vlang](https://github.com/vlang)
- _Simple, fast, safe, compiled language for developing maintainable software. Compiles itself in `<1s` with zero library dependencies. Supports automatic `C => V` translation. https://vlang.i_
- runs on Android too
- web server, UI lib
- 5 способов управления памятью
- vinix
	- использует autofree
- :symbols: [flappylearning](https://github.com/vlang/v/blob/master/examples/flappylearning/game.v) by [v](https://github.com/v)
	- `mut` for functions!
	- :symbols: [neuronevolution](https://github.com/vlang/v/blob/master/examples/flappylearning/modules/neuroevolution/neuronevolution.v)

## :mortar_board: Edu

- [The Book of V — The Book of V 0.4.5 documentation](https://the-book-of-v.readthedocs.io/en/latest/), 2019

## Edu #example

- [Category:V (Vlang) - Rosetta Code](https://rosettacode.org/wiki/Category:V_(Vlang))

## #review

- [V lang. Обзор и сравнение с Golang / Хабр](https://habr.com/ru/articles/699396/), 2022
- [V Language Review (2023) | skvortsov](https://n-skvortsov-1997.github.io/reviews/)
- [V Language Review (2022) | mawfig.github.io](https://mawfig.github.io/2022/06/18/v-lang-in-2022.html)
	- :fallen_leaf: (2022, outdated)
	- errors, benchmarks
	- compiling to C does not automatically make your language fast and specifically it does not automatically give you C level performance.
	- `valgrind --leak-check=full ./autofree_example`
	- forcing the value to be allocated on the heap reveals that autofree leaks the values.

## Memory management

- :beginner: [Memory management | docs | vlang repo]](https://github.com/vlang/v/blob/master/doc/docs.md#memory-management) by [v](https://github.com/v)

## C interop

- [Calling C from V | V Documentation](https://docs.vlang.io/v-and-c.html)
	- V can translate your C code to human readable V code, and generating V wrappers on top of C libraries. `c2v`.

## Apps #example

- [vpaint](https://github.com/pisaiah/vpaint) by [pisaiah](https://github.com/pisaiah)
	- _MS-Paint alternative written in V._

## :jigsaw: Libs

- [crayon](https://github.com/thecodrr/crayon) by [thecodrr](https://github.com/thecodrr)
	- colored terminal
- [shy](https://github.com/larpon/shy) by [larpon](https://github.com/larpon)
	- _Helps you being creative in V_
- [miniaudio](https://github.com/larpon/miniaudio) by [larpon](https://github.com/larpon)
	- _VVrap of the excellent miniaudio C audio library_
- [sdl](https://github.com/vlang/sdl) by [vlang](https://github.com/vlang)
	- _Official SDL2 & SDL3 bindings for V_
- [Vebview.JS](https://github.com/malisipi/Vebview.JS) by [malisipi](https://github.com/malisipi)
	- _Move Beyond the Web Border_
- [vgram](https://github.com/dariotarantini/vgram) by [dariotarantini](https://github.com/dariotarantini)
	- _Telegram Bot library written in V._
- [py2v](https://github.com/vlang/py2v) by [vlang](https://github.com/vlang)
	- _A Python to V transpiler._

## Web

- [vss](https://github.com/veltiosoft/vss) by [veltiosoft](https://github.com/veltiosoft)
	- _Easy-to-use static site generator_

## И23: А. С. Медведников | язык V - простой, быстрый, безопасный, компилируемый, Open Source | YT

- https://www.youtube.com/watch?v=xMGNlUZQ-6w

Не компилятор, а транспайлер на Си (как Vala?)

Batteries included, есть даже ORM.

Поддержка и нецентрализованной установки модулей (Git и Mercurial ссылками).

Garbage collection есть, 5 способов управления памятью.

Всегда был против GC. В Java он хотя бы сильно настраиваемый.

Autofree - есть в Lobster, Nim.

Go's GC. Оказалось, работает быстрее Autofree.

vinix использует autofree, работает хорошо. На ней запускается компилятор C++, Doom

Valgrind: нет утечек памяти в редакторе на V.

Вэбсерверы на V крутятся по году без рестартов, утечек и крэшей.

Arena Allocation - кусок памяти заранее отделяешь. Используется в популярных играх. Поддерживается через флаг prealloc.

Будет ещё ownership как в Rust.

Три мейнтейнера имеют право на merge. Два крайне талантливых программиста из Китая. Много фидбека и обсуждения из Китая.

Общение с Alibaba потому что используется их библиотека по корутинам.

Многие пришли в V из-за скорости компиляции. Меньше секунды. Сразу можно смотреть результат.

Десятки тысяч unit-тестов.

Билды проверяются на скорость. Нельзя одним коммитом замедлить скорость на 6%, придётся править.

Clang-анализаторы используются, но они медленные. Одно время пробовали PVS, они давали лицензию.

Автопроверка сборок GC/не-GC Valgrind'ом.

v ved - статический анализатор кода. В т. ч. проверка на code style и ненужные оптимизации.

Вдохновляются Go. Стандартная библиотека похожа. Ребята из Go хорошую работу проделали.

v translate doom - перевод C -> V. Есть лишь небольшие графические баги.

tcc в 7 раз быстрее gcc. Для оптимизированных билдов используется Clang.

C - современный ассемблер, язык, который запускается везде.

У Go нет режима оптимизации. Код, который билдит Go, уже максимально оптимизирован и билдит очень-очень быстро.

Python - оч. сложный язык. Фейк-простота завуалированная.

Деньги не приоритет в жизни. Интересно заниматься тем, что нравится и как-то улучшать мир.

## Interesting issues

- :speech_balloon: [Trojan Source: Stretched string | issue #12377 | v](https://github.com/vlang/v/issues/12377)

## Learn V in Y Minutes

- https://learnxinyminutes.com/v/
+ can return multiple values
- private by default, needs pub
- `outer:`, `continue outer`: labels to control execution flow

