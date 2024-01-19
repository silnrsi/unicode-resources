---
title: Representing Tifinagh in Unicode - Unicode Technical Note (proposed draft)
---

_Lorna Evans, SIL International (18-Jan-2024)_

Opentype tags
**Berber 	'BBR ' 	ber, cnu, jbe, jbn, mzb, oua, sds, shy, sjs, swn, tia, tjo**


- <a href="#intro">Introduction</a>
- <a href="#uni">The Unicode Model</a>
   - <a href="#cons">Basic Consonants</a>
   - <a href="#vowel">Vowels</a>
   - <a href="#punct">Punctuation</a>
   - <a href="digits">Digits</a>
   - <a href="#variant">Variant Glyphs</a>
   - <a href="#bicons">Bi- Tri-Consonants</a>
  - <a href="#contexual">Contextual Shaping</a>
  - <a href="#dir">Writing Direction</a>
- <a href="#resource">Resources</a>
  - <a href="#key">Keyboarding</a>
  - <a href="#font">Fonts</a>
- <a href="#neo">Languages Using Neo-Tifinagh script</a>
  - <a href="#tzm_zgh">Central Atlas Tamazight, Standard Moroccan Tamazight &#x005B;tzm&#x005D; &#x005B;zgh&#x005D;</a>
  - <a href="#kab">Kabyle, Amazigh &#x005B;kab&#x005D;</a>

- <a href="#trad">Languages Using Traditional Tifinagh script</a>
  - <a href="#gho">Ghomara, Shilha &#x005B;gho&#x005D;</a>
  - <a href="#rif">Tarifit, Riffian &#x005B;rif&#x005D;</a>
  - <a href="#shi">Tachelhit &#x005B;shi&#x005D;</a>
  - <a href="#siz">Siwi &#x005B;siz&#x005D;</a>
  - <a href="#taq">Tamasheq &#x005B;taq&#x005D;</a>
  - <a href="#thv">Tahaggart Tamahaq &#x005B;thv&#x005D;</a>
  - <a href="#thz">Tamajeq, Tayart &#x005B;thz&#x005D;</a>
  - <a href="#ttq">Tawallammat Tamajaq &#x005B;ttq&#x005D;</a>

- <a href="#work">Still working on - confusing sources

  - <a href="#kab_etc">Taqbaylit, Tumzabt, Tacenwit, Tacawit, Tamahaq (Neo-Tifinagh in Algeria), Tahaggart Tamahaq, Tachawit, Tachelhit, Tumzabt &#x005B;kab&#x005D; &#x005B;mzb&#x005D; &#x005B;shi&#x005D; &#x005B;shy&#x005D; &#x005B;thv&#x005D;</a>
  - <a href="#thz_a">Tuareg (Aïr dialect of Niger) &#x005B;thz&#x005D;</a>
  - <a href="#tda">Tuareg (Azawagh dialect of Niger-Mali), Tagdal &#x005B;tda&#x005D;</a>
  - <a href="#ttq_tmh">Tawallammat Tamajaq, Tamashek &#x005B;ttq&#x005D; &#x005B;tmh&#x005D;</a>
- <a href="#other">Other languages with no information</a>
  - <a href="#auj">Awjilah &#x005B;auj&#x005D;</a>
  - <a href="#gha">Ghadamès &#x005B;gha&#x005D;</a>
  - <a href="#nxm">Numidian &#x005B;nxm&#x005D;</a>
  - <a href="#grr">Taznatit &#x005B;grr&#x005D;</a>
  - <a href="#tez">Tetserret &#x005B;tez&#x005D;</a>
  - <a href="#zen">Zenaga &#x005B;zen&#x005D;</a>
- <a href="#ref">References</a>

## <a id="intro"></a>Introduction

Tifinagh is encoded in the U+2D30..U+2D7F block of Unicode.

This document aims to give guidance on the encoding of text using the Tifinagh script. Since the script is used for a number of orthographies covering different languages, the development of this document is ongoing. It aims to bring together the results of consensus between experts in the encoding of the various orthographies using the script. In terms of the Unicode standard, this document is purely informative since it is concerned with issues not covered by that standard. 

This document also aims to give guidance on font development for the different orthographies and languages.

**To Add**

- Perhaps include transliteration. where known.

- Perhaps sort orders, where known.

## <a id="uni"></a>The Unicode Model

### <a id="cons"></a>Basic Consonants

The basic consonants are relatively obvious and can be discovered by viewing the Unicode charts.

**Design**: There can be some design issues related to "dotted" characters especially when the design is similar. When these characters appear together, they can be difficult to read unless care is taken to change the size or spacing of the dots: <span class='akatab normal'>&#x2D30;&#x2D53;&#x2D3E;&#x2D46;&#x2D58;&#x2D30;</span>. The Neotifinagh design does not have as significant an issue: <span class='nototif normal'>&#x2D30;&#x2D53;&#x2D3E;&#x2D46;&#x2D58;&#x2D30;</span>

### <a id="vowel"></a>Vowels

Vowels are not as clearly defined. Neo-Tifinagh does not have any special vowels. However, different traditional Tifinagh orthographies may demonstrate vowels using combining marks in different ways. These vowels are primarily used as an aid in learning to read.

#### _SIL_

Vowels |     |     |     |     |     |  |
:-------   | :-- | :-- | :-- | :-- | :-- | :--
Tfng | <span class='akatab normal'>&#x2D30;&#x0302;</span> | <span class='akatab normal'>&#x2D30;&#x0306;</span> | <span class='akatab normal'>&#x2D62;&#x0323;</span> | <span class='akatab normal'>&#x2D62;&#x0302;</span> | <span class='akatab normal'>&#x2D53;&#x0302;</span> | <span class='akatab normal'>&#x2D67;&#x0302;</span>
USV  | 2D30 + 0302 | 2D30 + 0306 | 2D62 + 0323 | 2D62 + 0302 | 2D53 + 0302 | 2D67 + 0302

#### _APT_

Vowels |     |     |     |     |     |  |
:-------   | :-- | :-- | :-- | :-- | :-- | :--
Tfng | <span class='nototif normal'>&#x2D30;</span>    | <span class='nototif normal'>&#x2D66;</span>    | <span class='nototif normal'>&#x2D62;</span>    | <span class='nototif normal'>&#x2D67;</span> | <span class='nototif normal'>&#x2D66;&#x0302;</span> | <span class='nototif normal'>&#x2D67;&#x0302;</span>
USV  | 2D30 | 2D66 | 2D62 | 2D67 | 2D66 0302 | 2D67 0302 

#### _Hawad_

_Positioning of U+0308 is incorrect in most fonts_

Vowels |     |     |     |     |     |  |
:-------   | :-- | :-- | :-- | :-- | :-- | :--
Tfng | <span class='ebrima normal'>&#x2D5D;&#x0307;</span>    | <span class='ebrima normal'>&#x2D5D;&#x0308;</span>  | <span class='ebrima normal'>&#x2D5D;</span>  | <span class='ebrima normal'>&#x2D49;&#x0307;</span>    | <span class='ebrima normal'>&#x2D49;&#x0308;</span> |  
USV  | 2D5D 0307 | 2D5D 0308 | 2D5D | 2D49 0307 | 2D49 0308 | 

### <a id="punct"></a>Punctuation

Western-style punctuation signs are used in Tifinagh. Words are separated by a space. 

_A few languages use a special separator mark which has been encoded in the Tifinagh block._ The languages using the separator mark will be indicated in the section on that language. Otherwise, punctuation will not be listed in each section.


Punctuation |      |      |      |      |      |      | | |
:----       | :--  | :--  | :--  | :--  | :--  | :--  | :-- | :--
Tfng        | <span class='nototif normal'>.</span>    | <span class='nototif normal'>,</span>    | <span class='nototif normal'>;</span>    | <span class='nototif normal'>:</span>    | <span class='nototif normal'>?</span>    | <span class='nototif normal'>!</span>    | <span class='nototif normal'>...</span> | <span class='nototif normal'>&#x2D70;</span>
USV         | 002E | 002C | 003B | 003A | 003F | 0021 | 2026 | 2D70

#### Digits

There does not seem to be any common way to write numbers using Tifinagh script. The Ircam Tifinagh uses the usual Western-style digits

### <a id="variant"></a>Variant Glyphs

This chart includes a sampling of some of the possible glyph variants in current use. It does not demonstrate all of the possible historical glyph variants.

Because these glyphs are taken from various fonts, the height of a particular glyph may not be significant.

|  | 2D3     | 2D4      | 2D5      | 2D6      | 2D7    
:- | :--     | :--      | :--      | :--      | :--
0  |<span class='nototif normal'>&#x2D30;</span> <span class='akatab normal'>&#x2D30;</span> <span class='akatab normal'style='font-feature-settings: "cv01" 1'>&#x2D30;</span>| <span class='nototif normal'>&#x2D40;</span> <span class='akatab normal' style='font-feature-settings: "cv11" 1'>&#x2D40;</span>| <span class='nototif normal'>&#x2D50;</span> <span class='akatab normal'>&#x2D50;</span> <span class='akatab normal'style='font-feature-settings: "cv04" 1'>&#x2D50;</span>| <span class='nototif normal'>&#x2D60;</span> | <span class='nototif normal'>&#x2D70;</span>
1  |<span class='nototif normal'>&#x2D31;</span> <span class='akatab normal' style='font-feature-settings: "cv08" 1'>&#x2D31;</span>| <span class='nototif normal'>&#x2D41;</span> | <span class='nototif normal'>&#x2D51;</span> | <span class='nototif normal'>&#x2D61;</span> | 
2  |<span class='nototif normal'>&#x2D32;</span> | <span class='nototif normal'>&#x2D42;</span> | <span class='nototif normal'>&#x2D52;</span> | <span class='nototif normal'>&#x2D62;</span> <span class='akatab normal'>&#x2D62;</span> | 
3  |<span class='nototif normal'>&#x2D33;</span> <span class='akatab normal' style='font-feature-settings: "cv09" 1'>&#x2D33;</span>| <span class='nototif normal'>&#x2D43;</span> | <span class='nototif normal'>&#x2D53;</span> <span class='akatab normal'>&#x2D53;</span> <span class='akatab normal'style='font-feature-settings: "cv05" 1'>&#x2D53;</span>| <span class='nototif normal'>&#x2D63;</span> <span class='akatab normal'>&#x2D63;</span> <span class='akatab normal' style='font-feature-settings: "cv06" 1'>&#x2D63;</span>| 
4  |<span class='nototif normal'>&#x2D34;</span> <span class='akatab normal' style='font-feature-settings: "cv03" 1'>&#x2D34;</span>| <span class='nototif normal'>&#x2D44;</span> | <span class='nototif normal'>&#x2D54;</span> | <span class='nototif normal'>&#x2D64;</span> | 
5  |<span class='nototif normal'>&#x2D35;</span> | <span class='nototif normal'>&#x2D45;</span> | <span class='nototif normal'>&#x2D55;</span> | <span class='nototif normal'>&#x2D65;</span> <span class='akatab normal'>&#x2D65;</span>| 
6  |<span class='nototif normal'>&#x2D36;</span> <span class='akatab normal' style='font-feature-settings: "cv10" 1'>&#x2D36;</span>| <span class='nototif normal'>&#x2D46;</span> | <span class='nototif normal'>&#x2D56;</span> | <span class='nototif normal'>&#x2D66;</span> | 
7  |<span class='nototif normal'>&#x2D37;</span> | <span class='nototif normal'>&#x2D47;</span> | <span class='nototif normal'>&#x2D57;</span> | <span class='nototif normal'>&#x2D67;</span> <span class='akatab normal'>&#x2D67;</span>| 
8  |<span class='nototif normal'>&#x2D38;</span> <span class='akatab normal' style='font-feature-settings: "cv15" 1'>&#x2D38;</span>| <span class='nototif normal'>&#x2D48;</span> | <span class='nototif normal'>&#x2D58;</span> |  | 
9  |<span class='nototif normal'>&#x2D39;</span> | <span class='nototif normal'>&#x2D49;</span> | <span class='nototif normal'>&#x2D59;</span> |  | 
A  |<span class='nototif normal'>&#x2D3A;</span> | <span class='nototif normal'>&#x2D4A;</span> | <span class='nototif normal'>&#x2D5A;</span> <span class='akatab normal'>&#x2D5A;</span>|  | 
B  |<span class='nototif normal'>&#x2D3B;</span> | <span class='nototif normal'>&#x2D4B;</span> <span class='akatab normal'>&#x2D4B;</span> <span class='akatab normal' style='font-feature-settings: "cv07" 1'>&#x2D4B;</span>| <span class='nototif normal'>&#x2D5B;</span> <span class='akatab normal'>&#x2D5B;</span> <span class='akatab normal' style='font-feature-settings: "cv12" 1'>&#x2D5B;</span>|  | 
C  |<span class='nototif normal'>&#x2D3C;</span> <span class='akatab normal'>&#x2D3C;</span> <span class='akatab normal' style='font-feature-settings: "cv02" 1'>&#x2D3C;</span> <span class='akatab normal' style='font-feature-settings: "cv02" 2'>&#x2D3C;</span>| <span class='nototif normal'>&#x2D4C;</span> | <span class='nototif normal'>&#x2D5C;</span> <span class='akatab normal'>&#x2D5C;</span>|  | 
D  |<span class='nototif normal'>&#x2D3D;</span> | <span class='nototif normal'>&#x2D4D;</span> <span class='akatab normal'>&#x2D4D;</span>| <span class='nototif normal'>&#x2D5D;</span> |  | 
E  |<span class='nototif normal'>&#x2D3E;</span> | <span class='nototif normal'>&#x2D4E;</span> | <span class='nototif normal'>&#x2D5E;</span> |  | 
F  |<span class='nototif normal'>&#x2D3F;</span> | <span class='nototif normal'>&#x2D4F;</span> | <span class='nototif normal'>&#x2D5F;</span> <span class='akatab normal' style='font-feature-settings: "cv13" 1'>&#x2D5F;</span>| <span class='nototif normal'>&#x2D6F;</span> | <span class='nototif normal'>&#x2D7F;</span>

