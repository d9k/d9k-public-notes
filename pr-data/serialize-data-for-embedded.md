# Serialize data for embedded

- 2024

- I don't like the rigidness of plain C `struct`. You add one field and deserialization of existing savegame file is broken.

- :speaking_head_in_silhouette: I want to store not `{ value1, value2, value3 }` but `{ key1: value1, key2: value2, key3: value3  }` (types of values can be arbitrary, they must be handled manually on deserialization) / [d9k](https://discord.com/channels/768759024270704641/831589248239009832/1309704497001529464)

- [easy Serialization library ? : r/cpp](https://www.reddit.com/r/cpp/comments/p9ftmk/easy_serialization_library/)

-  [schemaless-benchmarks](https://github.com/ludocode/schemaless-benchmarks?tab=readme-ov-file) by [ludocode](https://github.com/ludocode)
	- _Benchmarks for Schemaless Data Serialization Libraries_

- Embedded Synonyms: MCU, Arduino, low memory

- :newspaper: [Store multiple types in a single std::map in C++ with std::any, just like a python dict - Raymii.org](https://raymii.org/s/articles/Store_multiple_types_in_a_single_stdmap_in_cpp_just_like_a_python_dict.html)

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

### :black_square_button: MessagePack

- [mpack](https://github.com/ludocode/mpack)
	- _Lightweight, suitable for embedded_
- [msgpack-mcu](https://github.com/hasegaw/msgpack-mcu) by [hasegaw](https://github.com/hasegaw)
	- _MessagePack serializer for MCUs_

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

### JSON flavours

- [smile-format-specification](https://github.com/FasterXML/smile-format-specification) by [FasterXML](https://github.com/FasterXML)
	- _is a binary data format that defines a binary equivalent of standard_
- [Jsonlite - JSON without quotes](https://deerchao.cn/projects/jsonlite/)

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

### :no_entry_sign: BSON

- [bson-cxx](https://github.com/dwight/bson-cxx) by [dwight](https://github.com/dwight)
	- _C++ BSON Library_
	- [Explaining BSON With Examples | MongoDB](https://www.mongodb.com/resources/languages/bson)
		- :microbe: JSON data is slightly smaller in byte size. BSON data is slightly larger in byte size.
	- [ardubson](https://github.com/argandas/ardubson) by [argandas](https://github.com/argandas)
		- _Lightweight BSON Library for Arduino_

### :no_entry_sign: YAML

- :sparkles: very human-readable
- :microbe: too verbose for small memory
- [Binary Data Language-Independent Type for YAML™ Version 1.1](https://yaml.org/type/binary.html)
	- just BASE64
		- [yEnc - Wikipedia](https://en.wikipedia.org/wiki/YEnc)
			- The yEnc homepage states that "_all major newsreaders have been extended to yEnc support_"
			- yEnc assumes that binary data mostly can be transmitted through Usenet and email. Therefore, 252 of the 256 possible bytes are passed through unencoded as a single byte. Only NUL, LF, CR, and = are escaped.

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
