# Haxe

## I think the one downside of Haxe (which is also is strength) is that it doesn’t ... | HN

https://news.ycombinator.com/item?id=18090164

logimame: I think the one downside of Haxe (which is also is strength) is that it doesn’t only support compiling to C/C++, but to every major language possible (Java, C#, PHP, Javascript), so the language ends up being too complex. You constantly have to think about how the languages features will map to your target language if you care about performance, which can be pretty unintuitive. And the C++ target (hxcpp) is quite heavyweight and takes a lot of time to compile (at least the last time I checked out). Also C interop doesn’t seem that convenient.

But I still have some hope on Haxe, because the main developer is working on [Hashlink](https://hashlink.haxe.org/), which can run Haxe code on a virtual machine but can also transpile it to C for production builds... It seems a more simple and “focused” Haxe target that doesn’t have all the warts of hxcpp...