Variants will only be included in each language section when there are known variants.

### <a id="bicons"></a>Bi- Tri-Consonants

Bi-consonants are additional letterforms used in the Tifinagh script, particularly for Tuareg, to represent a consonant cluster—a sequence of two consonants without an intervening vowel. These bi-consonants, sometimes also referred to as bigraphs, are not directly encoded as single characters in the Unicode Standard. Instead, they are represented as a sequence of the two consonant letters, separated either by U+200D ZERO WIDTH JOINER or by U+2D7F TIFINAGH CONSONANT JOINER.
 
When a bi-consonant is considered obligatory in text, it is represented by the two consonant letters, with U+2D7F TIFINAGH CONSONANT JOINER. inserted between them. This use of U+2D7F is comparable in function to the use of U+0652 ARABIC SUKUN to indicate the absence of a vowel after a consonant, when Tuareg is written in the Arabic script. However, instead of appearing as a visible mark in the text, U+2D7F TIFINAGH CONSONANT JOINER indicates the presence of a bi-consonant, which should then be rendered with a preformed glyph for the sequence. 

Some of the bi-consonants have ascenders. These should ascend above the normal height of the Tifinagh consonants.


USV | 2D7F between characters | → | Glyph</br>(2D7F) | Glyph</br>(ZWJ)
:----- | :--  | :-- | :-- | :-- 
1  2D31 2D5C | <span class='nototif normal'>&#x2D31; + &#x2D7F; + &#x2D5C;</span> | → | <span class='nototif normal'>&#x2D31;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv31" 1'>&#x2D31;&#x2D7F;&#x2D5C;</span>  | <span class='nototif normal'>&#x2D31;&#x200D;&#x2D5C;</span> 
2  2D33 2D5C | <span class='nototif normal'>&#x2D33; + &#x2D7F; + &#x2D5C;</span> | → | <span class='nototif normal'>&#x2D33;&#x2D7F;&#x2D5C;</span> | <span class='nototif normal'>&#x2D33;&#x200D;&#x2D5C;</span>
3  2D34 2D5C | <span class='nototif normal'>&#x2D34; + &#x2D7F; + &#x2D5C;</span> | → | <span class='akatab normal'>&#x2D34;&#x2D7F;&#x2D5C;</span> |
4  2D36 2D5C | <span class='nototif normal'>&#x2D36; + &#x2D7F; + &#x2D5C;</span> | → | <span class='akatab normal'>&#x2D36;&#x2D7F;&#x2D5C;</span> |
5  2D3C 2D5C | <span class='nototif normal'>&#x2D3C; + &#x2D7F; + &#x2D5C;</span> | → | <span class='nototif normal'>&#x2D3C;&#x2D7F;&#x2D5C;</span> <span class='akatab normal'>&#x2D3C;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv02" 1'>&#x2D3C;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv35" 1'>&#x2D3C;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv35" 2'>&#x2D3C;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv14" 1'>&#x2D3C;&#x2D7F;&#x2D5C;</span> |<span class='nototif normal'>&#x2D3C;&#x200D;&#x2D5C;</span> 
6  2D40 2D5C | <span class='nototif normal'>&#x2D40; + &#x2D7F; + &#x2D5C;</span> | → | <span class='nototif normal'>&#x2D40;&#x2D7F;&#x2D5C;</span> |<span class='nototif normal'>&#x2D40;&#x200D;&#x2D5C;</span>
7  2D49 2D5C | <span class='nototif normal'>&#x2D49; + &#x2D7F; + &#x2D5C;</span> | → | <span class='akatab normal'>&#x2D49;&#x2D7F;&#x2D5C;</span> |
8  2D4B 2D5C | <span class='nototif normal'>&#x2D4B; + &#x2D7F; + &#x2D5C;</span> | → | <span class='akatab normal'>&#x2D4B;&#x2D7F;&#x2D5C;</span> |
9  2D4C 2D5C | <span class='nototif normal'>&#x2D4C; + &#x2D7F; + &#x2D5C;</span> | → | <span class='nototif normal'>&#x2D4C;&#x2D7F;&#x2D5C;</span> <span class='akatab normal'>&#x2D4C;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv40" 1'>&#x2D4C;&#x2D7F;&#x2D5C;</span> |
10 2D4D 2D3E | <span class='nototif normal'>&#x2D4D; + &#x2D7F; + &#x2D3E;</span> | → | <span class='akatab normal'>&#x2D4D;&#x2D7F;&#x2D3E;</span> |
11 2D4D 2D5C | <span class='nototif normal'>&#x2D4D; + &#x2D7F; + &#x2D5C;</span> | → | <span class='nototif normal'>&#x2D4D;&#x2D7F;&#x2D5C;</span> <span class='akatab normal'>&#x2D4D;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv38" 1'>&#x2D4D;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv38" 2'>&#x2D4D;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv38" 3'>&#x2D4D;&#x2D7F;&#x2D5C;</span>|
12 2D4E 2D40 | <span class='nototif normal'>&#x2D4E; + &#x2D7F; + &#x2D40;</span> | → | <span class='nototif normal'>&#x2D4E;&#x2D7F;&#x2D40;</span> <span class='akatab normal'>&#x2D4E;&#x2D7F;&#x2D40;</span> |
13 2D4E 2D59 | <span class='nototif normal'>&#x2D4E; + &#x2D7F; + &#x2D59;</span> | → | <span class='akatab normal'>&#x2D4E;&#x2D7F;&#x2D59;</span> |
14 2D4E 2D5C | <span class='nototif normal'>&#x2D4E; + &#x2D7F; + &#x2D5C;</span> | → | <span class='ebrima normal'>&#x2D4E;&#x2D7F;&#x2D5C;</span> <span class='nototif normal'>&#x2D4E;&#x2D7F;&#x2D5C;</span> <span class='akatab normal'>&#x2D4E;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv34" 2'>&#x2D4E;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv34" 1'>&#x2D4E;&#x2D7F;&#x2D5C;</span>  <span class='akatab normal' style='font-feature-settings: "cv34" 3'>&#x2D4E;&#x2D7F;&#x2D5C;</span>|
15 2D4F 2D31 | <span class='nototif normal'>&#x2D4F; + &#x2D7F; + &#x2D31;</span> | → | <span class='nototif normal'>&#x2D4F;&#x2D7F;&#x2D31;</span>|
16 2D4F 2D34 | <span class='nototif normal'>&#x2D4F; + &#x2D7F; + &#x2D34;</span> | → | <span class='akatab normal'>&#x2D4F;&#x2D7F;&#x2D34;</span> <span class='ebrima normal'>&#x2D4F;&#x2D7F;&#x2D34;</span>|
17 2D4F 2D36 | <span class='nototif normal'>&#x2D4F; + &#x2D7F; + &#x2D36;</span> | → | <span class='nototif normal'>&#x2D4F;&#x2D7F;&#x2D36;</span> <span class='akatab normal'>&#x2D4F;&#x2D7F;&#x2D36;</span> <span class='akatab normal' style='font-feature-settings: "cv43" 1'>&#x2D4F;&#x2D7F;&#x2D36;</span>|
18 2D4F 2D37 | <span class='nototif normal'>&#x2D4F; + &#x2D7F; + &#x2D37;</span> | → | <span class='akatab normal'>&#x2D4F;&#x2D7F;&#x2D37;</span> <span class='akatab normal' style='font-feature-settings: "cv41" 1'>&#x2D4F;&#x2D7F;&#x2D37;</span>| 
19 2D4F 2D38 | <span class='nototif normal'>&#x2D4F; + &#x2D7F; + &#x2D38;</span> | → | <span class='akatab normal'>&#x2D4F;&#x2D7F;&#x2D38;</span> <span class='nototif normal'>&#x2D4F;&#x2D7F;&#x2D38;</span>|
20 2D4F 2D39 | <span class='nototif normal'>&#x2D4F; + &#x2D7F; + &#x2D39;</span> | → | <span class='nototif normal'>&#x2D4F;&#x2D7F;&#x2D39;</span> <span class='akatab normal'>&#x2D4F;&#x2D7F;&#x2D39;</span>|

USV | Glyph | → | Glyph and Glyph Variants</br>(using 2D7F between glyphs) | Using ZWJ instead of 2D7F
:----- | :--  | :-- | :-- | :-- 
21 2D4F 2D3C | <span class='nototif normal'>&#x2D4F; + &#x2D7F; + &#x2D3C;</span> | → | <span class='nototif normal'>&#x2D4F;&#x2D7F;&#x2D3C;</span> <span class='akatab normal'>&#x2D4F;&#x2D7F;&#x2D3C;</span> <span class='akatab normal' style='font-feature-settings: "cv42" 1'>&#x2D4F;&#x2D7F;&#x2D3C;</span> <span class='akatab normal' style='font-feature-settings: "cv14" 1'>&#x2D4F;&#x2D7F;&#x2D3C;</span>|
22 2D4F 2D3C 2D5C | <span class='nototif normal'>&#x2D4F; + &#x2D7F; + &#x2D3C; + &#x2D7F; + &#x2D5C;</span> | → | <span class='akatab normal'>&#x2D4F;&#x2D7F;&#x2D3C;&#x2D7F;&#x2D5C;</span>|
23 2D4F 2D3E | <span class='nototif normal'>&#x2D4F; + &#x2D7F; + &#x2D3E;</span> | → | <span class='nototif normal'>&#x2D4F;&#x2D7F;&#x2D3E;</span> <span class='akatab normal'>&#x2D4F;&#x2D7F;&#x2D3E;</span>|
24 2D4F 2D40 | <span class='nototif normal'>&#x2D4F; + &#x2D7F; + &#x2D40;</span> | → | <span class='nototif normal'>&#x2D4F;&#x2D7F;&#x2D40;</span>|
25 2D4F 2D4C | <span class='nototif normal'>&#x2D4F; + &#x2D7F; + &#x2D4C;</span> | → | <span class='nototif normal'>&#x2D4F;&#x2D7F;&#x2D4C;</span> <span class='akatab normal' style='font-feature-settings: "cv45" 1'>&#x2D4F;&#x2D7F;&#x2D4C;</span>|
26 2D4F 2D57 | <span class='nototif normal'>&#x2D4F; + &#x2D7F; + &#x2D57;</span> | → | <span class='nototif normal'>&#x2D4F;&#x2D7F;&#x2D57;</span>|
27 2D4F 2D59 | <span class='nototif normal'>&#x2D4F; + &#x2D7F; + &#x2D59;</span> | → | <span class='nototif normal'>&#x2D4F;&#x2D7F;&#x2D59;</span> <span class='akatab normal'>&#x2D4F;&#x2D7F;&#x2D59;</span>|
28 2D4F 2D5B | <span class='nototif normal'>&#x2D4F; + &#x2D7F; + &#x2D5B;</span> | → | <span class='akatab normal'>&#x2D4F;&#x2D7F;&#x2D5B;</span>|
29 2D4F 2D5C | <span class='nototif normal'>&#x2D4F; + &#x2D7F; + &#x2D5C;</span> | → | <span class='nototif normal'>&#x2D4F;&#x2D7F;&#x2D5C;</span> <span class='akatab normal'>&#x2D4F;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv37" 1'>&#x2D4F;&#x2D7F;&#x2D5C;</span>|
30 2D4F 2D5E | <span class='nototif normal'>&#x2D4F; + &#x2D7F; + &#x2D5E;</span> | → | <span class='nototif normal'>&#x2D4F;&#x2D7F;&#x2D5E;</span>|
31 2D4F 2D63 | <span class='nototif normal'>&#x2D4F; + &#x2D7F; + &#x2D63;</span> | → | <span class='nototif normal'>&#x2D4F;&#x2D7F;&#x2D63;</span>|
32 2D4F 2D64 | <span class='nototif normal'>&#x2D4F; + &#x2D7F; + &#x2D64;</span> | → | <span class='akatab normal'>&#x2D4F;&#x2D7F;&#x2D64;</span>|
33 2D53 2D5C | <span class='nototif normal'>&#x2D53; + &#x2D7F; + &#x2D5C;</span> | → | <span class='nototif normal'>&#x2D53;&#x2D7F;&#x2D5C;</span> <span class='akatab normal'>&#x2D53;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv39" 1'>&#x2D53;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv39" 2'>&#x2D53;&#x2D7F;&#x2D5C;</span>|
34 2D54 2D31 | <span class='nototif normal'>&#x2D54; + &#x2D7F; + &#x2D31;</span> | → | <span class='nototif normal'>&#x2D54;&#x2D7F;&#x2D31;</span>|
35 2D54 2D36 | <span class='nototif normal'>&#x2D54; + &#x2D7F; + &#x2D36;</span> | → | <span class='nototif normal'>&#x2D54;&#x2D7F;&#x2D36;</span>|
36 2D54 2D37 | <span class='nototif normal'>&#x2D54; + &#x2D7F; + &#x2D37;</span> | → | <span class='nototif normal'>&#x2D54;&#x2D7F;&#x2D37;</span>|
37 2D54 2D3D | <span class='nototif normal'>&#x2D54; + &#x2D7F; + &#x2D3D;</span> | → | <span class='nototif normal'>&#x2D54;&#x2D7F;&#x2D3D;</span>|
38 2D54 2D3E | <span class='nototif normal'>&#x2D54; + &#x2D7F; + &#x2D3E;</span> | → | <span class='akatab normal'>&#x2D54;&#x2D7F;&#x2D3E;</span> <span class='akatab normal' style='font-feature-settings: "cv46" 1'>&#x2D54;&#x2D7F;&#x2D3E;</span>|
39 2D54 2D4F | <span class='nototif normal'>&#x2D54; + &#x2D7F; + &#x2D4F;</span> | → | <span class='nototif normal'>&#x2D54;&#x2D7F;&#x2D4F;</span> <span class='akatab normal'>&#x2D54;&#x2D7F;&#x2D4F;</span>|
40 2D54 2D59 | <span class='nototif normal'>&#x2D54; + &#x2D7F; + &#x2D59;</span> | → | <span class='nototif normal'>&#x2D54;&#x2D7F;&#x2D59;</span>|

