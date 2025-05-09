# Rust

- :sparkles: Лучшие консольные утилиты
- :sparkles: Программирование микроконтроллеров
- :microbe: Сложная кривая обучения

- :newspaper: [Rust в ядре Linux: Грег Кроа-Хартман о будущем без багов](https://proglib.io/p/eto-vyigrysh-dlya-vseh-pochemu-klyuchevoy-razrabotchik-linux-bolshe-ne-hochet-pisat-na-c-2025-02-26), 2025
	- Грег Кроа-Хартман, один из ключевых разработчиков и сопровождающих ядра
	- большинство багов в ядре (по количеству, а не по серьезности) связаны с «глупыми незначительными крайними случаями в C», которые полностью отсутствуют в Rust. Речь идет о таких вещах, как переполнение буфера, пропуск проверки кодов возврата и ошибки типа use-after-free.
	- C++ не даст нам аналогичных преимуществ, а проблемы с комитетом по стандартизации указывают на то, что _«всем лучше отказаться от этого языка как можно скорее, если они хотят иметь кодовую базу, которую можно поддерживать в течение длительного времени»_.

- :tv: [Considering Rust | Jon Gjengset | YT](https://www.youtube.com/watch?v=DnT-LUQgc7s), 2020

- :speech_balloon: [Why and Why not Rust? - The Rust Programming Language Forum](https://users.rust-lang.org/t/why-and-why-not-rust/98354), 2023
	- jbe:
		- sometimes prone to boilerplate code or verbose syntax due to some limitations of the type system (e.g. regarding [method delegation](https://users.rust-lang.org/t/implementing-trait-by-forwarding-all-trait-methods-to-inner-value/63725))
		- async has been added to the language at a later stage, so async integration sometimes feels limited and [complex](https://users.rust-lang.org/t/pin-unpin-sometimes-feels-slapped-on-top-of-an-existing-language/65944) (pinning, lifetime issues, etc.)
		- error handling sometimes feels like having a lot of friction (one thing I ran into can be [found here](https://users.rust-lang.org/t/error-cannot-be-sent-shared-between-threads-safely/91455), [another example there](https://users.rust-lang.org/t/error-cannot-be-sent-shared-between-threads-safely/91455))
		- complexity of the language leads to inevitable design flaws in std (e.g. [this one](https://internals.rust-lang.org/t/semantics-of-asref/17016?u=jbe)) which are probably [impossible to fix](https://internals.rust-lang.org/t/rusts-complexity-rusts-stability-policy/16946?u=jbe)