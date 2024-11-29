# Serialize data for embedded

- 2024

- I don't like the rigidness of plain C `struct`. You add one field and deserialization of existing savegame file is broken.

- :speaking_head_in_silhouette: I want to store not `{ value1, value2, value3 }` but `{ key1: value1, key2: value2, key3: value3  }` (types of values can be arbitrary, they must be handled manually on deserialization) / [d9k](https://discord.com/channels/768759024270704641/831589248239009832/1309704497001529464)

- [easy Serialization library ? : r/cpp](https://www.reddit.com/r/cpp/comments/p9ftmk/easy_serialization_library/)

-  [schemaless-benchmarks](https://github.com/ludocode/schemaless-benchmarks?tab=readme-ov-file) by [ludocode](https://github.com/ludocode)
	- _Benchmarks for Schemaless Data Serialization Libraries_

- Embedded Synonyms: MCU, Arduino, low memory

- [ ] :newspaper: [Store multiple types in a single std::map in C++ with std::any, just like a python dict - Raymii.org](https://raymii.org/s/articles/Store_multiple_types_in_a_single_stdmap_in_cpp_just_like_a_python_dict.html)

## Serialize c++ structures

### :black_square_button: C++ 11 serializer

- [c-plus-plus-serializer](https://github.com/goblinhack/c-plus-plus-serializer?tab=readme-ov-file#user-defined-class-serialization) by [goblinhack](https://github.com/goblinhack)
	- _A minimal C++11 header only serializer. Can serialize basic types, strings, containers, maps and custom classes. No suppprt yet for pointer types._
	- [ ] I have simple probably genius idea: https://github.com/goblinhack/c-plus-plus-serializer + [custom class](https://github.com/goblinhack/c-plus-plus-serializer?tab=readme-ov-file#user-defined-class-serialization) with fields `std::map<string, int> ints`, `std::map<string, strings> strings` etc for each data type required by the game
		- [ ] Also  game version will be saved to `strings.version`  to apply migrations to savegame data.
		- [ ] Also `#define`s can be used to balance code readability, savegame binary readability and savegame size, for example `#define INTS_KEY_HEALTH 'h'`
	- :sparkles: Will work fast: native C++ with minimal overhead
	- :microbe: Just bit representation one-after-another, no keys, comments or markers to see which data piece is what.
	- :microbe: not portable
	- :sparkles: not widespread

### :black_square_button: palimpsest

- [palimpsest](https://github.com/stephane-caron/palimpsest) by [stephane-caron](https://github.com/stephane-caron)

- Serialize to and deserialize from [MessagePack](https://msgpack.org/)
- _Fast serializable C++ dictionaries_
- can be used at runtime
- New type must be declared at :open_file_folder: `src/mpack/Writer.cpp`
- smth. like Redux store
- `sudo apt install libeigen3-dev libfmt-dev libspdlog-dev`
- :speaking_head_in_silhouette: [How to remove single item from Dictionary? | issue #10 | palimpsest](https://github.com/stephane-caron/palimpsest/issues/10)
	- Seems to be fixed at [TRUEPIC/cborg](https://github.com/TRUEPIC/cborg):
- serialize vector?
- [ ] need to cut out Eigen support
- [ ] need to add for every new type code in `include/palimpsest/{json,pack}/riter.h`

### Others

- [-] [Zmeya](https://github.com/SergeyMakeev/Zmeya) by [SergeyMakeev](https://github.com/SergeyMakeev)
	- _Zmeya is a header-only C++11 binary serialization library designed for games and performance-critical applications_
	- Stores consequently in memory. Is not the case for GBC where some data goes to EWRAM
- Boost
	- [A practical guide to C++ serialization- CodeProject](https://www.codeproject.com/Articles/225988/A-practical-guide-to-Cplusplus-serialization)

## Common serialization schemaless standards

- :speech_balloon: [I was looking at MessagePack for communicating to and from my STM32F1-based micr... | Hacker News](https://news.ycombinator.com/item?id=22538710)

- событийный парсер / streaming parser

- :newspaper: [The Comprehensive Guide to YAML, JSON, TOML, HCL (HashiCorp ), XML & differences | by Sam Atmaramani | Medium](https://medium.com/@s.atmaramani/the-comprehensive-guide-to-yaml-json-toml-hcl-hashicorp-xml-differences-237ec82092ca)

### :black_square_button: MessagePack

- [MessagePack specification](https://github.com/msgpack/msgpack/blob/master/spec.md#type-system) by [msgpack](https://github.com/msgpack)
- [mpack](https://github.com/ludocode/mpack)
	- _Lightweight, suitable for embedded_
- [msgpack-mcu](https://github.com/hasegaw/msgpack-mcu) by [hasegaw](https://github.com/hasegaw)
	- _MessagePack serializer for MCUs_
- [msgpack11](https://github.com/ar90n/msgpack11) by [ar90n](https://github.com/ar90n)
	- _A tiny MessagePack library for C++11 (msgpack.org\[C++11\])_

### CBOR

- [CBOR](https://cbor.io/) - _Concise Binary Object Representation_

- :speech_balloon: [c++ - Converting `vector<char>` that contains cbor data to const char \* | SO](https://stackoverflow.com/questions/63027107/converting-vectorchar-that-contains-cbor-data-to-const-char)
- :newspaper: [SurrealDB | Understanding CBOR](https://surrealdb.com/blog/understanding-cbor)
- :scroll: [Implementations | CBOR](https://cbor.io/impls.html)
- No Schema needed
- _CBOR was originally part of the MsgPack project, by the way, before its designer forked it and renamed it after himself_
- :newspaper: [Understanding CBOR Encoded Data | dev.to](https://dev.to/mnelsonwhite/deserialising-cbor-encoded-data-in-net-5cgo)
- :newspaper: [CBOR — новый бинарный формат представления данных | Хабр](https://habr.com/ru/articles/208690/)
- :balloon: [CBOR/web (plain)](https://hildjj.github.io/node-cbor/example/index-plain.html)
- :balloon: [CBOR playground](https://cbor.me/)
- [cb0r](https://github.com/quartzjer/cb0r) by [quartzjer](https://github.com/quartzjer)
	- _Minimal Zero-Footprint CBOR Decoder in #C_
- [simple\_cbor\_stream\_parse](https://github.com/vi/simple_cbor_stream_parse) by [vi](https://github.com/vi)
	- _Simple low-level streamed callback-based CBOR push parser in C and C++_
- [cppbor](https://github.com/RantyDave/cppbor) by [RantyDave](https://github.com/RantyDave)
	- :scroll: [Implementations](https://cbor.io/impls.html)
	- _An implementation of cbor using C++ 17 variants_
	- _Being unit tested_
	- Omissions and shortcuts:
		- Maps can only use strings as keys.
		- 64 bit integers are not supported for either read or write.
		- Incoming floats can be of any width but will be coerced to a 32 bit float. Only 32 bit floats will be written.
		- Tagging is not supported (and ignored on ingestion).
	- [isode / cbor-lite — Bitbucket](https://bitbucket.org/isode/cbor-lite/src/master/)
	- [cborg](https://github.com/PelionIoT/cborg) by [PelionIoT](https://github.com/PelionIoT)
		- _Resistance is voltage divided by current._
		- :symbols: `Cbore& value(const uint8_t* unit, std::size_t length);`
		- :speaking_head_in_silhouette: [How to get keys of map? | issue #8 | cborg](https://github.com/PelionIoT/cborg/issues/8)
- [json-streaming-parser](https://github.com/squix78/json-streaming-parser/tree/master) by [squix78](https://github.com/squix78), 2017
	- _Arduino library for parsing potentially huge json streams on devices with scarce memory_
	- :sparkles: events
	- :microbe: only strings?
- [platform/system/libcppbor - Git at Google](https://android.googlesource.com/platform/system/libcppbor/)
	- :herb: 2024 still updated
	- :alembic: awesome test coverage
		- :symbols: [tests/cppbor/\_test.cpp](https://android.googlesource.com/platform/system/libcppbor/+/refs/heads/main/tests/cppbor_test.cpp)
	- [old libcppbor](https://github.com/google/libcppbor) by [google](https://github.com/google)
- [cn-cbor](https://github.com/cabo/cn-cbor) by [cabo](https://github.com/cabo)
	- _A constrained node implementation of CBOR in C_
- [Denis Tikhomirov / sjparser · GitLab](https://gitlab.com/dhurum/sjparser)
	- Streaming json parser, written on top of yajl.
	- can parse JSON data off a stream, incrementally
	- as close to "crash proof" as possible
	- generates verbose, useful error messages including context of where the error occurs in the input text.
- [QCBOR](https://github.com/laurencelundblade/QCBOR) by [laurencelundblade](https://github.com/laurencelundblade)
	- _Comprehensive, powerful, commercial-quality CBOR encoder/ decoder that is still suited for small devices._
- [libcbor](https://github.com/PJK/libcbor) by [PJK](https://github.com/PJK)
	- _CBOR protocol implementation for #C_
	- byte strings
		- [Type 2 – Byte strings — libcbor 0.8.0 documentation](https://libcbor.readthedocs.io/en/v0.8.0/api/type_2.html)
- [isode / cbor-lite — Bitbucket](https://bitbucket.org/isode/cbor-lite/src/master/)
	- 2022

### JSON

- :sparkles: very widespread
- :microbe: large size overhead
- :sparkles: human-readable
- encode binary string
	- :speech_balloon: [Binary Data in JSON String. Something better than Base64 | SO](https://stackoverflow.com/questions/1443158/binary-data-in-json-string-something-better-than-base64)
		- For download, you might be surprised how well base64 compresses under gzip (http://davidbcalhoun.com/2011/when-to-base64-encode-images-and-when-not-to)
	- [ ] multipart/form-data
	- Base91, Base93, Base122
	- Intel HEX
		- readability
	- [yEnc - Wikipedia](https://en.m.wikipedia.org/wiki/YEnc)
		- yEnc's overhead is often (if each byte value appears approximately with the same frequency on average) as little as 1–2%, (https://en.wikipedia.org/wiki/YEnc#cite_note-1) compared to 33–40% overhead for 6-bit encoding methods like uuencode (https://en.wikipedia.org/wiki/Uuencode) and Base64 (https://en.wikipedia.org/wiki/Base64).
		- [python3-yenc](https://github.com/oe-mirrors/python3-yenc) by [oe-mirrors](https://github.com/oe-mirrors)
		- [simple-yenc](https://github.com/eshaz/simple-yenc) by [eshaz](https://github.com/eshaz)
			- _Minimalist JavaScript binary string encoder / decoder with 1-2% overhead, compared to 33%-40% overhead for 6-bit encoding methods like Base64._

- [ ] [ArduinoJson](https://github.com/bblanchon/ArduinoJson) by [bblanchon](https://github.com/bblanchon)
	- _📟 JSON library for Arduino and embedded C++. Simple and efficient._
	- [Serialization tutorial | ArduinoJson 7](https://arduinojson.org/v7/tutorial/serialization/)
		- _JsonArray doesn’t hold any memory; instead, it refers to the data inside the JsonDocument. Therefore, you can only use a [JsonArray](https://arduinojson.org/v7/api/jsonarray/) if the corresponding JsonDocument is alive. Avoid returning a JsonArray from a function, because it will likely point to a destructed JsonDocument. Consider returning a JsonDocument instead._
	- [Examples | ArduinoJson 7](https://arduinojson.org/v7/example/)
	- :sparkles: STL vectors support [ArduinoJson/extras/tests/JsonVariant/stl\_containers.cpp at 7.x · bblanchon/ArduinoJson](https://github.com/bblanchon/ArduinoJson/blob/7.x/extras/tests/JsonVariant/stl_containers.cpp)
	- [ ] STL maps support?
	- :sparkles: NDJSON, JSON Lines
		- When parsing a JSON document from an input stream, ArduinoJson stops reading as soon as the document ends (e.g., at the closing brace).
		- This feature allows reading JSON documents one after the other; for example, you can use it to read line-delimited formats like NDJSON or JSON Lines.
			- `{"event":"add_to_cart"}\n{"event":"purchase"}`
	- :sparkles: [custom converters](https://arduinojson.org/news/2021/05/04/version-6-18-0/)
	- :beginner: [JsonConfigFile.ino | ArduinoJson 7](https://arduinojson.org/v7/example/config/)
		- This example shows how to store your project configuration in a file. It uses the [SD](https://www.arduino.cc/en/Reference/SD) library but can be easily modified for any other file-system, like [SPIFFS](http://arduino-esp8266.readthedocs.io/en/latest/filesystem.html).

- [jfes](https://github.com/dmitrii-eremin/jfes) by [dmitrii-eremin](https://github.com/dmitrii-eremin). #C
		- _Json For Embedded Systems (JFES)_
		- :newspaper: [Встроить JSON в Embedded? Проще простого | Хабр](https://habr.com/ru/articles/269383/)
- [jansson](https://github.com/akheron/jansson) by [akheron](https://github.com/akheron)
	- _C library for encoding, decoding and manipulating JSON data_
- [htcw\_json](https://github.com/codewitch-honey-crisis/htcw_json) by [codewitch-honey-crisis](https://github.com/codewitch-honey-crisis)
	- _a small pull parser for JSON_
	- :newspaper: [htcw\_json: A tiny streaming JSON parser- CodeProject](https://www.codeproject.com/Articles/5379857/htcw-json-A-tiny-streaming-JSON-parser)
- [ ] [json](https://github.com/nlohmann/json) by [nlohmann](https://github.com/nlohmann)
	- _JSON for Modern C++_
	- We designed the JSON class to behave just like an STL container. In fact, it satisfies the [**ReversibleContainer**](https://en.cppreference.com/w/cpp/named_req/ReversibleContainer) requirement.
	- :sparkles: Conversion from STL containers
	- :sparkles: library supports **JSON Pointer** ([RFC 6901](https://tools.ietf.org/html/rfc6901)) as alternative means to address structured values.
	- `json::diff()`
	- :sparkles: `JSON_USE_IMPLICIT_CONVERSIONS`
	- :sparkles: enum serialization helpers
	- :sparkles: [adds keys when serializing struct](https://github.com/nlohmann/json?tab=readme-ov-file#arbitrary-types-conversions)
	- :sparkles: Library supports CBOR, MessagePack
	- :sparkles: `NLOHMANN_DEFINE_TYPE_NON_INTRUSIVE` - macro to save `struct`
	- [ ] Is `.at()` fast? Does it caches keys?
	- :sparkles: `json` object assign as [nested const structure](https://github.com/nlohmann/json?tab=readme-ov-file#arbitrary-types-conversions)!
- [LightJSON](https://github.com/skyformat99/LightJSON) by [skyformat99](https://github.com/skyformat99)
	- _A Lightweight JSON CPP Library_
- [yajl](https://github.com/lloyd/yajl) by [lloyd](https://github.com/lloyd), 2015
	- _A fast streaming JSON parsing library in C._
	- [example/parse\_config.c at master · lloyd/yajl](https://github.com/lloyd/yajl/blob/master/example/parse_config.c) by [yajl](https://github.com/yajl)
- [json-parser](https://github.com/json-parser/json-parser) by [json-parser](https://github.com/json-parser)
	- _Very low footprint DOM-style JSON parser written in portable ANSI C_
- [tiny-json](https://github.com/rafagafe/tiny-json) by [rafagafe](https://github.com/rafagafe)
	- _The tiny-json is a versatile and easy to use json parser in C suitable for embedded systems. It is fast, robust and portable._
- [lwjson](https://github.com/MaJerle/lwjson) by [MaJerle](https://github.com/MaJerle)
	- _Lightweight JSON parser for embedded systems_
- [jemi: jemi](https://github.com/rdpoor/jemi) by [rdpoor](https://github.com/rdpoor)
	- _"json-emitter"_
	- _a compact, trusting, JSON serializer with static allocation in pure C for embedded systems_
	- :speech_balloon: [jemi: a compact JSON serializer for embedded systems : r/embedded](https://www.reddit.com/r/embedded/comments/xwfstn/jemi_a_compact_json_serializer_for_embedded/)
- [json11](https://github.com/dropbox/json11) by [dropbox](https://github.com/dropbox)
	- _A tiny JSON library for C++11._

- [json-stringify-safe](https://github.com/moll/json-stringify-safe/tree/master) by [moll](https://github.com/moll)
	- #JS _Like JSON.stringify, but doesn't throw on circular references_

### JSON5

- [json5](https://github.com/json5/json5) by [json5](https://github.com/json5)
	- _JSON5 — JSON for Humans_
	- [json5](https://github.com/P-i-N/json5) by [P-i-N](https://github.com/P-i-N)
		- _Header only JSON/JSON5 parser and serializer for C++_
		- :cactus: [gbooker/json5 fork](https://github.com/gbooker/json5/commits/master/)

- :newspaper: [Подробный обзор JSON, JSON5 и циклических зависимостей](https://nuancesprog.ru/p/15692/)

- :newspaper: [Understanding JSON and JSON5: A Beginner's Guide to JSON and JSON5 for Web Development](https://json-5.com/json-vs-json5)

- :speech_balloon: [Do people really use JSON5 nowadays? : r/webdev](https://www.reddit.com/r/webdev/comments/1e1a3de/do_people_really_use_json5_nowadays/)
	- There are around [~55M](https://www.npmjs.com/package/json5) weekly downloads on [npmjs.com](http://npmjs.com/), 2024
	- [json5-writer](https://github.com/noahsug/json5-writer) by [noahsug](https://github.com/noahsug)
		- #JS _Comment-preserving JSON5 parser

- [json5-spec](https://github.com/json5/json5-spec) by [json5](https://github.com/json5)
		- _The JSON5 Data Interchange Format_
		- 2018 last commit

- :speech_balloon: [\[settings\] Use JSON5 instead of JSONC for configuration files | issue #100688 | vscode](https://github.com/microsoft/vscode/issues/100688)
	- _Microsoft has provided much more robust tooling for dealing with JSONC than anything provided for the struggling JSON5 community. If Microsoft wants to help the community, please don’t stop them! Just try to do some roundtrip work with the partially abandoned JSON5 project and you will quickly find out there is absolutely no support for it._ / [brentonhouse](https://github.com/microsoft/vscode/issues/100688#issuecomment-715925440)
	- mischkl, I actually used the JSON5 project early on in some of my projects but quickly found out that it is basically a personal project that wasn't updated much. Also, unless I am missing something, I see no way of actually updating JSON5 files using their library. There was one ticket that was closed back in 2016 but it doesn't look like that feature was ever implemented. [Is there a way to do a roundtrip (load and save) · Issue #121 · json5/json5](https://github.com/json5/json5/issues/121)  - Without that, it is just a fancy way of reading JSON with comments and has little real-world practical value. If VS Code relied on using JSON5, how would the settings file get updated if you changed a setting using the GUI? / [brentonhouse](https://github.com/microsoft/vscode/issues/100688#issuecomment-715925440)

- [json5cpp](https://github.com/mortie/json5cpp) by [mortie](https://github.com/mortie)
	- _A JSON5 parser for C++ built on JsonCpp._
	- with benchmark!
	- Json5Cpp assumes, but doesn't validate, that the input is UTF-8. If the input isn't valid UTF-8, the parsed JSON tree won't necessarily be valid UTF-8. Use a separate UTF-8 validation library if that's a problem
	- only parsing?!
		- :speech_balloon: [Serialization to JSON5? | issue #2 | json5cpp](https://github.com/mortie/json5cpp/issues/2)
		- fgrthth

- [packages depending on json5](https://www.npmjs.com/browse/depended/json5)

### JSON flavours

- [jsobject](https://github.com/tmarrinan/jsobject) by [tmarrinan](https://github.com/tmarrinan)
	- :fallen_leaf: 2017
	- _JavaScript Object Interface for C++ (Including JSON Parser / Generator)_
	- [test input example](https://github.com/tmarrinan/jsobject/blob/master/example/resrc/json5_eg.json)

- [smile-format-specification](https://github.com/FasterXML/smile-format-specification) by [FasterXML](https://github.com/FasterXML)
	- _is a binary data format that defines a binary equivalent of standard_
- [Jsonlite - JSON without quotes](https://deerchao.cn/projects/jsonlite/)
- [jsonc](https://github.com/komkom/jsonc) by [komkom](https://github.com/komkom)
	- #Go _json like config with comments._
	- 2021 last commit

- [-] [Hjson, a user interface for JSON](https://hjson.github.io/)
	- don't like that quotes for values are unnecessary. It makes parsing with eyes harder

### :black_square_button: tser

- [tser](https://github.com/KonanM/tser) by [KonanM](https://github.com/KonanM)
- _tser - tiny serialization for C++_
- :microbe: No support for `std::variant` (unless trivially copyable)
- :microbe: No support for `std::stack`, `std::priority_queue`, `std::string_view`

### :black_square_button: bitsery

- [bitsery](https://github.com/fraillt/bitsery) by [fraillt](https://github.com/fraillt)

- _Your binary serialization library_
- x3 faster then messagepack
- [Motivation](https://github.com/fraillt/bitsery/blob/master/doc/design/README.md)
	- I wanted serializer that is easy to use as [cereal](http://uscilab.github.io/cereal/), is cross-platform compatible, and has support for forward/backward compatibility like [flatbuffers](https://google.github.io/flatbuffers/), is safe to use with untrusted (malicious) data, and most importantly is fast and has a small binary footprint.
	- Furthermore, I wanted full serialization control and the ability to work on a bit level, so I can further reduce data size.

### :black_square_button: binn

- [binn](https://github.com/liteserver/binn) by [liteserver](https://github.com/liteserver)
- :sparkles: The elements are stored with their sizes to increase the read performance.
- :sparkles: simple implementation, minimal overhead
- :sparkles: no intermediate data trees in memory, just writing
- :microbe: all by self
- #C
- _Binary Serialization_
	- bytes array?
		- list of `BINN_INT8`
		- binn_list_int8

### NoProto


- [10x Faster Than BSON: NoProto : r/rust](https://www.reddit.com/r/rust/comments/kdxenz/10x_faster_than_bson_noproto/)
- [NoProto](https://github.com/only-cliches/NoProto) by [only-cliches](https://github.com/only-cliches)
	- _Flexible, Fast & Compact Serialization with RPC_
	- NoProto combines the **performance** of compiled formats with the **flexibilty** of dynamic formats
	- NoProto is a **key-value database focused format**:
	- Schemas are dynamic at runtime, no compilation step

### HCL

- HashiCorpLanguage

- :speech_balloon: [Multi-line string | issue #34 | hcl](https://github.com/hashicorp/hcl/issues/34)
- :newspaper: [Mastering HashiCorp Configuration Language: A Practical Guide to HCL for Infrastructure Automation | by Warley's CatOps | Medium](https://medium.com/@williamwarley/mastering-hashicorp-configuration-language-a-practical-guide-to-hcl-for-infrastructure-automation-cd1adb0d46c0)

### TOML

- :door: [TOML: Tom's Obvious Minimal Language](https://toml.io/en/)

- :speech_balloon: [Is there a version of a TOML parser for Arduino? | issue #82 | toml11](https://github.com/ToruNiina/toml11/issues/82)

- :speech_balloon: [python - TOML vs YAML vs StrictYAML | SO](https://stackoverflow.com/questions/65283208/toml-vs-yaml-vs-strictyaml)
	- TOML's main semantic difference is that it doesn't support cycles, complex keys, or tags.
	- A different kind of simplicity TOML offers its syntax: Since it is vastly simpler than YAML, it is easier to emit errors users can understand. For example, a common error text in YAML syntax errors is „mapping values are not allowed in this context“ (try searching this on SO to find tons of questions). You get this for example here:

- :speech_balloon: [json - Does TOML support nested arrays of objects/tables? | SO](https://stackoverflow.com/questions/48998034/does-toml-support-nested-arrays-of-objects-tables)
- :newspaper: [What is wrong with TOML? - HitchDev](https://hitchdev.com/strictyaml/why-not/toml/)
	- In [this example of a StrictYAML story](https://github.com/crdoconnor/strictyaml/blob/master/hitch/story/map.story) and its [equivalent serialized TOML](https://github.com/crdoconnor/strictyaml/blob/master/hitch/story/map.toml) the latter ends up [spending](https://www.goodreads.com/quotes/775257-my-point-today-is-that-if-we-wish-to-count) 50% more characters to represent the exact same data
	- Dates and times, as many more experienced programmers are probably aware is an unexpectedly deep rabbit hole of [complications and quirky, unexpected, headache and bug inducing edge cases](https://infiniteundo.com/post/25326999628/falsehoods-programmers-believe-about-time).
	- The best way to deal with [essential complexity](https://simplicable.com/new/accidental-complexity-vs-essential-complexity) like these is to decouple, isolate the complexity and delegate it to a [specialist tool that is good at handling that specific problem](https://en.wikipedia.org/wiki/Unix_philosophy) which you can swap out later if required.

- :speech_balloon: [Allow hexadecimal, binary and octal integer representations | issue #53 | toml](https://github.com/toml-lang/toml/issues/53)

- :scroll: [Implementations | toml Wiki](https://github.com/toml-lang/toml/wiki#toml-v100)

- :alembic: [toml-test/tests](https://github.com/toml-lang/toml-test/tree/master/tests/valid)

### INI flavours

- [LeksysINI](https://github.com/Lek-sys/LeksysINI) by [Lek-sys](https://github.com/Lek-sys)
	- _Crossplatform all-in-one INI-file parser, written on C++ with STL. Supports subsections, multiline values, arrays, maps and file inclusions._
	- almost like TOML
	- :sparkles: comments, multilines, arrays, maps, subsections and inclusions

- [Ini Subsections? - AutoIt General Help and Support - AutoIt Forums](https://www.autoitscript.com/forum/topic/193222-ini-subsections/)

### StrictYAML

- :speech_balloon: [python - TOML vs YAML vs StrictYAML | SO](https://stackoverflow.com/questions/65283208/toml-vs-yaml-vs-strictyaml)
	- with StrictYAML, you do not need to care about the billion laughs attack (https://en.wikipedia.org/wiki/Billion_laughs_attack) that haunts some YAML implementations.
	- supports a validating schema. Also hierarchical data syntax is more obvious, therefore less discouraged. A bit more powerful and better for larger files

### :no_entry_sign: BSON

- [bson-cxx](https://github.com/dwight/bson-cxx) by [dwight](https://github.com/dwight)
	- _C++ BSON Library_
	- [Explaining BSON With Examples | MongoDB](https://www.mongodb.com/resources/languages/bson)
		- :microbe: JSON data is slightly smaller in byte size. BSON data is slightly larger in byte size.
	- [ardubson](https://github.com/argandas/ardubson) by [argandas](https://github.com/argandas)
		- _Lightweight BSON Library for Arduino_

### :no_entry_sign: YAML

- [YAMLDuino](https://github.com/tobozo/YAMLDuino) by [tobozo](https://github.com/tobozo)
	- _YAML <=> JSON converter for ESP32, ESP8266, RP2040 and possibly other devices_

- :sparkles: very human-readable
- :microbe: too verbose for small memory
- [Binary Data Language-Independent Type for YAML™ Version 1.1](https://yaml.org/type/binary.html)
	- just BASE64
		- [yEnc - Wikipedia](https://en.wikipedia.org/wiki/YEnc)
			- The yEnc homepage states that "_all major newsreaders have been extended to yEnc support_"
			- yEnc assumes that binary data mostly can be transmitted through Usenet and email. Therefore, 252 of the 256 possible bytes are passed through unencoded as a single byte. Only NUL, LF, CR, and = are escaped.

- :speech_balloon: [python - TOML vs YAML vs StrictYAML | SO](https://stackoverflow.com/questions/65283208/toml-vs-yaml-vs-strictyaml)
	- YAML's outstanding semantic feature is that it can represent a possibly cyclic graph. Moreover, YAML mappings can use complex nodes (sequences or mappings) as keys. These features are what you potentially need when you want to represent an arbitrary data structure.
	- I see indentation for structuring as interesting but ultimately flawed concept (not just for YAML, also for Python or Nim). Without a visible token that ends a structure, code gets more difficult to read the more nesting it has and the longer it is.

## Database/key-value store?

- [A Glimpse into the World of Embedded Database Feat. RocksDB | by Kartik Khare | Walmart Global Tech Blog | Medium](https://medium.com/walmartglobaltech/https-medium-com-kharekartik-rocksdb-and-embedded-databases-1a0f8e6ea74f)
- :newspaper: [Picking a Database for Embedded Systems | dev.to](https://dev.to/objectbox/embedded-databases-what-is-an-embedded-database-and-how-to-choose-one-27m8)
- :speech_balloon: [A Key Value Store for Embedded Devices ? - Any recommendations ? : r/embedded](https://www.reddit.com/r/embedded/comments/jo3wmz/a_key_value_store_for_embedded_devices_any/)

### BerkleyDB

- :speech_balloon: [For anyone thinking Berkeley DB, because it has transactions and logging, is a g... | Hacker News](https://news.ycombinator.com/item?id=10150394)
	- Its tools are crap: it can't tell you how big a database is without traversing every single entry, they hold locks while writing to the terminal (meaning you can't pipe them into a pager without freezing the whole DB), and if one of them crashes (due to e.g. a dropped SSH connection) they'll bring down the whole DB due to stale locks.
	- [Berkeley DB - Wikipedia](https://en.m.wikipedia.org/wiki/Berkeley_DB)
		- embedded database software library for key/value data

### SQLite

- :speech_balloon: [For anyone thinking Berkeley DB, because it has transactions and logging, is a g... | Hacker News](https://news.ycombinator.com/item?id=10150394)
	- And my sympathy to anyone who tries to run SQLite on this bad boy… combined with SQLite's shoddy track record interpreting any query more complicated than a key-value lookup, it would be a wonder if you're able to get any data in and out intact.
- :speech_balloon: [database - Sqlite on an embedded system | SO](https://stackoverflow.com/questions/178264/sqlite-on-an-embedded-system), 2008
	- _The smallest sqlite3 I came up with was 327 KBytes (for PowerPC), which was sufficient for the system so I stopped trying to make it smaller. This was the full sqlite3 CLI binary, the C APIs alone would have been somewhat smaller. I had set `SQLITE_OMIT_AUTHORIZATION`, `SQLITE_OMIT_EXPLAIN`, `SQLITE_OMIT_PROGRESS_CALLBACK`, and `SQLITE_OMIT_TCL_VARIABLE` to trim the size of the binary, and used `-Os`to get it to that size._
- [SQLite Library Footprint](https://www.sqlite.org/footprint.html)
- [In-Memory Databases](https://www.sqlite.org/inmemorydb.html)

### Others

- [sophia](https://github.com/pmwkaa/sophia) by [pmwkaa](https://github.com/pmwkaa)
	- _Modern transactional key-value/row storage library._

- [ostore](https://github.com/woodsmc/ostore) by [woodsmc](https://github.com/woodsmc)
	- _Simple Object Storage_

- [RocksDB | A persistent key-value store | RocksDB](https://rocksdb.org/)

## Common standarts with schema?

- FlatBuffers?
	- [FlatBuffers: Tutorial](https://flatbuffers.dev/flatbuffers_guide_tutorial.html)

- Protocol Buffers?
	- [nanopb](https://github.com/nanopb/nanopb) by [nanopb](https://github.com/nanopb)
		- _Protocol Buffers with small code size_
