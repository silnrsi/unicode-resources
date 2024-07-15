---
title: Unicode Technical Note xx - Representing Tifinagh in Unicode (proposed draft)
---

_Lorna Evans, SIL International (15-Jul-2024)_

_This is a work in progress. Additional information on language usage is most welcome._

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
  - <a href="#taq-ML">Tamasheq (Mali) &#x005B;taq&#x005D;</a>
  - <a href="#tda">Tagdal, Tuareg (Azawagh dialect of Niger-Mali) &#x005B;tda&#x005D;</a>
  - <a href="#thv">Tahaggart Tamahaq &#x005B;thv&#x005D;</a>
  - <a href="#thz">Tayart Tamajeq,  &#x005B;thz&#x005D;</a>
  - <a href="#ttq">Tawallammat Tamajaq &#x005B;ttq&#x005D;</a>
- <a href="#other">Other languages with little or no information</a>
  - <a href="#auj">Awjilah &#x005B;auj&#x005D;</a>
  - <a href="#gha">Ghadamès &#x005B;gha&#x005D;</a>
  - <a href="#grr">Taznatit &#x005B;grr&#x005D;</a>
  - <a href="#jbn">Nafusi, Zuwara &#x005B;jbn&#x005D;</a>
  - <a href="#mzb">Tumzabt &#x005B;mzb&#x005D;</a>
  - <a href="#nxm">Numidian &#x005B;nxm&#x005D;</a>
  - <a href="#shy">Tachawit, Tacawit &#x005B;shy&#x005D;</a>
  - <a href="#tez">Tetserret &#x005B;tez&#x005D;</a>
  - <a href="#zen">Zenaga &#x005B;zen&#x005D;</a>
- <a href="#ack">Acknowledgements</a>
- <a href="#ref">References</a>

## <a id="intro"></a>Introduction

Tifinagh is encoded in the U+2D30..U+2D7F block of Unicode. The encoding in the Tifinagh block is based on the modern alphabet called Neo-Tifinagh. It also includes the characters required for modern Tuareg.

This document gives guidance on the encoding of _modern orthographies_ using the Tifinagh script (no attempt is made to document all the variants used in ancient Tifinagh orthographies). Since the script is used for a number of orthographies covering different languages, the development of this document is ongoing. In terms of the Unicode standard, this document is purely informative since it is concerned with issues not covered by that standard. 

This document also gives guidance on font development for the different _modern_ orthographies and languages.

## <a id="uni"></a>The Unicode Model

### <a id="cons"></a>Basic Consonants

The basic consonants are relatively obvious and can be discovered by viewing the Unicode charts.

**Design**: There can be some design issues related to "dotted" characters especially when the design is similar. When these characters appear together, they can be difficult to read unless care is taken by the type designer to change the size or spacing of the dots: <span class='akatab normal'>&#x2D30;&#x2D53;&#x2D3E;&#x2D46;&#x2D58;&#x2D30;</span>. The design of the Neo-Tifinagh dotted characters reduces the level of confusion when adjacent to each other: <span class='nototif normal'>&#x2D30;&#x2D53;&#x2D3E;&#x2D46;&#x2D58;&#x2D30;</span>. Sidebearings on characters are still important.

### <a id="vowel"></a>Vowels

Vowels are not as clearly defined. Four vowels have been encoded for Neo-Tifinagh. However, different traditional Tifinagh orthographies may demonstrate vowels using combining marks in different ways. These vowels are primarily used as an aid in learning to read.

#### _SIL-Niger_

Vowels |     |     |     |     |     |  |
:--    | :-- | :-- | :-- | :-- | :-- | :--
Tfng   | <span class='akatab normal'>&#x2D30;&#x0302;</span> | <span class='akatab normal'>&#x2D30;&#x0306;</span> | <span class='akatab normal'>&#x2D62;&#x0323;</span> | <span class='akatab normal'>&#x2D62;&#x0302;</span> | <span class='akatab normal'>&#x2D53;&#x0302;</span> | <span class='akatab normal'>&#x2D67;&#x0302;</span>
USV    | 2D30 + 0302 | 2D30 + 0306 | 2D62 + 0323 | 2D62 + 0302 | 2D53 + 0302 | 2D67 + 0302

#### _APT_

Vowels |     |     |     |     |     |  |
:--    | :-- | :-- | :-- | :-- | :-- | :--
Tfng   | <span class='hapaxtuareg normal'>&#x2D30;</span>    | <span class='hapaxtuareg normal'>&#x2D66;</span>    | <span class='hapaxtuareg normal'>&#x2D62;</span>    | <span class='hapaxtuareg normal'>&#x2D67;</span> | <span class='hapaxtuareg normal'>&#xE040;</span> | <span class='hapaxtuareg normal'>&#xE541;</span>
USV  | 2D30 | 2D66 | 2D62 | 2D67 | 2D66 0302 | 2D67 0302 

#### _Hawad_

_Positioning of U+0308 is incorrect in most fonts_

Vowels |     |     |     |     |     |  |
:-------   | :-- | :-- | :-- | :-- | :-- | :--
Tfng | <span class='hapaxtuareg normal'>&#xE600;</span>    | <span class='hapaxtuareg normal'>&#xE601;</span>  | <span class='hapaxtuareg normal'>&#xE602;</span>  | <span class='hapaxtuareg normal'>&#xE603;</span>    | <span class='hapaxtuareg normal'>&#xE604;</span> |  
USV  | 2D5D 0307 | 2D5D 0308 | 2D5D | 2D49 0307 | 2D49 0308 | 

### <a id="punct"></a>Punctuation

Western-style punctuation signs are used in Tifinagh. Words are separated by a space. 

_A few languages use a special separator mark which has been encoded in the Tifinagh block._ The languages using the separator mark will be indicated in the section on that language. Otherwise, punctuation is not listed in each section.


Punctuation |      |      |      |      |      |      | | |
:----       | :--  | :--  | :--  | :--  | :--  | :--  | :-- | :--
Tfng        | <span class='nototif normal'>.</span>    | <span class='nototif normal'>,</span>    | <span class='nototif normal'>;</span>    | <span class='nototif normal'>:</span>    | <span class='nototif normal'>?</span>    | <span class='nototif normal'>!</span>    | <span class='nototif normal'>...</span> | <span class='nototif normal'>&#x2D70;</span>
USV         | 002E | 002C | 003B | 003A | 003F | 0021 | 2026 | 2D70

#### Digits

There is no common way to write numbers using Tifinagh script. The IRCAM Tifinagh uses the usual Western-style digits.

### <a id="variant"></a>Variant Glyphs

This chart includes a sampling of some of the possible glyph variants in current use. It does not demonstrate all of the possible historical glyph variants. In addition, because of the issues relating to <a href="#dir">Writing Direction</a>, there are variants which are mirrored or turned for right to left text or even for vertical text. Those variants are not included here.

Because these glyphs are taken from various fonts, the height of a particular glyph should not be considered significant.

|  | 2D3     | 2D4      | 2D5      | 2D6      | 2D7    
:- | :--     | :--      | :--      | :--      | :--
0  |<span class='nototif normal'>&#x2D30;</span> (<span class='hapaxrond normal'>&#xE002;</span> <span class='akatab normal'>&#x2D30;</span>)| <span class='nototif normal'>&#x2D40;</span> (<span class='hapaxrond normal'>&#xF005;</span> <span class='akatab normal' style='font-feature-settings: "cv11" 1'>&#x2D40;</span>)| <span class='nototif normal'>&#x2D50;</span> (<span class='akatab normal'>&#x2D50;</span> <span class='akatab normal'style='font-feature-settings: "cv04" 1'>&#x2D50;</span> <span class='hapaxtuareg normal'>&#x2D50;</span> <span class='hapaxrond normal'>&#x2D50;</span>)| <span class='nototif normal'>&#x2D60;</span> | <span class='nototif normal'>&#x2D70;</span>
1  |<span class='nototif normal'>&#x2D31;</span> (<span class='hapaxtuareg normal'>&#xF005;</span> <span class='akatab normal' style='font-feature-settings: "cv08" 1'>&#x2D31;</span>)| <span class='nototif normal'>&#x2D41;</span> | <span class='nototif normal'>&#x2D51;</span> | <span class='nototif normal'>&#x2D61;</span> | 
2  |<span class='nototif normal'>&#x2D32;</span> (<span class='hapaxtuareg normal'>&#xF1D5;</span>) | <span class='nototif normal'>&#x2D42;</span> (<span class='hapaxtuareg normal'>&#xE01E;</span>) | <span class='nototif normal'>&#x2D52;</span> | <span class='nototif normal'>&#x2D62;</span> (<span class='akatab normal'>&#x2D62;</span> <span class='hapaxtuareg normal'>&#xE531;</span> <span class='hapaxrond normal'>&#xE570;</span> <span class='hapaxrond normal'>&#xF208;</span>)| 
3  |<span class='nototif normal'>&#x2D33;</span> (<span class='akatab normal' style='font-feature-settings: "cv09" 1'>&#x2D33;</span>)| <span class='nototif normal'>&#x2D43;</span> | <span class='nototif normal'>&#x2D53;</span> (<span class='hapaxtuareg normal'>&#x2D53;</span> <span class='hapaxrond normal'>&#x2D53;</span>)| <span class='nototif normal'>&#x2D63;</span> (<span class='akatab normal'>&#x2D63;</span> <span class='akatab normal' style='font-feature-settings: "cv06" 1'>&#x2D63;</span>)| 
4  |<span class='nototif normal'>&#x2D34;</span> (<span class='akatab normal' style='font-feature-settings: "cv03" 1'>&#x2D34;</span> <span class='hapaxrond normal'>&#xE8BD;</span> <span class='hapaxrond normal'>&#xE517;</span> <span class='hapaxrond normal'>&#xE519;</span>)| <span class='nototif normal'>&#x2D44;</span> (<span class='hapaxrond normal'>&#xF5D1;</span>)| <span class='nototif normal'>&#x2D54;</span> (<span class='hapaxtuareg normal'>&#xF121;</span>) | <span class='nototif normal'>&#x2D64;</span> | 
5  |<span class='nototif normal'>&#x2D35;</span> | <span class='nototif normal'>&#x2D45;</span> | <span class='nototif normal'>&#x2D55;</span> (<span class='hapaxtuareg normal'>&#xF7C1;</span>)| <span class='nototif normal'>&#x2D65;</span> (<span class='akatab normal'>&#x2D65;</span> <span class='hapaxtuareg normal'>&#xF253;</span>)| 
6  |<span class='nototif normal'>&#x2D36;</span> (<span class='akatab normal' style='font-feature-settings: "cv10" 1'>&#x2D36;</span>)| <span class='nototif normal'>&#x2D46;</span> | <span class='nototif normal'>&#x2D56;</span> | <span class='nototif normal'>&#x2D66;</span> | 
7  |<span class='nototif normal'>&#x2D37;</span> | <span class='nototif normal'>&#x2D47;</span> | <span class='nototif normal'>&#x2D57;</span> (<span class='hapaxtuareg normal'>&#xE01A;</span>)| <span class='nototif normal'>&#x2D67;</span> (<span class='akatab normal'>&#x2D67;</span>)| 
8  |<span class='nototif normal'>&#x2D38;</span> (<span class='akatab normal' style='font-feature-settings: "cv15" 1'>&#x2D38;</span>)| <span class='nototif normal'>&#x2D48;</span> (<span class='hapaxtuareg normal'>&#xE06E;</span>)| <span class='nototif normal'>&#x2D58;</span> |  | 
9  |<span class='hapaxtuareg normal'>&#x2D39;</span> (<span class='nototif normal'>&#x2D39;</span> <span class='hapaxrond normal'>&#x2D39;</span>)| <span class='nototif normal'>&#x2D49;</span> (<span class='hapaxrond normal'>&#xE070;</span> <span class='hapaxrond normal'>&#x2D49;</span>) | <span class='nototif normal'>&#x2D59;</span> (<span class='hapaxtuareg normal'>&#xF002;</span>) |  | 
A  |<span class='nototif normal'>&#x2D3A;</span> (<span class='hapaxtuareg normal'>&#xF016;</span>) | <span class='nototif normal'>&#x2D4A;</span> | <span class='nototif normal'>&#x2D5A;</span> (<span class='akatab normal'>&#x2D5A;</span> <span class='nototifagraw normal'>&#x2D5A;</span>)|  | 
B  |<span class='nototif normal'>&#x2D3B;</span> (<span class='nototifagraw normal'>&#x2D3B;</span> <span class='hapaxrond normal'>&#xE040;</span>)| <span class='nototif normal'>&#x2D4B;</span> (<span class='akatab normal'>&#x2D4B;</span> <span class='akatab normal' style='font-feature-settings: "cv07" 1'>&#x2D4B;</span>)| <span class='nototif normal'>&#x2D5B;</span> (<span class='akatab normal'>&#x2D5B;</span> <span class='akatab normal' style='font-feature-settings: "cv12" 1'>&#x2D5B;</span> <span class='hapaxcarre normal'>&#x2D5B;</span>)|  | 
C  |<span class='nototif normal'>&#x2D3C;</span> (<span class='akatab normal'>&#x2D3C;</span> <span class='akatab normal' style='font-feature-settings: "cv02" 1'>&#x2D3C;</span> <span class='akatab normal' style='font-feature-settings: "cv02" 2'>&#x2D3C;</span>)| <span class='nototif normal'>&#x2D4C;</span> | <span class='hapaxberbere normal'>&#x2D5C;</span> (<span class='akatab normal'>&#x2D5C;</span>)|  | 
D  |<span class='nototif normal'>&#x2D3D;</span> | <span class='nototif normal'>&#x2D4D;</span> (<span class='akatab normal'>&#x2D4D;</span> <span class='hapaxtuareg normal'>&#x2D4D;</span> <span class='hapaxberbere normal'>&#x2D4D;</span>)| <span class='nototif normal'>&#x2D5D;</span> |  | 
E  |<span class='nototif normal'>&#x2D3E;</span> (<span class='hapaxtuareg normal'>&#xF0A2;</span> <span class='hapaxtuareg normal'>&#xF0A1;</span>) | <span class='nototif normal'>&#x2D4E;</span> (<span class='hapaxtuareg normal'>&#xF140;</span> <span class='hapaxrond normal'>&#xF0C2;</span>) | <span class='nototif normal'>&#x2D5E;</span> (<span class='nototifagraw normal'>&#x2D5E;</span>)|  | 
F  |<span class='nototif normal'>&#x2D3F;</span> | <span class='nototif normal'>&#x2D4F;</span> | <span class='nototif normal'>&#x2D5F;</span> (<span class='hapaxrond normal'>&#x2D5F;</span> <span class='akatab normal' style='font-feature-settings: "cv13" 1'>&#x2D5F;</span> <span class='nototifagraw normal'>&#x2D5F;</span>)| <span class='nototif normal'>&#x2D6F;</span> (<span class='nototifagraw normal'>&#x2D6F;</span>)| <span class='nototif normal'>&#x2D7F;</span>

### <a id="bicons"></a>Bi- Tri-consonants

Bi-consonants are additional letterforms used in the Tifinagh script, particularly for Tuareg, to represent a consonant cluster—a sequence of two consonants without an intervening vowel. These bi-consonants, sometimes also referred to as bigraphs, are not directly encoded as single characters in the Unicode Standard. Instead, they are represented as a sequence of the two consonant letters, separated either by U+200D ZERO WIDTH JOINER or by U+2D7F TIFINAGH CONSONANT JOINER.
 
When a bi-consonant is considered obligatory in text, it is represented by the two consonant letters, with U+2D7F TIFINAGH CONSONANT JOINER inserted between them. This use of U+2D7F is comparable in function to the use of U+0652 ARABIC SUKUN to indicate the absence of a vowel after a consonant in the Arabic script. However, instead of appearing as a visible mark in the text, U+2D7F TIFINAGH CONSONANT JOINER indicates the presence of a bi-consonant, which should then be rendered with a preformed glyph for the sequence. U+200D ZERO WIDTH JOINER should be used when the bi-consonant is not considered obligatory.

Some of the bi-consonants have ascenders. These should ascend above the normal height of the Tifinagh consonants.

Although rare, tri-consonants do exist. This document will use the term bi-consonant even when it may be a tri-consonant.

This chart does not demonstrate all of the possible historical glyph variants. Although this chart demonstrates the use of U+2D7F TIFINAGH CONSONANT JOINER, fonts should support either U+2D7F (obligatory bi-consonants) or U+200D (optional bi-consonants).

