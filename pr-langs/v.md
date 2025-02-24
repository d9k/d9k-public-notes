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