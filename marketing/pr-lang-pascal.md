# Marketing: Pascal

## In programming languages, why has C prevailed over Pascal? - Quora

https://www.quora.com/In-programming-languages-why-has-C-prevailed-over-Pascal

C “succeeded” Pascal because systems languages and hardware advances were the big deal in the last decades of the last century and up to the internet age. C filled the need for rapid hardware/software hybrid language better for industrial applications and for writing Operating Systems. Pascal is still around and used A LOT around the world and modern pascal compilers have ll the bells and whistles of Object Orientation, IDEs, Graphics, Game Engines, all that stuff.

Alec Cawley: Pascal, as designed by Wirth, was an incomplete language. It was designed for teaching, and did not include many things essential for a production language. For example, it had no facilities for separate compilation of modules and user defined libraries. And no facilities for accessing the hardware. So every Pascal compiler had to invent its own set - which they did, incompatibly. Whereas C was designed from the very start for a large project which accessed the hardware (Unix). Pascal was more elegant - but incomplete. A theoreticians solution. C was less elegant - but pragmatic. An engineers solution.

Dave Hansen: side projects I tried using Pascal on invariably were disappointing or outright failures. Pascal is a teaching language. It guides you into good habits and behaves reasonably when you make a mistake. C is a lousy teacher. It will give you enough rope to shoot yourself in the foot, spank you hard if you make a mistake, and may not even tell you what you did wrong. But C is a language for getting things done.

Levi Pearson: No one has mentioned it yet, but the strongest reason that C succeeded in the market over Pascal and other similar competitors was its unique position as the implementation language of Unix. Two things happened from the mid-70s to the mid-80s. Most universities doing any computing courses purchased Unix licenses (which included full source code) and began organizing coursework around it.  Both C and Unix were designed with portability in mind (partly by design, and partly by necessity) which allowed them to run on whatever machines were available, including cheap ones.