USV | 2D7F between characters | → | Glyph</br>(2D7F)
:----- | :--  | :-- | :--
1 /bt/ 2D31 2D5C | <span class='nototif normal'>&#x2D31; + &#x2D7F; + &#x2D5C;</span> | → | <span class='nototif normal'>&#x2D31;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv31" 1'>&#x2D31;&#x2D7F;&#x2D5C;</span>
2 /gʼt/ 2D33 2D5C | <span class='nototif normal'>&#x2D33; + &#x2D7F; + &#x2D5C;</span> | → | <span class='nototif normal'>&#x2D33;&#x2D7F;&#x2D5C;</span>
3 /gʼt/ 2D34 2D5C | <span class='nototif normal'>&#x2D34; + &#x2D7F; + &#x2D5C;</span> | → | <span class='akatab normal'>&#x2D34;&#x2D7F;&#x2D5C;</span>
4 /gt/ 2D36 2D5C | <span class='nototif normal'>&#x2D36; + &#x2D7F; + &#x2D5C;</span> | → | <span class='akatab normal'>&#x2D36;&#x2D7F;&#x2D5C;</span> <span class='hapaxtuareg normal'>&#xF340;</span>
5 /ft/ 2D3C 2D5C | <span class='nototif normal'>&#x2D3C; + &#x2D7F; + &#x2D5C;</span> | → | <span class='nototif normal'>&#x2D3C;&#x2D7F;&#x2D5C;</span> <span class='akatab normal'>&#x2D3C;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv02" 1'>&#x2D3C;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv35" 1'>&#x2D3C;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv35" 2'>&#x2D3C;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv14" 1'>&#x2D3C;&#x2D7F;&#x2D5C;</span>
6 /bt/ 2D40 2D5C | <span class='nototif normal'>&#x2D40; + &#x2D7F; + &#x2D5C;</span> | → | <span class='nototif normal'>&#x2D40;&#x2D7F;&#x2D5C;</span>
7 /yt/ 2D49 2D5C | <span class='nototif normal'>&#x2D49; + &#x2D7F; + &#x2D5C;</span> | → | <span class='akatab normal'>&#x2D49;&#x2D7F;&#x2D5C;</span>
8 /ẓt/ 2D4B 2D5C | <span class='nototif normal'>&#x2D4B; + &#x2D7F; + &#x2D5C;</span> | → | <span class='akatab normal'>&#x2D4B;&#x2D7F;&#x2D5C;</span>
9 /ẓt/ 2D4C 2D5C | <span class='nototif normal'>&#x2D4C; + &#x2D7F; + &#x2D5C;</span> | → | <span class='nototif normal'>&#x2D4C;&#x2D7F;&#x2D5C;</span> <span class='akatab normal'>&#x2D4C;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv40" 1'>&#x2D4C;&#x2D7F;&#x2D5C;</span>
10 /lk/ 2D4D 2D3E | <span class='nototif normal'>&#x2D4D; + &#x2D7F; + &#x2D3E;</span> | → | <span class='akatab normal'>&#x2D4D;&#x2D7F;&#x2D3E;</span>
11 /lt/ 2D4D 2D5C | <span class='nototif normal'>&#x2D4D; + &#x2D7F; + &#x2D5C;</span> | → | <span class='nototif normal'>&#x2D4D;&#x2D7F;&#x2D5C;</span> <span class='akatab normal'>&#x2D4D;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv38" 1'>&#x2D4D;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv38" 2'>&#x2D4D;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv38" 3'>&#x2D4D;&#x2D7F;&#x2D5C;</span>
12 /mb/ 2D4E 2D40 | <span class='nototif normal'>&#x2D4E; + &#x2D7F; + &#x2D40;</span> | → | <span class='nototif normal'>&#x2D4E;&#x2D7F;&#x2D40;</span> <span class='akatab normal'>&#x2D4E;&#x2D7F;&#x2D40;</span>
13 /ms/ 2D4E 2D59 | <span class='nototif normal'>&#x2D4E; + &#x2D7F; + &#x2D59;</span> | → | <span class='akatab normal'>&#x2D4E;&#x2D7F;&#x2D59;</span>
14 /mt/ 2D4E 2D5C | <span class='nototif normal'>&#x2D4E; + &#x2D7F; + &#x2D5C;</span> | → | <span class='ebrima normal'>&#x2D4E;&#x2D7F;&#x2D5C;</span> <span class='nototif normal'>&#x2D4E;&#x2D7F;&#x2D5C;</span> <span class='akatab normal'>&#x2D4E;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv34" 2'>&#x2D4E;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv34" 1'>&#x2D4E;&#x2D7F;&#x2D5C;</span>  <span class='akatab normal' style='font-feature-settings: "cv34" 3'>&#x2D4E;&#x2D7F;&#x2D5C;</span>
15 /nb/ 2D4F 2D31 | <span class='nototif normal'>&#x2D4F; + &#x2D7F; + &#x2D31;</span> | → | <span class='nototif normal'>&#x2D4F;&#x2D7F;&#x2D31;</span>
16 /ng/ 2D4F 2D34 | <span class='nototif normal'>&#x2D4F; + &#x2D7F; + &#x2D34;</span> | → | <span class='akatab normal'>&#x2D4F;&#x2D7F;&#x2D34;</span> <span class='ebrima normal'>&#x2D4F;&#x2D7F;&#x2D34;</span>
17 /nġ/ 2D4F 2D36 | <span class='nototif normal'>&#x2D4F; + &#x2D7F; + &#x2D36;</span> | → | <span class='nototif normal'>&#x2D4F;&#x2D7F;&#x2D36;</span> <span class='akatab normal'>&#x2D4F;&#x2D7F;&#x2D36;</span> <span class='akatab normal' style='font-feature-settings: "cv43" 1'>&#x2D4F;&#x2D7F;&#x2D36;</span>
18 /nd/ 2D4F 2D37 | <span class='nototif normal'>&#x2D4F; + &#x2D7F; + &#x2D37;</span> | → | <span class='akatab normal'>&#x2D4F;&#x2D7F;&#x2D37;</span> <span class='akatab normal' style='font-feature-settings: "cv41" 1'>&#x2D4F;&#x2D7F;&#x2D37;</span>
19 /nd/ 2D4F 2D38 | <span class='nototif normal'>&#x2D4F; + &#x2D7F; + &#x2D38;</span> | → | <span class='akatab normal'>&#x2D4F;&#x2D7F;&#x2D38;</span> <span class='nototif normal'>&#x2D4F;&#x2D7F;&#x2D38;</span>
20 /nd/ 2D4F 2D39 | <span class='nototif normal'>&#x2D4F; + &#x2D7F; + &#x2D39;</span> | → | <span class='nototif normal'>&#x2D4F;&#x2D7F;&#x2D39;</span> <span class='akatab normal'>&#x2D4F;&#x2D7F;&#x2D39;</span>

USV | 2D7F between characters | → | Glyph</br>(2D7F)
:----- | :--  | :-- | :--
21 /nf/ 2D4F 2D3C | <span class='nototif normal'>&#x2D4F; + &#x2D7F; + &#x2D3C;</span> | → | <span class='nototif normal'>&#x2D4F;&#x2D7F;&#x2D3C;</span> <span class='akatab normal'>&#x2D4F;&#x2D7F;&#x2D3C;</span> <span class='akatab normal' style='font-feature-settings: "cv42" 1'>&#x2D4F;&#x2D7F;&#x2D3C;</span> <span class='akatab normal' style='font-feature-settings: "cv14" 1'>&#x2D4F;&#x2D7F;&#x2D3C;</span>
22 /nft/ 2D4F 2D3C 2D5C | <span class='nototif normal'>&#x2D4F; + &#x2D7F; + &#x2D3C; + &#x2D7F; + &#x2D5C;</span> | → | <span class='akatab normal'>&#x2D4F;&#x2D7F;&#x2D3C;&#x2D7F;&#x2D5C;</span>
23 /nk/ 2D4F 2D3E | <span class='nototif normal'>&#x2D4F; + &#x2D7F; + &#x2D3E;</span> | → | <span class='nototif normal'>&#x2D4F;&#x2D7F;&#x2D3E;</span> <span class='akatab normal'>&#x2D4F;&#x2D7F;&#x2D3E;</span>
24 /nb/ 2D4F 2D40 | <span class='nototif normal'>&#x2D4F; + &#x2D7F; + &#x2D40;</span> | → | <span class='nototif normal'>&#x2D4F;&#x2D7F;&#x2D40;</span>
25 /nj/ 2D4F 2D4C | <span class='nototif normal'>&#x2D4F; + &#x2D7F; + &#x2D4C;</span> | → | <span class='nototif normal'>&#x2D4F;&#x2D7F;&#x2D4C;</span> <span class='akatab normal' style='font-feature-settings: "cv45" 1'>&#x2D4F;&#x2D7F;&#x2D4C;</span>
26 /nɣ/ 2D4F 2D57 | <span class='nototif normal'>&#x2D4F; + &#x2D7F; + &#x2D57;</span> | → | <span class='nototif normal'>&#x2D4F;&#x2D7F;&#x2D57;</span>
27 /ns/ 2D4F 2D59 | <span class='nototif normal'>&#x2D4F; + &#x2D7F; + &#x2D59;</span> | → | <span class='nototif normal'>&#x2D4F;&#x2D7F;&#x2D59;</span> <span class='akatab normal'>&#x2D4F;&#x2D7F;&#x2D59;</span>
28 /nš/ 2D4F 2D5B | <span class='nototif normal'>&#x2D4F; + &#x2D7F; + &#x2D5B;</span> | → | <span class='akatab normal'>&#x2D4F;&#x2D7F;&#x2D5B;</span>
29 /nt/ 2D4F 2D5C | <span class='nototif normal'>&#x2D4F; + &#x2D7F; + &#x2D5C;</span> | → | <span class='nototif normal'>&#x2D4F;&#x2D7F;&#x2D5C;</span> <span class='akatab normal'>&#x2D4F;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv37" 1'>&#x2D4F;&#x2D7F;&#x2D5C;</span>
30 /č/ 2D4F 2D5E | <span class='nototif normal'>&#x2D4F; + &#x2D7F; + &#x2D5E;</span> | → | <span class='nototif normal'>&#x2D4F;&#x2D7F;&#x2D5E;</span>
31 /nz/ 2D4F 2D63 | <span class='nototif normal'>&#x2D4F; + &#x2D7F; + &#x2D63;</span> | → | <span class='nototif normal'>&#x2D4F;&#x2D7F;&#x2D63;</span>
32 /nz/ 2D4F 2D64 | <span class='nototif normal'>&#x2D4F; + &#x2D7F; + &#x2D64;</span> | → | <span class='akatab normal'>&#x2D4F;&#x2D7F;&#x2D64;</span>
33 /wt/ 2D53 2D5C | <span class='nototif normal'>&#x2D53; + &#x2D7F; + &#x2D5C;</span> | → | <span class='nototif normal'>&#x2D53;&#x2D7F;&#x2D5C;</span> <span class='akatab normal'>&#x2D53;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv39" 1'>&#x2D53;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv39" 2'>&#x2D53;&#x2D7F;&#x2D5C;</span>
34 /rb/ 2D54 2D31 | <span class='nototif normal'>&#x2D54; + &#x2D7F; + &#x2D31;</span> | → | <span class='nototif normal'>&#x2D54;&#x2D7F;&#x2D31;</span>
35 /rj/ 2D54 2D36 | <span class='nototif normal'>&#x2D54; + &#x2D7F; + &#x2D36;</span> | → | <span class='nototif normal'>&#x2D54;&#x2D7F;&#x2D36;</span>
36 /rd/ 2D54 2D37 | <span class='nototif normal'>&#x2D54; + &#x2D7F; + &#x2D37;</span> | → | <span class='nototif normal'>&#x2D54;&#x2D7F;&#x2D37;</span>
37 /rk/ 2D54 2D3D | <span class='nototif normal'>&#x2D54; + &#x2D7F; + &#x2D3D;</span> | → | <span class='nototif normal'>&#x2D54;&#x2D7F;&#x2D3D;</span>
38 /rk/ 2D54 2D3E | <span class='nototif normal'>&#x2D54; + &#x2D7F; + &#x2D3E;</span> | → | <span class='akatab normal'>&#x2D54;&#x2D7F;&#x2D3E;</span> <span class='akatab normal' style='font-feature-settings: "cv46" 1'>&#x2D54;&#x2D7F;&#x2D3E;</span>
39 /rn/ 2D54 2D4F | <span class='nototif normal'>&#x2D54; + &#x2D7F; + &#x2D4F;</span> | → | <span class='nototif normal'>&#x2D54;&#x2D7F;&#x2D4F;</span> <span class='akatab normal'>&#x2D54;&#x2D7F;&#x2D4F;</span>
40 /rs/ 2D54 2D59 | <span class='nototif normal'>&#x2D54; + &#x2D7F; + &#x2D59;</span> | → | <span class='nototif normal'>&#x2D54;&#x2D7F;&#x2D59;</span>

USV | 2D7F between characters | → | Glyph</br>(2D7F)
:----- | :--  | :-- | :-- 
41 /rt/ 2D54 2D5C | <span class='nototif normal'>&#x2D54; + &#x2D7F; + &#x2D5C;</span> | → | <span class='nototif normal'>&#x2D54;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv32" 1'>&#x2D54;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv32" 2'>&#x2D54;&#x2D7F;&#x2D5C;</span> <span class='hapaxtuareg normal'>&#xF1D5;</span>
42 /gt/ 2D56 2D5C | <span class='nototif normal'>&#x2D56; + &#x2D7F; + &#x2D5C;</span> | → | <span class='nototif normal'>&#x2D56;&#x2D7F;&#x2D5C;</span>
43 /sk/ 2D59 2D3E | <span class='nototif normal'>&#x2D59; + &#x2D7F; + &#x2D3E;</span> | → | <span class='akatab normal'>&#x2D59;&#x2D7F;&#x2D3E;</span>
44 /sn/ 2D59 2D4F | <span class='nototif normal'>&#x2D59; + &#x2D7F; + &#x2D4F;</span> | → | <span class='nototif normal'>&#x2D59;&#x2D7F;&#x2D4F;</span>
45 /st/ 2D59 2D5C | <span class='nototif normal'>&#x2D59; + &#x2D7F; + &#x2D5C;</span> | → | <span class='nototif normal'>&#x2D59;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv33" 1'>&#x2D59;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv33" 2'>&#x2D59;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv33" 3'>&#x2D59;&#x2D7F;&#x2D5C;</span> <span class='hapaxtuareg normal'>&#xE880;</span>
46 /šk/ 2D5B 2D3E | <span class='nototif normal'>&#x2D5B; + &#x2D7F; + &#x2D3E;</span> | → | <span class='akatab normal'>&#x2D5B;&#x2D7F;&#x2D3E;</span> <span class='akatab normal' style='font-feature-settings: "cv47" 1'>&#x2D5B;&#x2D7F;&#x2D3E;</span> <span class='akatab normal' style='font-feature-settings: "cv47" 2'>&#x2D5B;&#x2D7F;&#x2D3E;</span> <span class='akatab normal' style='font-feature-settings: "cv12" 1'>&#x2D5B;&#x2D7F;&#x2D3E;</span>
47 /šn/ 2D5B 2D4F | <span class='nototif normal'>&#x2D5B; + &#x2D7F; + &#x2D4F;</span> | → | <span class='akatab normal'>&#x2D5B;&#x2D7F;&#x2D4F;</span>
48 /št/ 2D5B 2D5C | <span class='nototif normal'>&#x2D5B; + &#x2D7F; + &#x2D5C;</span> | → | <span class='nototif normal'>&#x2D5B;&#x2D7F;&#x2D5C;</span> <span class='akatab normal'>&#x2D5B;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv48" 1'>&#x2D5B;&#x2D7F;&#x2D5C;</span> <span class='hapaxtuareg normal'>&#xF3AF;</span>
49 /ts/ 2D5C 2D59 | <span class='nototif normal'>&#x2D5C; + &#x2D7F; + &#x2D59;</span> | → | <span class='nototif normal'>&#x2D5C;&#x2D7F;&#x2D59;</span>
50 /wt/ 2D61 2D5C | <span class='nototif normal'>&#x2D61; + &#x2D7F; + &#x2D5C;</span> | → | <span class='nototif normal'>&#x2D61;&#x2D7F;&#x2D5C;</span>
51 /yt/ 2D62 2D5C | <span class='nototif normal'>&#x2D62; + &#x2D7F; + &#x2D5C;</span> | → | <span class='nototif normal'>&#x2D62;&#x2D7F;&#x2D5C;</span> <span class='ebrima normal'>&#x2D62;&#x2D7F;&#x2D5C;</span>
52 /zt/ 2D63 2D5C | <span class='nototif normal'>&#x2D63; + &#x2D7F; + &#x2D5C;</span> | → | <span class='akatab normal'>&#x2D63;&#x2D7F;&#x2D5C;</span>
53 /zt/ 2D65 2D5C | <span class='nototif normal'>&#x2D65; + &#x2D7F; + &#x2D5C;</span> | → | <span class='nototif normal'>&#x2D65;&#x2D7F;&#x2D5C;</span>

