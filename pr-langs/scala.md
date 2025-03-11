# Scala

- [ ] :tv: [Путь от монолита на PHP к микросервисам на Scala / Денис Иванов (2GIS)](https://vkvideo.ru/video-152308462_456241576)

## Scala + #Android?

- :speech_balloon: [Any good examples of an android app written in Scala? : r/scala](https://www.reddit.com/r/scala/comments/y47zlz/any_good_examples_of_an_android_app_written_in/)
	- Scala used to be useable on Android. However, the JVM advanced and android didn't and scala stuck with the former. If I remember correctly you have to downgrade to scala 2.11 if you want to write android apps with it.
	- [Transpilers?](https://www.reddit.com/r/scala/comments/y47zlz/comment/mf3vbj4/?utm_source=share&utm_medium=web3x&utm_name=web3xcss&utm_term=1&utm_content=share_button)

- :speech_balloon: [java - Scala с Android - есть у кого-нибудь опыт? | SO на русском](https://ru.stackoverflow.com/questions/73405/scala-%D1%81-android-%D0%B5%D1%81%D1%82%D1%8C-%D1%83-%D0%BA%D0%BE%D0%B3%D0%BE-%D0%BD%D0%B8%D0%B1%D1%83%D0%B4%D1%8C-%D0%BE%D0%BF%D1%8B%D1%82)

- [scalaonandroid](https://github.com/makingthematrix/scalaonandroid) by [makingthematrix](https://github.com/makingthematrix)
	- _A tutorial and examples of how to write Android apps in Scala 2.13 and Scala 3._

## #article

- :newspaper: [4 вопроса для разработчика Scala](https://proglib.io/p/4-scala-questions)
- :newspaper: [Как использовать implicit'ы в Scala и сохранить рассудок | Хабр](https://habr.com/ru/articles/329600/)

## #video

- :tv: [Why are #Scala devs paid so well? | DevInsideYou | YT](https://www.youtube.com/shorts/sJ1XWac28lA)
	- Spark & Kafka are written in Scala.
	- Designed for professionals.

## #scripting

- [scala-cli](https://github.com/VirtusLab/scala-cli) by [VirtusLab](https://github.com/VirtusLab)
	- _Scala CLI is a command-line tool to interact with the Scala language. It lets you compile, run, test, and package your Scala code (and more!)_
	- :beginner: [Dependencies | Scala CLI docs](https://scala-cli.virtuslab.org/docs/getting_started#dependencies)

## #frontEnd

#### Scala.js

- [scala-js](https://github.com/scala-js/scala-js) by [scala-js](https://github.com/scala-js)
	#### - _Scala.js, the Scala to JavaScript compiler_
- :door: [Scala-js.org](https://www.scala-js.org/)
	- Scala.js and Vite: Set up a hello world project ready for live reloading in the browser. Generate minimized production assets.
	- Laminar: Build UIs with Laminar using Functional Reactive Programming (FRP), a hybrid model between imperative and functional programming particularly well suited for UI development in Scala.
	- ScalablyTyped: Integrate JavaScript libraries using ScalablyTyped.
- :speech_balloon: [Scala.js in 2024 | /r/scala](https://www.reddit.com/r/scala/comments/1bvzzec/scalajs_in_2024/)
	- _TypeScript is easier to build, has better tooling, has less overhead than Scala.js, and has more seamless interop with JS, but it just isn't anywhere near as good Scala_
	- _TS lacks ADTs and pattern matching_
	- _Some companies stopped using Scala mainly because of the difficulty in finding developers_
		- _Developers can pick up Scala in 1 month or so with proper training materials and online lectures(like rockjvm)._
	- We use Scala-js for everything related to JavaScript. All frontend libraries were interfaced to scala-js when this was done. By the way, Scala has macro support so that you can use excellent libraries like Slick or Autowire to do RPC and so on. Also, not to mention the Effects System! / PlatypusIllustrious7
	- I wouldn't recommend ScalablyTyped. The facades it generates are different from the ones you would create manually. It's often not obvious where to import things from, and it can be hard to map JS library's documentation and code examples to ScalablyTyped's output. You don't need to write types for the whole TS/JS library, just the parts that you need, and you can even use `js.Dynamic` when convenient. Choose Typescript if you have a node.js backend, of if you like the TypeScript way of doing things: superficial convenience over correctness (in many ways), using a thousand npm packages for every little thing, etc.
- :beginner: [JavaScript types - Scala.js](https://www.scala-js.org/doc/interoperability/types.html)

## СИЛА Функционального Программирования / Всё о Scala / Интервью со Scala Developer Олегом Нижниковым / АйТиБорода, 2021

- https://www.youtube.com/watch?v=nII0ralSlRo

Попробовал разные языки в разработке простых web-приложений, в спортивном программировании.

С Haskell-ным менталитетом вернулся обратно к Scala. Java-мир предлагает больше вещей, где можно себя проявить.

Тинькофф - крупная IT-компания. Tinkoff Travel - агрегатор tutu.ru и подобных.

В Scala постоянно голод на библиотеки. Бывают библиотеки, которые делают одно и то же, но для разных стэков.

В Тинькофф > 100 скалистов (!). Сначала на Scala писали Gateway для фронта на JS. Gateway в различные внутренние сервисы, по большей части купленные. Потом оказалось, что Scala обладает прекрасным TTM (time-to-market), быстро обретает высокое качество.

Начало 20 века - развитие конструктивной математики.

1958 - первый функциональный язык. Один из первых языков высокого уровня вообще. За 14 лет до появления Си.

ФП продвигается в основном людьми из академии.

Большая часть фич Java пришла из функционального программирования. JIT, GC, Generic-типы.

Помимо Scala Мартин Одерски создал Generic Java, которая стала потом частью Java.

Почти все языки сейчас переняли лямбды. Паттерн-матчинг.

Функция - преобразование одного множества в другое. В отличие от процедур должны быть чистыми.

Мартин Одерски писал компиляторы. Ему нужно было сети петри моделировать.

Иммутабельные структуры - ФП считалось неэффективным. Оно постоянно конструирует объекты, которые надо выкидывать.

Парадигмы Scala ООП+ФП. Егор Бугаенко, например, считает, что и объекты должны быть иммутабельными.

Конструкции функционального языка позволяют отделять работу с внешним миром от чистых функций - библиотеки Scala zio, monix.

В Scala нет статических методов, есть глобальный объект. Для взаимодействия с Java: у классов есть объект-компаньон. Функции тоже объекты. Unwrapping?

Trait: и mixin и interface.

ООП - инкапсуляция. ФП - максимальная открытость. Но благодаря проверке типов компилятор не даст передать не то. Но в ФП тоже инкапсуляция в плане тела функции.

Маленькие функции ФП и удобные инструменты их комбинирования облегчают переиспользование и тестирование.

Clojure - наследник Common Lisp. Появились разные виды скобочек.

Racket - наследник другой ветви ФП-языков, Scheme. Конструктор DSL-ей.

Lisp - код языка должен быть максимально похож на данные. Поэтому удобно писать макросы - трансформеры кода.

Haskell - основная фича - ленивые вычисления.

Idris - язык с зависимыми типами, академический.

Подходы из Haskell упрощают серверное multithreading-программирование. Механизмы асинхронности, конкурентности.

Apache Spark для BigData написан на Scala.

На Scala удобно разрабатывать экспериментальные компиляторы.

Akka - популярная, но устаревшая экосистема акторов.

Scala Cats - ФП.
Scala Cats Effects - примитивны для concurrency, fibers.

Scala zio - новая библ., породившая экосистему библиотек.

sbt - один из самых сложный build tool'ов. Включает в себя пакетный менеджер. Альтернативы: maven, gradle, bazel.

Scala 3 (dotty) - более безопасные преобразования типов. DOT - dependent object types. Scala 3 отличается от 2 больше, чем Python 3 от 2. Но, в отличии от Python Scala 3 сможет использовать библиотеки Scala 2.

Минорное поднятие версии (2.12 -> 2.13) создаёт бинарную обратную несовместимость. В Scala 3 планируется добавить бинарную совместимость через промежуточный код.

VS Code - нужен плагин Metals.

Couchbase NoSQL клиент.

Общество достаточно большое, чтобы помочь всем новичкам.

t.me/scala_ru

Читает худ. лит. на англ. Книга "капитализм и шизофрения".

Peopleware - читают с женой друг другу главы из книги.

Конференции СНГ: ScalaRussia, FPure, F(by).

## How 1 Software Engineer Outperforms 138 - Lichess Case Study / Tom Delalande

- https://www.youtube.com/watch?v=7VSVfQcaxFY

Scala + SnapDOM.

Play framework.

MongoDB - stores JSON objects, has good compression. Replicates. Aggregation framework.

Redis is used to communicate between services. Websocket services saves events to the cache which then read by a core service (or WS service after redeploy).

Architecture is a monolith with satellites. _It's convenient because all the state is in one place, and can be cached in-heap for all the modules on the site to use... Proper cache invalidation across multiple instances would be impossible_

Lag compensation + optimistic client-side rendering.

## Learn Scala in Y Minutes

- https://learnxinyminutes.com/scala/

- `def` instead of function. Type can be defined by return type only. Returns last expression automatically.
- `var` / `val` for variable/constant value.
- :microbe: WARNING: The `return` keyword exists in Scala, but it only returns from the inner-most `def` that surrounds it. Using return in Scala is error-prone and should be avoided. It has no effect on anonymous functions.
- :sparkles: Constructor arguments are declared after the class name, and initialization is done in the class body.
+ :sparkles: Values and methods are assumed public by def.
- :sparkles: No fall-through to next case.
- :sparkles: match by value, type, case object field value, condition, list or tuple members, nest patterns. case-function
- :thinking_face: Accessing undefined index in structure throws exception, not returns `undefined` value as in JS.
- :thinking_face: No special syntax (square brackets) for arrays?
- :thinking_face: Implicit conversion functions: `"Retriever".breed`
	- _\[Seems implicit conversion functions are very dangerous almost like monkey-patching\]_
- Round braces are tuples.
- Object and classes can have same name: companion object for static methods.
- Case classes for immutable data storage. Auto methods: `copy()`, `equals()`, `getters`, pattern matching
- Traits: no constructor args.
- `val r = 1 to 5` - range generators

## Scala in 100 Seconds | Fireship

- https://www.youtube.com/watch?v=I7-hxTbpscU

Scalable LAnguage. 2004.

Data engineering, Apache Spark.

`for / if..else` return result.

`val` - immutable values
`var` - mutable

`Option[int]`. Option - monad. Return `None` instead of null

trait

List and most standart data structures immutable too.

First-class function.

More monads: `Either[Left, Right]`, `Try`, `Future` (like Promise in TS)

## Why no early return from lambda in Scala

### Many happy early returns – Making the matrix

- https://makingthematrix.wordpress.com/2021/03/09/many-happy-early-returns/

If / for / match as expression eliminates most need in early return.

Option is a collection which can consist of either zero or one element.

### Scala return statements in anonymous functions - Stack Overflow

- https://stackoverflow.com/questions/17754976/scala-return-statements-in-anonymous-functions

BTW, Ruby, Smalltalk, and Common Lisp (off the top of my head) also have similar "non-local" returns.

Lambdas are expressions and it's nice when an expression and all its subexpression have the same meaning no matter what the nesting structure.

The return keyword is reserved for (class) methods, it cannot be used in functions. You can easily test that

## Memory usage

:newspaper: [Memory leak in Scala application— Beginner’s guide | Medium](https://medium.com/@anasanjaria/investigating-memory-leak-in-scala-application-beginners-guide-1205b2041076)
- [benchmarks](https://github.com/kostya/benchmarks) by [kostya](https://github.com/kostya)
	- _Some benchmarks of different languages_

## Java interoperability

- :speech_balloon: [Can Scala classes be used in Java? | SO](https://stackoverflow.com/questions/44993014/can-scala-classes-be-used-in-java)

## ML

- :newspaper: [Варианты использования Java ML библиотек совместно со Spring, Docker, Spark, Rapids, CUDA | Хабр](https://habr.com/ru/articles/679248/)
- :newspaper: [ML на Scala с улыбкой, для тех, кто не боится экспериментов | Хабр](https://habr.com/ru/companies/youla/articles/452914/)

## Books

- [5 книг, с которыми анализ данных и Scala до безобразия просты](https://proglib.io/p/scala-data-analysis)

## #vs #TS (TypeScript)

- :microbe: higher memory usage
- :microbe: slow compilation
- :microbe: more strict (soundness) type system may be inconvenience. TS in unsound (Type incompatibility may be easy ignored with hacks)
- :sparkles: more stable libs
- :sparkles: more extensive standard library
- :sparkles: ML
- :sparkles: doesn't require additional libs for FP
- :sparkles: for / match / if - expressions which return result
- :sparkles: `_` in lambdas

## Scala expressive language abilities for #coding

### currying

- [Currying in Scala | Baeldung on Scala](https://www.baeldung.com/scala/currying)

Currying is the process of converting a function with multiple arguments into a sequence of functions that take one argument. Each function returns another function that consumes the following argument.

```scala
val curriedSum: Int => Int => Int = x => y => x + y
val increment: Int => Int = curriedSum(1)
```