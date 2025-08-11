# TypeScript

## Security

- :speech_balloon: [Why our company replaced Golang+GraphQL with TypeScript+Prisma+tRPC | /r/golang](https://www.reddit.com/r/golang/comments/xp0dpc/why_our_company_replaced_golanggraphql_with/), 2021
	# - Immediate_Jacket_153: TS becomes HORRIBLE to keep up to date and vulnerability free as you scale. Nothing quite like getting a Critical CVE on a package that then breaks everything in production when your minor version bump cascades 1000s of changes.
	- bmo333: Completely agree on the CVE on a package that spans hundreds of packages. Very fun to deal with.

## Types

- :speech_balloon: [I'm currently in the process of removing tRPC from our codebase. It's been a nig... | Hacker News](https://news.ycombinator.com/item?id=37100904)
	- spankalee: TypeScript is actually a great schema language and fixes a number of problems in GraphQL's SDL, especially the lack of generics.

## NodeJS platform unstability

[NX vs Turborepo? Concerned about betting on either : r/reactjs](https://www.reddit.com/r/reactjs/comments/yhzf3f/nx_vs_turborepo_concerned_about_betting_on_either/)

zambizzi: 10 years in the JS universe after first-half of my career in Enterprise Java and .NET...and can confirm. It just never seems to mature.

lars_jeppesen: Which is a good thing.

kross10000: Not really a good thing for developers and companies who just want to get stuff done and keep it around for a while without doing a rewrite every 2 years. A lot of that "innovation" is only because the baseline sucks so much on every level, from language to tooling all around, so people are constantly trying to improve it. I like to write TS + react a lot, but the constantly evolving stuff around it is a pain in the ass. No one working many years professionally with that can deny it. Basically every time I start a new project there's a bunch of new stuff which is just now en vogue, until I start my next project in 2 years.