This should not be considered an exhaustive list of all bi-consonants used for Tifinagh, nor are the shapes of the bi-consonants necessarily definitive. There are a wide range of glyph variants.

Bi-consonants are only included in each language section when there are known variants.


### <a id="contexual"></a>Contextual Shaping

Contextul shaping should be implemented when the design of U+2D4D TIFINAGH LETTER YAL and U+2D4F TIFINAGH LETTER YAN are simply vertical strokes. 

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
| | | | | |

Contextual shaping will only be included in each language section when there is known shaping.

### <a id="dir"></a>Writing Direction

In early inscriptions, Tifinagh was written horizontally from left to right, from right to left, vertically (bottom to top, top to bottom) or even in boustrophedon. However, the most frequently used directionality in the modern-day Tifinagh script is horizontal from left to right.

Given that left-to-right directionality seems to be the most widely used one in the Maghreb and in Niger, the strong directionality of Tifinagh is defined to be left-to-right. When needed, it is possible to explicitly declare a right-to-left directionality. The glyphs will then have to be mirrored, according to the rules in effect for the specified variant. If the glyphs are to be mirrored, then this must be implemented in the font.

**The following text demonstrates Tifinagh left-to-right behaviour:**<br>
<span class='akatab normal'> ⵙⵏⵜⵜ ⵜⵙⴾⵍⵏ ⵓⵔ ⵜⴶⵂⵏⵜ ⵎⵉ </span>

**Using the same text, right-to-left behaviour is demonstrated using U+202E RIGHT-TO-LEFT OVERRIDE:**<br>
<span dir="rtl" class='akatab normal'> &#x202E; ⵙⵏⵜⵜ ⵜⵙⴾⵍⵏ ⵓⵔ ⵜⴶⵂⵏⵜ ⵎⵉ </span>

**The following text demonstrates both Tifinagh directional behaviours using the U+202E RIGHT-TO-LEFT OVERRIDE and U+202C OP DIRECTIONAL FORMATTING:**<br>
<span dir="rtl" class='akatab normal'> &#x202E; ⵙⵏⵜⵜ ⵜⵙⴾⵍⵏ ⵓⵔ ⵜⴶⵂⵏⵜ ⵎⵉ  &#x202C; ⵙⵏⵜⵜ ⵜⵙⴾⵍⵏ ⵓⵔ ⵜⴶⵂⵏⵜ ⵎⵉ </span>
</p>‮
<!-- 
Using hard-coded directional characters in the HTML code (as illustrated above) can prevent accidental deletion of invisible characters.
-->

### <a id="dir_var"></a>Variant Directional Glyphs

Because the script can be written in multiple directions, the glyphs must be mirrored or turned. Below is a sampling of some of the different shapes required for differing directions. Some glyphs, like a circle, could look the same in any direction. However, unless the glyphs are monoline, there will be slight variations in the glyph design. Where there are glyph variants, the number of glyphs required for different directions will increase exponentially.

|  | &#x2192;     | &#x2190;      | &#x2191;      | &#x2193;    
:- | :--     | :--      | :--      | :--
2D30  |<span class='hapaxtuareg normal'>&#x2D30;</span>| <span class='hapaxtuareg normal'>&#x2D30;</span> | <span class='hapaxtuareg normal'>&#x2D30;</span>|<span class='hapaxtuareg normal'>&#x2D30;</span>
2D31  |<span class='hapaxtuareg normal'>&#x2D31;</span>| <span class='hapaxtuareg normal'>&#x2D31;</span> | <span class='hapaxtuareg normal'>&#xE310;</span>|<span class='hapaxtuareg normal'>&#xE310;</span>
2D32  |<span class='hapaxtuareg normal'>&#x2D32;</span>| <span class='hapaxtuareg normal'>&#x2D32;</span> | <span class='hapaxtuareg normal'>&#x2D32;</span>|<span class='hapaxtuareg normal'>&#x2D32;</span>
2D33  |<span class='hapaxtuareg normal'>&#x2D33;</span>| <span class='hapaxtuareg normal'>&#x2D33;</span> | <span class='hapaxtuareg normal'>&#xE885;</span>|<span class='hapaxtuareg normal'>&#xF031;</span>
2D34  |<span class='hapaxtuareg normal'>&#x2D34;</span>| <span class='hapaxtuareg normal'>&#x2D34;</span> | <span class='hapaxtuareg normal'>&#xF031;</span>|<span class='hapaxtuareg normal'>&#xE885;</span>
2D35  |<span class='hapaxtuareg normal'>&#x2D35;</span>| <span class='hapaxtuareg normal'>&#x2D35;</span> | <span class='hapaxtuareg normal'>&#xF691;</span>|<span class='hapaxtuareg normal'>&#xF691;</span>
2D36  |<span class='hapaxtuareg normal'>&#x2D36;</span>| <span class='hapaxtuareg normal'>&#x2D36;</span> | <span class='hapaxtuareg normal'>&#xF061;</span>|<span class='hapaxtuareg normal'></span>
2D37  |<span class='hapaxtuareg normal'>&#x2D37;</span>| <span class='hapaxtuareg normal'>&#x2D37;</span> | <span class='hapaxtuareg normal'>&#xE00C;</span>|<span class='hapaxtuareg normal'>&#xF0C3;</span>
2D38  |<span class='hapaxtuareg normal'>&#x2D38;</span>| <span class='hapaxtuareg normal'>&#x2D38;</span> | <span class='hapaxtuareg normal'>&#xF0C3;</span>|<span class='hapaxtuareg normal'>&#xE00C;</span>
2D39  |<span class='hapaxtuareg normal'>&#xE330;</span>| <span class='hapaxtuareg normal'>&#xF017;</span> | <span class='hapaxtuareg normal'>&#xE106;</span>|<span class='hapaxtuareg normal'>&#xE8A8;</span>
2D3A  |<span class='hapaxtuareg normal'>&#x2D3A;</span>| <span class='hapaxtuareg normal'>&#xE330;</span> | <span class='hapaxtuareg normal'>&#xE8A8;</span>|<span class='hapaxtuareg normal'>&#xE106;</span>
2D3B  |<span class='hapaxtuareg normal'>&#xF062;</span>| <span class='hapaxtuareg normal'>&#xF062;</span> | <span class='hapaxtuareg normal'>&#xF063;</span>|<span class='hapaxtuareg normal'>&#xF063;</span>
2D3C  |<span class='hapaxtuareg normal'>&#x2D3C;</span>| <span class='hapaxtuareg normal'>&#x2D3C;</span> | <span class='hapaxtuareg normal'>&#xE012;</span>|<span class='hapaxtuareg normal'>&#xE012;</span>
2D3D  |<span class='hapaxtuareg normal'>&#x2D3D;</span>| <span class='hapaxtuareg normal'>-</span> | <span class='hapaxtuareg normal'>-</span>|<span class='hapaxtuareg normal'>-</span>
2D3E  |<span class='hapaxtuareg normal'>&#x2D3E;</span>| <span class='hapaxtuareg normal'>&#xF0A3;</span> | <span class='hapaxtuareg normal'>&#xF0A4;</span>|<span class='hapaxtuareg normal'>-</span>
2D3F  |<span class='hapaxtuareg normal'>&#x2D3F;</span>| <span class='hapaxtuareg normal'>-</span> | <span class='hapaxtuareg normal'>-</span>|<span class='hapaxtuareg normal'>-</span>
2D40  |<span class='hapaxtuareg normal'>&#xE310;</span>| <span class='hapaxtuareg normal'>&#xE310;</span> | <span class='hapaxtuareg normal'>&#x2D31;</span>|<span class='hapaxtuareg normal'>&#x2D31;</span>
2D41  |<span class='hapaxtuareg normal'>&#x2D41;</span>| <span class='hapaxtuareg normal'>-</span> | <span class='hapaxtuareg normal'>-</span>|<span class='hapaxtuareg normal'>-</span>
2D42  |<span class='hapaxtuareg normal'>&#x2D42;</span>| <span class='hapaxtuareg normal'>&#x2D42;</span> | <span class='hapaxtuareg normal'>-</span>|<span class='hapaxtuareg normal'>-</span>
2D43  |<span class='hapaxtuareg normal'>&#x2D43;</span>| <span class='hapaxtuareg normal'>-</span> | <span class='hapaxtuareg normal'>-</span>|<span class='hapaxtuareg normal'>-</span>
2D44  |<span class='hapaxtuareg normal'>&#x2D44;</span>| <span class='hapaxtuareg normal'>&#x2D44;</span> | <span class='hapaxtuareg normal'>-</span>|<span class='hapaxtuareg normal'>-</span>
2D45  |<span class='hapaxtuareg normal'>&#x2D45;</span>| <span class='hapaxtuareg normal'>&#x2D45;</span> | <span class='hapaxtuareg normal'>-</span>|<span class='hapaxtuareg normal'>-</span>
2D46  |<span class='hapaxtuareg normal'>&#x2D46;</span>| <span class='hapaxtuareg normal'>&#x2D46;</span> | <span class='hapaxtuareg normal'>&#x2D46;</span>|<span class='hapaxtuareg normal'>&#x2D46;</span>
2D47  |<span class='hapaxtuareg normal'>&#x2D47;</span>| <span class='hapaxtuareg normal'>-</span> | <span class='hapaxtuareg normal'>-</span>|<span class='hapaxtuareg normal'>-</span>
2D48  |<span class='hapaxtuareg normal'>&#x2D48;</span>| <span class='hapaxtuareg normal'>&#x2D48;</span> | <span class='hapaxtuareg normal'>&#x2D57;</span>|<span class='hapaxtuareg normal'>&#x2D57;</span>
2D49  |<span class='hapaxtuareg normal'>&#x2D49;</span>| <span class='hapaxtuareg normal'>&#xF153;</span> | <span class='hapaxtuareg normal'>&#xF163;</span>|<span class='hapaxtuareg normal'>&#xF162;</span>
2D4A  |<span class='hapaxtuareg normal'>&#x2D4A;</span>| <span class='hapaxtuareg normal'>&#x2D4A;</span> | <span class='hapaxtuareg normal'>&#xF250;</span>|<span class='hapaxtuareg normal'>&#xF250;</span>
2D4B  |<span class='hapaxtuareg normal'>&#x2D4B;</span>| <span class='hapaxtuareg normal'>&#x2D4B;</span> | <span class='hapaxtuareg normal'>-</span>|<span class='hapaxtuareg normal'>-</span>
2D4C  |<span class='hapaxtuareg normal'>&#x2D4C;</span>| <span class='hapaxtuareg normal'>&#x2D4C;</span> | <span class='hapaxtuareg normal'>&#x2D4C;</span>|<span class='hapaxtuareg normal'>&#x2D4C;</span>
2D4D  |<span class='hapaxtuareg normal'>&#xF0B1;</span>| <span class='hapaxtuareg normal'>&#xF0B1;</span> | <span class='hapaxtuareg normal'>&#xF0B2;</span>|<span class='hapaxtuareg normal'>&#xF0B2;</span>
2D4E  |<span class='hapaxtuareg normal'>&#x2D4E;</span>| <span class='hapaxtuareg normal'>&#xF0C0;</span> | <span class='hapaxtuareg normal'>&#xF0C4;</span>|<span class='hapaxtuareg normal'>&#xF6F2;</span>
2D4F  |<span class='hapaxtuareg normal'>&#xF0D0;</span>| <span class='hapaxtuareg normal'>&#xF0D0;</span> | <span class='hapaxtuareg normal'>&#xF0D1;</span>|<span class='hapaxtuareg normal'>&#xF0D1;</span>
2D50  |<span class='hapaxtuareg normal'>&#xE038;</span>| <span class='hapaxtuareg normal'>&#xE038;</span> | <span class='hapaxtuareg normal'>-</span>|<span class='hapaxtuareg normal'>-</span>
2D51  |<span class='hapaxtuareg normal'>&#x2D51;</span>| <span class='hapaxtuareg normal'>&#x2D51;</span> | <span class='hapaxtuareg normal'>-</span>|<span class='hapaxtuareg normal'>-</span>
2D52  |<span class='hapaxtuareg normal'>&#x2D52;</span>| <span class='hapaxtuareg normal'>-</span> | <span class='hapaxtuareg normal'>-</span>|<span class='hapaxtuareg normal'>-</span>
2D53  |<span class='hapaxtuareg normal'>&#x2D53;</span>| <span class='hapaxtuareg normal'>&#x2D53;</span> | <span class='hapaxtuareg normal'>-</span>|<span class='hapaxtuareg normal'>-</span>
2D54  |<span class='hapaxtuareg normal'>&#x2D54;</span>| <span class='hapaxtuareg normal'>&#x2D54;</span> | <span class='hapaxtuareg normal'>&#x2D54;</span>|<span class='hapaxtuareg normal'>&#x2D54;</span>
2D55  |<span class='hapaxtuareg normal'>&#x2D55;</span>| <span class='hapaxtuareg normal'>&#xF563;</span> | <span class='hapaxtuareg normal'>-</span>|<span class='hapaxtuareg normal'>-</span>
2D56  |<span class='hapaxtuareg normal'>&#x2D56;</span>| <span class='hapaxtuareg normal'>&#x2D56;</span> | <span class='hapaxtuareg normal'>-</span>|<span class='hapaxtuareg normal'>-</span>
2D57  |<span class='hapaxtuareg normal'>&#x2D57;</span>| <span class='hapaxtuareg normal'>&#x2D57;</span> | <span class='hapaxtuareg normal'>&#x2D48;</span>|<span class='hapaxtuareg normal'>&#x2D48;</span>
2D58  |<span class='hapaxtuareg normal'>&#x2D58;</span>| <span class='hapaxtuareg normal'>&#x2D58;</span> | <span class='hapaxtuareg normal'>&#x2D58;</span>|<span class='hapaxtuareg normal'>&#x2D58;</span>
2D59  |<span class='hapaxtuareg normal'>&#x2D59;</span>| <span class='hapaxtuareg normal'>&#x2D59;</span> | <span class='hapaxtuareg normal'>&#x2D59;</span>|<span class='hapaxtuareg normal'>&#x2D59;</span>
2D5A  |<span class='hapaxtuareg normal'>&#x2D5A;</span>| <span class='hapaxtuareg normal'>-</span> | <span class='hapaxtuareg normal'>-</span>|<span class='hapaxtuareg normal'>-</span>
2D5B  |<span class='hapaxtuareg normal'>&#x2D5B;</span>| <span class='hapaxtuareg normal'>&#xF166;</span> | <span class='hapaxtuareg normal'>&#xF0C5;</span>|<span class='hapaxtuareg normal'>&#xF167;</span>
2D5C  |<span class='hapaxtuareg normal'>&#x2D5C;</span>| <span class='hapaxtuareg normal'>&#x2D5C;</span> | <span class='hapaxtuareg normal'>&#x2D5C;</span>|<span class='hapaxtuareg normal'>&#x2D5C;</span>
2D5D  |<span class='hapaxtuareg normal'>&#x2D5D;</span>| <span class='hapaxtuareg normal'>&#x2D5D;</span> | <span class='hapaxtuareg normal'>&#xF351;</span>|<span class='hapaxtuareg normal'>&#xF351;</span>
2D5E  |<span class='hapaxtuareg normal'>&#x2D5E;</span>| <span class='hapaxtuareg normal'>-</span> | <span class='hapaxtuareg normal'>-</span>|<span class='hapaxtuareg normal'>-</span>
2D5F  |<span class='hapaxtuareg normal'>&#x2D5F;</span>| <span class='hapaxtuareg normal'>&#xF1D1;</span> | <span class='hapaxtuareg normal'>-</span>|<span class='hapaxtuareg normal'>-</span>
2D60  |<span class='hapaxtuareg normal'>&#x2D60;</span>| <span class='hapaxtuareg normal'>&#x2D60;</span> | <span class='hapaxtuareg normal'>-</span>|<span class='hapaxtuareg normal'>-</span>
2D61  |<span class='hapaxtuareg normal'>&#x2D61;</span>| <span class='hapaxtuareg normal'>&#x2D61;</span> | <span class='hapaxtuareg normal'>&#xF0C0;</span>|<span class='hapaxtuareg normal'>&#x2D4E;</span>
2D62  |<span class='hapaxtuareg normal'>&#x2D62;</span>| <span class='hapaxtuareg normal'>&#xE87B;</span> | <span class='hapaxtuareg normal'>&#xF203;</span>|<span class='hapaxtuareg normal'>&#xF202;</span>
2D63  |<span class='hapaxtuareg normal'>&#x2D63;</span>| <span class='hapaxtuareg normal'>&#x2D63;</span> | <span class='hapaxtuareg normal'>&#xF290;</span>|<span class='hapaxtuareg normal'>&#xF290;</span>
2D64  |<span class='hapaxtuareg normal'>&#x2D64;</span>| <span class='hapaxtuareg normal'>&#xF222;</span> | <span class='hapaxtuareg normal'>&#xF050;</span>|<span class='hapaxtuareg normal'>&#xE11A;</span>
2D65  |<span class='hapaxtuareg normal'>&#x2D65;</span>| <span class='hapaxtuareg normal'>&#x2D65;</span> | <span class='hapaxtuareg normal'>-</span>|<span class='hapaxtuareg normal'>-</span>
2D66  |<span class='hapaxtuareg normal'>&#x2D66;</span>| <span class='hapaxtuareg normal'>&#xF0C3;</span> | <span class='hapaxtuareg normal'>&#x2D37;</span>|<span class='hapaxtuareg normal'>&#x2D38;</span>
2D67  |<span class='hapaxtuareg normal'>&#x2D67;</span>| <span class='hapaxtuareg normal'>&#x2D67;</span> | <span class='hapaxtuareg normal'></span>|<span class='hapaxtuareg normal'></span>

