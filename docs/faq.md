# SIL Private Use Area - Frequently Asked Questions

<- [Back to Intro](https://github.com/silnrsi/silpua/) 

Authors: Kent Spielmann, Lorna Evans, Bob Hallissy

This document provides answers to frequently asked questions about SIL’s Private Use Area (PUA). To view the complete text of each question and answer, click the question.



**Note**:
For a greater understanding of Unicode and the PUA, the [Unicode](https://www.unicode.org/faq/) site may be of further interest.

### *What is the PUA?*

The [Private Use Area](https://scripts.sil.org/Glossary#pua) (PUA) is a range of [Unicode](https://scripts.sil.org/Glossary#unicode) [codepoints](https://scripts.sil.org/Glossary#codepoint) (E000 - F8FF and [planes](https://scripts.sil.org/Glossary#plane) 15 and 16) that are reserved for private definition and use within an organisation or corporation for creating proprietary, non-standard character definitions. This might include use by software developers and end users who need a special set of characters for their own purposes. There are 6400 PUA code points (128K) available in the [Basic Multilingual Plane](https://scripts.sil.org/Glossary#bmp). Although this may seem like a lot, this “code space” needs to be managed so that the available code points do not run out in the long term.

The PUA range in the [Basic Multilingual Plane](https://scripts.sil.org/Glossary#bmp) is from U+E000 to U+F8FF. In addition, Unicode reserves the so-called “[supplementary planes](https://scripts.sil.org/Glossary#supplement)” 15 (U+F0000–U+FFFFF) and 16 (U+100000–U+10FFFF) for private use.

### *What are Unicode codepoints?*

[Dodepoints](https://scripts.sil.org/Glossary#codepoint) are similar to ASCII numbers used to represent symbols and characters found in the writing systems of languages throughout the world. Instead of having just 256 different symbols available, the [Basic Multilingual Plane](https://scripts.sil.org/Glossary#bmp) uses 65,536 code values (64K). By convention, code points are usually represented by 4 hexadecimal digits to represent the 64K different characters. For example, U+E000 represents the code value at E000 (decimal 57,344) which is the lowest number in the [PUA](https://scripts.sil.org/Glossary#pua) range.

Moreover, Unicode also assumes smart font technology in the software which uses it. This means that Unicode only needs to assign one codepoint for letters and symbols which may vary depending on context. For example, smart fonts will place an accent on a letter in the proper place, be it on a lower or uppercase, wide or thin letter. It will even use a _dotless i_ (or other letter variant) when appropriate.

Codepoints in the 16 [Supplementary planes](https://scripts.sil.org/Glossary#supplement) may be represented using 5 or 6 hexadecimal digits. For example, the lowest codepoint in supplementary plane 15 is U+F0000, and the lowest codepoint in plane 16 is U+100000. 

The supplementary planes are not used in the current version of Unicode but have been provided for for future extensions. The [SIL PUA Strategy](https://scripts.sil.org/PUA_Corp) does include using the PUA supplementary planes for cross mapping between various entity allocations in the [Basic Multilingual Plane](https://scripts.sil.org/Glossary#bmp) PUA area. 


### *What is SIL’s PUA assignment strategy?*

SIL corporation-wide PUA usage uses the codepoint range U+F100–U+F8FF. Individual SIL field entities might also make independent PUA character assignments in the range U+E000–U+EFFF. 

SIL’s corporate strategy is based on [PUA Corporate Strategy](https://scripts.sil.org/PUA_Corp). This document is no longer kept up-to-date as SIL is no longer adding characters to the PUA.


### *What are SIL’s PUA assignments?*

The [SIL PUA](..\README.md) allows local SIL entities to make free use of the lower portion of the PUA range, U+E000–U+EFFF, while the upper portion, U+F100–U+F8FF, is reserved and managed for corporation-wide use.

The **SIL PUA committee** (no longer functioning) publishes [SIL Private Use Area - Assignments](pua-assignments.md) documentation on approved assignments of characters to Corporate-controlled portions of the PUA.

The following table shows how Unicode private-use character assignments are arranged within the SIL corporate-wide portion of the PUA.

See [SIL Private Use Area - Assignments](pua-assignments.md) for a table listing our roadmap.

### *How do I add characters to my entity block?*

First, check thoroughly that your character is not already in [Unicode](https://www.unicode.org) (See [collation charts](https://www.unicode.org/charts/collation/) or [charts](https://www.unicode.org/charts) ) or within [SIL Private Use Area - Assignments](pua-assignments.md).  Second, if you do not find a suitable character contact your entity Unicode representative. 

### *How do I submit characters for inclusion in the SIL corporate PUA (the corporation-wide block)?*

The SIL PUA committee is no longer accepting submissions.


### *What is the relationship between SIL’s PUA Committee and the UTC? Is there any conflict between this strategy and the Unicode guidelines?*

There was never an official relationship between the SIL PUA Committee and the UTC. The SIL PUA Committee operated within the guidelines as described in the “Private Use Area: U+E000–U+F8FF” section of [Special Areas and Format Characters](https://www.unicode.org/versions/latest/ch23.pdf#G19184) Unicode Consortium. 2022 _The Unicode Standard_.

<- [Back to Intro](https://github.com/silnrsi/silpua/) 

-> [Forward to A strategy for deprecating SIL PUA characters](pua-deprecation-strategy)
