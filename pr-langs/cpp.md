# C++

## Антон Полухин | Незаменимый С++ | VK video, 2022

https://vkvideo.ru/video-77278886_456239374

Поисковые движки. Браузеры.

Высоконагруженные сервисы.

Игровые движки.
Спецэффекты и анимация для фильмов. C++11
Компиляторы.
Программы исследовательских лабораторий.
ОС, драйверы
Автопром.
Embedded.
Заводы.
Сопромат.
Биржа.
JVM

6:45 Zero Overhead. Поддержаа большого числа платформ.

9:45 Assembler: + максимум из железа, - оч. медленная разработка, - непереносимый код, - не всегда быстрее

11:00 Пример: целочисленное деление. Сравнение в Compiler Explorer. На assembler реализуется сложно. Компилятор C++ за десятки лет стал знать гигантское число низкоуровневых оптимизаций, над которыми думали множество групп людей. Выучить их, держать в голове и не путаться asm-разработчику невозможно.

13:00 Rust: лет через 15 больше возможностей для оптимизации, frontend компилятора больше знает о том, как алиасятся различные типы.

17:45 Из C можно легко перейти на C++. В Rust нужно оборачивать в unsafe. Нет хорошего генератора Rust-объявлений из C headers. Нужно допиливать руками и мучаться с borrow checker.

21:00 Даже если у языка крутой компилятор и подключены статические анализаторы, всё равно нужно писать тесты. Unsafe

22:45 Golang. Лучшая поддержка асинхронности и многопоточности из коробки - корутины.

Альтернативы для многопоточности на C++: Boost.Fibers, Yandex.Taxi userver, Quantum, Folly Fibers, Coroutines TS, C++20. Go скорее конкурент Python, чем C++.

24:30 Обманные бенчмарки: отключается сборщик мусора. Выделяется такой кусок памяти, что сборщик не запускается во время бенчмарка. Соломенное чучело: непрофессиональный код C++, с идиомами языка, привычного составителю бенча (например, аллокация float в цикле). C++ из коробки не оч. хорош с регулярными выражениями.

29:45 Простейший сборщик мусора - mark & sweep. Хранит ссылки на структуры данных, обходит их и помечает используемое. Непомеченное удаляет. Двусвязный список? Как собирать мусор? Stop the world (останавливаем все потоки, чтобы race condition не происходили).

34:30 Сборщик мусора no stop the world: ничего не останавливает. Накладные расходы на синхронизацию, обычно через атомарные инструкции. Нужно хранить доп. данные в структуре. Чем больше и сложнее структура, тем сложнее железу оптимизировать работу с ней. Иногда оптимизируют сборщик, чтобы он не проверял всё каждый раз, а обычно делал легковесные обходы, но оставляет за собой мусор. Идеальный сборщик мусора, не оставляющий мусор => нужно испльзовать shared_ptr. C++ разработчики знают, насколько он медленный. Но двусвязный список на shared_ptr это чиклические ссылки, их нужно тоже как-то обнаруживать и удалять. Баланс между скоростью работы (использованием CPU) и качеством сборки мусора (использованием оперативы). Большинство gc настраиваемые.

39:00 C# / Java лучше C++ для приложений, где не нужно быстро обрабатывать большие данные. Logstash на Java - считывает логи, бьёт на ключи и отправляет. Но ест процессора в 8 раз больше приложения, которое эти логи порождает. И в 2 раза больше оперативной памяти. Аналог, написанный на C++ в топе использования ресурсов даже не показывается.

41:20 C++ - высокий порог вхождения. Проблемы с безопасностью. Крошечная стандартная библиотека. Инфраструктуру нужно настраивать под себя. Go/Python/Rust позволяют создать стартап за день.

43:00 Итоги.

49:00 Вопрос: идея написать корпоративный фреймворк, позволяющий быстро разрабатывать приложения на C++.

https://github.com/apolukhin

## Libs