USV | Glyph | → | Glyph and Glyph Variants</br>(using 2D7F between glyphs) | Using ZWJ instead of 2D7F
:----- | :--  | :-- | :-- | :-- 
41 2D54 2D5C | <span class='nototif normal'>&#x2D54; + &#x2D7F; + &#x2D5C;</span> | → | <span class='nototif normal'>&#x2D54;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv32" 1'>&#x2D54;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv32" 2'>&#x2D54;&#x2D7F;&#x2D5C;</span>|
42 2D56 2D5C | <span class='nototif normal'>&#x2D56; + &#x2D7F; + &#x2D5C;</span> | → | <span class='nototif normal'>&#x2D56;&#x2D7F;&#x2D5C;</span>|
43 2D59 2D3E | <span class='nototif normal'>&#x2D59; + &#x2D7F; + &#x2D3E;</span> | → | <span class='akatab normal'>&#x2D59;&#x2D7F;&#x2D3E;</span>|
44 2D59 2D4F | <span class='nototif normal'>&#x2D59; + &#x2D7F; + &#x2D4F;</span> | → | <span class='nototif normal'>&#x2D59;&#x2D7F;&#x2D4F;</span>|
45 2D59 2D5C | <span class='nototif normal'>&#x2D59; + &#x2D7F; + &#x2D5C;</span> | → | <span class='nototif normal'>&#x2D59;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv33" 1'>&#x2D59;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv33" 2'>&#x2D59;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv33" 3'>&#x2D59;&#x2D7F;&#x2D5C;</span>|
46 2D5B 2D3E | <span class='nototif normal'>&#x2D5B; + &#x2D7F; + &#x2D3E;</span> | → | <span class='akatab normal'>&#x2D5B;&#x2D7F;&#x2D3E;</span> <span class='akatab normal' style='font-feature-settings: "cv47" 1'>&#x2D5B;&#x2D7F;&#x2D3E;</span> <span class='akatab normal' style='font-feature-settings: "cv47" 2'>&#x2D5B;&#x2D7F;&#x2D3E;</span> <span class='akatab normal' style='font-feature-settings: "cv12" 1'>&#x2D5B;&#x2D7F;&#x2D3E;</span>|
47 2D5B 2D4F | <span class='nototif normal'>&#x2D5B; + &#x2D7F; + &#x2D4F;</span> | → | <span class='akatab normal'>&#x2D5B;&#x2D7F;&#x2D4F;</span>|
48 2D5B 2D5C | <span class='nototif normal'>&#x2D5B; + &#x2D7F; + &#x2D5C;</span> | → | <span class='nototif normal'>&#x2D5B;&#x2D7F;&#x2D5C;</span> <span class='akatab normal'>&#x2D5B;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv48" 1'>&#x2D5B;&#x2D7F;&#x2D5C;</span>|
49 2D5C 2D59 | <span class='nototif normal'>&#x2D5C; + &#x2D7F; + &#x2D59;</span> | → | <span class='nototif normal'>&#x2D5C;&#x2D7F;&#x2D59;</span>|
50 2D61 2D5C | <span class='nototif normal'>&#x2D61; + &#x2D7F; + &#x2D5C;</span> | → | <span class='nototif normal'>&#x2D61;&#x2D7F;&#x2D5C;</span>|
51 2D62 2D5C | <span class='nototif normal'>&#x2D62; + &#x2D7F; + &#x2D5C;</span> | → | <span class='nototif normal'>&#x2D62;&#x2D7F;&#x2D5C;</span> <span class='ebrima normal'>&#x2D62;&#x2D7F;&#x2D5C;</span>|
52 2D63 2D5C | <span class='nototif normal'>&#x2D63; + &#x2D7F; + &#x2D5C;</span> | → | <span class='akatab normal'>&#x2D63;&#x2D7F;&#x2D5C;</span>|
53 2D65 2D5C | <span class='nototif normal'>&#x2D65; + &#x2D7F; + &#x2D5C;</span> | → | <span class='nototif normal'>&#x2D65;&#x2D7F;&#x2D5C;</span>|

This should not be considered an exhaustive list of all bi-consonants used for Tifinagh, nor are the shapes of the bi-consonants necessarily definitive. There are a wide range of glyph variants.

Bi-consonants will only be included in each language section when there are known variants.


### <a id="contexual"></a>Contextual Shaping

Contextual Shaping |     |     |     |     |     |  |
:-------   | :-- | :-- | :-- | :-- | :-- | :--
<span class='akatab normal'>&#x2D4D;</span> | + | <span class='akatab normal'>&#x2D4D;</span> | + | <span class='akatab normal'>&#x2D4D;</span> | → | <span class='akatab normal'>&#x2D4D;&#x2D4D;&#x2D4D;</span> or <span class='akatab normal' style='font-feature-settings: "cv19" 1'>&#x2D4D;&#x2D4D;&#x2D4D;</span>
2D4D | | 2D4D | | 2D4D | | |
| | | | | |
<span class='akatab normal'>&#x2D4D;</span> | + | <span class='akatab normal'>&#x2D4F;</span>| + |<span class='akatab normal'>&#x2D4D;</span> | → | <span class='akatab normal'>&#x2D4D;&#x2D4F;&#x2D4D;</span> or <span class='akatab normal' style='font-feature-settings: "cv19" 1'>&#x2D4D;&#x2D4F;&#x2D4D;</span>
2D4D | | 2D4F | | 2D4D | |
| | | | | |
<span class='akatab normal'>&#x2D4F;</span> | + | <span class='akatab normal'>&#x2D4D;</span> | + | <span class='akatab normal'>&#x2D4F;</span>| → | <span class='akatab normal'>&#x2D4F;&#x2D4D;&#x2D4F;</span> or <span class='akatab normal' style='font-feature-settings: "cv19" 1'>&#x2D4F;&#x2D4D;&#x2D4F;</span>
2D4F | | 2D4D | | 2D4F | | 
| | | | | |
<span class='akatab normal'>&#x2D4F;</span> | + | <span class='akatab normal'>&#x2D4F;</span>| + | <span class='akatab normal'>&#x2D4F;</span> | → | <span class='akatab normal'>&#x2D4F;&#x2D4F;&#x2D4F;</span> or <span class='akatab normal' style='font-feature-settings: "cv19" 1'>&#x2D4F;&#x2D4F;&#x2D4F;</span>
2D4F | | 2D4F | | 2D4F | |

Contextual shaping will only be included in each language section when there is known shaping.

### <a id="dir"></a>Writing Direction

Historically, in early inscriptions, Berber was written horizontally from left to right, from right to left, vertically (bottom to top, top to bottom) or even in boustrophedon. However, the most frequently used directionality in the modern-day Berber script is horizontal from left to right.

Given that left-to-right directionality seems to be the most widely used one in the Maghreb and in Niger, the strong directionality of Tifinagh is defined to be left-to-right. If needed, it is possible to explicitly declare a right-to-left directionality. The glyphs will then have to be mirrored, if needed, according to the rules in effect for the specified variant. If the glyphs are to be mirrored, then this must be implemented in the font.

**The following text demonstrates Tifinagh left-to-right behaviour:**<br>
<span class='akatab normal'> ⵙⵏⵜⵜ ⵜⵙⴾⵍⵏ ⵓⵔ ⵜⴶⵂⵏⵜ ⵎⵉ </span>

**The following text demonstrates Tifinagh right-to-left behaviour using the U+202E character:**<br>
<span dir="rtl" class='akatab normal'> &#x202E; ⵙⵏⵜⵜ ⵜⵙⴾⵍⵏ ⵓⵔ ⵜⴶⵂⵏⵜ ⵎⵉ </span>

**The following text demonstrates both Tifinagh directional behaviours using the U+202E and U+202C characters:**<br>
<span dir="rtl" class='akatab normal'> &#x202E; ⵙⵏⵜⵜ ⵜⵙⴾⵍⵏ ⵓⵔ ⵜⴶⵂⵏⵜ ⵎⵉ  &#x202C; ⵙⵏⵜⵜ ⵜⵙⴾⵍⵏ ⵓⵔ ⵜⴶⵂⵏⵜ ⵎⵉ </span>
</p>‮
<!-- 
Using hard-coded directional characters in the HTML code (as illustrated above) can prevent accidental deletion of invisible characters.
-->

## <a id="resource"></a>Resources

### <a id="key"></a>Keyboarding

