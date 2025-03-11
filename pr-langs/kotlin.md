# Kotlin

## Learn Kotlin in Y Minutes

- https://learnxinyminutes.com/kotlin

- `when` - замена switch..case / match..case
- `when`, `if` - выражения, возвращающие значение
	- `in 1..100`

## #vs #Scala

- :newspaper: [A Comparison Between Kotlin and Scala | Baeldung](https://www.baeldung.com/kotlin/kotlin-vs-scala)
	- covariant and contravariant generic types
	- :sparkles: The default visibility modifier in Kotlin is _public_
	- :sparkles: инициазация классов как в Scala
			- secondary constructors in Kotlin, but they must delegate to the primary constructor:
	- :sparkles: Kotlin also treats functions as its first-class citizens
	- :sparkles: Kotlin has `inline` keyword for functions. Define `fun` inside another `fun`
	- :sparkles: Illegal `null` assignment. `?` at the end of type required to accept `null` assignment
		- `val x: String? = null`
		- `println(x?.length)`
	- :sparkles: curried functions support
	- :sparkles: easier case classes alternative
		- `data class MailOrder {...}`
		- `when(order) { is MailOrder -> { ...`
	- :microbe: A class is final in Kotlin by default. `open` keyword
	- :microbe: `companion object`
	- `data` classes

- :newspaper: [Kotlin или Scala: что выбрать для разработки приложения в 2025?](https://chillicode.agency/blog/kotlin-vs-scala-razlichiya#kotlin-vs-scala-kratkoe-opisanie-klyuchevyh-razlichiy)

- более быстрая компиляция, чем у Scala
- Scala, как правило, известна своей более развитой системой типов, которая поддерживает сложные типы, самоопределяющиеся типы, неявные параметры и др.
- хорошая поддержка Android-разработки