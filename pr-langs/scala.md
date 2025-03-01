# Scala

- [ ] :tv: [Путь от монолита на PHP к микросервисам на Scala / Денис Иванов (2GIS)](https://vkvideo.ru/video-152308462_456241576)

#### Scala + #Android?

- :speech_balloon: [Any good examples of an android app written in Scala? : r/scala](https://www.reddit.com/r/scala/comments/y47zlz/any_good_examples_of_an_android_app_written_in/)
	- Scala used to be useable on Android. However, the JVM advanced and android didn't and scala stuck with the former. If I remember correctly you have to downgrade to scala 2.11 if you want to write android apps with it.
	- [Transpilers?](https://www.reddit.com/r/scala/comments/y47zlz/comment/mf3vbj4/?utm_source=share&utm_medium=web3x&utm_name=web3xcss&utm_term=1&utm_content=share_button)

- :speech_balloon: [java - Scala с Android - есть у кого-нибудь опыт? | SO на русском](https://ru.stackoverflow.com/questions/73405/scala-%D1%81-android-%D0%B5%D1%81%D1%82%D1%8C-%D1%83-%D0%BA%D0%BE%D0%B3%D0%BE-%D0%BD%D0%B8%D0%B1%D1%83%D0%B4%D1%8C-%D0%BE%D0%BF%D1%8B%D1%82)

- [scalaonandroid](https://github.com/makingthematrix/scalaonandroid) by [makingthematrix](https://github.com/makingthematrix)
	- _A tutorial and examples of how to write Android apps in Scala 2.13 and Scala 3._

#### #scripting

- [scala-cli](https://github.com/VirtusLab/scala-cli) by [VirtusLab](https://github.com/VirtusLab)
	- _Scala CLI is a command-line tool to interact with the Scala language. It lets you compile, run, test, and package your Scala code (and more!)_

# СИЛА Функционального Программирования / Всё о Scala / Интервью со Scala Developer Олегом Нижниковым / АйТиБорода, 2021

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