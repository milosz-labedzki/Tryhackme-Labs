* `ASCII` - A 7-bit character encoding standard that assigns numerical values (0–127) to basic English letters, numbers, punctuation marks, and system control codes.

* `Unicode` - A universal character encoding standard that assigns a unique numerical code point to every character, symbol, and script used across computing platforms and languages worldwide.

* `UTF-8` - A variable-width character encoding for Unicode that represents characters using one to four 8-bit bytes, maintaining full backward compatibility with ASCII and serving as the default web encoding standard.

* `UTF-16` - A variable-width character encoding for Unicode that uses one or two 16-bit code units (2 or 4 bytes) per code point, commonly used internally by operating system runtimes and environments like Windows, Java, and JavaScript.

* `UTF-32` - A fixed-width character encoding for Unicode that allocates exactly 32 bits (4 bytes) to every code point, offering simplified direct array indexing at the cost of significantly higher memory consumption.

* `How emoji is encoded` - Emojis are assigned distinct Unicode code points—often chained together using Zero Width Joiner (ZWJ) control characters to modify modifiers, skin tones, or combinations—which are then serialized into binary storage using standard encodings like UTF-8 or UTF-16.