## <a id="resource"></a>Resources

It is important to realize that a keyboard only outputs codepoints. A font will support codepoints; but a font may also include variant glyphs for specific languages. A carefully chosen keyboard _and_ font are both required in order to display the correct behavior for a particular language. 

### <a id="key"></a>Keyboarding

The only standard keyboard known at the moment is the [Moroccan standard keyboard](http://hapax.qc.ca/pdf/NM%2017.6.000.pdf) for Neo-Tiginagh. A keyboard based on the Moroccan standard keyboard is supported in Microsoft Windows.

Keyman is a cross-platform keyboarding application. Four keyboards are available for the Tifinagh script:

- [Tifinagh &#x28;Basic&#x29; Basic](https://keyman.com/keyboards/basic_kbdtifi) [tzm]

- [Tifinagh &#x28;Full&#x29; Basic](https://keyman.com/keyboards/basic_kbdtifi2) [tzm, thz, tda, thv, kab, mzb, shi, shy, rif, tmh, zen, zgh]

- [Tawallammat Tifinagh &#x28;SIL&#x29;](https://keyman.com/keyboards/sil_tawallammat) [ttq, tzm]

- [Tuareg Tifinagh](https://keyman.com/keyboards/tuareg_tifinagh) [taq, thv]

[lexilogos.com input](https://www.lexilogos.com/clavier/tifinagh.htm)

[Neo-Tifinagh Character Picker](https://r12a.github.io/pickers/tfng-zgh/index.html)

[Tifinagh Character Picker](https://r12a.github.io/pickers/tfng-all/index.html)

### <a id="font"></a>Fonts

These fonts provide support for some or all of the Tifinagh block.

- [Noto Sans Tifinagh](https://fonts.google.com/noto/specimen/Noto+Sans+Tifinagh)
- [Akatab](https://software.sil.org/akatab/) - currently only covers part of the Tifinagh block for Tamahaq, Tamashek, and Tawallammat languages
- [Tagmukay](https://software.sil.org/tagmukay/) - only covers part of the Tifinagh block for the Tawallammat Tamajaq language
- [Catrinity](https://catrinity-font.de/)
- [IRCAM Tifinagh fonts](https://www.ircam.ma/fr/alphabet-tifinaghe) - supports Neo-Tifinagh
- [Hapax font set](http://www.hapax.qc.ca/polices/)
- [MPH 2B Damase](https://www.dafont.com/mph-2b-damase.font)
- [DejaVu](https://dejavu-fonts.github.io/)

## <a id="neo"></a>Languages Using Neo-Tifinagh script

### <a id="tzm_zgh"></a>Central Atlas Tamazight, Standard Moroccan Tamazight

_Source_: [Tifinaghe-IRCAM](https://www.win.tue.nl/~aeb/natlang/berber/tifinagh/tifinagh-ircam.html), [Omniglot](https://omniglot.com/writing/tamazight.htm), [Tamazight: Neo-Tifinagh orthography notes](https://r12a.github.io/scripts/tfng/zgh.html)

_Language tag:_ `tzm-Tfng`, `zgh`

_Opentype language system tag:_ `BBR `

_SLDR:_ [zgh](https://github.com/silnrsi/sldr/blob/master/sldr/z/zgh.xml)

_Keyman keyboard_: [Tifinagh &#x28;Basic&#x29; Basic](https://keyman.com/keyboards/basic_kbdtifi) [tzm]

_Keyman keyboard_: [Tifinagh &#x28;Full&#x29; Basic](https://keyman.com/keyboards/basic_kbdtifi2) [tzm, thz, tda, thv, kab, mzb, shi, shy, rif, tmh, zen, zgh]

Characters | | | | | | | | | &#x0020;
:------- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :--
Tfng | <span class='nototif normal'>&#x2D30;</span> | <span class='nototif normal'>&#x2D31;</span> | <span class='nototif normal'>&#x2D33;</span> | <span class='nototif normal'>&#x2D37;</span> | <span class='nototif normal'>&#x2D39;</span> | <span class='nototif normal'>&#x2D3B;</span> | <span class='nototif normal'>&#x2D3C;</span> | <span class='nototif normal'>&#x2D3D;</span> | <span class='nototif normal'>&#x2D40;</span>
USV  | 2D30 | 2D31 | 2D33 | 2D37 | 2D39 | 2D3B | 2D3C | 2D3D | 2D40
Latn | /a/ | /b/ | /g/ | /d/ | /ḍ/ | /e/ | /f/ | /k/ | /h/
| | | | | | | | |
Tfng | <span class='nototif normal'>&#x2D43;</span> | <span class='nototif normal'>&#x2D44;</span> | <span class='nototif normal'>&#x2D45;</span> | <span class='nototif normal'>&#x2D47;</span> | <span class='nototif normal'>&#x2D49;</span> | <span class='nototif normal'>&#x2D4A;</span> | <span class='nototif normal'>&#x2D4D;</span> | <span class='nototif normal'>&#x2D4E;</span> | <span class='nototif normal'>&#x2D4F;</span>
USV  | 2D43 | 2D44 | 2D45 | 2D47 | 2D49 |2D4A | 2D4D | 2D4E | 2D4F
Latn | /ḥ/ | /ɛ/ | /x/ | /q/ | /i/ | /j/ | /l/ | /m/ | /n/
| | | | | | | | |
Tfng | <span class='nototif normal'>&#x2D53;</span> | <span class='nototif normal'>&#x2D54;</span> | <span class='nototif normal'>&#x2D55;</span> | <span class='nototif normal'>&#x2D56;</span> | <span class='nototif normal'>&#x2D59;</span> | <span class='nototif normal'>&#x2D5A;</span> | <span class='nototif normal'>&#x2D5B;</span> | <span class='nototif normal'>&#x2D5C;</span> | <span class='nototif normal'>&#x2D5F;
USV | 2D53 | 2D54 | 2D55 | 2D56 | 2D59 |2D5A | 2D5B | 2D5C | 2D5F
Latn | /u/ | /r/ | /ṛ/ | /ɣ/ | /s/ | /ṣ/ | /c/ | /t/ | /ṭ/ | /ʷ/
| | | | | | | | |
Tfng | <span class='nototif normal'>&#x2D61;</span> | <span class='nototif normal'>&#x2D62;</span> | <span class='nototif normal'>&#x2D63;</span> | <span class='nototif normal'>&#x2D65;</span> | <span class='nototif normal'>&#x2D6F;</span> |
USV  | 2D61 | 2D62 | 2D63 | 2D65 | 2D6F |
Latn | /w/ | /y/ | /z/ | /ẓ/ | /ʷ/ |
| | | | | | | | |

#### Known glyph variants

The Unicode chart glyphs are based on Neo-Tifinagh shapes; thus, no glyph variants are required.

#### Bi-consonants

Bi-consonants are not “required” in Neo-Tifinagh. If a font supports bi-consonants, the two consonants separated by the ZWJ should thus form a bi-consonant. If a font does not support bi-consonants, they should simply appear as separate consonants.

#### Contextual Shaping

Neo-Tifinagh does not use contextual shaping for the “l” and “n”. This is because the glyphs are distinguishable from each other when side by side.

#### Collation

<span class='nototif normal'>&#x2D30;</span> &lt; <span class='nototif normal'>&#x2D31;</span> &lt; <span class='nototif normal'>&#x2D33;</span> &lt;&lt; <span class='nototif normal'>&#x2D33;&#x2D6F;</span> &lt; <span class='nototif normal'>&#x2D37;</span> &lt; <span class='nototif normal'>&#x2D39;</span> &lt; <span class='nototif normal'>&#x2D3B;</span> &lt; <span class='nototif normal'>&#x2D3C;</span> &lt; <span class='nototif normal'>&#x2D3D;</span> &lt;&lt; <span class='nototif normal'>&#x2D3D;&#x2D6F;</span> &lt; <span class='nototif normal'>&#x2D40;</span> &lt; <span class='nototif normal'>&#x2D43;</span> &lt; <span class='nototif normal'>&#x2D44;</span> &lt; <span class='nototif normal'>&#x2D45;</span> &lt; <span class='nototif normal'>&#x2D47;</span> &lt; <span class='nototif normal'>&#x2D49;</span> &lt; <span class='nototif normal'>&#x2D4A;</span> &lt; <span class='nototif normal'>&#x2D4D;</span> &lt; <span class='nototif normal'>&#x2D4E;</span> &lt; <span class='nototif normal'>&#x2D4F;</span> &lt; <span class='nototif normal'>&#x2D53;</span> &lt; <span class='nototif normal'>&#x2D54;</span> &lt; <span class='nototif normal'>&#x2D55;</span> &lt; <span class='nototif normal'>&#x2D56;</span> &lt; <span class='nototif normal'>&#x2D59;</span> &lt; <span class='nototif normal'>&#x2D5A;</span> &lt; <span class='nototif normal'>&#x2D5B;</span> &lt; <span class='nototif normal'>&#x2D5C;</span> &lt; <span class='nototif normal'>&#x2D5F;</span> &lt; <span class='nototif normal'>&#x2D61;</span> &lt; <span class='nototif normal'>&#x2D62;</span> &lt; <span class='nototif normal'>&#x2D63;</span> &lt; <span class='nototif normal'>&#x2D65;</span>


### <a id="kab"></a>Kabyle, Amazigh

_Source_: [Omniglot](https://omniglot.com/writing/kabyle.php), [Projet de norme marocaine: Alphabet tifinaghe](https://www.unicode.org/L2/L2004/04195-pnm-17.1.100.pdf) 

_Language Tag_: `kab-Tfng`

_Opentype language system tag:_ `BBR `

Characters | | | | | | | | | &#x0020;
:------- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :--
Tfng | <span class='nototif normal'>&#x2D30;</span> | <span class='nototif normal'>&#x2D31;</span> | <span class='nototif normal'>&#x2D33;</span>| <span class='nototif normal'>&#x2D35;</span> | <span class='nototif normal'>&#x2D37;</span> | <span class='nototif normal'>&#x2D39;</span> | <span class='nototif normal'>&#x2D3B;</span> | <span class='nototif normal'>&#x2D3C;</span> | <span class='nototif normal'>&#x2D3D;</span> 
USV  | 2D30 | 2D31 | 2D33 | 2D35 | 2D37 | 2D39 | 2D3B | 2D3C | 2D3D 
Latn | /a/  | /b/  | /g/  | /ǧ/ | /d/ | /ḍ/ | /e/ | /f/ | /k/ 
| | | | | | | | |
Tfng | <span class='nototif normal'>&#x2D41;</span> | <span class='nototif normal'>&#x2D43;</span> | <span class='nototif normal'>&#x2D44;</span> | <span class='nototif normal'>&#x2D45;</span> | <span class='nototif normal'>&#x2D47;</span> | <span class='nototif normal'>&#x2D49;</span> | <span class='nototif normal'>&#x2D4A;</span> | <span class='nototif normal'>&#x2D4D;</span> | <span class='nototif normal'>&#x2D4E;</span> 
USV  | 2D41 | 2D43 | 2D44 | 2D45 | 2D47 | 2D49 |2D4A | 2D4D | 2D4E 
Latn | /h/ | /ḥ/ | /ɛ/ | /x/ | /q/ | /i/ | /j/ | /l/ | /m/ 
| | | | | | | | |
Tfng | <span class='nototif normal'>&#x2D4F;</span> | <span class='nototif normal'>&#x2D53;</span> | <span class='nototif normal'>&#x2D54;</span> | <span class='nototif normal'>&#x2D55;</span> | <span class='nototif normal'>&#x2D56;</span> | <span class='nototif normal'>&#x2D59;</span> | <span class='nototif normal'>&#x2D5A;</span> | <span class='nototif normal'>&#x2D5B;</span> | <span class='nototif normal'>&#x2D5C;</span> 
USV | 2D4F | 2D53 | 2D54 | 2D55 | 2D56 | 2D59 |2D5A | 2D5B | 2D5C 
Latn | /n/ | /u/ | /r/ | /ṛ/ | /ɣ/ | /s/ | /ṣ/ | /c/ | /t/ 
| | | | | | | | |
Tfng | <span class='nototif normal'>&#x2D5E; | <span class='nototif normal'>&#x2D5F; | <span class='nototif normal'>&#x2D61;</span> | <span class='nototif normal'>&#x2D62;</span> | <span class='nototif normal'>&#x2D63;</span> | <span class='nototif normal'>&#x2D65;</span> | <span class='nototif normal'>&#x2D6F;</span> |
USV  | 2D5E | 2D5F| 2D61 | 2D62 | 2D63 | 2D65 | 2D6F |
Latn | /č/ | /ṭ/ | /w/ | /y/ | /z/ | /ẓ/ | /ʷ/ |
| | | | | | | | |

#### Known glyph variants

A variant of U+2D4d is used: <span class='hapaxberbere normal'>&#x2D4D;</span>

#### Bi-consonants

Bi-consonants are not “required” in Neo-Tifinagh. If a font supports bi-consonants, the two consonants separated by the ZWJ should thus form a bi-consonant. If a font does not support bi-consonants, they should simply appear as separate consonants.

#### Collation

<span class='nototif normal'>&#x2D30;</span> &lt; <span class='nototif normal'>&#x2D31;</span> &lt;&lt; <span class='nototif normal'>&#x2D31;&#x2D6F;</span> &lt; <span class='nototif normal'>&#x2D5B;</span> &lt; <span class='nototif normal'>&#x2D5E;</span> &lt; <span class='nototif normal'>&#x2D37;</span> &lt;&lt; <span class='nototif normal'>&#x2D37;&#x2D65;</span> &lt; <span class='nototif normal'>&#x2D39;</span> &lt; <span class='nototif normal'>&#x2D3B;</span> &lt; <span class='nototif normal'>&#x2D44;</span> &lt; <span class='nototif normal'>&#x2D3C;</span> &lt; <span class='nototif normal'>&#x2D33;</span> &lt;&lt; <span class='nototif normal'>&#x2D33;&#x2D6F;</span> &lt; <span class='nototif normal'>&#x2D35;</span> &lt; <span class='nototif normal'>&#x2D56;</span> &lt;&lt; <span class='nototif normal'>&#x2D56;&#x2D6F;</span> &lt; <span class='nototif normal'>&#x2D41;</span> &lt; <span class='nototif normal'>&#x2D43;</span> &lt; <span class='nototif normal'>&#x2D49;</span> &lt; <span class='nototif normal'>&#x2D4A;</span> &lt; <span class='nototif normal'>&#x2D3D;</span> &lt;&lt; <span class='nototif normal'>&#x2D3D;&#x2D6F;</span> &lt; <span class='nototif normal'>&#x2D4D;</span> &lt; <span class='nototif normal'>&#x2D4E;</span> &lt; <span class='nototif normal'>&#x2D4F;</span> &lt; <span class='nototif normal'>&#x2D47;</span> &lt;&lt; <span class='nototif normal'>&#x2D47;&#x2D6F;</span> &lt; <span class='nototif normal'>&#x2D54;</span> &lt; <span class='nototif normal'>&#x2D55;</span> &lt; <span class='nototif normal'>&#x2D59;</span> &lt; <span class='nototif normal'>&#x2D5A;</span> &lt; <span class='nototif normal'>&#x2D5C;</span> &lt;&lt; <span class='nototif normal'>&#x2D5C;&#x2D59;</span>  &lt; <span class='nototif normal'>&#x2D5F;</span> &lt; <span class='nototif normal'>&#x2D53;</span> &lt; <span class='nototif normal'>&#x2D61;</span> &lt; <span class='nototif normal'>&#x2D45;</span> &lt;&lt; <span class='nototif normal'>&#x2D45;&#x2D6F;</span> &lt; <span class='nototif normal'>&#x2D62;</span> &lt; <span class='nototif normal'>&#x2D63;</span> &lt; <span class='nototif normal'>&#x2D65;</span>

## <a id="trad"></a>Languages Using Traditional Tifinagh script

### <a id="gho"></a>Ghomara, Shilha

_Source_: [Omniglot](https://omniglot.com/writing/shilha.htm)

_Language Tag_: `gho-Tfng`

_Opentype language system tag:_ `BBR `

Characters | | | | | | | | | &#x0020;
:------- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :--
Tfng | <span class='nototif normal'>&#x2D30;</span> | <span class='nototif normal'>&#x2D31;</span> |<span class='nototif normal'>&#x2D33;</span> | <span class='nototif normal'>&#x2D37;</span> | <span class='nototif normal'>&#x2D39;</span> | <span class='nototif normal'>&#x2D3C;</span> | <span class='nototif normal'>&#x2D3D;</span> | <span class='nototif normal'>&#x2D40;</span> | <span class='nototif normal'>&#x2D43;</span> 
USV |2D30 | 2D31 | 2D33 | 2D37 | 2D39 | 203C | 2D3D | 2D40 |2D43
Latn | /a/ | /b/ | /g/ | /d/ | /d&#x0323;/ | /f/ | /k/ | /h/ | /h&#x0323;/
| | | | | | | | |
Tfng | <span class='nototif normal'>&#x2D44;</span> |<span class='nototif normal'>&#x2D45;</span> | <span class='nototif normal'>&#x2D47;</span> | <span class='nototif normal'>&#x2D49;</span> | <span class='nototif normal'>&#x2D4A;</span> | <span class='nototif normal'>&#x2D4D;</span> | <span class='nototif normal'>&#x2D4E;</span> | <span class='nototif normal'>&#x2D4F;</span> | <span class='nototif normal'>&#x2D53;</span>
USV | 2D44 | 2D45 | 2D47 | 2D49 | 204A | 2D4D | 2D4E | 2D4F |2D53 
Latn  | /&#x025B;/ | /x/ | /q/ | /i/ | /z&#x030C;/ | /l/ | /m/ | /n/ | /u/
| | | | | | | | |
Tfng  | <span class='nototif normal'>&#x2D54;</span> |<span class='nototif normal'>&#x2D55;</span> | <span class='nototif normal'>&#x2D56;</span> | <span class='nototif normal'>&#x2D59;</span> | <span class='nototif normal'>&#x2D5A;</span> | <span class='nototif normal'>&#x2D5B;</span> | <span class='nototif normal'>&#x2D5C;</span> | <span class='nototif normal'>&#x2D5F;</span> | <span class='nototif normal'>&#x2D61;</span>
USV | 2D54 | 2D55 | 2D56 | 2D59 | 205A | 2D5B | 2D5C | 2D5F | 2D61
Latn | /r/ | /r&#x0323;/ | /&#x0263;/ | /s/ | /s&#x0323;/ | /s&#x030C;/ | /t/ | /t&#x0323;/ | /w/
| | | | | | | | |
Tfng | <span class='nototif normal'>&#x2D62;</span> | <span class='nototif normal'>&#x2D63;</span> | <span class='nototif normal'>&#x2D65;</span> | <span class='nototif normal'>&#x2D6F;</span> | | | | | 
USV | 2D62 | 2D63 | 2D65 | 2D6F | | | | | 
Latn  | /y/ | /z/ | /z&#x0323;/ | /&#x02b7;/ | | | | | |
| | | | | | | | |

#### Known glyph variants

A variant of U+2D4d is used: <span class='hapaxberbere normal'>&#x2D4D;</span>

#### Bi-consonants

Unknown.

#### Collation

<span class='nototif normal'>&#x2D30;</span> &lt; <span class='nototif normal'>&#x2D31;</span> &lt; <span class='nototif normal'>&#x2D33;</span> &lt;&lt; <span class='nototif normal'>&#x2D33;&#x2D6F;</span> &lt; <span class='nototif normal'>&#x2D37;</span> &lt; <span class='nototif normal'>&#x2D39;</span> &lt; <span class='nototif normal'>&#x2D3C;</span> &lt; <span class='nototif normal'>&#x2D3D;</span> &lt;&lt; <span class='nototif normal'>&#x2D3D;&#x2D6F;</span> &lt;
<span class='nototif normal'>&#x2D40;</span> &lt; <span class='nototif normal'>&#x2D43;</span> &lt; <span class='nototif normal'>&#x2D44;</span> &lt; <span class='nototif normal'>&#x2D45;</span> &lt;&lt; <span class='nototif normal'>&#x2D45;&#x2D6F;</span>
&lt; <span class='nototif normal'>&#x2D47;</span> &lt; <span class='nototif normal'>&#x2D49;</span> &lt; <span class='nototif normal'>&#x2D4A;</span> &lt; <span class='nototif normal'>&#x2D4D;</span> &lt; <span class='nototif normal'>&#x2D4E;</span> &lt; <span class='nototif normal'>&#x2D4F;</span> &lt; <span class='nototif normal'>&#x2D53;</span> &lt; <span class='nototif normal'>&#x2D54;</span> &lt; <span class='nototif normal'>&#x2D55;</span> &lt; <span class='nototif normal'>&#x2D56;</span> &lt;&lt; <span class='nototif normal'>&#x2D56;&#x2D6F;</span> 
&lt; <span class='nototif normal'>&#x2D59;</span> &lt; <span class='nototif normal'>&#x2D5A;</span> &lt; <span class='nototif normal'>&#x2D5B;</span> &lt; <span class='nototif normal'>&#x2D5C;</span> &lt; <span class='nototif normal'>&#x2D5F;</span> &lt; <span class='nototif normal'>&#x2D61;</span> &lt; <span class='nototif normal'>&#x2D62;</span> &lt; <span class='nototif normal'>&#x2D63;</span> &lt; <span class='nototif normal'>&#x2D65;</span>

### <a id="rif"></a>Tarifit, Riffian

_Language tag:_ `rif-Tfng`

_Opentype language system tag:_ `BBR `

_Source_: [Omniglot](https://omniglot.com/writing/riffian.htm), [2009 New Testament](https://archive.org/details/newtestament-tarifit)

Characters | | | | | | | | | &#x0020;
:------- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :--
Tfng       | <span class='nototif normal'>&#x2D30;</span> | <span class='nototif normal'>&#x2D31;</span> | <span class='nototif normal'>&#x2D33;</span> | <span class='nototif normal'>&#x2D37;</span> | <span class='nototif normal'>&#x2D39;</span> | <span class='nototif normal'>&#x2D3B;</span> | <span class='nototif normal'>&#x2D3C;</span> | <span class='nototif normal'>&#x2D3D;</span> | <span class='nototif normal'>&#x2D40;</span>
USV        | 2D30 | 2D31 | 2D33 | 2D37 | 2D39 | 2D3B | 2D3C | 2D3D | 2D40
Latn        | /a/ | /b/ | /g/ | /d/ | /ḍ/ | /&#x01dd;/ | f | k | /h/
| | | | | | | | |
Tfng       | <span class='nototif normal'>&#x2D43;</span>  | <span class='nototif normal'>&#x2D44;</span> | <span class='nototif normal'>&#x2D45;</span> | <span class='nototif normal'>&#x2D47;</span> | <span class='nototif normal'>&#x2D49;</span> | <span class='nototif normal'>&#x2D4A;</span> | <span class='nototif normal'>&#x2D4D;</span> | <span class='nototif normal'>&#x2D4E;</span> | <span class='nototif normal'>&#x2D4F;</span>
USV        | 2D43 | 2D44 | 2D45 | 2D47 | 2D49 | 2D4A | 2D4D | 2D4E | 2D4F
Latn        | /h&#x0323;/ | /&#x025B;/ | /x/ | /q/ | /i/ | /j/ | /l/ | /m/ | /n/
| | | | | | | | |
Tfng        | <span class='nototif normal'>&#x2D53;</span> | <span class='nototif normal'>&#x2D54;</span> | <span class='nototif normal'>&#x2D55;</span> | <span class='nototif normal'>&#x2D56;</span> | <span class='nototif normal'>&#x2D59;</span> | <span class='nototif normal'>&#x2D5A;</span> | <span class='nototif normal'>&#x2D5B;</span> | <span class='nototif normal'>&#x2D5C;</span> | <span class='nototif normal'>&#x2D5E;</span> 
USV        | 2D53 | 2D54 | 2D55 | 2D56 | 2D59 | 2D5A | 2D5B | 2D5C | 2D5E 
Latn        | /u/ | /r/ | /r&#x0323;/ | /&#x0263;/ | /s/ | /s&#x0323;/ | /c/ | /t/ | /c&#x030C;/ 
| | | | | | | | |
Tfng        | <span class='nototif normal'>&#x2D5F;</span> | <span class='nototif normal'>&#x2D61;</span> | <span class='nototif normal'>&#x2D62;</span> | <span class='nototif normal'>&#x2D63;</span> | <span class='nototif normal'>&#x2D65;</span> | <span class='nototif normal'>&#x2D6F;</span>|  |  |  | |  | 
USV        | 2D5F | 2D61 | 2D62 | 2D63 | 2D65 | 2D6F |  |  | |  |  
Latn        | /t&#x0323;/ | /w/ | /y/ | /z/ | /z&#x0323;/ | /ʷ/ |  |  | |  |
| | | | | | | | |

#### Collation

<span class='nototif normal'>&#x2D30;</span> &lt; <span class='nototif normal'>&#x2D31;</span> &lt; <span class='nototif normal'>&#x2D33;</span> &lt;&lt; <span class='nototif normal'>&#x2D33;&#x2D6F;</span> &lt; <span class='nototif normal'>&#x2D37;</span> &lt; <span class='nototif normal'>&#x2D39;</span> &lt; <span class='nototif normal'>&#x2D3B;</span> &lt; <span class='nototif normal'>&#x2D3C;</span> &lt; <span class='nototif normal'>&#x2D3D;</span> &lt;&lt; <span class='nototif normal'>&#x2D3D;&#x2D6F;</span> &lt; <span class='nototif normal'>&#x2D40;</span> &lt; <span class='nototif normal'>&#x2D43;</span> &lt; <span class='nototif normal'>&#x2D44;</span> &lt; <span class='nototif normal'>&#x2D45;</span> &lt; <span class='nototif normal'>&#x2D47;</span> &lt; <span class='nototif normal'>&#x2D49;</span> &lt; <span class='nototif normal'>&#x2D4A;</span> &lt; <span class='nototif normal'>&#x2D4D;</span> &lt; <span class='nototif normal'>&#x2D4E;</span> &lt; <span class='nototif normal'>&#x2D4F;</span> &lt; <span class='nototif normal'>&#x2D53;</span> &lt; <span class='nototif normal'>&#x2D54;</span> &lt; <span class='nototif normal'>&#x2D55;</span> &lt; <span class='nototif normal'>&#x2D56;</span> &lt; <span class='nototif normal'>&#x2D59;</span> &lt; <span class='nototif normal'>&#x2D5A;</span> &lt; <span class='nototif normal'>&#x2D5B;</span> &lt; <span class='nototif normal'>&#x2D5E;</span> &lt; <span class='nototif normal'>&#x2D5C;</span> &lt; <span class='nototif normal'>&#x2D5F;</span> &lt; <span class='nototif normal'>&#x2D61;</span> &lt; <span class='nototif normal'>&#x2D62;</span> &lt; <span class='nototif normal'>&#x2D63;</span> &lt; <span class='nototif normal'>&#x2D65;</span>

_Source_: <a href="#tarifit2004">A Dictionary of Tarifit Berber (2004).</a> This set of characters is different than the set (dated 2009) above.

Characters | | | | | | | | | &#x0020;
:------- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :--
Tfng       | <span class='nototif normal'>&#x2D30;</span> | <span class='nototif normal'>&#x2D33;</span> | <span class='nototif normal'>&#x2D37;</span> | <span class='nototif normal'>&#x2D39;</span> | <span class='nototif normal'>&#x2D3B;</span> | <span class='nototif normal'>&#x2D3C;</span> | <span class='nototif normal'>&#x2D3D;</span> | <span class='nototif normal'>&#x2D40;</span> | <span class='nototif normal'>&#x2D43;</span>
USV        | 2D30 | 2D33 | 2D37 | 2D39 | 2D3B | 2D3C | 2D3D | 2D40 | 2D43
Latn        | /a/ | /g/ | /d/ | /dˁ/ | /&#x01dd;/ | /f/ | /k/ | /b, β, p/ | /h, &#x0127;/
| | | | | | | | |
Tfng       | <span class='nototif normal'>&#x2D45;</span> | <span class='nototif normal'>&#x2D47;</span> | <span class='nototif normal'>&#x2D49;</span> | <span class='nototif normal'>&#x2D4A;</span> | <span class='nototif normal'>&#x2D4D;</span> | <span class='nototif normal'>&#x2D4E;</span> | <span class='nototif normal'>&#x2D4F;</span> | <span class='nototif normal'>&#x2D52;</span> | <span class='nototif normal'>&#x2D53;</span>
USV        | 2D45 | 2D47 | 2D49 | 2D4A | 2D4D | 2D4E | 2D4F | 2D52 | 2D53
Latn        | /x/ | /q/ | /i/ | /ʒ/ | /l/ | /m/ | /n, &#x014b;/ | /ʕ/ | /u/
| | | | | | | | |
Tfng        |  <span class='nototif normal'>&#x2D54;</span> | <span class='nototif normal'>&#x2D56;</span> | <span class='nototif normal'>&#x2D59;</span> | <span class='nototif normal'>&#x2D5B;</span> | <span class='nototif normal'>&#x2D5C;</span> | <span class='nototif normal'>&#x2D5D;</span> | <span class='nototif normal'>&#x2D60;</span> | <span class='nototif normal'>&#x2D61;</span> | <span class='nototif normal'>&#x2D62;</span>  
USV        | 2D54 | 2D56 | 2D59 | 2D5B | 2D5C | 2D5D | 2D60 | 2D61 | 2D62 
Latn        | /r, rˁ/ | /&#x0263;/ | /s, sˁ/ | /ʃ/ | /t, tˁ/ | /θ/ | /ð, ðˁ/ | /w/ | /y/
| | | | | | | | |
Tfng        | <span class='nototif normal'>&#x2D63;</span> | | | | | | | 
USV        | 2D63 | | | | | | | |   
Latn        | /z, zˁ/ | | | | | | | |
| | | | | | | | |

#### Glyph variants and Bi-consonants

Unknown.

### <a id="shi"></a>Tachelhit

_Language tag:_ `shi`

_Opentype language system tag:_ `BBR `

_SLDR:_ [shi](https://github.com/silnrsi/sldr/blob/master/sldr/s/shi.xml)

Characters | | | | | | | | | &#x0020;
:------- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :--
Tfng | <span class='nototif normal'>&#x2D30;</span> | <span class='nototif normal'>&#x2D31;</span> | <span class='nototif normal'>&#x2D33;</span> | <span class='nototif normal'>&#x2D37;</span> | <span class='nototif normal'>&#x2D39;</span> | <span class='nototif normal'>&#x2D3B;</span> | <span class='nototif normal'>&#x2D3C;</span> | <span class='nototif normal'>&#x2D3D;</span> | <span class='nototif normal'>&#x2D40;</span> 
USV  |2D30 | 2D31 | 2D33 | 2D37      | 2D39 | 2D3B      | 2D3C | 2D3D | 2D40
| | | | | | | | |
Tfng | <span class='nototif normal'>&#x2D43;</span> | <span class='nototif normal'>&#x2D44;</span> | <span class='nototif normal'>&#x2D45;</span> | <span class='nototif normal'>&#x2D47;</span> | <span class='nototif normal'>&#x2D49;</span> | <span class='nototif normal'>&#x2D4A;</span> | <span class='nototif normal'>&#x2D4D;</span> | <span class='nototif normal'>&#x2D4E;</span> | <span class='nototif normal'>&#x2D4F;</span> 
USV  |2D43 | 2D44 | 2D45 | 2D47      | 2D49 | 2D4A      | 2D4D | 2D4E | 2D4F
| | | | | | | | |
Tfng | <span class='nototif normal'>&#x2D53;</span> | <span class='nototif normal'>&#x2D54;</span> | <span class='nototif normal'>&#x2D55;</span>| <span class='nototif normal'>&#x2D56;</span> | <span class='nototif normal'>&#x2D59;</span> | <span class='nototif normal'>&#x2D5A;</span> | <span class='nototif normal'>&#x2D5B;</span> | <span class='nototif normal'>&#x2D5C;</span> | <span class='nototif normal'>&#x2D5F;</span> 
USV  |2D53 | 2D54 | 2D55 | 2D56      | 2D59 | 2D5A      | 2D5B | 2D5C | 2D5F
| | | | | | | | |
Tfng | <span class='nototif normal'>&#x2D61;</span> | <span class='nototif normal'>&#x2D62;</span> | <span class='nototif normal'>&#x2D63;</span>| <span class='nototif normal'>&#x2D65;</span> | <span class='nototif normal'>&#x2D6F;</span> |  |  |  |  
USV  |2D61 | 2D62 | 2D63 | 2D65 | 2D6F | | | |
| | | | | | | | |

#### Glyph variants and Bi-consonants

Unknown.

#### Collation

<span class='nototif normal'>&#x2D30;</span> &lt; <span class='nototif normal'>&#x2D31;</span> &lt; <span class='nototif normal'>&#x2D33;</span> &lt;&lt; <span class='nototif normal'>&#x2D33;&#x2D6F;</span> <span class='nototif normal'>&#x2D37;</span> &lt; <span class='nototif normal'>&#x2D39;</span> &lt; <span class='nototif normal'>&#x2D3B;</span> &lt; <span class='nototif normal'>&#x2D3C;</span> &lt; <span class='nototif normal'>&#x2D3D;</span> &lt;&lt; <span class='nototif normal'>&#x2D3D;&#x2D6F;</span> &lt; <span class='nototif normal'>&#x2D40;</span> &lt; <span class='nototif normal'>&#x2D43;</span> &lt; <span class='nototif normal'>&#x2D44;</span> &lt; <span class='nototif normal'>&#x2D45;</span> &lt; <span class='nototif normal'>&#x2D47;</span> &lt; <span class='nototif normal'>&#x2D49;</span> &lt; <span class='nototif normal'>&#x2D4A;</span> &lt; <span class='nototif normal'>&#x2D4D;</span> &lt; <span class='nototif normal'>&#x2D4E;</span> &lt; <span class='nototif normal'>&#x2D4F;</span> &lt; <span class='nototif normal'>&#x2D53;</span> &lt; <span class='nototif normal'>&#x2D54;</span> &lt; <span class='nototif normal'>&#x2D55;</span> &lt; <span class='nototif normal'>&#x2D56;</span> &lt; <span class='nototif normal'>&#x2D59;</span> &lt; <span class='nototif normal'>&#x2D5A;</span> &lt; <span class='nototif normal'>&#x2D5B;</span> &lt; <span class='nototif normal'>&#x2D5C;</span> &lt; <span class='nototif normal'>&#x2D5F;</span> &lt; <span class='nototif normal'>&#x2D61;</span> &lt; <span class='nototif normal'>&#x2D62;</span> &lt; <span class='nototif normal'>&#x2D63;</span> &lt; <span class='nototif normal'>&#x2D65;</span>


### <a id="siz"></a>Siwi

_Source_: [Omniglot](https://omniglot.com/writing/siwi.htm)

_Language Tag_: `siz-Tfng`

_Opentype language system tag:_ `BBR `

Characters | | | | | | | | | &#x0020;
:------- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :--
Tfng   | <span class='nototif normal'>&#x2D30;</span> | <span class='nototif normal'>&#x2D31;</span> | <span class='nototif normal'>&#x2D33;</span> | <span class='nototif normal'>&#x2D36;</span> | <span class='nototif normal'>&#x2D37;</span> | <span class='nototif normal'>&#x2D39;</span> | <span class='nototif normal'>&#x2D3B;</span> | <span class='nototif normal'>&#x2D3C;</span> | <span class='nototif normal'>&#x2D3D;</span>
USV | 2D30 | 2D31 | 2D33 | 2D36 | 2D37 | 2D39 | 2D3B | 2D3C | 2D3D
Latn | /a/ | /b/ | /g/ | /j/ | /d/ | /d&#x0323;/ | /&#x01DD;/ | /f/ | /k/
| | | | | | | | |
Tfng   | <span class='nototif normal'>&#x2D40;</span> | <span class='nototif normal'>&#x2D43;</span> | <span class='nototif normal'>&#x2D44;</span> | <span class='nototif normal'>&#x2D45;</span> | <span class='nototif normal'>&#x2D47;</span> | <span class='nototif normal'>&#x2D49;</span> | <span class='nototif normal'>&#x2D4D;</span> | <span class='nototif normal'>&#x2D4E;</span> | <span class='nototif normal'>&#x2D4F;</span> 
USV | 2D40 | 2D43 | 2D44 | 2D45 | 2D47 | 2D49 | 2D4D | 2D4E | 2D4F
Latn | /h/ | /h&#x0323;/ | /&#x0027;/ | /x/ | /q/ | /i/ | /l/ | /m/ | /n/
| | | | | | | | |
Tfng   | <span class='nototif normal'>&#x2D53;</span> | <span class='nototif normal'>&#x2D54;</span> | <span class='nototif normal'>&#x2D55;</span> | <span class='nototif normal'>&#x2D56;</span> | <span class='nototif normal'>&#x2D59;</span> | <span class='nototif normal'>&#x2D5A;</span> | <span class='nototif normal'>&#x2D5B;</span> | <span class='nototif normal'>&#x2D5C;</span> | <span class='nototif normal'>&#x2D5E;</span>
USV  | 2D53 | 2D54 | 2D55 | 2D56 | 2D59 | 2D5A | 2D5B | 2D5C | 2D5E
Latn | /u/ | /r/ | /r&#x0323;/ | /g&#x030C;/ | /s/ | /s&#x0323;/ | /s&#x030C;/ | /t/ | /c&#x030C;/ 
| | | | | | | | |
Tfng   | <span class='nototif normal'>&#x2D5F;</span> | <span class='nototif normal'>&#x2D61;</span> | <span class='nototif normal'>&#x2D62;</span> | <span class='nototif normal'>&#x2D63;</span> | <span class='nototif normal'>&#x2D65;</span> | <span class='nototif normal'>&#x2D6F;</span>
USV | 2D5F | 2D61 | 2D62 | 2D63 | 2D65 | 2D6F
Latn | /t&#x0323;/ | /w/ | /y/ | /z/ | /z&#x0323;/ | /&#x02b7;/


Other characters | | | |
:-------   | :-- | :-- | :--
Tfng | <span class='nototif normal'>&#x2D30;&#x2D49;</span> |<span class='nototif normal'>&#x2D30;&#x2D53;</span> |<span class='nototif normal'>&#x2D54;&#x2D54;</span>
USV  | 2D30 2D49 | 2D30 2D53 | 2D54 2D54
Latin | /ai/ /e/ | /au/ /o/ | /rr/
| | |

#### Glyph variants and Bi-consonants

Unknown.

#### Collation

<span class='nototif normal'>&#x2D30;</span> &lt;&lt; <span class='nototif normal'>&#x2D30;&#x2D49;</span> &lt;&lt; <span class='nototif normal'>&#x2D30;&#x2D53;</span> &lt; <span class='nototif normal'>&#x2D31;</span> &lt;&lt; <span class='nototif normal'>&#x2D31;&#x2D6F;</span> &lt; <span class='nototif normal'>&#x2D33;</span> &lt;&lt; <span class='nototif normal'>&#x2D33;&#x2D6F;</span> &lt; <span class='nototif normal'>&#x2D37;</span> &lt; <span class='nototif normal'>&#x2D36;</span> &lt; <span class='nototif normal'>&#x2D39;</span> &lt; <span class='nototif normal'>&#x2D3B;</span> &lt; <span class='nototif normal'>&#x2D3C;</span> &lt;&lt; <span class='nototif normal'>&#x2D3C;&#x2D6F;</span> &lt; <span class='nototif normal'>&#x2D3D;</span> &lt; <span class='nototif normal'>&#x2D3D;&#x2D6F;</span> &lt; <span class='nototif normal'>&#x2D40;</span> &lt; <span class='nototif normal'>&#x2D43;</span> &lt; <span class='nototif normal'>&#x2D44;</span> &lt; <span class='nototif normal'>&#x2D45;</span> &lt;&lt; <span class='nototif normal'>&#x2D45;&#x2D6F;</span> &lt; <span class='nototif normal'>&#x2D47;</span> &lt; <span class='nototif normal'>&#x2D49;</span> &lt; <span class='nototif normal'>&#x2D4D;</span> &lt;&lt; <span class='nototif normal'>&#x2D4D;&#x2D6F;</span> &lt; <span class='nototif normal'>&#x2D4E;</span> &lt; <span class='nototif normal'>&#x2D4E;&#x2D6F;</span> &lt; <span class='nototif normal'>&#x2D4F;</span> &lt; <span class='nototif normal'>&#x2D53;</span> &lt; <span class='nototif normal'>&#x2D54;</span> &lt;&lt; <span class='nototif normal'>&#x2D54;&#x2D54;</span> &lt; <span class='nototif normal'>&#x2D55;</span> &lt; <span class='nototif normal'>&#x2D56;</span> &lt;&lt; <span class='nototif normal'>&#x2D56; &#x2D6F;</span> &lt; <span class='nototif normal'>&#x2D59;</span> &lt; <span class='nototif normal'>&#x2D5A;</span> &lt; <span class='nototif normal'>&#x2D5B;</span> &lt; <span class='nototif normal'>&#x2D5C;</span> &lt; <span class='nototif normal'>&#x2D5E;</span> &lt; <span class='nototif normal'>&#x2D5F;</span> &lt; <span class='nototif normal'>&#x2D61;</span> &lt; <span class='nototif normal'>&#x2D62;</span> &lt; <span class='nototif normal'>&#x2D63;</span> &lt; <span class='nototif normal'>&#x2D65;</span> 


### <a id="taq"></a>Tamasheq

_Source_: [Omniglot](https://omniglot.com/writing/tamasheq.htm)

_Language Tag_: `taq-Tfng`

_Opentype language system tag:_ `TMH ` and `BBR `

Characters | | | | | | | | | &#x0020;
:------- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :--
Tfng       | <span class='nototif normal'>&#x2D30;</span> | <span class='nototif normal'>&#x2D31;</span> | <span class='nototif normal'>&#x2D34;</span> | <span class='nototif normal'>&#x2D36;</span> | <span class='nototif normal'>&#x2D37; / &#x2D38;</span> | <span class='nototif normal'>&#x2D39;</span> | <span class='nototif normal'>&#x2D3C;</span> | <span class='nototif normal'>&#x2D3E;</span> | <span class='nototif normal'>&#x2D42;</span> 
USV        | 2D30 | 2D31 | 2D34 | 2D36 | 2D37 or 2D38 | 2D39 | 2D3C | 2D3E | 2D42 
Latn        | /a/ | /b/ | /g/ | /j/ | /d/ | /ḍ/ | /f/ | /k/ | /h/ 
| | | | | | | | |
 Tfng       |<span class='nototif normal'>&#x2D43;</span> |<span class='nototif normal'>&#x2D44;</span> | <span class='nototif normal'>&#x2D46;</span> | <span class='nototif normal'>&#x2D48;</span> | <span class='nototif normal'>&#x2D49;</span> | <span class='nototif normal'>&#x2D4B; or &#x2D4C;</span> | <span class='nototif normal'>&#x2D4D;</span> | <span class='nototif normal'>&#x2D4E;</span> | <span class='nototif normal'>&#x2D4F;</span> 
USV        | 2D43 | 2D44| 2D46 | 2D48 | 2D49 | 2D4B or 2D4C | 2D4D | 2D4E | 2D4F 
Latn        | /h&#x0323;/ | /&#x025B;/ | /x/ | /q/ | /i/ | /z&#x030C;/ | /l/ | /m/ | /n/ 
| | | | | | | | |
Tfng       | <span class='nototif normal'>&#x2D51;</span> | <span class='nototif normal'>&#x2D53;</span> |<span class='nototif normal'>&#x2D54;</span> |<span class='nototif normal'>&#x2D57;</span>| <span class='nototif normal'>&#x2D59;</span> | <span class='nototif normal'>&#x2D5A;</span> | <span class='nototif normal'>&#x2D5B;</span> | <span class='nototif normal'>&#x2D5C;</span> | <span class='nototif normal'>&#x2D5F;</span> 
USV         | 2D51 | 2D53 | 2D54 | 2D57 | 2D59 | 2D5A | 2D5B | 2D5C | 2D5F 
Latn        | /&#x014B;/ | /o/ /u/ | /r/ | /&#x0263;/ | /s/ | /s&#x0323;/ | /s&#x030C;/ | /t/ | /t&#x0323;/
| | | | | | | | |
Tfng       | <span class='nototif normal'>&#x2D61;</span> | <span class='nototif normal'>&#x2D62;</span> | <span class='nototif normal'>&#x2D63;</span> | <span class='nototif normal'>&#x2D65;</span> |<span class='nototif normal'>&#x2D66;</span> |
USV         | 2D61 | 2D62 | 2D63 | 2D65 | 2D66 | 
Latn        | /w/ | /y/ | /z/ | /z&#x0323;/ | /e/ /&#x01DD;/| 
| | | | | | | | |

#### Glyph variants and Bi-consonants

Unknown.

#### Collation

<span class='nototif normal'>&#x2D30;</span> &lt; <span class='nototif normal'>&#x2D31;</span> &lt; <span class='nototif normal'>&#x2D34;</span> &lt; <span class='nototif normal'>&#x2D36;</span> &lt; <span class='nototif normal'>&#x2D37; / &#x2D38;</span> &lt; <span class='nototif normal'>&#x2D39;</span> &lt; <span class='nototif normal'>&#x2D3C;</span> &lt; <span class='nototif normal'>&#x2D3E;</span> &lt; <span class='nototif normal'>&#x2D42;</span> &lt; <span class='nototif normal'>&#x2D43;</span> &lt; <span class='nototif normal'>&#x2D44;</span> &lt; <span class='nototif normal'>&#x2D46;</span> &lt; <span class='nototif normal'>&#x2D48;</span> &lt; <span class='nototif normal'>&#x2D49;</span> &lt; <span class='nototif normal'>&#x2D4C; or &#x2D4B;</span> &lt;  <span class='nototif normal'>&#x2D4D;</span> &lt; <span class='nototif normal'>&#x2D4E;</span> &lt; <span class='nototif normal'>&#x2D4F;</span> &lt; <span class='nototif normal'>&#x2D51;</span> &lt; <span class='nototif normal'>&#x2D53;</span> &lt; <span class='nototif normal'>&#x2D54;</span> &lt; <span class='nototif normal'>&#x2D57;</span> &lt; <span class='nototif normal'>&#x2D59;</span> &lt; <span class='nototif normal'>&#x2D5A;</span> &lt; <span class='nototif normal'>&#x2D5B;</span> &lt; <span class='nototif normal'>&#x2D5C;</span> &lt; <span class='nototif normal'>&#x2D5F;</span> &lt; <span class='nototif normal'>&#x2D61;</span> &lt; <span class='nototif normal'>&#x2D62;</span> &lt; <span class='nototif normal'>&#x2D63;</span> &lt; <span class='nototif normal'>&#x2D65;</span> &lt; <span class='nototif normal'>&#x2D66;</span>

### <a id="taq-ML"></a>Tamasheq (Mali)

_Source_: [Savage, 2000](#savage2000)

_Language Tag_: `taq-Tfng-ML`

_Opentype language system tag:_ `TMH ` and `BBR `

_Two of these characters are possibly not right. The second U+2D4D is wrong, but I do not know what it should be. U+2D49 is also possibly not correct. In the source it is reversed._

Characters | | | | | | | | | &#x0020;
:------- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :--
Tfng       | <span class='akatab normal' style='font-feature-settings: "cv01" 1'>&#x2D30;</span> | <span class='akatab normal'>&#x2D31;</span> | <span class='akatab normal'>&#x2D36;</span> | <span class='akatab normal'>&#x2D37;</span> | <span class='akatab normal'>&#x2D39;</span> |<span class='akatab normal' style='font-feature-settings: "cv02" 1'>&#x2D3C;</span> | <span class='akatab normal'>&#x2D3E;</span> | <span class='akatab normal'>&#x2D4D;</span> | <span class='akatab normal'>&#x2D4D; ???</span> 
USV        | 2D30 | 2D31 | 2D36 | 2D37 | 2D39 | 2D3C | 2D3E | 2D4D | 2D4D ???
Latn        | /&#x0251;/ | /b/ | /&#x0261;/ | /d/ | /ḍ/ | /f/ | /k/ | /l/ | /ḷ/ 
| | | | | | | | |
 Tfng       | <span class='akatab normal'>&#x2D42;</span> | <span class='akatab normal'>&#x2D46;</span> | <span class='akatab normal'>&#x2D48;</span> | <span class='akatab normal'>&#x2D49;</span> | <span class='akatab normal'>&#x2D4B;</span> | <span class='akatab normal'>&#x2D4C;</span> | <span class='akatab normal'>&#x2D4E;</span> | <span class='akatab normal'>&#x2D4F;</span> | <span class='akatab normal'>&#x2D53;</span>
USV        | 2D42 | 2D46| 2D48 | 2D49 | 2D4B | 2D4C | 2D4E | 2D4F | 2D53 
Latn        | /h/ | /x/ | /q/ | /y/ | /z&#x030C;/ | /z&#x0323;/  | /m/ | /n/ | /w/ 
| | | | | | | | |
Tfng       | <span class='akatab normal'>&#x2D54;</span> | <span class='akatab normal'>&#x2D57;</span> | <span class='akatab normal'>&#x2D58;</span> | <span class='akatab normal'>&#x2D59;</span> | <span class='akatab normal'>&#x2D5A;</span> | <span class='akatab normal' style='font-feature-settings: "cv12" 1'>&#x2D5B;</span> | <span class='akatab normal'>&#x2D5C;</span> | <span class='akatab normal' style='font-feature-settings: "cv13" 1'>&#x2D5F;</span> | <span class='akatab normal'>&#x2D63;</span> 
USV         | 2D54 | 2D57 | 2D58 | 2D59 | 2D5A | 2D5B | 2D5C | 2D5F | 2D63 
Latn        | /r/ | /&#x0263;/ | /j&#x030c;/ | /s/ | /s&#x0323;/ | /s&#x030c;/ | /t/ | /t&#x0323;/ | /z/
| | | | | | | | |

#### Glyph variants

USV |&#x0020; | &#x0020; | &#x0020;
:--  | :--  | :--  | :--
2D30 | <span class='nototif normal'>&#x2D30;</span>|&#x003E;|<span class='akatab normal'>&#x2D30;</span>
2D3C | <span class='nototif normal'>&#x2D3C;</span>|&#x003E;|<span class='akatab normal' style='font-feature-settings: "cv02" 1'>&#x2D3C;</span>
2D4D | <span class='nototif normal'>&#x2D4D;</span>|&#x003E;|<span class='akatab normal'>&#x2D4D;</span>
2D5C | <span class='nototif normal'>&#x2D5C;</span>|&#x003E;|<span class='akatab normal'>&#x2D5C;</span>
2D5A | <span class='nototif normal'>&#x2D5A;</span>|&#x003E;|<span class='akatab normal'>&#x2D5A;</span>
2D5F | <span class='nototif normal'>&#x2D5F;</span>|&#x003E;|<span class='akatab normal' style='font-feature-settings: "cv13" 1'>&#x2D5F;</span>
2D63 | <span class='nototif normal'>&#x2D63;</span>|&#x003E;|<span class='akatab normal'>&#x2D63;</span>


#### Bi-Consonants

USV | 2D7F between characters | → | Glyph 
:----- | :--  | :-- | :-- 
2D4F 2D37 | <span class='akatab normal'>&#x2D4F; + &#x2D7F; + &#x2D37;</span> | → | <span class='akatab normal' style='font-feature-settings: "cv41" 1'>&#x2D4F;&#x2D7F;&#x2D37;</span>
2D59 2D4F | <span class='akatab normal'>&#x2D59; + &#x2D7F; + &#x2D4F;</span> | → | <span class='akatab normal'>&#x2D59;&#x2D7F;&#x2D4F;</span>
2D4F 2D5C | <span class='akatab normal'>&#x2D4F; + &#x2D7F; + &#x2D5C;</span> | → | <span class='akatab normal' style='font-feature-settings: "cv37" 2'>&#x2D4F;&#x2D7F;&#x2D5C;</span>
2D4F 2D3E | <span class='akatab normal'>&#x2D4F; + &#x2D7F; + &#x2D3E;</span> | → | <span class='akatab normal' style='font-feature-settings: "cv36" 1'>&#x2D4F;&#x2D7F;&#x2D3E;</span>
2D4F 2D3C | <span class='akatab normal'>&#x2D4F; + &#x2D7F; + &#x2D3C;</span> | → | <span class='akatab normal' style='font-feature-settings: "cv42" 1'>&#x2D4F;&#x2D7F;&#x2D3C;</span>
2D54 2D5C | <span class='akatab normal'>&#x2D54; + &#x2D7F; + &#x2D5C;</span> | → | <span class='akatab normal' style='font-feature-settings: "cv32" 1'>&#x2D54;&#x2D7F;&#x2D5C;</span>
2D59 2D5C | <span class='akatab normal'>&#x2D59; + &#x2D7F; + &#x2D5C;</span> | → | <span class='akatab normal' style='font-feature-settings: "cv33" 3'>&#x2D59;&#x2D7F;&#x2D5C;</span>
2D49 2D5C | <span class='akatab normal'>&#x2D49; + &#x2D7F; + &#x2D5C;</span> | → | <span class='akatab normal' style='font-feature-settings: "cv33" 1'>&#x2D49;&#x2D7F;&#x2D5C;</span>
2D4D 2D5C | <span class='akatab normal'>&#x2D4D; + &#x2D7F; + &#x2D5C;</span> | → | <span class='akatab normal' style='font-feature-settings: "cv38" 2'>&#x2D4D;&#x2D7F;&#x2D5C;</span>
2D53 2D5C | <span class='akatab normal'>&#x2D53; + &#x2D7F; + &#x2D5C;</span> | → | <span class='akatab normal' style='font-feature-settings: "cv39" 2'>&#x2D53;&#x2D7F;&#x2D5C;</span>
2D4C 2D5C | <span class='akatab normal'>&#x2D4C; + &#x2D7F; + &#x2D5C;</span> | → | <span class='akatab normal' style='font-feature-settings: "cv40" 2'>&#x2D4C;&#x2D7F;&#x2D5C;</span>
2D4E 2D5C | <span class='akatab normal'>&#x2D4E; + &#x2D7F; + &#x2D5C;</span> | → | <span class='akatab normal'>&#x2D4E;&#x2D7F;&#x2D5C;</span>
2D3C 2D5C | <span class='akatab normal'>&#x2D3C; + &#x2D7F; + &#x2D5C;</span> | → | <span class='akatab normal' style='font-feature-settings: "cv35" 2'>&#x2D3C;&#x2D7F;&#x2D5C;</span>

#### Contextual Shaping

Contextual Shaping |     |     |     |     |     |  |
:-------   | :-- | :-- | :-- | :-- | :-- | :--
<span class='akatab normal'>&#x2D4D;</span> | + | <span class='akatab normal'>&#x2D4D;</span> | + | <span class='akatab normal'>&#x2D4D;</span> | → | <span class='akatab normal'>&#x2D4D;&#x2D4D;&#x2D4D;</span>
2D4D | | 2D4D | | 2D4D | | |
| | | | | |
<span class='akatab normal'>&#x2D4D;</span> | + | <span class='akatab normal'>&#x2D4F;</span>| + |<span class='akatab normal'>&#x2D4D;</span> | → | <span class='akatab normal'>&#x2D4D;&#x2D4F;&#x2D4D;</span>
2D4D | | 2D4F | | 2D4D | |
| | | | | |
<span class='akatab normal'>&#x2D4F;</span> | + | <span class='akatab normal'>&#x2D4D;</span> | + | <span class='akatab normal'>&#x2D4F;</span>| → | <span class='akatab normal'>&#x2D4F;&#x2D4D;&#x2D4F;</span> 
2D4F | | 2D4D | | 2D4F | | 
| | | | | |
<span class='akatab normal'>&#x2D4F;</span> | + | <span class='akatab normal'>&#x2D4F;</span>| + | <span class='akatab normal'>&#x2D4F;</span> | → | <span class='akatab normal'>&#x2D4F;&#x2D4F;&#x2D4F;</span>
2D4F | | 2D4F | | 2D4F | |
| | | | | |

#### Collation

<span class='akatab normal' style='font-feature-settings: "cv01" 1'>&#x2D30;</span> &lt;
<span class='akatab normal'>&#x2D31;</span> &lt;
<span class='akatab normal'>&#x2D5C;</span> &lt;
<span class='akatab normal' style='font-feature-settings: "cv13" 1'>&#x2D5F;</span> &lt;
<span class='akatab normal'>&#x2D37;</span> &lt;
<span class='akatab normal'>&#x2D39;</span> &lt;
<span class='akatab normal'>&#x2D3E;</span> &lt;
<span class='akatab normal'>&#x2D36;</span> &lt;
<span class='akatab normal'>&#x2D48;</span> &lt;
<span class='akatab normal'>&#x2D4E;</span> &lt;
<span class='akatab normal'>&#x2D4F;</span> &lt;
<span class='akatab normal'>&#x2D54;</span> &lt;
<span class='akatab normal' style='font-feature-settings: "cv02" 1'>&#x2D3C;</span> &lt;
<span class='akatab normal'>&#x2D59;</span> &lt;
<span class='akatab normal'>&#x2D5A;</span> &lt;
<span class='akatab normal'>&#x2D63;</span> &lt;
<span class='akatab normal'>&#x2D4C;</span> &lt;
<span class='akatab normal' style='font-feature-settings: "cv12" 1'>&#x2D5B;</span> &lt;
<span class='akatab normal'>&#x2D4B;</span> &lt;
<span class='akatab normal'>&#x2D46;</span> &lt;
<span class='akatab normal'>&#x2D57;</span> &lt;
<span class='akatab normal'>&#x2D42;</span> &lt;
<span class='akatab normal'>&#x2D58;</span> &lt;
<span class='akatab normal'>&#x2D4D;</span> &lt;
<span class='akatab normal'>&#x2D4D; ???</span> &lt;
<span class='akatab normal'>&#x2D53;</span> &lt;
<span class='akatab normal'>&#x2D49;</span>

### <a id="tda"></a>Tuareg (Azawagh dialect of Niger-Mali), Tagdal

_**Source**_: [L2/04-142](https://www.unicode.org/L2/L2004/04142r-n2739r-tifinagh.pdf) (pages 8 & 31)

_**Language Tag**_: `tda-Tfng`


### <a id="thv"></a> Tahaggart Tamahaq

_Language tag:_ `thv-Tfng`

_Opentype language system tag:_ `TMH ` and `BBR `

_Keyman keyboard:_ [Tuareg Tifinagh](https://keyman.com/keyboards/tuareg_tifinagh) [taq, thv]

_Font:_ [Akatab](https://software.sil.org/akatab/)

_**Source**_: Possibly from keyboard?

Characters | | | | | | | | | &#x0020;
:------- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :--
Tfng | <span class='akatab normal'>&#x2D30;</span> | <span class='akatab normal'>&#x2D31;</span> | <span class='akatab normal' style='font-feature-settings: "cv03" 1'>&#x2D34;</span>| <span class='akatab normal'>&#x2D36;</span> | <span class='akatab normal'>&#x2D37;</span> | <span class='akatab normal'>&#x2D39;</span> | <span class='akatab normal'>&#x2D3C;</span> | <span class='akatab normal'>&#x2D3E;</span> | <span class='akatab normal'>&#x2D42;</span> 
USV  |2D30 | 2D31 | 2D34 | 2D36      | 2D37 | 2D39      | 2D3C | 2D3E | 2D42
Latn | /a/   | /b/    | /g/    | /g&#x030c;/ | /d/    | d&#x0323; | /f/    | /k/    | /h/   
| | | | | | | | |
Tfng | <span class='akatab normal'>&#x2D46;</span> | <span class='akatab normal'>&#x2D48;</span> | <span class='akatab normal'>&#x2D49;</span>| <span class='akatab normal'>&#x2D4B;</span> | <span class='akatab normal'>&#x2D4C;</span> | <span class='akatab normal'>&#x2D4D;</span> | <span class='akatab normal'>&#x2D4E;</span> | <span class='akatab normal'>&#x2D4F;</span> | <span class='akatab normal'>&#x2D50;</span> 
USV  |2D46 | 2D48 | 2D49 | 2D4B      | 2D4C | 2D4D      | 2D4E | 2D4F | 2D50
Latn | /x/   | /q/    | /&#x0263;/    | /j/ | /z&#x0323;/    | /d/ | /m/    | /n/    | /&#x014b;/   
| | | | | | | | |
Tfng | <span class='akatab normal'>&#x2D53;</span> | <span class='akatab normal'>&#x2D54;</span> | <span class='akatab normal'>&#x2D57;</span>| <span class='akatab normal'>&#x2D59;</span> | <span class='akatab normal'>&#x2D5B;</span> | <span class='akatab normal'>&#x2D5C;</span> | <span class='akatab normal'>&#x2D5F;</span> | <span class='akatab normal'>&#x2D63;</span> |  
USV  |2D53 | 2D54 | 2D57 | 2D59 | 2D5B | 2D5C | 2D5F | 2D63 | 
Latn | /u/   | /r/    | /&#x0263;/ | /s/ | /s&#x030C;/ | /t/ | /t&#x0323;/ | /z/ | 

#### Glyph variants

USV |&#x0020; | &#x0020; | &#x0020;
:--  | :--  | :--  | :--
2D30 | <span class='nototif normal'>&#x2D30;</span>|&#x003E;|<span class='akatab normal'>&#x2D30;</span>
2D34 | <span class='nototif normal' style='font-feature-settings: "cv03" 1'>&#x2D34;</span>|&#x003E;|<span class='akatab normal'>&#x2D34;</span>
2D3C | <span class='nototif normal'>&#x2D3C;</span>|&#x003E;|<span class='akatab normal'>&#x2D3C;</span>
2D4B | <span class='nototif normal'>&#x2D4B;</span>|&#x003E;|<span class='akatab normal'>&#x2D4B;</span>
2D4D | <span class='nototif normal'>&#x2D4D;</span>|&#x003E;|<span class='akatab normal'>&#x2D4D;</span>
2D50 | <span class='nototif normal'>&#x2D50;</span>|&#x003E;|<span class='akatab normal'>&#x2D50;</span>
2D53 | <span class='nototif normal'>&#x2D53;</span>|&#x003E;|<span class='akatab normal'>&#x2D53;</span>
2D5B | <span class='nototif normal'>&#x2D5B;</span>|&#x003E;|<span class='akatab normal'>&#x2D5B;</span>
2D63 | <span class='nototif normal'>&#x2D63;</span>|&#x003E;|<span class='akatab normal'>&#x2D63;</span>

#### Bi-consonants

Unknown.

### <a id="thz"></a>Tayart Tamajeq, Tuareg (Aïr dialect of Niger)

_Source_: [Omniglot](https://omniglot.com/writing/tayarttamajeq.htm) and [L2/04-142](https://www.unicode.org/L2/L2004/04142r-n2739r-tifinagh.pdf) (pages 8 & 31)

_Language Tag_: `thz-Tfng`

_Opentype language system tag:_ `TMH ` and `BBR `

The order of these characters is based on Unicode codepoints, not on the order listed in the sources. The two sources have an inconsistent character set. This is a combination of the two. 

Characters | | | | | | | | | &#x0020;
:------- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :--
Tfng | <span class='nototif normal'>&#x2D30;</span> |  <span class='nototif normal'>&#x2D33;</span> | <span class='nototif normal'>&#x2D36;</span> | <span class='nototif normal'>&#x2D37;</span> | <span class='nototif normal'>&#x2D39;</span> | <span class='nototif normal'>&#x2D3B;</span> | <span class='nototif normal'>&#x2D3C;</span> | <span class='nototif normal'>&#x2D3E;</span> | <span class='nototif normal'>&#x2D40;</span> 
USV | 2D30 | 2D33 | 2D36 | 2D37 | 2D39 | 203B | 2D3C | 2D3E | 2D40 
Latn | /a/ | /g/ | /g&#x030C;/ | /d/ | /d&#x0323;/ | /&#x01DD;/ | /f/ | /k/ | /b/
| | | | | | | | |
Tfng  | <span class='nototif normal'>&#x2D42;</span> | <span class='nototif normal'>&#x2D46;</span> | <span class='nototif normal'>&#x2D48;</span> | <span class='nototif normal'>&#x2D49;</span> | <span class='nototif normal'>&#x2D4C;</span> | <span class='nototif normal'>&#x2D4D;</span> | <span class='nototif normal'>&#x2D4E;</span> | <span class='nototif normal'>&#x2D4F;</span> | <span class='nototif normal'>&#x2D51;</span>
USV | 2D42 | 2D46 | 2D48 | 2D49 | 2D4C | 2D4D | 2D4E | 2D4F | 2D51
Latn | /h/ | /x/ | /q/ | /i/ | /j/ | /l/ | /m/ | /n/ | /&#x014B;/
| | | | | | | | |
Tfng   | <span class='nototif normal'>&#x2D53;</span> | <span class='nototif normal'>&#x2D54;</span>| <span class='nototif normal'>&#x2D55;</span> | <span class='nototif normal'>&#x2D57;</span> | <span class='nototif normal'>&#x2D59;</span>| <span class='nototif normal'>&#x2D5A;</span> | <span class='nototif normal'>&#x2D5B;</span> | <span class='nototif normal'>&#x2D5C;</span> | <span class='nototif normal'>&#x2D5F;</span> 
USV  | 2D53 | 2D54 |  2D55 | 2D57 | 2D59 | 2D5A | 2D5B | 2D5C | 2D5F 
Latn  | /w/ /u/ | /r/ | /r&#x0323;/ | /&#x0263;/ | /s/ | /s&#x0323;/ | /s&#x030C;/ | /t/ | /t&#x0323;/ 
| | | | | | | | |
Tfng   | <span class='nototif normal'>&#x2D62;</span> | <span class='nototif normal'>&#x2D63;</span> / <span class='nototif normal'>&#x2D64;</span> | <span class='nototif normal'>&#x2D65;</span> | <span class='nototif normal'>&#x2D66;</span> | <span class='nototif normal'>&#x2D67;</span> | <span class='nototif normal'>&#x2D70;</span>
USV | 2D62 | 2D63 / 2D64 | 2D65 | 2D66 | 2D67 | 2D70
Latn | /y/ | /z/ | /z&#x0323;/ | /e/ | /o/ |
| | | | | | | | |

It is unclear if this is meant to be a required bi-consonant.

Other "letters" | |
:-------   | :-- 
Tfng | <span class='nototif normal'>&#x2D5C;&#x2D5B;</span> 
USV  | 2D5C 2D5B
Latn | c&#x030C;

#### Punctuation

All punctuation required for Neo-Tifinagh is also required for `thz`. In addition, the separator mark is used: U+2D70 <span class='nototif normal'>&#x2D70;</span>.

#### Glyph variants

&#x0020; | &#x0020; | &#x0020;
:--  | :--  | :--
<span class='nototif normal'>&#x2D30;</span>|&#x003E;|<span class='akatab normal'>&#x2D30;</span>
<span class='nototif normal'>&#x2D3C;</span>|&#x003E;|<span class='akatab normal' style='font-feature-settings: "cv02" 2'>&#x2D3C;</span>
<span class='nototif normal'>&#x2D4D;</span>|&#x003E;|<span class='akatab normal'>&#x2D4D;</span>
<span class='nototif normal'>&#x2D53;</span>|&#x003E;|<span class='akatab normal'>&#x2D53;</span>
<span class='nototif normal'>&#x2D5B;</span>|&#x003E;|<span class='akatab normal'>&#x2D5B;</span>
<span class='nototif normal'>&#x2D67;</span>|&#x003E;|<span class='akatab normal'>&#x2D67;</span>

#### Bi-consonants

Unknown.

#### Collation

<span class='nototif normal'>&#x2D30;</span> &lt; <span class='nototif normal'>&#x2D40;</span> &lt; <span class='nototif normal'>&#x2D33;</span> &lt; <span class='nototif normal'>&#x2D36;</span> &lt; <span class='nototif normal'>&#x2D37;</span> &lt; <span class='nototif normal'>&#x2D39;</span> &lt; <span class='nototif normal'>&#x2D3B;</span> &lt; <span class='nototif normal'>&#x2D66;</span> &lt; <span class='nototif normal'>&#x2D3C;</span> &lt; <span class='nototif normal'>&#x2D3E;</span> &lt; <span class='nototif normal'>&#x2D42;</span> &lt; <span class='nototif normal'>&#x2D46;</span> &lt; <span class='nototif normal'>&#x2D48;</span> &lt; <span class='nototif normal'>&#x2D49;</span> &lt; <span class='nototif normal'>&#x2D4C;</span> &lt; <span class='nototif normal'>&#x2D4D;</span> &lt; <span class='nototif normal'>&#x2D4E;</span> &lt; <span class='nototif normal'>&#x2D4F;</span> &lt; <span class='nototif normal'>&#x2D51;</span> &lt; <span class='nototif normal'>&#x2D67;</span> &lt; <span class='nototif normal'>&#x2D54;</span> &lt; <span class='nototif normal'>&#x2D55;</span> &lt; <span class='nototif normal'>&#x2D57;</span> &lt; <span class='nototif normal'>&#x2D59;</span> &lt; <span class='nototif normal'>&#x2D5A;</span> &lt; <span class='nototif normal'>&#x2D5B;</span> &lt; <span class='nototif normal'>&#x2D5C;</span> &lt;&lt; <span class='nototif normal'>&#x2D5C;&#x2D5B;</span> &lt; <span class='nototif normal'>&#x2D5F;</span> &lt; <span class='nototif normal'>&#x2D53;</span> &lt; <span class='nototif normal'>&#x2D62;</span> &lt; <span class='nototif normal'>&#x2D63;</span> &lt; <span class='nototif normal'>&#x2D64;</span> &lt; <span class='nototif normal'>&#x2D65;</span> 

### <a id="ttq"></a>Tawallammat Tamajaq

_Language Tag_: `ttq-Tfng`, `tmh-Tfng` (macrolanguage)

_Opentype language system tag:_ `TMH ` and `BBR `

_Keyman keyboard:_ [Tawallammat Tifinagh (SIL)](https://keyman.com/keyboards/sil_tawallammat) [ttq, tzm]

_Font:_ [Tagmukay](https://software.sil.org/tagmukay/)

_**Source**_: Personal communication.

Characters | | | | | | | | | &#x0020;
:------- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :--
Tfng | <span class='tagmukay normal'>&#x2D30;</span> | <span class='tagmukay normal'>&#x2D36;</span> | <span class='tagmukay normal'>&#x2D39;</span>| <span class='tagmukay normal'>&#x2D3C;</span> | <span class='tagmukay normal'>&#x2D3E;</span> | <span class='tagmukay normal'>&#x2D40;</span> | <span class='tagmukay normal'>&#x2D42;</span> | <span class='tagmukay normal'>&#x2D46;</span> | <span class='tagmukay normal'>&#x2D48;</span> 
USV  |2D30 | 2D36 | 2D39 | 2D3C | 2D3E | 2D40 | 2D42 | 2D46 | 2D48
Latn | /a/   | /g/    | /d/    | /f/ | /k/    | /b/ | /h/    | /q/    | /x/   
| | | | | | | | |
Tfng | <span class='tagmukay normal'>&#x2D49;</span> | <span class='tagmukay normal'>&#x2D4C;</span> | <span class='tagmukay normal'>&#x2D4d;</span> | <span class='tagmukay normal'>&#x2D4e;</span>| <span class='tagmukay normal'>&#x2D4f;</span> | <span class='tagmukay normal'>&#x2D51;</span> | <span class='tagmukay normal'>&#x2D53;</span> | <span class='tagmukay normal'>&#x2D54;</span> | <span class='tagmukay normal'>&#x2D57;</span>  
USV  | 2D49 | 2D4C | 2D4D | 2D4E | 2D4F | 2D51 | 2D53 | 2D54 | 2D57 
Latn | /i/ /y/ | /j/   | /l/    | /m/    | /n/ | /&#x014b;/  | /w/ | /r/    | /c/      
| | | | | | | | |
Tfng | <span class='tagmukay normal'>&#x2D59;</span> | <span class='tagmukay normal'>&#x2D5B;</span> | <span class='tagmukay normal'>&#x2D5C;</span> | <span class='tagmukay normal'>&#x2D62;</span> | <span class='tagmukay normal'>&#x2D63;</span> | <span class='tagmukay normal'>&#x2D64;</span>| <span class='tagmukay normal'>&#x2D67;</span> |  |  |  |  
USV  | 2D59 | 2D5B | 2D5C | 2D62 | 2D63 | 2D64 | 2D67 | |
Latn | /s/  | /s&#x030c;/ | /t/   | /y/    | /z/ | /z/    | /o/    | | 

#### Vowels

SIL and APT have differing orthographies for the same language

##### _SIL_

Vowels |     |     |     |     |     |  |
:-------   | :-- | :-- | :-- | :-- | :-- | :--
Tfng | <span class='akatab normal'>&#x2D30;&#x0302;</span> | <span class='akatab normal'>&#x2D30;&#x0306;</span> | <span class='akatab normal'>&#x2D62;&#x0323;</span> | <span class='akatab normal'>&#x2D62;&#x0302;</span> | <span class='akatab normal'>&#x2D53;&#x0302;</span> | <span class='akatab normal'>&#x2D67;&#x0302;</span>
USV  | 2D30 + 0302 | 2D30 + 0306 | 2D62 + 0323 | 2D62 + 0302 | 2D53 + 0302 | 2D67 + 0302
Latn | /ɑ/ | /ǝ/ | /i/ | /e/ | /u/ | /o/


##### _APT_

Vowels |     |     |     |     |     |  |
:-------   | :-- | :-- | :-- | :-- | :-- | :--
Tfng | <span class='akatab normal'>&#x2D30;</span>    | <span class='akatab normal'>&#x2D66;</span>    | <span class='akatab normal'>&#x2D62;</span>    | <span class='akatab normal'>&#x2D67;</span> |  | 
USV  | 2D30 | 2D66 | 2D62 | 2D67 | | 
Latn | /ɑ/ | /ǝ/ | /i/ | /e/ | /u/ | /o/

#### Punctuation

All punctuation required for Neo-Tifinagh is also required for `ttq`. In addition, the separator mark is used: U+2D70 <span class='tagmukay normal'>&#x2D70;</span>.

#### Glyph variants

USV |&#x0020; | &#x0020; | &#x0020;
:--  | :--  | :--  | :--
2D30 | <span class='nototif normal'>&#x2D30;</span>|&#x003E;|<span class='tagmukay normal'>&#x2D30;</span>
2D3C | <span class='nototif normal'>&#x2D3C;</span>|&#x003E;|<span class='tagmukay normal'>&#x2D3C;</span>
2D4D | <span class='nototif normal'>&#x2D4D;</span>|&#x003E;|<span class='tagmukay normal'>&#x2D4D;</span>
2D53 | <span class='nototif normal'>&#x2D53;</span>|&#x003E;|<span class='tagmukay normal'>&#x2D53;</span>
2D5B | <span class='nototif normal'>&#x2D5B;</span>|&#x003E;|<span class='tagmukay normal'>&#x2D5B;</span>
2D63 | <span class='nototif normal'>&#x2D63;</span>|&#x003E;|<span class='tagmukay normal'>&#x2D63;</span>

#### Tri- Bi-Consonants

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
2D4F 2D4C | <span class='tagmukay normal'>&#x2D4F; + &#x2D7F; + &#x2D4C;</span> | → | <span class='tagmukay normal'>&#x2D4F;&#x2D7F;&#x2D4C;</span> (<span class='tagmukay normal' style='font-feature-settings: "ss01" 1'>&#x2D4F;&#x2D7F;&#x2D4C;</span>)
2D4F 2D57 | <span class='tagmukay normal'>&#x2D4F; + &#x2D7F; + &#x2D57;</span> | → | <span class='tagmukay normal'>&#x2D4F;&#x2D7F;&#x2D57;</span>
2D4F 2D59 | <span class='tagmukay normal'>&#x2D4F; + &#x2D7F; + &#x2D59;</span> | → | <span class='tagmukay normal'>&#x2D4F;&#x2D7F;&#x2D59;</span>
2D4F 2D5C | <span class='tagmukay normal'>&#x2D4F; + &#x2D7F; + &#x2D5C;</span> | → | <span class='tagmukay normal'>&#x2D4F;&#x2D7F;&#x2D5C;</span>
2D4F 2D64 | <span class='tagmukay normal'>&#x2D4F; + &#x2D7F; + &#x2D64;</span> | → | <span class='tagmukay normal'>&#x2D4F;&#x2D7F;&#x2D64;</span>
2D54 2D5C | <span class='tagmukay normal'>&#x2D54; + &#x2D7F; + &#x2D5C;</span> | → | <span class='tagmukay normal'>&#x2D54;&#x2D7F;&#x2D5C;</span>
2D59 2D5C | <span class='tagmukay normal'>&#x2D59; + &#x2D7F; + &#x2D5C;</span> | → | <span class='tagmukay normal'>&#x2D59;&#x2D7F;&#x2D5C;</span>
2D5B 2D5C | <span class='tagmukay normal'>&#x2D5B; + &#x2D7F; + &#x2D5C;</span> | → | <span class='tagmukay normal'>&#x2D5B;&#x2D7F;&#x2D5C;</span>

#### Contextual Shaping

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

## <a id="other"></a>Other languages with little or no information

These language are reported to have used or are using Tifinagh script. However, no further information is available.

### <a id="auj"></a>Awjilah

_Language Tag_: `auj-Tfng` 	

### <a id="gha"></a>Ghadamès

_Language Tag_: `gha-Tfng`

### <a id="grr"></a>Taznatit

_Language Tag_: `grr-Tfng`


### <a id="jbn"></a>Nafusi, Zuwara

_Source_: [Omniglot](https://www.omniglot.com/writing/zuwara.htm)

_Language Tag_: `jbn-Tfng`

Omniglot indicates this language can be written with Tifinagh, but no further information is given.

### <a id="mzb"></a>Tumzabt

_Language Tags_: `mzb-Tfng`

_**Source**_: Savage, 2003. p. 2.

This source lists a set of characters that are used in a Algerian school text book entitled “Adlis” printed in 1988 (pp 12,13). It is unknown how widely used this book (or the characters) are actually used.


### <a id="nxm"></a>Numidian

_Language Tag_: `nxm-Tfng`

### <a id="shy"></a>Tachawit, Tacawit

_Language Tags_: `shy-Tfng`

_**Source**_: Savage, 2003. p. 2.

This source lists a set of characters that are used in a Algerian school text book entitled “Adlis” printed in 1988 (pp 12,13). It is unknown how widely used this book (or the characters) are actually used.

### <a id="tez"></a>Tetserret

_Language Tag_: `tez-Tfng`

### <a id="zen"></a>Zenaga

_Language Tag_: `zen-Tfng`

## Other Berber languages

These are Berber languages which do not appear to have ever used the Tifinagh script:

- Chenoua `[cnu]`
- Judeo-Berber `[jbe]`
- Tagargrent, Ouargli `[oua]`
- Sened `[sds]`
- Senhaja Berber `[sjs]`
- Sawknah `[swn]`
- Tidikelt Tamazight `[tia]`
- Temacine Tamazight `[tjo]`

## <a id="ack"></a>Acknowledgements

The following people have generously offered feedback for this document: Jon Coblentz.

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

<a id="ishida_zgh"></a>Ishida, Richard. [Tamazight: Neo-Tifinagh orthography notes](https://r12a.github.io/scripts/tfng/zgh.html)

<a id="tarifit2004"></a>McClelland III, Clive W. 2004. A Dictionary of Tarifit Berber. The Edwin Mellen Press. Lewiston, New York.

Morocco-Canada-France (prepared by P. Andries). 2004. Proposal to add the Tifinagh Script. [L2/04-142](https://www.unicode.org/L2/L2004/04142r-n2739r-tifinagh.pdf)

<a id="savage2000"></a>Savage, Andrew. 2000. Writing Tuareg Vowels. Advantages and Disadvantages of the Three Script Options: Arabic, Tifinagh and Roman. Submitted in partial fulfillment of the requirements for the degree of Master of Letters in Linguistics from the Univerisity of New England, New South Wales, Australia.

[2009 New Testament](https://archive.org/details/newtestament-tarifit)

2004. [Projet de norme marocaine: Alphabet tifinaghe](https://www.unicode.org/L2/L2004/04195-pnm-17.1.100.pdf)