The only standard keyboard known at the moment is the [Moroccan standard keyboard](http://hapax.qc.ca/pdf/NM%2017.6.000.pdf). A keyboard based on the Moroccan standard keyboard is supported in Microsoft Windows.

Keyman is a cross-platform keyboarding application. Four keyboards are available for the Tifinagh script:

- [Tifinagh &#x28;Basic&#x29; Basic](https://keyman.com/keyboards/basic_kbdtifi) [tzm]

- [Tifinagh &#x28;Full&#x29; Basic](https://keyman.com/keyboards/basic_kbdtifi2) [tzm, thz, tda, thv, kab, mzb, shi, shy, rif, tmh, zen, zgh]

- [Tawallammat Tifinagh &#x28;SIL&#x29;](https://keyman.com/keyboards/sil_tawallammat) [ttq, tzm]

- [Tuareg Tifinagh](https://keyman.com/keyboards/tuareg_tifinagh) [taq, thv]



### <a id="font"></a>Fonts

These fonts provide support for some or all of the Tifinagh block.

- (Noto Sans Tifinagh)[https://fonts.google.com/noto/specimen/Noto+Sans+Tifinagh]
- (Akatab)[https://software.sil.org/akatab/] - currently only covers part of the Tifinagh block for Tamahaq, Tamashek, and Tawallammat languages
- (Tagmukay)[https://software.sil.org/tagmukay/] - currently only covers part of the Tifinagh block for the Tawallammat Tamajaq language
- (Catrinity)[https://catrinity-font.de/]
- (IRCAM Tifinagh fonts)[https://www.ircam.ma/fr/alphabet-tifinaghe] - supports neo-Tifinagh
- (Hapax font set)[http://www.hapax.qc.ca/polices/]
- (MPH 2B Damase)[https://www.dafont.com/mph-2b-damase.font]
- (DejaVu)[https://dejavu-fonts.github.io/]

## <a id="neo"></a>Languages Using Neo-Tifinagh script

### <a id="tzm_zgh"></a>Central Atlas Tamazight, Standard Moroccan Tamazight

_Source_: Tifinaghe-IRCAM, [Omniglot](https://omniglot.com/writing/tamazight.htm), Souad Sahraoui

_Language tag:_ `tzm-Tfng`, `zgh`

_Opentype language system tag:_ `BBR `

_Keyman keyboard_: [Tifinagh &#x28;Basic&#x29; Basic](https://keyman.com/keyboards/basic_kbdtifi) [tzm]

_Keyman keyboard_: [Tifinagh &#x28;Full&#x29; Basic](https://keyman.com/keyboards/basic_kbdtifi2) [tzm, thz, tda, thv, kab, mzb, shi, shy, rif, tmh, zen, zgh]

#### Alphabet

Consonants |     |     |     |     |     |     |     |     |     | |
:-------   | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- 
Tfng | <span class='nototif normal'>ⴱ</span>  | <span class='nototif normal'>ⴳ</span> | <span class='nototif normal'>ⴳⵯ</span> | <span class='nototif normal'>ⴷ</span> | <span class='nototif normal'>ⴹ</span> | <span class='nototif normal'>ⴼ</font></span> | <span class='nototif normal'>ⴽ</span> | <span class='nototif normal'>ⴽⵯ</span> | <span class='nototif normal'>ⵀ</span> | <span class='nototif normal'>ⵃ </span>
USV | 2D31 | 2D33 | 2D33 + 2D6F | 2D37 | 2D39 | 2D3C | 2D3D | 2D3D + 2D6F | 2D40 | 2D43 
Latn | b | g | gʷ | d | ḍ | f | k | kʷ | h | ḥ 
 | | | | | | | | | |
Tfng | <span class='nototif normal'>ⵅ</span> | <span class='nototif normal'>ⵇ</span> | <span class='nototif normal'>ⵊ</span> | <span class='nototif normal'>ⵍ</span> | <span class='nototif normal'>ⵎ</span> | <span class='nototif normal'>ⵏ</span> | <span class='nototif normal'>ⵔ</span> | <span class='nototif normal'>ⵕ</span> | <span class='nototif normal'>ⵖ</span> | <span class='nototif normal'>ⵙ </span>
USV | 2D45 | 2D47 | 2D4A | 2D4D | 2D4E | 2D4F | 2D54 | 2D55 | 2D56 | 2D59 
Latn |  x | q | j | l | m | n | r | ṛ | ɣ | s 
 | | | | | | | | | |
Tfng | <span class='nototif normal'>ⵚ</span> | <span class='nototif normal'>ⵛ</span> | <span class='nototif normal'>ⵜ</span> | <span class='nototif normal'>ⵟ</span> | <span class='nototif normal'>ⵡ</span> | <span class='nototif normal'>ⵢ</span> | <span class='nototif normal'>ⵣ | <span class='nototif normal'>ⵥ </span>
USV | 2D5A | 2D5B | 2D5C | 2D5F | 2D61 | 2D62 | 2D63 | 2D65 
Latn | ṣ | c | t | ṭ | w | y | z | ẓ 

Vowels |     |     |     |     | |
:----  | :-- | :-- | :-- | :-- | :-- 
Tfng     | <span class='nototif normal'>ⴰ</span>   | <span class='nototif normal'>ⴻ</span>   | <span class='nototif normal'>ⵄ</span>   | <span class='nototif normal'>ⵉ</span>   | <span class='nototif normal'>ⵓ</span>
USV | 2D30 | 2D3B | 2D44 | 2D49 | 2D53
Latn     | a   | e   | ɛ   | i   | u 

#### Known glyph variants

The Tifinagh script was encoded based on Neo-Tifinagh shapes. It seems unlikely that there would be glyph variants.

#### Bi-consonants

Bi-consonants are not “required” in Neo-Tifinagh. If a font supports bi-consonants, the two consonants separated by the ZWJ should thus form a bi-consonant. If a font does not support bi-consonants, they should simply appear as separate consonants.

#### Contextual Shaping

Neo-Tifinagh does not use contextual shaping for the “l” and “n”. This is because the glyphs are distinguishable from each other when side by side.

### <a id="kab"></a>Kabyle, Amazigh

_Source_: [Omniglot](https://omniglot.com/writing/kabyle.php)

_Language Tag_: `kab-Tfng`

_Opentype language system tag:_ `BBR `

See also "<a href="#kab_etc">Neo-Tifinagh in Algeria</a>" listed above for comparison. The character sets do not match.

Characters |      |      |      |      |      |      |      |    |  | | |
:-------   | :--  | :--  | :--  | :--  | :--  | :--  | :--  | :-- | :-- | :-- | :--
Tfng       | <span class='nototif normal'>&#x2D30;<span> | <span class='nototif normal'>&#x2D31;<span> | <span class='nototif normal'>&#x2D31;&#x2D6F;<span> | <span class='nototif normal'>&#x2D5B;<span> | <span class='nototif normal'>&#x2D5E;<span> | <span class='nototif normal'>&#x2D37;<span> | <span class='nototif normal'>&#x2D39;<span> | <span class='nototif normal'>&#x2D3B;<span> | <span class='nototif normal'>&#x2D44;<span> | <span class='nototif normal'>&#x2D3C;<span> | 
USV        | 2D30 | 2D31 | 2D31 2D6F| 2D5B | 2D5E | 2D37 | 2D39 | 2D3B | 2D44 | 2D3C |
Latn        | a | b | bw| c | c&#x030c; | d | ḍ | &#x01dd; | &#x025B; | f |
 |  |  |  |  |  |  |  |  | | |
Tfng       | <span class='nototif normal'>&#x2D33;<span> | <span class='nototif normal'>&#x2D33;&#x2D6F;<span>|<span class='nototif normal'>&#x2D35;<span> | <span class='nototif normal'>&#x2D56;<span> | <span class='nototif normal'>&#x2D56;&#x2D6F;<span> | <span class='nototif normal'>&#x2D41;<span> | <span class='nototif normal'>&#x2D43;<span> | <span class='nototif normal'>&#x2D49;<span> | <span class='nototif normal'>&#x2D4A;<span> | <span class='nototif normal'>&#x2D3D;<span> | <span class='nototif normal'>&#x2D3D;&#x2D6F;<span> 
USV        | 2D33 | 2D33 2D6F | 2D35 | 2D56 | 2D56 2D6F | 2D41 | 2D43 | 2D49 | 2D4A | 2D3D | 2D3D 2D6F 
Latn        | g | gw| g&#x030C; | &#x0263; | &#x0263;w | h | h&#x0323; | i | j | k | kw
 |  |  |  |  |  |  |  |  | | |
Tfng        | <span class='nototif normal'>&#x2D4D;<span> | <span class='nototif normal'>&#x2D4E;<span> | <span class='nototif normal'>&#x2D4F;<span> | <span class='nototif normal'>&#x2D47;<span> | <span class='nototif normal'>&#x2D47;&#x2D6F;<span> | <span class='nototif normal'>&#x2D54;<span> | <span class='nototif normal'>&#x2D55;<span> | <span class='nototif normal'>&#x2D59;<span> | <span class='nototif normal'>&#x2D5A;<span> | <span class='nototif normal'>&#x2D5C;<span> |<span class='nototif normal'>&#x2D5F;<span>
USV        | 2D4D | 2D4E | 2D4F | 2D47 | 2D47 2D6F | 2D54 | 2D55 | 2D59 | 2D5A | 2D5C | 2D5F
Latn        | l | m | n | q | qw | r | r&#x030C; or r&#x0323; | s | s&#x0323; | t | t&#x0323;
 |  |  |  |  |  |  |  |  | | |
Tfng        | <span class='nototif normal'>&#x2D53;<span> | <span class='nototif normal'>&#x2D61;<span> | <span class='nototif normal'>&#x2D45;<span> | <span class='nototif normal'>&#x2D45;&#x2D6F;<span> | <span class='nototif normal'>&#x2D62;<span> | <span class='nototif normal'>&#x2D63;<span> | <span class='nototif normal'>&#x2D65;<span> | <span class='nototif normal'>&#x2D5C;&#x2D59;<span> | <span class='nototif normal'>&#x2D37;&#x2D63;<span>|  | 
USV        | 2D53 | 2D61 | 2D45 | 2D45 2D6F |2D62 | 2D63 | 2D65 | 2D5C 2D59  | 2D37 2D63 |  | 
Latn        | u | w | x | xw | y | z | z&#x0323; | ts| dz | |

#### Known glyph variants

- Variants are used for c č and l. However, the variants are not in any of the Akatab, Ebrima, or Noto fonts.

#### Bi-consonants

Bi-consonants are not “required” in Neo-Tifinagh. If a font supports bi-consonants, the two consonants separated by the ZWJ should thus form a bi-consonant. If a font does not support bi-consonants, they should simply appear as separate consonants.

## <a id="trad"></a>Languages Using Traditional Tifinagh script

### <a id="gho"></a>Ghomara, Shilha

_Source_: [Omniglot](https://omniglot.com/writing/shilha.htm)

_Language Tag_: `gho-Tfng`

_Opentype language system tag:_ `BBR `

Characters |     |     |     |     |     |     |     |     |     | |
:-------   | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- 
Tfng | <span class='nototif normal'>&#x2D30;<span> | <span class='nototif normal'>&#x2D31;<span> |<span class='nototif normal'>&#x2D33;<span> | <span class='nototif normal'>&#x2D33;&#x2D6F;<span> | <span class='nototif normal'>&#x2D37;<span> | <span class='nototif normal'>&#x2D39;<span> | <span class='nototif normal'>&#x2D3C;<span> | <span class='nototif normal'>&#x2D3D;<span> | <span class='nototif normal'>&#x2D3D;&#x2D6F;<span> | <span class='nototif normal'>&#x2D40;<span>
USV |2D30 | 2D31 | 2D33 | 2D33 2D6F | 2D37 | 2D39 | 203C | 2D3D | 2D3D 2D6F | 2D40
Latn |a | b | g |gw| d| d&#x0323;| f | k | kw | h
 | |  |  |  |  |  |  | |  |  |
Tfng | <span class='nototif normal'>&#x2D43;<span> | <span class='nototif normal'>&#x2D44;<span> |<span class='nototif normal'>&#x2D45;<span> | <span class='nototif normal'>&#x2D45;&#x2D6F;<span> | <span class='nototif normal'>&#x2D47;<span> | <span class='nototif normal'>&#x2D49;<span> | <span class='nototif normal'>&#x2D4A;<span> | <span class='nototif normal'>&#x2D4D;<span> | <span class='nototif normal'>&#x2D4E;<span> | <span class='nototif normal'>&#x2D4F;<span>
USV |2D43 | 2D44 | 2D45 | 2D45 2D6F | 2D47 | 2D49 | 204A | 2D4D | 2D4E | 2D4F
Latn | h&#x0323; | &#x025B; |x| xw| q| i | z&#x030C; | l | m | n
 | |  |  |  |  |  |  | |  |  |
Tfng | <span class='nototif normal'>&#x2D53;<span> | <span class='nototif normal'>&#x2D54;<span> |<span class='nototif normal'>&#x2D55;<span> | <span class='nototif normal'>&#x2D56;<span> | <span class='nototif normal'>&#x2D56;&#x2D6F;<span> | <span class='nototif normal'>&#x2D59;<span> | <span class='nototif normal'>&#x2D5A;<span> | <span class='nototif normal'>&#x2D5B;<span> | <span class='nototif normal'>&#x2D5C;<span> | <span class='nototif normal'>&#x2D5F;<span>
USV |2D53 | 2D54 | 2D55 | 2D56 | 2D56 2D6F | 2D59 | 205A | 2D5B | 2D5C | 2D5F
Latn | u | r |r&#x0323;| &#x0263;| &#x0263;w| s | s&#x0323; | s&#x030C; | t | t&#x0323;
 | |  |  |  |  |  |  | |  |  |
Tfng | <span class='nototif normal'>&#x2D61;<span> | <span class='nototif normal'>&#x2D62;<span> |<span class='nototif normal'>&#x2D63;<span> | <span class='nototif normal'>&#x2D65;<span> | | | | | | 
USV |2D61 | 2D62 | 2D63 | 2D65 | | | |  | | 
Latn | w | y | z |z&#x0323;| | |  |  |  |  |
 | |  |  |  |  |  |  | |  |  |

#### Known glyph variants

A variant for "l" is not in any of the Akatab, Ebrima, or Noto fonts.

### <a id="rif"></a>Tarifit, Riffian

_Language tag:_ `rif-Tfng`

_Opentype language system tag:_ `BBR `

_Source_: [Omniglot](https://omniglot.com/writing/riffian.htm), [2009 New Testament](https://archive.org/details/newtestament-tarifit)

Characters |      |      |      |      |      |      |      |    |  | | 
:-------   | :--  | :--  | :--  | :--  | :--  | :--  | :--  | :-- | :-- | :-- 
Tfng       | <span class='nototif normal'>&#x2D30;<span> | <span class='nototif normal'>&#x2D31;<span> | <span class='nototif normal'>&#x2D33;<span> | <span class='nototif normal'>&#x2D33;&#x2D6F;<span> | <span class='nototif normal'>&#x2D37;<span> | <span class='nototif normal'>&#x2D39;<span> | <span class='nototif normal'>&#x2D3B;<span> | <span class='nototif normal'>&#x2D3C;<span> | <span class='nototif normal'>&#x2D3D;<span> | <span class='nototif normal'>&#x2D3D;&#x2D6F;<span>
USV        | 2D30 | 2D31 | 2D33 | 2D33 2D6F |2D37 | 2D39 | 2D3B | 2D3C | 2D3D | 2D3D 2D6F 
Latn        | a | b | g | gw | d | ḍ | &#x01dd; | f | k | kw
 |  |  |  |  |  |  |  |  | | |
Tfng       | <span class='nototif normal'>&#x2D40;<span> | <span class='nototif normal'>&#x2D43;<span>|<span class='nototif normal'>&#x2D44;<span> | <span class='nototif normal'>&#x2D45;<span> | <span class='nototif normal'>&#x2D47;<span> | <span class='nototif normal'>&#x2D49;<span> | <span class='nototif normal'>&#x2D4A;<span> | <span class='nototif normal'>&#x2D4D;<span> | <span class='nototif normal'>&#x2D4E;<span> | <span class='nototif normal'>&#x2D4F;<span>
USV        | 2D40 | 2D43 | 2D44 | 2D45 | 2D47 | 2D49 | 2D4A | 2D4D | 2D4E | 2D4F
Latn        | h | h&#x0323; | &#x025B; | x | q | i | j | l | m | n
 |  |  |  |  |  |  |  |  | | |
Tfng        | <span class='nototif normal'>&#x2D53;<span> | <span class='nototif normal'>&#x2D54;<span> | <span class='nototif normal'>&#x2D55;<span> | <span class='nototif normal'>&#x2D56;<span> | <span class='nototif normal'>&#x2D59;<span> | <span class='nototif normal'>&#x2D5A;<span> | <span class='nototif normal'>&#x2D5B;<span> | <span class='nototif normal'>&#x2D5E;<span> | <span class='nototif normal'>&#x2D5C;<span> | <span class='nototif normal'>&#x2D5F;<span>
USV        | 2D53 | 2D54 | 2D55 | 2D56 | 2D59 | 2D5A | 2D5B | 2D5E | 2D5C | 2D5F
Latn        | u | r | r&#x0323; | &#x0263; | s | s&#x0323; | c | c&#x030C; | t | t&#x0323;
 |  |  |  |  |  |  |  |  | | |
Tfng        | <span class='nototif normal'>&#x2D61;<span> | <span class='nototif normal'>&#x2D62;<span> | <span class='nototif normal'>&#x2D63;<span> | <span class='nototif normal'>&#x2D65;<span> | <span class='nototif normal'>&#x2D6F;<span>|  |  |  | |  | 
USV        | 2D61 | 2D62 | 2D63 | 2D65 | 2D6F |  |  | |  |  
Latn        | w | y | z | z&#x0323; |  |  |  | |  |

**Glyph variants and Biconsonants**

None known.

### <a id="shi"></a>Tachelhit

_Language tag:_ `shi`

_Opentype language system tag:_ `BBR `

_SLDR:_ [shi](https://github.com/silnrsi/sldr/blob/master/sldr/s/shi.xml)

Characters |     |     |     |     |     |     |     |     |     |
:-------   | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :--
Tfng | <span class='nototif normal'>&#x2D30;<span> | <span class='nototif normal'>&#x2D31;<span> | <span class='nototif normal'>&#x2D33;<span>| <span class='nototif normal'>&#x2D37;<span> | <span class='nototif normal'>&#x2D39;<span> | <span class='nototif normal'>&#x2D3B;<span> | <span class='nototif normal'>&#x2D3C;<span> | <span class='nototif normal'>&#x2D3D;<span> | <span class='nototif normal'>&#x2D40;<span> 
USV  |2D30 | 2D31 | 2D33 | 2D37      | 2D39 | 2D3B      | 2D3C | 2D3D | 2D40
 |  |  |  |  |  |  | |  |
Tfng | <span class='nototif normal'>&#x2D43;<span> | <span class='nototif normal'>&#x2D44;<span> | <span class='nototif normal'>&#x2D45;<span>| <span class='nototif normal'>&#x2D47;<span> | <span class='nototif normal'>&#x2D49;<span> | <span class='nototif normal'>&#x2D4A;<span> | <span class='nototif normal'>&#x2D4D;<span> | <span class='nototif normal'>&#x2D4E;<span> | <span class='nototif normal'>&#x2D4F;<span> 
USV  |2D43 | 2D44 | 2D45 | 2D47      | 2D49 | 2D4A      | 2D4D | 2D4E | 2D4F
 |  |  |  |  |  |  | |  |
Tfng | <span class='nototif normal'>&#x2D53;<span> | <span class='nototif normal'>&#x2D54;<span> | <span class='nototif normal'>&#x2D55;<span>| <span class='nototif normal'>&#x2D56;<span> | <span class='nototif normal'>&#x2D59;<span> | <span class='nototif normal'>&#x2D5A;<span> | <span class='nototif normal'>&#x2D5B;<span> | <span class='nototif normal'>&#x2D5C;<span> | <span class='nototif normal'>&#x2D5F;<span> 
USV  |2D53 | 2D54 | 2D55 | 2D56      | 2D59 | 2D5A      | 2D5B | 2D5C | 2D5F
 |  |  |  |  |  |  | |  |
Tfng | <span class='nototif normal'>&#x2D61;<span> | <span class='nototif normal'>&#x2D62;<span> | <span class='nototif normal'>&#x2D63;<span>| <span class='nototif normal'>&#x2D65;<span> | <span class='nototif normal'>&#x2D6F;<span> |  |  |  |  
USV  |2D61 | 2D62 | 2D63 | 2D65 | 2D6F | | | |

#### Glyph variants

Unknown.

### <a id="siz"></a>Siwi

_Source_: [Omniglot](https://omniglot.com/writing/siwi.htm)

_Language Tag_: `siz-Tfng`

_Opentype language system tag:_ `BBR `

Characters |     |     |     |     |     |     |     |     |     | |
:-------   | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- 
Tfng | <span class='nototif normal'>&#x2D30;<span> | <span class='nototif normal'>&#x2D31;<span> | <span class='nototif normal'>&#x2D31;&#x2D6F;<span> |<span class='nototif normal'>&#x2D33;<span> | <span class='nototif normal'>&#x2D33;&#x2D6F;<span> | <span class='nototif normal'>&#x2D37;<span> | <span class='nototif normal'>&#x2D36;<span> | <span class='nototif normal'>&#x2D39;<span> | <span class='nototif normal'>&#x2D3B;<span> | <span class='nototif normal'>&#x2D3C;<span> 
USV |2D30 | 2D31 | 2D31 2D6F | 2D33 | 2D33 2D6F | 2D37 | 2D36 | 2D39 | 203B | 2D3D
Latn |a | b | b&#x0323; | g |gw| d| j| d&#x0323; | &#x01DD; | f 
 | |  |  |  |  |  |  | |  |  |
Tfng | <span class='nototif normal'>&#x2D3C;&#x2D6F;<span> |<span class='nototif normal'>&#x2D3F;<span> | <span class='nototif normal'>&#x2D3F;&#x2D6F;<span> | <span class='nototif normal'>&#x2D40;<span> | <span class='nototif normal'>&#x2D43;<span> | <span class='nototif normal'>&#x2D44;<span> | <span class='nototif normal'>&#x2D45;<span> | <span class='nototif normal'>&#x2D45;&#x2D6F;<span> |<span class='nototif normal'>&#x2D47;<span> | <span class='nototif normal'>&#x2D49;<span>
USV |2D3C 2D6F | 2D3F | 2D3F 2D6F | 2D40 | 2D43 | 2D44 | 2D45 | 2D45 2D6F | 2D47| 2D49
Latn |f&#x0323; | k | kw | h | h&#x0323; | glottal | x | xw | q | i
 | |  |  |  |  |  |  | |  |  |
Tfng | <span class='nototif normal'>&#x2D4D;<span> | <span class='nototif normal'>&#x2D4D;&#x2D6F;<span> | <span class='nototif normal'>&#x2D4E;<span> | <span class='nototif normal'>&#x2D4E;&#x2D6F;<span> | <span class='nototif normal'>&#x2D4F;<span> | <span class='nototif normal'>&#x2D53;<span> | <span class='nototif normal'>&#x2D54;<span> | <span class='nototif normal'>&#x2D55;<span> | <span class='nototif normal'>&#x2D56;<span> | <span class='nototif normal'>&#x2D56; &#x2D6F;<span>
USV |2D4D | 2D4D 2D6F | 2D4E | 2D4E 2D6F | 2D4F | 2D53 | 2D54 | 2D55| 2D56 | 2D56 2D6F
Latn |l | l&#x0323; | m | m&#x0323; | n | u | r | r&#x0323; | g&#x030C; | g&#x030C;w
 | |  |  |  |  |  |  | |  |  |
Tfng | <span class='nototif normal'>&#x2D59;<span> | <span class='nototif normal'>&#x2D5A;<span> | <span class='nototif normal'>&#x2D5B;<span> | <span class='nototif normal'>&#x2D5C;<span> | <span class='nototif normal'>&#x2D5E;<span> | <span class='nototif normal'>&#x2D5F;<span> | <span class='nototif normal'>&#x2D61;<span> | <span class='nototif normal'>&#x2D62;<span> | <span class='nototif normal'>&#x2D63;<span> | <span class='nototif normal'>&#x2D65;<span>
USV |2D59 | 2D5A | 2D5B | 2D5C | 2D5E | 2D5F | 2D61 | 2D62| 2D63 | 2D65
Latn |s | s&#x0323; | s&#x030C; | t | c&#x030C; | t&#x0323; | w | y | z | z&#x0323;


Other characters | | | |
:-------   | :-- | :-- | :--
Tfng | <span class='nototif normal'>&#x2D30;&#x2D49;</span> |<span class='nototif normal'>&#x2D30;&#x2D53;</span> |<span class='nototif normal'>&#x2D54;&#x2D54;</span>
USV  | 2D30 2D49 | 2D30 2D53 | 2D54 2D54
Latin | ai/e | au/o | rr

### <a id="taq"></a>Tamasheq

_Source_: [Omniglot](https://omniglot.com/writing/tamasheq.htm)

_Language Tag_: `taq-Tfng`

_Opentype language system tag:_ `TMH ` and `BBR `

Characters |      |      |      |      |      |      |      |    |  | | |
:-------   | :--  | :--  | :--  | :--  | :--  | :--  | :--  | :-- | :-- | :-- | :--
Tfng       | <span class='nototif normal'>&#x2D30;<span> | <span class='nototif normal'>&#x2D31;<span> | <span class='nototif normal'>&#x2D34;<span> | <span class='nototif normal'>&#x2D36;<span> | <span class='nototif normal'>&#x2D37; / &#x2D38;<span> | <span class='nototif normal'>&#x2D39;<span> | <span class='nototif normal'>&#x2D3C;<span> | <span class='nototif normal'>&#x2D3E;<span> | <span class='nototif normal'>&#x2D42;<span> |<span class='nototif normal'>&#x2D43;<span> |<span class='nototif normal'>&#x2D44;<span>
USV        | 2D30 | 2D31 | 2D34 | 2D36 | 2D37 or 2D38 | 2D39 | 2D3C | 2D3E | 2D42 | 2D43 | 2D44
Latn        | a | b | g | j | d | ḍ | f | k | h | h&#x0323;| &#x025B;
 |  |  |  |  |  |  |  |  | | |
Tfng       | <span class='nototif normal'>&#x2D46;<span> | <span class='nototif normal'>&#x2D48;<span> | <span class='nototif normal'>&#x2D49;<span> | <span class='nototif normal'>&#x2D4C; or &#x2D4B;<span> | <span class='nototif normal'>&#x2D4D;<span> | <span class='nototif normal'>&#x2D4E;<span> | <span class='nototif normal'>&#x2D4F;<span> | <span class='nototif normal'>&#x2D51;<span> | <span class='nototif normal'>&#x2D53;<span> |<span class='nototif normal'>&#x2D54;<span> |<span class='nototif normal'>&#x2D57;<span>
USV        | 2D46 | 2D48 | 2D49 | 2D4C or 2D4B | 2D4D | 2D4E | 2D4F | 2D51 | 2D53 | 2D54 | 2D57
Latn        | x | q | i | z&#x030C; | l | m | n | &#x014B; | o/u | r| &#x0263;
 |  |  |  |  |  |  |  |  | | |
Tfng       | <span class='nototif normal'>&#x2D59;<span> | <span class='nototif normal'>&#x2D5A;<span> | <span class='nototif normal'>&#x2D5B;<span> | <span class='nototif normal'>&#x2D5C;<span> | <span class='nototif normal'>&#x2D5F;<span> | <span class='nototif normal'>&#x2D61;<span> | <span class='nototif normal'>&#x2D62;<span> | <span class='nototif normal'>&#x2D63;<span> | <span class='nototif normal'>&#x2D65;<span> |<span class='nototif normal'>&#x2D66;<span> |
USV        | 2D59 | 2D5A | 2D5B | 2D5C | 2D5F | 2D61 | 2D62 | 2D63 | 2D65 | 2D66 | 
Latn        | s | s&#x0323; | s&#x030C; | t | t&#x0323; | w | y | z | z&#x0323; | e/&#x01DD;/&#x025B;| 
 

### <a id="thv"></a> Tahaggart Tamahaq

_Language tag:_ `thv-Tfng`

_Opentype language system tag:_ `TMH ` and `BBR `

_Keyman keyboard:_ [Tuareg Tifinagh](https://keyman.com/keyboards/tuareg_tifinagh) [taq, thv]

_Font:_ [Akatab](https://software.sil.org/akatab/)

Characters |     |     |     |     |     |     |     |     |     |
:-------   | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :--
Tfng | <span class='akatab normal'>&#x2D30;<span> | <span class='akatab normal'>&#x2D31;<span> | <span class='akatab normal' style='font-feature-settings: "cv03" 1'>&#x2D34;<span>| <span class='akatab normal'>&#x2D36;<span> | <span class='akatab normal'>&#x2D37;<span> | <span class='akatab normal'>&#x2D39;<span> | <span class='akatab normal'>&#x2D3C;<span> | <span class='akatab normal'>&#x2D3E;<span> | <span class='akatab normal'>&#x2D42;<span> 
USV  |2D30 | 2D31 | 2D34 | 2D36      | 2D37 | 2D39      | 2D3C | 2D3E | 2D42
Latn | a   | b    | g    | g&#x030c; | d    | d&#x0323; | f    | k    | h   
 |  |  |  |  |  |  | |  |
Tfng | <span class='akatab normal'>&#x2D46;<span> | <span class='akatab normal'>&#x2D48;<span> | <span class='akatab normal'>&#x2D49;<span>| <span class='akatab normal'>&#x2D4B;<span> | <span class='akatab normal'>&#x2D4C;<span> | <span class='akatab normal'>&#x2D4D;<span> | <span class='akatab normal'>&#x2D4E;<span> | <span class='akatab normal'>&#x2D4F;<span> | <span class='akatab normal'>&#x2D50;<span> 
USV  |2D46 | 2D48 | 2D49 | 2D4B      | 2D4C | 2D4D      | 2D4E | 2D4F | 2D50
Latn | x   | q    | &#x0263;    | j | z&#x0323;    | dd | m    | n    | &#x014b;   
 |  |  |  |  |  |  | |  |
Tfng | <span class='akatab normal'>&#x2D53;<span> | <span class='akatab normal'>&#x2D54;<span> | <span class='akatab normal'>&#x2D57;<span>| <span class='akatab normal'>&#x2D59;<span> | <span class='akatab normal'>&#x2D5B;<span> | <span class='akatab normal'>&#x2D5C;<span> | <span class='akatab normal'>&#x2D5F;<span> | <span class='akatab normal'>&#x2D63;<span> |  
USV  |2D53 | 2D54 | 2D57 | 2D59 | 2D5B | 2D5C | 2D5F | 2D63 | 
Latn | u   | rr    | &#x0263; | s | s&#x030C;s&#x030C; | t | t&#x0323; | zz | 

#### Glyph variants

USV |&#x0020; | &#x0020; | &#x0020;
:--  | :--  | :--  | :--
2D30 | <span class='nototif normal'>&#x2D30;<span>|&#x003E;|<span class='akatab normal'>&#x2D30;<span>
2D34 | <span class='nototif normal' style='font-feature-settings: "cv03" 1'>&#x2D34;<span>|&#x003E;|<span class='akatab normal'>&#x2D34;<span>
2D3C | <span class='nototif normal'>&#x2D3C;<span>|&#x003E;|<span class='akatab normal'>&#x2D3C;<span>
2D4B | <span class='nototif normal'>&#x2D4B;<span>|&#x003E;|<span class='akatab normal'>&#x2D4B;<span>
2D4D | <span class='nototif normal'>&#x2D4D;<span>|&#x003E;|<span class='akatab normal'>&#x2D4D;<span>
2D50 | <span class='nototif normal'>&#x2D50;<span>|&#x003E;|<span class='akatab normal'>&#x2D50;<span>
2D53 | <span class='nototif normal'>&#x2D53;<span>|&#x003E;|<span class='akatab normal'>&#x2D53;<span>
2D5B | <span class='nototif normal'>&#x2D5B;<span>|&#x003E;|<span class='akatab normal'>&#x2D5B;<span>
2D63 | <span class='nototif normal'>&#x2D63;<span>|&#x003E;|<span class='akatab normal'>&#x2D63;<span>



### <a id="thz"></a>Tamajeq, Tayart

_Source_: [Omniglot](https://omniglot.com/writing/tayarttamajeq.htm)

_Language Tag_: `thz-Tfng`

_Opentype language system tag:_ `TMH ` and `BBR `

The order of these characters is based on Unicode codepoints, not on the order listed in Omniglot. 

Characters |     |     |     |     |     |     |     |     |     | | |
:-------   | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- 
Tfng | <span class='nototif normal'>&#x2D30;<span> | <span class='nototif normal'>&#x2D40;<span> | <span class='nototif normal'>&#x2D33;<span> | <span class='nototif normal'>&#x2D36;<span> | <span class='nototif normal'>&#x2D37;<span> | <span class='nototif normal'>&#x2D39;<span> | <span class='nototif normal'>&#x2D3B;<span> | <span class='nototif normal'>&#x2D66;<span> | <span class='nototif normal'>&#x2D3C;<span> | <span class='nototif normal'>&#x2D3E;<span> | <span class='nototif normal'>&#x2D42;<span> 
USV |2D30 | 2D40 | 2D33 | 2D36 | 2D37 | 2D39 | 203B | 2066 | 2D3C | 2D3E | 2D42 
Latn |a | b | g | g&#x030C;| d| d&#x0323; | &#x01DD; | e | f | k | h 
 | |  |  |  |  |  |  | |  |  |
Tfng | <span class='nototif normal'>&#x2D46;<span> | <span class='nototif normal'>&#x2D48;<span> | <span class='nototif normal'>&#x2D49;<span> | <span class='nototif normal'>&#x2D4C;<span> | <span class='nototif normal'>&#x2D4D;<span> | <span class='nototif normal'>&#x2D4E;<span> | <span class='nototif normal'>&#x2D4F;<span> | <span class='nototif normal'>&#x2D51;<span> | <span class='nototif normal'>&#x2D67;<span> | <span class='nototif normal'>&#x2D54;<span>| <span class='nototif normal'>&#x2D55;<span>
USV |2D46 | 2D48 | 2D49 | 2D4C | 2D4D | 2D4E | 2D4F | 2D51| 2D67 | 2D54 |  2D55
Latn |x | q | i | j | l | m | n | &#x014B;| o | r | r&#x0323; |
 | |  |  |  |  |  |  | |  |  |
Tfng | <span class='nototif normal'>&#x2D57;<span> | <span class='nototif normal'>&#x2D59;<span> | <span class='nototif normal'>&#x2D5a;<span> | <span class='nototif normal'>&#x2D5b;<span> | <span class='nototif normal'>&#x2D5c;<span> | <span class='nototif normal'>&#x2D5F;<span> | <span class='nototif normal'>&#x2D53;<span> | <span class='nototif normal'>&#x2D62;<span> | <span class='nototif normal'>&#x2D63; / &#x2D64;<span> | <span class='nototif normal'>&#x2D65;<span>| |
USV |2D57 | 2D59 | 2D5A | 2D5B | 2D5C | 2D5F | 2D53 | 2D62| 2D63 or 2D64 | 2D65 | |
Latn |&#x0263; | s | s&#x0323; | s&#x030c; | t | t&#x0323; | w/u | y | z | z&#x0323; | |

It is unclear if this is meant to be a required bi-consonant.

Other "letters" | |
:-------   | :-- 
Tfng | <span class='nototif normal'>&#x2D5C;&#x2D5B;</span> 
USV  | 2D5C 2D5B
Latn | c&#x030C;

#### Punctuation

All punctuation required for Neo-Tifinagh is also required for `thz`. In addition, the separator mark is used: U+2D70 <span class='nototif normal'>&#x2D70;</span>.

#### Known glyph variants

&#x0020; | &#x0020; | &#x0020;
:--  | :--  | :--
<span class='nototif normal'>&#x2D30;<span>|&#x003E;|<span class='akatab normal'>&#x2D30;<span>
<span class='nototif normal'>&#x2D3C;<span>|&#x003E;|<span class='akatab normal' style='font-feature-settings: "cv02" 2'>&#x2D3C;<span>
<span class='nototif normal'>&#x2D4D;<span>|&#x003E;|<span class='akatab normal'>&#x2D4D;<span>
<span class='nototif normal'>&#x2D5B;<span>|&#x003E;|<span class='akatab normal'>&#x2D5B;<span>
<span class='nototif normal'>&#x2D67;<span>|&#x003E;|<span class='akatab normal'>&#x2D67;<span>

### <a id="ttq"></a>Tawallammat Tamajaq

_Language Tag_: `ttq-Tfng`

_Opentype language system tag:_ `TMH ` and `BBR `

_Keyman keyboard:_ [Tawallammat Tifinagh (SIL)](https://keyman.com/keyboards/sil_tawallammat) [ttq, tzm]

_Font:_ [Tagmukay](https://software.sil.org/tagmukay/)

Characters |     |     |     |     |     |     |     |     |     |
:-------   | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :--
Tfng | <span class='tagmukay normal'>&#x2D30;<span> | <span class='tagmukay normal'>&#x2D36;<span> | <span class='tagmukay normal'>&#x2D39;<span>| <span class='tagmukay normal'>&#x2D3C;<span> | <span class='tagmukay normal'>&#x2D3E;<span> | <span class='tagmukay normal'>&#x2D40;<span> | <span class='tagmukay normal'>&#x2D42;<span> | <span class='tagmukay normal'>&#x2D46;<span> | <span class='tagmukay normal'>&#x2D48;<span> 
USV  |2D30 | 2D36 | 2D39 | 2D3C | 2D3E | 2D40 | 2D42 | 2D46 | 2D48
Latn | a   | g    | d    | f | k    | b | h    | q    | x   
 |  |  |  |  |  |  | |  |
Tfng | <span class='tagmukay normal'>&#x2D4C;<span> | <span class='tagmukay normal'>&#x2D4d;<span> | <span class='tagmukay normal'>&#x2D4e;<span>| <span class='tagmukay normal'>&#x2D4f;<span> | <span class='tagmukay normal'>&#x2D51;<span> | <span class='tagmukay normal'>&#x2D53;<span> | <span class='tagmukay normal'>&#x2D54;<span> | <span class='tagmukay normal'>&#x2D57;<span> | <span class='tagmukay normal'>&#x2D59;<span> 
USV  |2D4C | 2D4D | 2D4E | 2D4F | 2D51 | 2D53 | 2D54 | 2D57 | 2D59
Latn | j   | l    | m    | n | &#x014b;  | w | r    | c    | s   
 |  |  |  |  |  |  | |  |
Tfng | <span class='tagmukay normal'>&#x2D5B;<span> | <span class='tagmukay normal'>&#x2D5C;<span> | <span class='tagmukay normal'>&#x2D62;<span> | <span class='tagmukay normal'>&#x2D64;<span>| <span class='tagmukay normal'>&#x2D67;<span> |  |  |  |  
USV  |2D5B | 2D5C | 2D62 | 2D64 | 2D67 | | | | 
Latn | s&#x030c; | t   | y    | z    | o    | | | | 

Vowels |     |     |     |     |     |  |
:-------   | :-- | :-- | :-- | :-- | :-- | :--
Tfng | <span class='tagmukay normal'>&#x2D30;&#x0302;</span> | <span class='tagmukay normal'>&#x2D62;&#x0323;</span> | <span class='tagmukay normal'>&#x2D62;&#x0302;</span> | <span class='tagmukay normal'>&#x2D53;&#x0302;</span> | <span class='tagmukay normal'>&#x2D67;&#x0302;</span>
USV  | 2D30 + 0302 | 2D62 + 0323 | 2D62 + 0302 | 2D53 + 0302 | 2D67 + 0302
Latn | a | i | e | u | o

**Glyph variants**

USV |&#x0020; | &#x0020; | &#x0020;
:--  | :--  | :--  | :--
2D30 | <span class='nototif normal'>&#x2D30;<span>|&#x003E;|<span class='tagmukay normal'>&#x2D30;<span>
2D3C | <span class='nototif normal'>&#x2D3C;<span>|&#x003E;|<span class='tagmukay normal'>&#x2D3C;<span>
2D4D | <span class='nototif normal'>&#x2D4D;<span>|&#x003E;|<span class='tagmukay normal'>&#x2D4D;<span>
2D53 | <span class='nototif normal'>&#x2D53;<span>|&#x003E;|<span class='tagmukay normal'>&#x2D53;<span>
2D5B | <span class='nototif normal'>&#x2D5B;<span>|&#x003E;|<span class='tagmukay normal'>&#x2D5B;<span>
2D63 | <span class='nototif normal'>&#x2D63;<span>|&#x003E;|<span class='tagmukay normal'>&#x2D63;<span>

**Tri- Bi-Consonants**

USV | 2D7F between characters | → | Glyph 
:----- | :--  | :-- | :-- 
2D3C 2D5C | <span class='tagmukay normal'>&#x2D3C; + &#x2D7F; + &#x2D5C;</span> | → | <span class='tagmukay normal'>&#x2D3C;&#x2D7F;&#x2D5C;</span>
2D4D 2D5C | <span class='tagmukay normal'>&#x2D4D; + &#x2D7F; + &#x2D5C;</span> | → | <span class='tagmukay normal'>&#x2D4D;&#x2D7F;&#x2D5C;</span>
2D4E 2D40 | <span class='tagmukay normal'>&#x2D4E; + &#x2D7F; + &#x2D40;</span> | → | <span class='tagmukay normal'>&#x2D4E;&#x2D7F;&#x2D40;</span>
2D4E 2D59 | <span class='tagmukay normal'>&#x2D4E; + &#x2D7F; + &#x2D59;</span> | → | <span class='tagmukay normal'>&#x2D4E;&#x2D7F;&#x2D59;</span>
2D4E 2D5C | <span class='tagmukay normal'>&#x2D4E; + &#x2D7F; + &#x2D5C;</span> | → | <span class='tagmukay normal'>&#x2D4E;&#x2D7F;&#x2D5C;</span>
2D4F 2D36 | <span class='tagmukay normal'>&#x2D4F; + &#x2D7F; + &#x2D36;</span> | → | <span class='tagmukay normal'>&#x2D4F;&#x2D7F;&#x2D36;</span>
2D4F 2D39 | <span class='tagmukay normal'>&#x2D4F; + &#x2D7F; + &#x2D39;</span> | → | <span class='tagmukay normal'>&#x2D4F;&#x2D7F;&#x2D39;</span>
2D4F 2D3C | <span class='tagmukay normal'>&#x2D4F; + &#x2D7F; + &#x2D3C;</span> | → | <span class='tagmukay normal'>&#x2D4F;&#x2D7F;&#x2D3C;</span>
2D4F 2D3C 2D5C | <span class='tagmukay normal'>&#x2D4F; + &#x2D7F; + &#x2D3C; + &#x2D7F; + &#x2D5C;</span> | → | <span class='tagmukay normal'>&#x2D4F;&#x2D7F;&#x2D3C;&#x2D7F;&#x2D5C;</span>
2D4F 2D3E | <span class='tagmukay normal'>&#x2D4F; + &#x2D7F; + &#x2D3E;</span> | → | <span class='tagmukay normal'>&#x2D4F;&#x2D7F;&#x2D3E;</span>
2D4F 2D4C | <span class='tagmukay normal'>&#x2D4F; + &#x2D7F; + &#x2D4C;</span> | → | <span class='tagmukay normal'>&#x2D4F;&#x2D7F;&#x2D4C;</span>
2D4F 2D57 | <span class='tagmukay normal'>&#x2D4F; + &#x2D7F; + &#x2D57;</span> | → | <span class='tagmukay normal'>&#x2D4F;&#x2D7F;&#x2D57;</span>
2D4F 2D59 | <span class='tagmukay normal'>&#x2D4F; + &#x2D7F; + &#x2D59;</span> | → | <span class='tagmukay normal'>&#x2D4F;&#x2D7F;&#x2D59;</span>
2D4F 2D5C | <span class='tagmukay normal'>&#x2D4F; + &#x2D7F; + &#x2D5C;</span> | → | <span class='tagmukay normal'>&#x2D4F;&#x2D7F;&#x2D5C;</span>
2D4F 2D64 | <span class='tagmukay normal'>&#x2D4F; + &#x2D7F; + &#x2D64;</span> | → | <span class='tagmukay normal'>&#x2D4F;&#x2D7F;&#x2D64;</span>
2D54 2D5C | <span class='tagmukay normal'>&#x2D54; + &#x2D7F; + &#x2D5C;</span> | → | <span class='tagmukay normal'>&#x2D54;&#x2D7F;&#x2D5C;</span>
2D59 2D5C | <span class='tagmukay normal'>&#x2D59; + &#x2D7F; + &#x2D5C;</span> | → | <span class='tagmukay normal'>&#x2D59;&#x2D7F;&#x2D5C;</span>
2D5B 2D5C | <span class='tagmukay normal'>&#x2D5B; + &#x2D7F; + &#x2D5C;</span> | → | <span class='tagmukay normal'>&#x2D5B;&#x2D7F;&#x2D5C;</span>

Contextual Shaping |     |     |     |     |     |  |
:-------   | :-- | :-- | :-- | :-- | :-- | :--
<span class='tagmukay normal'>&#x2D4D;</span> | + | <span class='tagmukay normal'>&#x2D4D;</span> | + | <span class='tagmukay normal'>&#x2D4D;</span> | → | <span class='tagmukay normal'>&#x2D4D;&#x2D4D;&#x2D4D;</span>
2D4D | | 2D4D | | 2D4D | | |
| | | | | |
<span class='tagmukay normal'>&#x2D4D;</span> | + | <span class='tagmukay normal'>&#x2D4F;</span>| + |<span class='tagmukay normal'>&#x2D4D;</span> | → | <span class='tagmukay normal'>&#x2D4D;&#x2D4F;&#x2D4D;</span>
2D4D | | 2D4F | | 2D4D | |
| | | | | |
<span class='tagmukay normal'>&#x2D4F;</span> | + | <span class='tagmukay normal'>&#x2D4D;</span> | + | <span class='akatab normal'>&#x2D4F;</span>| → | <span class='tagmukay normal'>&#x2D4F;&#x2D4D;&#x2D4F;</span>
2D4F | | 2D4D | | 2D4F | | 
| | | | | |
<span class='tagmukay normal'>&#x2D4F;</span> | + | <span class='tagmukay normal'>&#x2D4F;</span>| + | <span class='tagmukay normal'>&#x2D4F;</span> | → | <span class='tagmukay normal'>&#x2D4F;&#x2D4F;&#x2D4F;</span>
2D4F | | 2D4F | | 2D4F | |

#### Punctuation

All punctuation required for Neo-Tifinagh is also required for `ttq`. In addition, the separator mark is used: U+2D70 <span class='tagmukay normal'>&#x2D70;</span>.

## <a id="work"></a>Still working on - confusing sources

### <a id="kab_etc"></a>Taqbaylit, Tumzabt, Tacenwit, Tacawit, Tamahaq (Neo-Tifinagh in Algeria), Tahaggart Tamahaq, Tachawit, Tachelhit, Tumzabt

_**Source**_: Savage, 2003. p. 2.

_Language Tags_: `kab-Tfng`, `mzb-Tfng`, `shi-Tfng`, `shy-Tfng, `thv-Tfng`

This set of characters is used in a Algerian school text book entitled “Adlis” printed in 1988 (pp 12,13). It is unknown how widely used this book (or the characters) are actually used.

The glyphs or codepoints for y, h, and i may be incorrect.

Characters |      |      |      |      |      |      |      |    |  | |
:-------   | :--  | :--  | :--  | :--  | :--  | :--  | :--  | :-- | :-- | :-- | 
Tfng       | <span class='nototif normal'>&#x2D30;<span> | <span class='nototif normal'>&#x2D30;&#x0302;<span> | <span class='nototif normal'>&#x2D33;<span> | <span class='nototif normal'>&#x2D35;<span> | <span class='nototif normal'>&#x2D37;<span> | <span class='nototif normal'>&#x2D39;<span> | <span class='nototif normal'>&#x2D3B;<span> | <span class='nototif normal'>&#x2D3C;<span> | <span class='nototif normal'>&#x2D3D;<span> | |
USV        | 2D30 | 2D30 0302 | 2D33 | 2D35 | 2D37 | 2D39 | 2D3B | 2D3C | 2D3D |
Latn        | a | ɛ | g | g&#x030c; | d | ḍ | c | f | k |
 |  |  |  |  |  |  |  |  | | |
Tfng       | <span class='nototif normal'>&#x2D40;<span> | <span class='nototif normal'>&#x2D43;<span> | <span class='nototif normal'>&#x2D44;<span> | <span class='nototif normal'>&#x2D45;<span> | <span class='nototif normal'>&#x2D47;<span> | <span class='nototif normal'>&#x2D49;<span> | <span class='nototif normal'>&#x2D4A;<span> | <span class='nototif normal'>&#x2D4D;<span> | <span class='nototif normal'>&#x2D4E;<span> | <span class='nototif normal'>&#x2D4F;<span> 
USV        | 2D40 | 2D43 | 2D44 | 2D45 | 2D47 | 2D49 | 2D4A | 2D4D | 2D4E | 2D4F 
Latn        | b | h&#x0323; | h | x | q | i | j | l | m | n
 |  |  |  |  |  |  |  |  | | |
Tfng        | <span class='nototif normal'>&#x2D53;<span> | <span class='nototif normal'>&#x2D54;<span> | <span class='nototif normal'>&#x2D59;<span> | <span class='nototif normal'>&#x2D5B;<span> | <span class='nototif normal'>&#x2D5C;<span> | <span class='nototif normal'>&#x2D5F;<span> | <span class='nototif normal'>&#x2D61;<span> | <span class='nototif normal'>&#x2D62;<span> | <span class='nototif normal'>&#x2D63;<span> | 
USV        | 2D53 | 2D54 | 2D59 | 2D5B | 2D5C | 2D5F | 2D61 | 2D62 | 2D63 
Latn        | u | r / r&#x0323; | s / s&#x0323; | c / c&#x030C; | t | t&#x0323; | w | y | z / z&#x0323;

#### Known glyph variants

&#x0020; | &#x0020; | &#x0020;
:--  | :--  | :--
<span class='nototif normal'>&#x2D30;<span> | &#x003E; | <span class='akatab normal'>&#x2D30;<span>
<span class='nototif normal'>&#x2D30;&#x0302;<span>|&#x003E;|<span class='akatab normal'>&#x2D30;&#x0302;<span>
<span class='nototif normal'>&#x2D3C;<span>|&#x003E;|<span class='akatab normal'>&#x2D3C;<span>
<span class='nototif normal'>&#x2D4D;<span>|&#x003E;|<span class='akatab normal'>&#x2D4D;<span>
<span class='nototif normal'>&#x2D53;<span>|&#x003E;|<span class='akatab normal'>&#x2D53;<span>
<span class='nototif normal'>&#x2D5B;<span>|&#x003E;|<span class='akatab normal'>&#x2D5B;<span>

#### Bi-consonants

n2739 page 36 lists some bi-consonants used in the L'Ahaggar. These would likely be for `thv-Tfng`

### <a id="thz_a"></a>Tuareg (Aïr dialect of Niger)

_Source_: Aghali-Zakara chart in Unicode proposal n2739 page 31.

_Language Tag_: `thz-Tfng`

Omniglot lists a different set of characters for `thz`

Characters |     |     |     |     |     |     |     |     |     | | |
:-------   | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- 
Tfng | <span class='nototif normal'>&#x2D30;<span> | <span class='nototif normal'>&#x2D40;<span> | <span class='nototif normal'>&#x2D39;<span> | <span class='nototif normal'>&#x2D3C;<span> | <span class='nototif normal'>&#x2D36;<span> | <span class='nototif normal'>&#x2D58;<span> | <span class='nototif normal'>&#x2D42;<span> | <span class='nototif normal'>&#x2D4C;<span> | <span class='nototif normal'>&#x2D3E;<span> | <span class='nototif normal'>&#x2D4D;<span> |
USV |2D30 | 2D40 | 2D39 | 2D3C | 2D36 | 2D58 | 2D42 | 2D4C| 2D3E | 2D4D | 
Latn |a | b | d | f | g | &#x0263; | h | j| k | l |
 | |  |  |  |  |  |  | |  |  |
Tfng | <span class='nototif normal'>&#x2D4E;<span> | <span class='nototif normal'>&#x2D4F;<span> | <span class='nototif normal'>&#x2D47;<span> | <span class='akanototab-R normal'>&#x2D54;<span> | <span class='nototif normal'>&#x2D59;<span> | <span class='nototif normal'>&#x2D5B;<span> | <span class='nototif normal'>&#x2D5C;<span> | <span class='nototif normal'>&#x2D53;<span> | <span class='nototif normal'>&#x2D57;<span> | <span class='nototif normal'>&#x2D62;<span>| <span class='nototif normal'>&#x2D63;<span>
USV |2D4E | 2D4F | 2D47 | 2D54 | 2D59 | 2D5B | 2D5C | 2D53| 2D57 | 2D62 |  2D63
Latn |m | n | q | r | s | &#x161; | t | w| x | y | z |

2D57 is listed twice. I changed the first one to 2D47 (horizontal 3 dots instead of vertical)


### <a id="tda"></a>Tuareg (Azawagh dialect of Niger-Mali), Tagdal

_**Source**_: Aghali-Zakara chart in Unicode proposal

_**Language Tag**_: `tda-Tfng-NE`

Characters |     |     |     |     |     |     |     |     |     | | | |
:-------   | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- 
Tfng | <span class='nototif normal'>&#x2D30;<span> | <span class='nototif normal'>&#x2D40;<span> | <span class='nototif normal'>&#x2D39;<span> | <span class='nototif normal'>&#x2D3C;<span> | <span class='nototif normal'>&#x2D36;<span> | <span class='nototif normal'>&#x2D57;<span> | <span class='nototif normal'>&#x2D42;<span> | <span class='nototif normal'>&#x2D4C;<span> | <span class='nototif normal'>&#x2D3E;<span> | <span class='nototif normal'>&#x2D4D;<span>| <span class='nototif normal'>&#x2D4E;<span>  
USV |2D30 | 2D40 | 2D39 | 2D3C | 2D36 | 2D57 | 2D42 | 2D4C| 2D3E | 2D4D | 2D4E 
Latn |a | b | d | f | g | &#x0263; | h | j| k | l | m  
 | |  |  |  |  |  |  |  |  |  
Tfng  | <span class='nototif normal'>&#x2D4F;<span> | <span class='nototif normal'>&#x2D46;<span> | <span class='nototif normal'>&#x2D54;<span> | <span class='nototif normal'>&#x2D59;<span> | <span class='nototif normal'>&#x2D5B;<span> | <span class='nototif normal'>&#x2D5C;<span> | <span class='nototif normal'>&#x2D53;<span> | <span class='nototif normal'>&#x2D48;<span> | <span class='nototif normal'>&#x2D62;<span>| <span class='nototif normal'>&#x2D63;<span> | <span class='nototif normal'>&#x2D64;<span>
USV | 2D4F | 2D46 | 2D54 | 2D59 | 2D5B | 2D5C | 2D53| 2D48 | 2D62 |  2D63 | 2D64
Latn | n | q | r | s | s&#x030C; | t | w | x| y | z | z&#x0323;

#### Known glyph variants

&#x0020; | &#x0020; | &#x0020;
:--  | :--  | :--
<span class='nototif normal'>&#x2D30;<span>|&#x003E;|<span class='akatab normal'>&#x2D30;<span>
<span class='nototif normal'>&#x2D3C;<span>|&#x003E;|<span class='akatab normal'>&#x2D3C;<span>
<span class='nototif normal'>&#x2D4D;<span>|&#x003E;|<span class='akatab normal'>&#x2D4D;<span>
<span class='nototif normal'>&#x2D53;<span>|&#x003E;|<span class='akatab normal'>&#x2D53;<span>



### <a id="ttq_tmh"></a>Tawallammat Tamajaq, Tamashek

_**Source**_: ??? 

_**Language Tag**_: `ttq-Tfng`, `tmh-Tfng` (macrolanguage)

Characters |     |     |     |     |     |     |     |     |     | |
:-------   | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- 
Tfng | <span class='akatab normal'>&#x2D40;<span> | <span class='akatab normal'>&#x2D57;<span> | <span class='akatab normal'>&#x2D39;<span> | <span class='akatab normal'>&#x2D3C;<span> | <span class='akatab normal'>&#x2D36;<span> | <span class='akatab normal'>&#x2D42;<span> | <span class='akatab normal'>&#x2D4C;<span> | <span class='akatab normal'>&#x2D3E;<span> |<span class='akatab normal'>&#x2D4D;<span> | <span class='akatab normal'>&#x2D4E;<span>
USV | 2D40 | 2D57 | 2D39 | 2D3C | 2D36 | 2D42 | 2D4C | 2D3E |2D4D | 2D4E 
Latn | b | ɣ | d | f | g | h | j | k | l | m
 | | | | | | | | | |
Tfng | <span class='akatab normal'>&#x2D4F;<span> | <span class='akatab normal'>&#x2D51;<span> | <span class='akatab normal'>&#x2D46;<span> | <span class='akatab normal'>&#x2D54;<span> | <span class='akatab normal'>&#x2D59;<span> | <span class='akatab normal'>&#x2D5B;<span> | <span class='akatab normal'>&#x2D5C;<span> | <span class='akatab normal'>&#x2D53;<span> | <span class='akatab normal'>&#x2D48;<span> | <span class='akatab normal'>&#x2D62;<span>
USV | 2D4F | 2D51 | 2D46 | 2D54 | 2D59 | 2D5B | 2D5C | 2D53 | 2D48 | 2D62
Latn | n | ŋ | q | r | s | š | t | w | x | y
 | | | | | | | | | |
Tfng | <span class='akatab normal'>&#x2D49;</span> | <span class='akatab normal'>&#x2D64;</span> | <span class='akatab normal'>&#x2D30;</span>
USV | 2D49 | 2D64 | 2D30
Latn | i/y | z | ɑ

Auxiliary | |
:-------   | :--
Tfng | <span class='akatab normal'>&#x2D63;</span>
USV  | 2D63
Latn | z

#### Vowels

SIL and APT have differing orthographies for the same language

##### _SIL_

Vowels |     |     |     |     |     |  |
:-------   | :-- | :-- | :-- | :-- | :-- | :--
Tfng | <span class='akatab normal'>&#x2D30;&#x0302;</span> | <span class='akatab normal'>&#x2D30;&#x0306;</span> | <span class='akatab normal'>&#x2D62;&#x0323;</span> | <span class='akatab normal'>&#x2D62;&#x0302;</span> | <span class='akatab normal'>&#x2D53;&#x0302;</span> | <span class='akatab normal'>&#x2D67;&#x0302;</span>
USV  | 2D30 + 0302 | 2D30 + 0306 | 2D62 + 0323 | 2D62 + 0302 | 2D53 + 0302 | 2D67 + 0302
Latn | ɑ | ǝ | i | e | u | o


##### _APT_

Vowels |     |     |     |     |     |  |
:-------   | :-- | :-- | :-- | :-- | :-- | :--
Tfng | <span class='akatab normal'>&#x2D30;</span>    | <span class='akatab normal'>&#x2D66;</span>    | <span class='akatab normal'>&#x2D62;</span>    | <span class='akatab normal'>&#x2D67;</span> |  | 
USV  | 2D30 | 2D66 | 2D62 | 2D67 | | 
Latn | ɑ | ǝ | i | e | u | o

#### Punctuation

All punctuation required for Neo-Tifinagh is also required for `ttq`. In addition, the separator mark is used: U+2D70 <span class='nototif normal'>&#x2D70;</span>.

#### Contextual Shaping

Contextual Shaping |     |     |     |     |     
:-------   | :-- | :-- | :-- | :-- 
<span class='akatab normal'>&#x2D4D;</span> | + | <span class='akatab normal'>&#x2D4D;</span> | → | <span class='akatab normal'>&#x2D4D;&#x2D4D;</span>
2D4D | | 2D4D | | |
| | | | 
<span class='akatab normal'>&#x2D4D;</span> | + | <span class='akatab normal'>&#x2D4F;</span> | → | <span class='akatab normal'>&#x2D4D;&#x2D4F;</span>
2D4D | | 2D4F | | 
| | | | 
<span class='akatab normal'>&#x2D4F;</span> | + | <span class='akatab normal'>&#x2D4D;</span> | → | <span class='akatab normal'>&#x2D4F;&#x2D4D;</span>
2D4F | | 2D4D | |
| | | | 
<span class='akatab normal'>&#x2D4F;</span> | + | <span class='akatab normal'>&#x2D4F;</span> | → | <span class='akatab normal'>&#x2D4F;&#x2D4F;</span>
2D4F | | 2D4F | |







## <a id="other"></a>Other languages with no information

These language are reported to have used or are using Tifinagh script. However, no further information is available.

### <a id="auj"></a>Awjilah

_Language Tag_: auj-Tfng 	

_Opentype language system tag:_ `BBR `

### <a id="gha"></a>Ghadamès

_Language Tag_: gha-Tfng

_Opentype language system tag:_ `BBR `

### <a id="nxm"></a>Numidian

_Language Tag_: nxm-Tfng

### <a id="grr"></a>Taznatit

_Language Tag_: grr-Tfng

_Opentype language system tag:_ `BBR `

### <a id="tez"></a>Tetserret

_Language Tag_: tez-Tfng

_Opentype language system tag:_ `BBR `

### <a id="zen"></a>Zenaga

_Language Tag_: zen-Tfng

_Opentype language system tag:_ `BBR `

## <a id="ref"></a>References

[Omniglot - Central Atlas Tamazight &#x28;Tamaziɣt / ⵜⴰⵎⴰⵣⵉⵖⵜ&#x29; &#x5B;tzm&#x5D;](https://omniglot.com/writing/tamazight.htm)

[Omniglot - Kabyle &#x28;Taqbaylit / ⵜⴰⵇⴱⴰⵢⵍⵉⵜ&#x29; &#x5B;kab&#x5D;](https://omniglot.com/writing/kabyle.php)

[Omniglot - Riffian &#x28;Tarifit / ⵜⴰⵔⵉⴼⵉⵜ&#x200E; / تاريفيت&#x200e;&#x29; &#x5B;rif&#x5D;](https://omniglot.com/writing/riffian.htm)

[Omniglot - Shilha &#x28;Tašəlḥiyt / ⵜⴰⵛⵍⵃⵉⵢⵜ&#x29; &#x5B;gho&#x5D;](https://omniglot.com/writing/shilha.htm)

[Omniglot - Siwi &#x28;ⴶⵍⴰⵏⵏⵉⵙⵉⵡⴰⵏ / Jlan n isiwan&#x29; &#x5B;siz&#x5D;](https://omniglot.com/writing/siwi.htm)

[Omniglot - Tamasheq &#x28;Tafaghist&#x29; &#x5B;taq&#x5D;](https://omniglot.com/writing/tamasheq.htm) (but could be other languages?)

[Omniglot - Tayart Tamajeq &#x28;Tamajeq, ⵜⵎⵌⵆ, ثمجق&#x200e;&#x29; &#x5B;thz&#x5D;](https://omniglot.com/writing/tayarttamajeq.htm)

[Tifinaghe-IRCAM &#x5B;tzm&#x5D;](https://www.win.tue.nl/~aeb/natlang/berber/tifinagh/tifinagh-ircam.html)

Aghali-Zakara, M. 1994. "Graphies berbères et dilemme de diffusion: interactions des alphabets latin, ajami et tifinagh, Etudes et Documents berbères, 11, 1994 : 107-121.

Andries, P. 2004-06-06. Proposal to add the Tifinagh Script. N2739R ISO/IEC JTC 1/SC 2/WG 2 N2739. http://anubis.dkuug.dk/jtc1/sc2/wg2/docs/n2739.pdf.

____. 2005. Inventaire des oeils de la police pan-berbère Hapax Berbère. http://hapax.qc.ca/polices/inventaire-des-oeils.pdf (accessed 19-May-2008)

de Foucauld, Charles Eugène. 1951. Dictionnaire touareg–français, dialecte de l’Ahaggar. 4 vols. [Paris]: Imprimerie nationale de France.

Savage, Andrew. 2000. Writing Tuareg Vowels. Advantages and Disadvantages of the Three Script Options: Arabic, Tifinagh and Roman. Submitted in partial fulfillment of the requirements for the degree of Master of Letters in Linguistics from the Univerisity of New England, New South Wales, Australia.

_____. 2003. Tifinagh Unicode Propositions, Stanthorpe, http://www.unicode.org/L2/L2003/03143-tifinagh-samples.pdf


[ALPHABETS OF TAMASHEK IN MALI](http://web.archive.org/web/20031210100153/wwwusers.imaginet.fr/~yusuf/tamashek.html)

[Entrance to Kidal.](https://en-academic.com/dic.nsf/enwiki/18396)

(Souad Sahraoui. 2021. English and the Languages of Algeria: Suggestions towards a New Language Policy)[https://www.academia.edu/75532503/English_and_the_Languages_of_Algeria_Suggestions_towards_a_New_Language_Policy]

(lexilogos.com input)[https://www.lexilogos.com/clavier/tifinagh.htm]

(Tamazight: Neo-Tifinagh orthography notes)[https://r12a.github.io/scripts/tfng/zgh.html]

(The Tifinagh alphabet)[https://www.win.tue.nl/~aeb/natlang/berber/tifinagh/tifinagh.html]

(Grammaire Tamachek)[https://www.win.tue.nl/~aeb/natlang/berber/tifinagh/tifinagh-hanoteau.html]

(Livre I)[https://www.win.tue.nl/~aeb/natlang/berber/tifinagh/tifinagh-basset.html]

(P. Thott-Hansen, Kortfattet Dansk Haandbog i de vigstigste af Afrikas Sprog, København, 1969.)[https://www.win.tue.nl/~aeb/natlang/berber/tifinagh/tifinagh-thott-hansen.html]

(Comparaison entre le libyque (occidental et oriental), le tifinagh saharien, six variations du système touarègue et le néo-tifinagh développé par l'Académie berbère)[https://www.win.tue.nl/~aeb/natlang/berber/tifinagh/tifinagh-mondeberbere.html]

                                                                   
