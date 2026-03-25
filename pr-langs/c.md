# #C

## Why I don't use C | nextmn | YT

https://www.youtube.com/watch?v=k7fHUrgvhPM

Header files. x2 files is not good for large projects.
2:20 Portability is one of strong points of C.
3:00 No centralized build system: Make, CMake, Meson, Ninja, SCons, MSBuild

## Why we still use C despite so many C alternatives / rats159 / YT, 2026.03

- https://youtube.com/watch?v=eFzkbQq2jJU

C is still running on every machine and being popular.

C appeared at 1970s. Blocks of code and lexical scoping from Algol.

1:30 Too much of undefined behavior. But every new language and every new x-platform library must be C API compatible.

3:00 C project choose C for good reason (low-level memory control). Zig, Odin, C3 are good at this too. C macros and pointer arithmetic seems simple and powerful gestures but cause problems very often.

3:40 Zig's comptime, Odin's multipointers.

4:20 You can store by yourself address and length of string in C and take new string without reallocation.

5:00 Custom allocators are powerful but huge pain when you want to integrate it with other libraries.

5:15 C lacks generics

5:40 Zig can gradually be integrated into C codebases. Maximally explicit syntax and super-fine control. Great for embedded systems.

6:00 Zig have mechanisms to act like a C. C calling convention, C-type layout.

7:00 Odin: great for line-to-line C ports. Not so great for embedded systems.

8:30 C3: perfect 2-way interop with C. Higher-level API for macros. Easiest switch from C.

10:00 C++ alternatives: Rust, Carbon, V, Num. Rust probably the best alternative because C++ devs trying to shove best Rust features into the new C++ library. But these features need to be supported at the language level