- [fmt](https://github.com/fmtlib/fmt) by [fmtlib](https://github.com/fmtlib)
	- _A modern formatting library_
- [awesome-cpp](https://github.com/fffaraz/awesome-cpp) by [fffaraz](https://github.com/fffaraz)
	- _A curated list of awesome C++ (or C) frameworks, libraries, resources, and shiny things. Inspired by awesome-... stuff._

# How To Scare C++ Programmer / Virbox / YT, 2022

https://youtube.com/watch?v=MHBG_R_dhwk

## Comments

@jaysistar2711: You compared buffered I/O in Python to direct I/O in C++

@Lightn0x: This is why C++ is reserved for people who know what they are doing :D

@boeing-747: C++ cin and cout streams are very slow by default because they have to wait and sync with the C standard streams. Add std::ios_base::sync_with_stdio(false); and run the test again
- @fakestiv: Done it... synced C++: 0.196s, python: 0.130s, non-synced C++: 0.026s

# Почему C++ спасает от эйджизма в 2025 году? / Артем Бабенко / YT, 2025

https://youtube.com/watch?v=zMUGiwjHZXE

Почему C++ спасает от эйджизма в 2025 году? / Артем Бабенко

"В 35 лет ты как бы уже взрослый для фронта".

Автор знает кейсы успешного устройства в 60+ лет.

3:00 Проектам часто более 10 лет. Здесь не сносят всё под ноль каждые 2 года.

3:30 Gatekeep, серьёзная проверка на входе. И по алгоритмам и по математике.

3:50 Пример: авионика, индустриальные контроллеры - серьёзная вещь, которая должна стабильно работать.

4:00 Банки. Графика - серьёзная математика.

4:40 Нужна стабильность, а не прогрессивность. Работа может быть достаточно занудной. Совместная работа с железячниками, тоже немолодыми.

5:15 Игровые движки - senior 5+ лет, глубокая оптимизация.

5:30 Драйвера - возьмут и в 70.

6:00 Занудство, умение читать стандарты, алгоритмы.

6:25 Не бояться low-level задач. Нужна математика.

6:50 Работа с кодовой базой, которой 12 лет, "без фишечек и рюшечек".

7:35 Кстати, почему векторы выстраиваются по кэшу?

7:50 Frontend - постоянно нужно быть гибким, учить новые версии фреймворков, а это свойственно больше молодёжи.

8:20 Мобильная разработка, все мегамолодые. Много дешёвых джуниоров с горящими глазами.

9:00 Data sciense - важен диплом серьёзного ВУЗа.

9:30 Python / Node - тоже ниши для молодых.

9:45 Все эти ниши распиарены, много курсов, постоянный приток новичков.

10:10 Embedded, в основном IoT. 6000 - 8000 $ в США.

11:10 Биржи, банки - от 10000$.

11:45 Gamedev - зп небольшие. Европа - от 4000 евро, США, от 7000 $

13:45 C++ embedded, IoT. miltech, security. Возьмут и в 60.

14:00 Unreal Engine с tooling'ом.

15:00 C++ quant finance, risk engines.

## Моё резюме по C++, 2026.07.10

C++ - язык, на котором постоянно создаются и обкатываются идеи по низкоуровневому взаимодействию с железом. На каждой конференции по C++ что-то новое в подходах по оптимизации и организации кода.

На C/C++ написано больше половины программ за всё время, на всех устройствах.

С++ - единственный язык, на котором можно написать вообще что угодно, ничем не ограниченное творчество, но и сломать/запутать программу можно как угодно.

Когда создают новый проект, первым делом ограничивают документально стандарты и подходы, пишут местные стандарты проектирования.

Ещё C++ невозможно полностью изучить.
Слишком много подходов, стандартов, расширений функционала и постоянно появляются новые.

Производители железа тоже оптимизируют железо для работы именно с C++ (Примеры оптимизаций под другие языки программирования: LISP-машины, Java processor).

## Psychology of People Who Prefer C++ Over Modern Languages / DevPsyche / YT, 2026

https://youtube.com/watch?v=u8mZqAA19SE

0:35 A deep visceral hatred of magic.
1:10 You don't want language to make decisions for you.
1:35 Desire for absolute control.
2:00 Rust: borrow checker, checks variables lifetimes.
3:30 Satisfaction from writing code that requires bare minimum of CPU interaction. You don't pay for what you don't use.
4:00 Belief that software should respect physical limitations of hardware.
4:22 RAII explanation
4:40 the moment object goes out of scope the resource is deterministically destroyed.
5:40 Modern programming language tries to enforce you into specific box to keep you safe. C+ gives you raw materials to build your own box.
7:00 new C++ standarts. smart pointers, move semantics
7:20 Dialect problem. No two companies use C++ the exact same way. You're not just learning language. You're constantly learning local dialects.
7:50 Hardware integration / legacy dependency.
8:10 Another languages are islands. C++ is a continent.
9:10 When a studio tries to render photorealistic world at 120 fps they can't afford unpredictable latency of garbage collector. They need to manage cache, lines and memory alignment.
10:00 Rendering engine of the browser.