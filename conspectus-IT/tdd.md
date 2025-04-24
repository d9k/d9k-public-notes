# TDD

## TDD is dead. Long live testing. (DHH)

- https://dhh.dk/2014/tdd-is-dead-long-live-testing.html

 rarely unit test in the traditional sense of the word, where all dependencies are mocked out, and thousands of tests can close in seconds. It just hasn't been a useful way of dealing with the testing of Rails applications. I test active record models directly, letting them hit the database, and through the use of fixtures.

## Why Most Unit Testing is Waste

- https://gist.github.com/ktzar/596ee5aae7c41f2e585331e4b71d1e2c

By James O Coplien from http://rbcs-us.com/documents/Why-Most-Unit-Testing-is-Waste.pdf

### Into Modern Times

Unit testing was a staple of the FORTRAN days, when a function was a function and was sometimes worthy of functional testing.

The design units changed from things-that-computed to small heterogeneous composites called objects that combine several programming artefacts, including functions and data, together inside one wrapper.

The exact function to be called is determined at run-time.

That made it impossible to reason about run-time behaviour of code by inspection alone. You had to run the program to get the faintest idea of what was going on. So, testing became in again.

Design became much more data-focused because objects were shaped more by their data structure than by any properties of their methods.

So integration testing was out; unit testing was in.

CRC cards (popularly representing Classes, Responsibilities, and Collaborators) were a popular design technique where each class was represented by a person. Object orientation became synonymous with anthropomorphic design.

### The Cure is Worse than the Disease

To do complete testing, the number of lines of code in unit tests would have to be orders of magnitude larger than those in the unit under test.

### Tests for their Own Sake and Designed Tests

One brute-force attack on this problem is to run tests continuously. People confuse automated tests with unit tests: so much so that when I criticise unit testing, people rebuke me for critising automation. If you write a test to cover as many possibilities as possible you can dedicate a rack of machines to running the tests 24 hours a day, 7 days a week, tracking the most recent check-in.

Do formal boundary-condition checking, more white-box testing, and so forth. That requires that the unit under test be designed for testability. This is how hardware engineers do it: designers provide "test points" that can read out values on a J-Tag pin of a chip, to access internal signal values of the chip.

### The Belief that Tests are Smarter than Code

Software engineering research has shown that the most costeffective places to remove bugs are during the transition from analysis to design, in design itself, and in the disciplines of coding. It's much easier to avoid putting bugs in than to take them out.

If the probability of the test passing is 100%, then there is no information — by definition, from information theory.

### Low-Risk Tests Have Low (even potentially negative) Payoff

Don’t underestimate the intelligence of your people, but don’t underestimate the collective stupidity of many people working together in a complex domain.

One question to ask about every test is: If this test fails, what business requirement is compromised?

The test does have a cost: maintenance, computing time, administration, and so forth. The test could have net negative value. That is the fourth category of tests to remove. These are tests which, though they may even do some amount of verification, do no validation.

### Complex Things are Complicated

So a test may pass 99.99% of the time but the one test in ten thousand that fails kills you.

Again, borrowing from the hardware world, you can design for a given probability of failure or you can do worst-case analysis (WCA) to reduce the probability of failure to arbitrarily low levels. Hardware people typically use WCA during asynchronous system design to guard against “glitches” in signal arrivals that wander outside the design parameters one in every 100 million times. In hardware, such a module would be said to have a FIT rate of 10 — ten Failures In a Trillion.

In object-orientation it is impossible to know, for a given use of some state value within a program, what instruction last modified that state.

### Less is More, or: You are Not Schizophrenic

The naïve tester will try to tease data from the tails by keeping all the tests around or even by adding more tests; that leads exactly to the situation my client found himself in, with more complexity (or code mass or choose-your-favourite-measure) in the tests than in the code. The classes he was testing are code. The tests are code. Developers write code. When developers write code they insert about three system-affecting bugs per thousand lines of code.

Watch what your developers do when running a test suite: they’re doing, not thinking (like most of the Agile Manifesto, by the way).

### You Pay for Tests in Maintenance — and Quality!

Janzen and Saledian, “Does Test-Driven Development Really Improve Software Design Quality?” IEEE Software 25(2), March/April 2008, pp. 77 - 84.)

When I look at most unit tests — especially those written with JUnit — they are assertions in disguise. When I write a great piece of software I sprinkle it with assertions that describe promises that I expect the callers of my functions to live up to, as well as promises that function makes to its clients. Those assertions evolve in the same artefact as the rest of my code. Most environments have provisions to administratively neuter those assertions when you ship.

An even more professional approach is to leave the assertions in the code when you ship, and to automatically file a bug report on behalf of the end user and perhaps to try to re-start the application every time an assertion fails.

Turn unit tests into assertions. Use them to feed your fault-tolerance architecture on high-availability systems.

Create system tests with good feature coverage (not code coverage) — remembering that proper response to bad inputs or other unanticipated conditions is part of your feature set.

### Green Bar Fever

There are two potential goals in testing. One is to use it as a learning tool: to learn more about the program and how it works. The other is as an oracle.

### Wrapup

Don’t forget the Product Owner perspective in Scrum or the business analyst or Program Manager: risk management is squarely in the center of their job, which may be why Jeff Sutherland says that the PO should conceive (and at best design) the system tests as an input to, or during, Sprint Planning.

- Keep unit tests that test key algorithms for which there is a broad, formal, independent oracle of correctness, and for which there is ascribable business value.

- If you can text X with either a system test or a unit test, use a system test — context is everything.

- Turn most unit tests into assertions.

- Be humble about what tests can achieve. Tests don’t improve quality: developers do.