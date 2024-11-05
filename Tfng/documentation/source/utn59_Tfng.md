---
title: Unicode Technical Note 59 - Representing Tifinagh in Unicode
---

_Lorna Evans and Jon Coblentz, SIL Global (05-Nov-2024)_

_Further information, corrections, and additions on script use, as well as information on language usage is most welcome._

- <a href="#intro">Introduction</a>
- <a href="#uni">The Unicode Model</a>
   - <a href="#cons">Basic Consonants</a>
   - <a href="#vowel">Vowels</a>
   - <a href="#punct">Punctuation</a>
   - <a href="digits">Digits</a>
   - <a href="#variant">Variant Glyphs</a>
   - <a href="#bicons">Bi- Tri-Consonants</a>
  - <a href="#contextual">Contextual Shaping</a>
  - <a href="#dir">Writing Direction</a>
  - <a href="#dir_var">Directional Glyphs</a>
- <a href="#resource">Resources</a>
  - <a href="#key">Keyboarding</a>
  - <a href="#font">Fonts</a>
- <a href="#neo">Languages Using Neo-Tifinagh script</a>
  - <a href="#tzm_zgh">Central Atlas Tamazight, Standard Moroccan Tamazight &#x005B;tzm&#x005D; &#x005B;zgh&#x005D;</a>
  - <a href="#kab">Kabyle, Amazigh, Taqbaylit &#x005B;kab&#x005D;</a>
  - <a href="#rif">Tarifit, Riffian &#x005B;rif&#x005D;</a>
  - <a href="#shi">Tachelhit &#x005B;shi&#x005D;</a>
- <a href="#trad">Languages Using Traditional Tifinagh script</a>
  - <a href="#cnu">Chenoua, Tacenwit &#x005B;cnu&#x005D;</a>
  - <a href="#gho">Ghomara, Shilha &#x005B;gho&#x005D;</a>
  - <a href="#mzb">Tumzabt &#x005B;mzb&#x005D;</a>
  - <a href="#shy">Tachawit, Tacawit &#x005B;shy&#x005D;</a>
  - <a href="#siz">Siwi &#x005B;siz&#x005D;</a>
  - <a href="#taq">Tamasheq &#x005B;taq&#x005D;</a>
  - <a href="#taq-ML">Tamasheq (Mali) &#x005B;taq&#x005D;</a>
  - <a href="#tda">Tagdal, Tuareg (Azawagh dialect of Niger-Mali) &#x005B;tda&#x005D;</a>
  - <a href="#thv">Tahaggart Tamahaq, Tamahaq (Tuareg) &#x005B;thv&#x005D;</a>
  - <a href="#thz">Tayart Tamajeq,  &#x005B;thz&#x005D;</a>
  - <a href="#ttq">Tawallammat Tamajaq &#x005B;ttq&#x005D;</a>
- <a href="#other">Other languages with little or no information</a>
  - <a href="#auj">Awjilah &#x005B;auj&#x005D;</a>
  - <a href="#gha">Ghadamès &#x005B;gha&#x005D;</a>
  - <a href="#grr">Taznatit &#x005B;grr&#x005D;</a>
  - <a href="#jbn">Nafusi (Zuwara dialect) &#x005B;jbn&#x005D;</a>
  - <a href="#nxm">Numidian &#x005B;nxm&#x005D;</a>
  - <a href="#tez">Tetserret &#x005B;tez&#x005D;</a>
  - <a href="#zen">Zenaga &#x005B;zen&#x005D;</a>
- <a href="#ack">Acknowledgements</a>
- <a href="#ref">References</a>

## <a id="intro"></a>Introduction

Tifinagh is encoded in the U+2D30..U+2D7F block of Unicode. The encoding in the Tifinagh block is based on the modern alphabet called Neo-Tifinagh. It also includes characters for modern attested Tuareg.

This document gives some guidance on the encoding of _modern orthographies_ using the Tifinagh script (no attempt is made to document all the variants used in ancient Tifinagh orthographies). Since the script is used for a number of orthographies covering different languages, the development of this document is ongoing. In terms of the Unicode standard, this document is purely informative since it is concerned with issues not covered by that standard. 

This document also gives guidance on font development for the different _modern_ orthographies and languages.

## <a id="uni"></a>The Unicode Model

### <a id="cons"></a>Basic Consonants

The basic consonants are relatively obvious and can be discovered by viewing the Unicode charts.

**Design**: There can be some design issues related to "dotted" characters especially when the design is similar. When these characters appear together, they can be difficult to read unless care is taken by the type designer to change the size or spacing of the dots: <span class='akatab normal'>&#x2D30;&#x2D53;&#x2D3E;&#x2D46;&#x2D58;&#x2D30;</span>. The design of the Neo-Tifinagh dotted characters reduces the level of confusion when adjacent to each other: <span class='nototif normal'>&#x2D30;&#x2D53;&#x2D3E;&#x2D46;&#x2D58;&#x2D30;</span>. Sidebearings on characters are still important.

In some fonts the characters do not rest on a baseline. They could be described as centered. For example, the design of these characters <span class='akatab normal'>&#x2D31;&#x2D30;&#x2D53;&#x2D3E;&#x2D42;&#x2D65;</span> is more consistent with the traditional handwritten Tifinagh styles.

Neo-Tifinagh fonts generally have a distinct baseline: <span class='nototif normal'>&#x2D31;&#x2D30;&#x2D53;&#x2D3E;&#x2D42;&#x2D65;</span>

### <a id="vowel"></a>Vowels

Vowels are not as clearly defined. Four vowels have been encoded for Neo-Tifinagh. However, different traditional Tifinagh orthographies may demonstrate vowels using combining marks in different ways. These vowels are primarily used as an aid in learning to read. Several competing systems (<a href="#Andries2004">L2/04-142</a> (pages 6, 7, & 30)) have been advocated:

#### _SIL-Niger_

Vowels |     |     |     |     |     |
:--    | :-- | :-- | :-- | :-- | :-- | :--
Tfng   | <span class='akatab normal'>&#x2D30;&#x0302;</span> | <span class='akatab normal'>&#x2D30;&#x0306;</span> | <span class='akatab normal'>&#x2D62;&#x0323;</span> | <span class='akatab normal'>&#x2D62;&#x0302;</span> | <span class='akatab normal'>&#x2D53;&#x0302;</span> | <span class='akatab normal'>&#x2D67;&#x0302;</span>
USV    | 2D30 + 0302 | 2D30 + 0306 | 2D62 + 0323 | 2D62 + 0302 | 2D53 + 0302 | 2D67 + 0302

#### _APT_

Vowels |     |     |     |     |     |
:--    | :-- | :-- | :-- | :-- | :-- | :--
Tfng   | <span class='utn normal'>&#xED30;</span>    | <span class='utn normal'>&#x2D66;</span>    | <span class='utn normal'>&#xED62;</span>    | <span class='utn normal'>&#x2D67;</span> | <span class='utn normal'>&#xE014;</span> | <span class='utn normal'>&#xED67;</span>
USV  | 2D30 | 2D66 | 2D62 | 2D67 | 2D53 | 2D67 

#### _Hawad_

Vowels |     |     |     |     |     |
:-------   | :-- | :-- | :-- | :-- | :-- | :--
Tfng | <span class='utn normal'>&#xE030;</span>    | <span class='utn normal'>&#xE031;</span>  | <span class='utn normal'>&#x2D5D;</span>  | <span class='utn normal'>&#xE032;</span>    | <span class='utn normal'>&#xE033;</span> |  
USV  | 2D5D 0307 | 2D5D 0308 | 2D5D | 2D49 0307 | 2D49 0308 | 

The combining marks required for these three systems would be:

- 0302 COMBINING CIRCUMFLEX ACCENT
- 0306 COMBINING BREVE
- 0307 COMBINING DOT ABOVE
- 0308 COMBINING DIAERESIS
- 0323 COMBINING DOT BELOW

There is some indication in the <a href="#unicode">Unicode Standard (chapter 19)</a> that the following two combining marks may also be used:

- 0304 COMBINING MACRON
- 0309 COMBINING HOOK ABOVE

### <a id="punct"></a>Punctuation

Western-style punctuation signs are used in Tifinagh. These include: <span class='nototif normal'>. , : ; ? ! ( ) &#x00AB; &#x00BB; &#x201E; &#x201D; &#x2026;</span> 

Modern usage separates words by a space. 

_A few languages use a special separator mark which has been encoded in the Tifinagh block._ That character is U+2D70 (<span class='nototif normal'>&#x2D70;</span>) The languages using the separator mark will be indicated in the section on that language. Otherwise, punctuation is not listed in each section.

#### Digits

There is no common way to write numbers using Tifinagh script. The IRCAM Tifinagh uses the usual Western-style digits.

### <a id="variant"></a>Variant Glyphs

This chart includes a sampling of some of the possible glyph variants in current use. It does not demonstrate all of the possible historical glyph variants. In addition, because of the issues relating to <a href="#dir">Writing Direction</a>, there are variants which are mirrored or turned for right to left text or even for vertical text. The default directional variants are included below under <a href="#dir_var">Directional Glyphs</a>. In general, when a variant is used for a glyph, the same principle would apply for similar glyphs. For example, if a round glyph with a horizontal bar has a square variant, then another round glyph with a vertical bar would likely be square.

Because these glyphs are taken from various fonts, the height of a particular glyph should not be considered significant.

|  | 2D3     | 2D4      | 2D5      | 2D6      | 2D7    
:- | :---     | :---      | :---      | :---      | :--
0  |<span class='utn normal'>&#x2D30;</span> <span class='utn normal'>&#xED30;</span> <span class='utn normal'>&#xE000;</span></br>_ya_| <span class='utn normal'>&#x2D40;</span> <span class='utn normal'>&#xED40;</span> <span class='utn normal'>&#xE00A;</span></br>_yah or Tuareg yab_| <span class='utn normal'>&#x2D50;</span> <span class='utn normal'>&#xED50;</span> <span class='utn normal'>&#xE010;</span> <span class='utn normal'>&#xE011;</span> <span class='utn normal'>&#xE012;</span></br>_Tuareg yagn_| <span class='utn normal'>&#x2D60;</span> <span class='utn normal'>&#xE026;</span></br>_yav_ | <span class='utn normal'>&#x2D70;</span></br>_tazarast_
1  |<span class='utn normal'>&#x2D31;</span> <span class='utn normal'>&#xED31;</span> <span class='utn normal' >&#xE001;</span></br>_yab_| <span class='utn normal'>&#x2D41;</span></br>_Berber yah_ | <span class='utn normal'>&#x2D51;</span></br>_Tuareg yang_ | <span class='utn normal'>&#x2D61;</span></br>_yaw_ | 
2  |<span class='utn normal'>&#x2D32;</span> <span class='utn normal'>&#xED32;</span></br>_yabh_ | <span class='utn normal'>&#x2D42;</span> <span class='utn normal'>&#xED42;</span></br>_Tuareg yah_ | <span class='utn normal'>&#x2D52;</span></br>_yap_ | <span class='utn normal'>&#x2D62;</span> <span class='utn normal'>&#xED62;</span> <span class='utn normal'>&#xE01A;</span> <span class='utn normal'>&#xE01B;</span> <span class='utn normal'>&#xE020;</span> <span class='utn normal'>&#xE01C;</span> <span class='utn normal'>&#xE03B;</span></br>_yay_| 
3  |<span class='utn normal'>&#x2D33;</span> <span class='utn normal'>&#xED33;</span></br>_yag_| <span class='utn normal'>&#x2D43;</span></br>_yahh_ | <span class='utn normal'>&#x2D53;</span> <span class='utn normal'>&#xED53;</span> <span class='utn normal'>&#xE013;</span> <span class='utn normal'>&#xE014;</span></br>_yu or Tuareg yaw_| <span class='utn normal'>&#x2D63;</span> <span class='utn normal'>&#xED63;</span> <span class='utn normal'>&#xE01D;</span> <span class='utn normal'>&#xE01E;</span></br>_yaz_| 
4  |<span class='utn normal'>&#x2D34;</span> <span class='utn normal'>&#xED34;</span> <span class='utn normal'>&#xE002;</span> <span class='utn normal'>&#xE003;</span> <span class='utn normal'>&#xE004;</span> <span class='utn normal'>&#xE024;</span></br>_yaghh_| <span class='utn normal'>&#x2D44;</span> <span class='utn normal'>&#xED44;</span></br>_yaa_| <span class='utn normal'>&#x2D54;</span> <span class='utn normal'>&#xED54;</span></br>_yar_ | <span class='utn normal'>&#x2D64;</span> <span class='utn normal'>&#xE01F;</span></br>_Tawellemet yaz_| 
5  |<span class='utn normal'>&#x2D35;</span></br>_Berber yaj_ | <span class='utn normal'>&#x2D45;</span></br>_yakh_ | <span class='utn normal'>&#x2D55;</span> <span class='utn normal'>&#xED55;</span></br>_yarr_| <span class='utn normal'>&#x2D65;</span> <span class='utn normal'>&#xED65;</span></br>_yazz_| 
6  |<span class='utn normal'>&#x2D36;</span> <span class='utn normal'>&#xED36;</span></br>_yaj_| <span class='utn normal'>&#x2D46;</span></br>_Tuareg yakh_ | <span class='utn normal'>&#x2D56;</span></br>_yagh_ | <span class='utn normal'>&#x2D66;</span></br>_ye_ | 
7  |<span class='utn normal'>&#x2D37;</span> <span class='utn normal'>&#xED37;</span></br>_yad_ | <span class='utn normal'>&#x2D47;</span></br>_yaq_ | <span class='utn normal'>&#x2D57;</span> <span class='utn normal'>&#xED57;</span></br>_Tuareg yagh_| <span class='utn normal'>&#x2D67;</span> <span class='utn normal'>&#xED67;</span></br>_yo_| 
8  |<span class='utn normal'>&#x2D38;</span> <span class='utn normal'>&#xED38;</span></br>_yadh_| <span class='utn normal'>&#x2D48;</span> <span class='utn normal'>&#xED48;</span></br>_Tuareg yaq_| <span class='utn normal'>&#x2D58;</span></br>_Ayer yagh or Adrar yaj_ |  | 
9  |<span class='utn normal'>&#x2D39;</span> <span class='utn normal'>&#xED39;</span> <span class='utn normal'>&#xE005;</span></br>_yadd_| <span class='utn normal'>&#x2D49;</span> <span class='utn normal'>&#xED49;</span> <span class='utn normal'>&#xE00B;</span></br>_yi_ | <span class='utn normal'>&#x2D59;</span> <span class='utn normal'>&#xED59;</span></br>_yas_ |  | 
A  |<span class='utn normal'>&#x2D3A;</span> <span class='utn normal'>&#xED3A;</span> <span class='utn normal'>&#xE006;</span></br>_yaddh_ | <span class='utn normal'>&#x2D4A;</span></br>_yazh_ | <span class='utn normal'>&#x2D5A;</span> <span class='utn normal'>&#xED5A;</span> <span class='utn normal'>&#xE015;</span></br>_yass_|  | 
B  |<span class='utn normal'>&#x2D3B;</span> <span class='utn normal'>&#xED3B;</span></br>_yey_| <span class='utn normal'>&#x2D4B;</span> <span class='utn normal'>&#xED4B;</span> <span class='utn normal'>&#xE00C;</span></br>_Ahaggar yazh_| <span class='utn normal'>&#x2D5B;</span> <span class='utn normal'>&#xED5B;</span> <span class='utn normal'>&#xE017;</span> <span class='utn normal'>&#xE023;</span> <span class='utn normal'>&#xE016;</span></br>_yash_|  | 
C  |<span class='utn normal'>&#x2D3C;</span> <span class='utn normal'>&#xED3C;</span> <span class='utn normal'>&#xE007;</span> <span class='utn normal'>&#xE008;</span></br>_yaf_| <span class='utn normal'>&#x2D4C;</span></br>_Tuareg yazh_ | <span class='utn normal'>&#x2D5C;</span> <span class='utn normal'>&#xED5C;</span></br>_yat_|  | 
D  |<span class='utn normal'>&#x2D3D;</span></br>_yak_ | <span class='utn normal'>&#x2D4D;</span> <span class='utn normal'>&#xED4D;</span> <span class='utn normal'>&#xE00E;</span></br>_yal_| <span class='utn normal'>&#x2D5D;</span></br>_yath_ |  | 
E  |<span class='utn normal'>&#x2D3E;</span> <span class='utn normal'>&#xED3E;</span> <span class='utn normal'>&#xE009;</span> <span class='utn normal'>&#xE021;</span> <span class='utn normal'>&#xE022;</span></br>_Tuareg yak_ | <span class='utn normal'>&#x2D4E;</span> <span class='utn normal'>&#xED4E;</span> <span class='utn normal'>&#xE00F;</span></br>_yam_ | <span class='utn normal'>&#x2D5E;</span> <span class='utn normal'>&#xED5E;</span> <span class='utn normal'>&#xE025;</span></br>_yach_|  | 
F  |<span class='utn normal'>&#x2D3F;</span></br>_yakhh_ | <span class='utn normal'>&#x2D4F;</span></br>_yan_ | <span class='utn normal'>&#x2D5F;</span> <span class='utn normal'>&#xED5F;</span> <span class='utn normal'>&#xE018;</span> <span class='utn normal'>&#xE019;</span></br>_yatt_| <span class='utn normal'>&#x2D6F;</span> <span class='utn normal'>&#xED6F;</span></br>_tamatart_| <span class='utn normal'>&#x2D7F;</span></br>_joiner_

### <a id="bicons"></a>Bi- Tri-consonants

Bi-consonants are additional letterforms used in the Tifinagh script, particularly for Tuareg, to represent a consonant cluster—a sequence of two consonants without an intervening vowel. These bi-consonants, sometimes also referred to as bigraphs, are not directly encoded as single characters in the Unicode Standard. Instead, they are represented as a sequence of the two consonant letters, separated either by U+200D ZERO WIDTH JOINER or by U+2D7F TIFINAGH CONSONANT JOINER.
 
When a bi-consonant is considered obligatory in text, it is represented by the two consonant letters, with U+2D7F TIFINAGH CONSONANT JOINER inserted between them. This use of U+2D7F is comparable in function to the use of U+0652 ARABIC SUKUN to indicate the absence of a vowel after a consonant in the Arabic script. However, instead of appearing as a visible mark in the text, U+2D7F TIFINAGH CONSONANT JOINER indicates the presence of a bi-consonant, which should then be rendered with a preformed glyph for the sequence. U+200D ZERO WIDTH JOINER should be used when the bi-consonant is not considered obligatory.

Some of the bi-consonants have ascenders. These should ascend above the normal height of the Tifinagh consonants.

Although rare, tri-consonants do exist. This document will use the term bi-consonant even when it may be a tri-consonant.

This chart does not demonstrate all of the possible historical glyph variants. It should be noted that if the base glyph is a variant, that will affect the variant for the bi-consonant. For example, if a language uses a square variant of <span class='nototif normal'>&#x2D59;</span> (<span class='utn normal'>&#xED59;</span>), then the bi-consonant should also be square (<span class='utn normal'>&#xE036;</span> instead of <span class='nototif normal'>&#x2D59;&#x2D7F;&#x2D5C;</span>). This document does not include an exhaustive list of the glyph variants for the base characters used in the bi-consonants below.

Although this chart demonstrates the use of U+2D7F TIFINAGH CONSONANT JOINER, fonts could support both U+2D7F (obligatory bi-consonants) and U+200D (optional bi-consonants).

USV | 2D7F between characters | → | Glyph</br>(2D7F)
:--- | :----  | :-- | :--
1 /bt/ 2D31 2D5C | <span class='nototif normal'>&#x2D31; + &#x2D7F; + &#x2D5C;</span> | → | <span class='nototif normal'>&#x2D31;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv31" 1'>&#x2D31;&#x2D7F;&#x2D5C;</span>
2 /gʼt/ 2D33 2D5C | <span class='nototif normal'>&#x2D33; + &#x2D7F; + &#x2D5C;</span> | → | <span class='nototif normal'>&#x2D33;&#x2D7F;&#x2D5C;</span>
3 /gʼt/ 2D34 2D5C | <span class='nototif normal'>&#x2D34; + &#x2D7F; + &#x2D5C;</span> | → | <span class='akatab normal'>&#x2D34;&#x2D7F;&#x2D5C;</span>
4 /gt/ 2D36 2D5C | <span class='nototif normal'>&#x2D36; + &#x2D7F; + &#x2D5C;</span> | → | <span class='akatab normal'>&#x2D36;&#x2D7F;&#x2D5C;</span> <span class='utn normal'>&#xE034;</span>
5a /ft/ 2D3C 2D5C | <span class='nototif normal'>&#x2D3C; + &#x2D7F; + &#x2D5C;</span> | → | <span class='nototif normal'>&#x2D3C;&#x2D7F;&#x2D5C;</span>
5b |<span class='utn normal'>&#xED3C; + &#x2D7F; + &#x2D5C;</span> | → | <span class='akatab normal'>&#x2D3C;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv35" 1'>&#x2D3C;&#x2D7F;&#x2D5C;</span>
5c |<span class='utn normal'>&#xE007; + &#x2D7F; + &#x2D5C;</span> | → | <span class='akatab normal' style='font-feature-settings: "cv02" 1'>&#x2D3C;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv35" 2'>&#x2D3C;&#x2D7F;&#x2D5C;</span>
5d |<span class='utn normal'>&#xE008; + &#x2D7F; + &#x2D5C;</span> | → | <span class='akatab normal' style='font-feature-settings: "cv14" 1'>&#x2D3C;&#x2D7F;&#x2D5C;</span>
6 /bt/ 2D40 2D5C | <span class='nototif normal'>&#x2D40; + &#x2D7F; + &#x2D5C;</span> | → | <span class='nototif normal'>&#x2D40;&#x2D7F;&#x2D5C;</span>
7 /yt/ 2D49 2D5C | <span class='nototif normal'>&#x2D49; + &#x2D7F; + &#x2D5C;</span> | → | <span class='akatab normal'>&#x2D49;&#x2D7F;&#x2D5C;</span>
8 /ẓt/ 2D4B 2D5C | <span class='nototif normal'>&#x2D4B; + &#x2D7F; + &#x2D5C;</span> | → | <span class='akatab normal'>&#x2D4B;&#x2D7F;&#x2D5C;</span>
9 /ẓt/ 2D4C 2D5C | <span class='nototif normal'>&#x2D4C; + &#x2D7F; + &#x2D5C;</span> | → | <span class='nototif normal'>&#x2D4C;&#x2D7F;&#x2D5C;</span> <span class='akatab normal'>&#x2D4C;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv40" 1'>&#x2D4C;&#x2D7F;&#x2D5C;</span>
10 /lk/ 2D4D 2D3E | <span class='nototif normal'>&#x2D4D; + &#x2D7F; + &#x2D3E;</span> | → | <span class='akatab normal'>&#x2D4D;&#x2D7F;&#x2D3E;</span>
11 /lt/ 2D4D 2D5C | <span class='nototif normal'>&#x2D4D; + &#x2D7F; + &#x2D5C;</span> | → | <span class='nototif normal'>&#x2D4D;&#x2D7F;&#x2D5C;</span> <span class='akatab normal'>&#x2D4D;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv38" 1'>&#x2D4D;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv38" 2'>&#x2D4D;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv38" 3'>&#x2D4D;&#x2D7F;&#x2D5C;</span>
12 /mb/ 2D4E 2D40 | <span class='nototif normal'>&#x2D4E; + &#x2D7F; + &#x2D40;</span> | → | <span class='nototif normal'>&#x2D4E;&#x2D7F;&#x2D40;</span> <span class='akatab normal'>&#x2D4E;&#x2D7F;&#x2D40;</span>
13 /ms/ 2D4E 2D59 | <span class='nototif normal'>&#x2D4E; + &#x2D7F; + &#x2D59;</span> | → | <span class='akatab normal'>&#x2D4E;&#x2D7F;&#x2D59;</span>
14 /mt/ 2D4E 2D5C | <span class='nototif normal'>&#x2D4E; + &#x2D7F; + &#x2D5C;</span> | → | <span class='utn normal'>&#xE038;</span> <span class='nototif normal'>&#x2D4E;&#x2D7F;&#x2D5C;</span> <span class='akatab normal'>&#x2D4E;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv34" 2'>&#x2D4E;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv34" 1'>&#x2D4E;&#x2D7F;&#x2D5C;</span>  <span class='akatab normal' style='font-feature-settings: "cv34" 3'>&#x2D4E;&#x2D7F;&#x2D5C;</span>
15 /nb/ 2D4F 2D31 | <span class='nototif normal'>&#x2D4F; + &#x2D7F; + &#x2D31;</span> | → | <span class='nototif normal'>&#x2D4F;&#x2D7F;&#x2D31;</span>
16 /ng/ 2D4F 2D34 | <span class='nototif normal'>&#x2D4F; + &#x2D7F; + &#x2D34;</span> | → | <span class='akatab normal'>&#x2D4F;&#x2D7F;&#x2D34;</span> <span class='utn normal'>&#xE039;</span>
17 /nġ/ 2D4F 2D36 | <span class='nototif normal'>&#x2D4F; + &#x2D7F; + &#x2D36;</span> | → | <span class='nototif normal'>&#x2D4F;&#x2D7F;&#x2D36;</span> <span class='akatab normal'>&#x2D4F;&#x2D7F;&#x2D36;</span> <span class='akatab normal' style='font-feature-settings: "cv43" 1'>&#x2D4F;&#x2D7F;&#x2D36;</span>
18 /nd/ 2D4F 2D37 | <span class='nototif normal'>&#x2D4F; + &#x2D7F; + &#x2D37;</span> | → | <span class='akatab normal'>&#x2D4F;&#x2D7F;&#x2D37;</span> <span class='akatab normal' style='font-feature-settings: "cv41" 1'>&#x2D4F;&#x2D7F;&#x2D37;</span>
19 /nd/ 2D4F 2D38 | <span class='nototif normal'>&#x2D4F; + &#x2D7F; + &#x2D38;</span> | → | <span class='akatab normal'>&#x2D4F;&#x2D7F;&#x2D38;</span> <span class='nototif normal'>&#x2D4F;&#x2D7F;&#x2D38;</span>
20 /nd/ 2D4F 2D39 | <span class='nototif normal'>&#x2D4F; + &#x2D7F; + &#x2D39;</span> | → | <span class='nototif normal'>&#x2D4F;&#x2D7F;&#x2D39;</span> <span class='akatab normal'>&#x2D4F;&#x2D7F;&#x2D39;</span>

USV | 2D7F between characters | → | Glyph</br>(2D7F)
:--- | :----  | :-- | :--
21 /nf/ 2D4F 2D3C | <span class='nototif normal'>&#x2D4F; + &#x2D7F; + &#x2D3C;</span> | → | <span class='nototif normal'>&#x2D4F;&#x2D7F;&#x2D3C;</span> <span class='akatab normal'>&#x2D4F;&#x2D7F;&#x2D3C;</span> <span class='akatab normal' style='font-feature-settings: "cv42" 1'>&#x2D4F;&#x2D7F;&#x2D3C;</span> <span class='akatab normal' style='font-feature-settings: "cv14" 1'>&#x2D4F;&#x2D7F;&#x2D3C;</span>
22 /nft/ 2D4F 2D3C 2D5C | <span class='nototif normal'>&#x2D4F; + &#x2D7F; + &#x2D3C; + &#x2D7F; + &#x2D5C;</span> | → | <span class='akatab normal'>&#x2D4F;&#x2D7F;&#x2D3C;&#x2D7F;&#x2D5C;</span>
23 /nk/ 2D4F 2D3E | <span class='nototif normal'>&#x2D4F; + &#x2D7F; + &#x2D3E;</span> | → | <span class='nototif normal'>&#x2D4F;&#x2D7F;&#x2D3E;</span> <span class='akatab normal'>&#x2D4F;&#x2D7F;&#x2D3E;</span>
24 /nb/ 2D4F 2D40 | <span class='nototif normal'>&#x2D4F; + &#x2D7F; + &#x2D40;</span> | → | <span class='nototif normal'>&#x2D4F;&#x2D7F;&#x2D40;</span>
25 /nj/ 2D4F 2D4C | <span class='nototif normal'>&#x2D4F; + &#x2D7F; + &#x2D4C;</span> | → | <span class='nototif normal'>&#x2D4F;&#x2D7F;&#x2D4C;</span> <span class='akatab normal' style='font-feature-settings: "cv45" 1'>&#x2D4F;&#x2D7F;&#x2D4C;</span>
26 /nɣ/ 2D4F 2D57 | <span class='nototif normal'>&#x2D4F; + &#x2D7F; + &#x2D57;</span> | → | <span class='nototif normal'>&#x2D4F;&#x2D7F;&#x2D57;</span>
27 /ns/ 2D4F 2D59 | <span class='nototif normal'>&#x2D4F; + &#x2D7F; + &#x2D59;</span> | → | <span class='nototif normal'>&#x2D4F;&#x2D7F;&#x2D59;</span> <span class='akatab normal'>&#x2D4F;&#x2D7F;&#x2D59;</span>
28 /nš/ 2D4F 2D5B | <span class='nototif normal'>&#x2D4F; + &#x2D7F; + &#x2D5B;</span> | → | <span class='akatab normal'>&#x2D4F;&#x2D7F;&#x2D5B;</span>
29 /nt/ 2D4F 2D5C | <span class='nototif normal'>&#x2D4F; + &#x2D7F; + &#x2D5C;</span> | → | <span class='nototif normal'>&#x2D4F;&#x2D7F;&#x2D5C;</span> <span class='akatab normal'>&#x2D4F;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv37" 1'>&#x2D4F;&#x2D7F;&#x2D5C;</span>
30 /nč/ 2D4F 2D5E | <span class='nototif normal'>&#x2D4F; + &#x2D7F; + &#x2D5E;</span> | → | <span class='nototif normal'>&#x2D4F;&#x2D7F;&#x2D5E;</span>
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
41a /rt/ 2D54 2D5C | <span class='nototif normal'>&#x2D54; + &#x2D7F; + &#x2D5C;</span> | → | <span class='nototif normal'>&#x2D54;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv32" 1'>&#x2D54;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv32" 2'>&#x2D54;&#x2D7F;&#x2D5C;</span>
41b | <span class='utn normal'>&#xED54; + &#x2D7F; + &#x2D5C;</span> | → | <span class='utn normal'>&#xE035;</span>
42 /gt/ 2D56 2D5C | <span class='nototif normal'>&#x2D56; + &#x2D7F; + &#x2D5C;</span> | → | <span class='nototif normal'>&#x2D56;&#x2D7F;&#x2D5C;</span>
43 /sk/ 2D59 2D3E | <span class='nototif normal'>&#x2D59; + &#x2D7F; + &#x2D3E;</span> | → | <span class='akatab normal'>&#x2D59;&#x2D7F;&#x2D3E;</span>
44 /sn/ 2D59 2D4F | <span class='nototif normal'>&#x2D59; + &#x2D7F; + &#x2D4F;</span> | → | <span class='nototif normal'>&#x2D59;&#x2D7F;&#x2D4F;</span>
45a /st/ 2D59 2D5C | <span class='nototif normal'>&#x2D59; + &#x2D7F; + &#x2D5C;</span> | → | <span class='nototif normal'>&#x2D59;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv33" 1'>&#x2D59;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv33" 2'>&#x2D59;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv33" 3'>&#x2D59;&#x2D7F;&#x2D5C;</span> 
45b | <span class='utn normal'>&#xED59; + &#x2D7F; + &#x2D5C;</span> | → | <span class='utn normal'>&#xE036;</span>
46a /šk/ 2D5B 2D3E | <span class='utn normal'>&#xED5B; + &#x2D7F; + &#x2D3E;</span> | → | <span class='akatab normal'>&#x2D5B;&#x2D7F;&#x2D3E;</span> <span class='akatab normal' style='font-feature-settings: "cv47" 1'>&#x2D5B;&#x2D7F;&#x2D3E;</span> 
46b | <span class='utn normal'>&#xE016; + &#x2D7F; + &#x2D3E;</span> | → | <span class='akatab normal' style='font-feature-settings: "cv47" 2'>&#x2D5B;&#x2D7F;&#x2D3E;</span> <span class='akatab normal' style='font-feature-settings: "cv12" 1'>&#x2D5B;&#x2D7F;&#x2D3E;</span>
47 /šn/ 2D5B 2D4F | <span class='nototif normal'>&#x2D5B; + &#x2D7F; + &#x2D4F;</span> | → | <span class='akatab normal'>&#x2D5B;&#x2D7F;&#x2D4F;</span>
48a /št/ 2D5B 2D5C | <span class='nototif normal'>&#x2D5B; + &#x2D7F; + &#x2D5C;</span> | → | <span class='nototif normal'>&#x2D5B;&#x2D7F;&#x2D5C;</span> <span class='akatab normal'>&#x2D5B;&#x2D7F;&#x2D5C;</span> <span class='akatab normal' style='font-feature-settings: "cv48" 1'>&#x2D5B;&#x2D7F;&#x2D5C;</span>
48b | <span class='utn normal'>&#xE017; + &#x2D7F; + &#x2D5C;</span> | → | <span class='utn normal'>&#xE037;</span>
49 /ts/ 2D5C 2D59 | <span class='nototif normal'>&#x2D5C; + &#x2D7F; + &#x2D59;</span> | → | <span class='nototif normal'>&#x2D5C;&#x2D7F;&#x2D59;</span>
50 /wt/ 2D61 2D5C | <span class='nototif normal'>&#x2D61; + &#x2D7F; + &#x2D5C;</span> | → | <span class='nototif normal'>&#x2D61;&#x2D7F;&#x2D5C;</span>
51 /yt/ 2D62 2D5C | <span class='nototif normal'>&#x2D62; + &#x2D7F; + &#x2D5C;</span> | → | <span class='nototif normal'>&#x2D62;&#x2D7F;&#x2D5C;</span>
52 /zt/ 2D63 2D5C | <span class='akatab normal'>&#x2D63; + &#x2D7F; + &#x2D5C;</span> | → | <span class='akatab normal'>&#x2D63;&#x2D7F;&#x2D5C;</span>
53 /zt/ 2D65 2D5C | <span class='nototif normal'>&#x2D65; + &#x2D7F; + &#x2D5C;</span> | → | <span class='nototif normal'>&#x2D65;&#x2D7F;&#x2D5C;</span>

This should not be considered an exhaustive list of all bi-consonants used for Tifinagh, nor are the shapes of the bi-consonants necessarily definitive. There are a wide range of glyph variants. Many of the variants are regional or personal preference.

Bi-consonants are only included in each language section when there are known variants.


### <a id="contextual"></a>Contextual Shaping

Contextual shaping should be implemented when the design of U+2D4D TIFINAGH LETTER YAL and U+2D4F TIFINAGH LETTER YAN are simply vertical strokes. 

Contextual Shaping |     |     |     |     |     |  |
:----   | :-- | :-- | :-- | :-- | :-- | :---
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
<span class='akatab-v2 normal'>&#x2D59;&#x2D4F;&#x2D5C;&#x2D5C; &#x2D5C;&#x2D59;&#x2D3E;&#x2D4D;&#x2D4F; &#x2D53;&#x2D54; &#x2D5C;&#x2D36;&#x2D42;&#x2D4F;&#x2D5C; &#x2D4E;&#x2D49;</span> (Senatet tsokalén wr teǧǧehnet émi.)

**Using the same text, right-to-left behaviour is demonstrated using U+202E RIGHT-TO-LEFT OVERRIDE:**<br>
<span dir="rtl" class='akatab-v2 normal'> &#x202E;&#x2D59;&#x2D4F;&#x2D5C;&#x2D5C; &#x2D5C;&#x2D59;&#x2D3E;&#x2D4D;&#x2D4F; &#x2D53;&#x2D54; &#x2D5C;&#x2D36;&#x2D42;&#x2D4F;&#x2D5C; &#x2D4E;&#x2D49;</span>

**The following text demonstrates both Tifinagh directional behaviours using the U+202E RIGHT-TO-LEFT OVERRIDE and U+202C POP DIRECTIONAL FORMATTING:**<br>
<span dir="rtl" class='akatab-v2 normal'> &#x202E;&#x2D59;&#x2D4F;&#x2D5C;&#x2D5C; &#x2D5C;&#x2D59;&#x2D3E;&#x2D4D;&#x2D4F; &#x2D53;&#x2D54; &#x2D5C;&#x2D36;&#x2D42;&#x2D4F;&#x2D5C; &#x2D4E;&#x2D49;  &#x202C; &#x2D59;&#x2D4F;&#x2D5C;&#x2D5C; &#x2D5C;&#x2D59;&#x2D3E;&#x2D4D;&#x2D4F; &#x2D53;&#x2D54; &#x2D5C;&#x2D36;&#x2D42;&#x2D4F;&#x2D5C; &#x2D4E;&#x2D49; </span>
</p>‮
<!-- 
Using hard-coded directional characters in the HTML code (as illustrated above) can prevent accidental deletion of invisible characters.
-->

Each glyph would be designed for the left to right behavior as well as another glyph for the right to left behavior. These could be called `yadd-tfng` and `yadd-tfng.rtl`.

These would then need to be added to a GSUB lookup for substitution:

```
    sub yadd-tfng            by yadd-tfng.rtl ;            #uni2D39
```

That lookup would then be used in the `rtla` feature in GSUB.

It is beyond the scope of this document to give more detailed information about OpenType support for Tifinagh.


### <a id="dir_var"></a>Directional Glyphs

The script can be written horizontally from left-to-right, from right-to-left, vertically (bottom-to-top, top-to-bottom) or even in boustrophedon, circular, or spiral. Because the script can be written in multiple directions, the glyphs must be mirrored for right-to-left text, turned anti-clockwise 90&#x00B0; for bottom-to-top text, or turned clockwise 90&#x00B0; for top-to-bottom text. Below is a sampling of some of the different shapes required for differing directions. Some glyphs, like a circle, could look the same in any direction. However, unless the glyphs are monoline, there will be slight variations in the glyph design. Where there are glyph variants, the number of glyphs required for different directions will increase exponentially.

For vertical writing, the glyphs should be designed on a center baseline. <a href="#unknown">A Shifinagh Handbook</a> (page 3) indicates that when writing top to bottom &#x201C;You write away from yourself. Do not imagine a base line for the letters, but a centre line.&#x201D; It is difficult to know where punctuation should be positioned in vertical writing, since the majority of vertical writing were ancient rock inscriptions.


|  | <span class='normal'>&#x2192;</span>     | <span class='normal'>&#x2190;</span>      | <span class='normal'>&#x2191;</span>      | <span class='normal'>&#x2193;</span>    
:- | :--     | :--      | :--      | :--
2D30  |<span class='utn normal'>&#x2D30;</span>| <span class='utn normal'>&#x2D30;</span> | <span class='utn normal'>&#x2D30;</span>|<span class='utn normal'>&#x2D30;</span>
2D31  |<span class='utn normal'>&#x2D31;</span>| <span class='utn normal'>&#x2D31;</span> | <span class='utn normal'>&#xF031;</span>|<span class='utn normal'>&#xF031;</span>
2D32  |<span class='utn normal'>&#x2D32;</span>| <span class='utn normal'>&#x2D32;</span> | <span class='utn normal'>&#xF032;</span>|<span class='utn normal'>&#xF032;</span>
2D33  |<span class='utn normal'>&#x2D33;</span>| <span class='utn normal'>&#x2D33;</span> | <span class='utn normal'>&#xF033;</span>|<span class='utn normal'>&#xF034;</span>
2D34  |<span class='utn normal'>&#x2D34;</span>| <span class='utn normal'>&#x2D34;</span> | <span class='utn normal'>&#xF034;</span>|<span class='utn normal'>&#xF033;</span>
2D35  |<span class='utn normal'>&#x2D35;</span>| <span class='utn normal'>&#x2D35;</span> | <span class='utn normal'>&#xF035;</span>|<span class='utn normal'>&#xF035;</span>
2D36  |<span class='utn normal'>&#x2D36;</span>| <span class='utn normal'>&#x2D36;</span> | <span class='utn normal'>&#xF036;</span>|<span class='utn normal'>&#xF136;</span>
2D37  |<span class='utn normal'>&#x2D37;</span>| <span class='utn normal'>&#x2D37;</span> | <span class='utn normal'>&#xF037;</span>|<span class='utn normal'>&#xF038;</span>
2D38  |<span class='utn normal'>&#x2D38;</span>| <span class='utn normal'>&#x2D38;</span> | <span class='utn normal'>&#xF038;</span>|<span class='utn normal'>&#xF037;</span>
2D39  |<span class='utn normal'>&#x2D39;</span>| <span class='utn normal'>&#xED3A;</span> | <span class='utn normal'>&#xF039;</span>|<span class='utn normal'>&#xF139;</span>

&#x00A0;

|  | <span class='normal'>&#x2192;</span>     | <span class='normal'>&#x2190;</span>      | <span class='normal'>&#x2191;</span>      | <span class='normal'>&#x2193;</span>    
:- | :--     | :--      | :--      | :--
2D3A  |<span class='utn normal'>&#x2D3A;</span>| <span class='utn normal'>&#xED39;</span> | <span class='utn normal'>&#xF03A;</span>|<span class='utn normal'>&#xF13A;</span>
2D3B  |<span class='utn normal'>&#x2D3B;</span>| <span class='utn normal'>&#x2D3B;</span> | <span class='utn normal'>&#xF03B;</span>|<span class='utn normal'>&#xF03B;</span>
2D3C  |<span class='utn normal'>&#x2D3C;</span>| <span class='utn normal'>&#x2D3C;</span> | <span class='utn normal'>&#xF03C;</span>|<span class='utn normal'>&#xF03C;</span>
2D3D  |<span class='utn normal'>&#x2D3D;</span>| <span class='utn normal'>&#xFD3D;</span> | <span class='utn normal'>&#xF03D;</span>|<span class='utn normal'>&#xF13D;</span>
2D3E  |<span class='utn normal'>&#x2D3E;</span>| <span class='utn normal'>&#xFD3E;</span> | <span class='utn normal'>&#xF03E;</span>|<span class='utn normal'>&#xF13E;</span>
2D3F  |<span class='utn normal'>&#x2D3F;</span>| <span class='utn normal'>&#xFD3F;</span> | <span class='utn normal'>&#xF03F;</span>|<span class='utn normal'>&#xF13F;</span>
2D40  |<span class='utn normal'>&#x2D40;</span>| <span class='utn normal'>&#x2D40;</span> | <span class='utn normal'>&#xF040;</span>|<span class='utn normal'>&#xF040;</span>
2D41  |<span class='utn normal'>&#x2D41;</span>| <span class='utn normal'>&#xFD41;</span> | <span class='utn normal'>&#xF041;</span>|<span class='utn normal'>&#xF041;</span>
2D42  |<span class='utn normal'>&#x2D42;</span>| <span class='utn normal'>&#x2D42;</span> | <span class='utn normal'>&#xF042;</span>|<span class='utn normal'>&#xF042;</span>
2D43  |<span class='utn normal'>&#x2D43;</span>| <span class='utn normal'>&#xFD43;</span> | <span class='utn normal'>&#xF043;</span>|<span class='utn normal'>&#xF143;</span>
2D44  |<span class='utn normal'>&#x2D44;</span>| <span class='utn normal'>&#x2D44;</span> | <span class='utn normal'>&#xF044;</span>|<span class='utn normal'>&#xF056;</span>
2D45  |<span class='utn normal'>&#x2D45;</span>| <span class='utn normal'>&#x2D45;</span> | <span class='utn normal'>&#xF045;</span>|<span class='utn normal'>&#xF145;</span>
2D46  |<span class='utn normal'>&#x2D46;</span>| <span class='utn normal'>&#x2D46;</span> | <span class='utn normal'>&#xF046;</span>|<span class='utn normal'>&#xF046;</span>
2D47  |<span class='utn normal'>&#x2D47;</span>| <span class='utn normal'>&#xFD47;</span> | <span class='utn normal'>&#xF047;</span>|<span class='utn normal'>&#xF147;</span>
2D48  |<span class='utn normal'>&#x2D48;</span>| <span class='utn normal'>&#x2D48;</span> | <span class='utn normal'>&#xF048;</span>|<span class='utn normal'>&#xF048;</span>
2D49  |<span class='utn normal'>&#x2D49;</span>| <span class='utn normal'>&#xFD49;</span> | <span class='utn normal'>&#xF049;</span>|<span class='utn normal'>&#xF149;</span>
2D4A  |<span class='utn normal'>&#x2D4A;</span>| <span class='utn normal'>&#x2D4A;</span> | <span class='utn normal'>&#xF04A;</span>|<span class='utn normal'>&#xF04A;</span>
2D4B  |<span class='utn normal'>&#x2D4B;</span>| <span class='utn normal'>&#x2D4B;</span> | <span class='utn normal'>&#xF04B;</span>|<span class='utn normal'>&#xF04B;</span>
2D4C  |<span class='utn normal'>&#x2D4C;</span>| <span class='utn normal'>&#x2D4C;</span> | <span class='utn normal'>&#xF04C;</span>|<span class='utn normal'>&#xF04C;</span>
2D4D  |<span class='utn normal'>&#x2D4D;</span>| <span class='utn normal'>&#xFD4D;</span> | <span class='utn normal'>&#xF04D;</span>|<span class='utn normal'>&#xF04D;</span>
2D4E  |<span class='utn normal'>&#x2D4E;</span>| <span class='utn normal'>&#xFD4E;</span> | <span class='utn normal'>&#xF04E;</span>|<span class='utn normal'>&#xF14E;</span>
2D4F  |<span class='utn normal'>&#x2D4F;</span>| <span class='utn normal'>&#x2D4F;</span> | <span class='utn normal'>&#xF04F;</span>|<span class='utn normal'>&#xF04F;</span>

|  | <span class='normal'>&#x2192;</span>     | <span class='normal'>&#x2190;</span>      | <span class='normal'>&#x2191;</span>      | <span class='normal'>&#x2193;</span>    
:- | :--     | :--      | :--      | :--
2D50  |<span class='utn normal'>&#x2D50;</span>| <span class='utn normal'>&#x2D50;</span> | <span class='utn normal'>&#xF050;</span>|<span class='utn normal'>&#xF050;</span>
2D51  |<span class='utn normal'>&#x2D51;</span>| <span class='utn normal'>&#x2D51;</span> | <span class='utn normal'>&#xF051;</span>|<span class='utn normal'>&#xF151;</span>
2D52  |<span class='utn normal'>&#x2D52;</span>| <span class='utn normal'>&#xFD52;</span> | <span class='utn normal'>&#xF052;</span>|<span class='utn normal'>&#xF152;</span>
2D53  |<span class='utn normal'>&#x2D53;</span>| <span class='utn normal'>&#x2D53;</span> | <span class='utn normal'>&#xF053;</span>|<span class='utn normal'>&#xF053;</span>
2D54  |<span class='utn normal'>&#x2D54;</span>| <span class='utn normal'>&#x2D54;</span> | <span class='utn normal'>&#xF054;</span>|<span class='utn normal'>&#xF054;</span>
2D55  |<span class='utn normal'>&#x2D55;</span>| <span class='utn normal'>&#xFD55;</span> | <span class='utn normal'>&#xF055;</span>|<span class='utn normal'>&#xF155;</span>
2D56  |<span class='utn normal'>&#x2D56;</span>| <span class='utn normal'>&#x2D56;</span> | <span class='utn normal'>&#xF056;</span>|<span class='utn normal'>&#xF044;</span>
2D57  |<span class='utn normal'>&#x2D57;</span>| <span class='utn normal'>&#x2D57;</span> | <span class='utn normal'>&#xF057;</span>|<span class='utn normal'>&#xF057;</span>
2D58  |<span class='utn normal'>&#x2D58;</span>| <span class='utn normal'>&#x2D58;</span> | <span class='utn normal'>&#xF058;</span>|<span class='utn normal'>&#xF058;</span>
2D59  |<span class='utn normal'>&#x2D59;</span>| <span class='utn normal'>&#x2D59;</span> | <span class='utn normal'>&#xF059;</span>|<span class='utn normal'>&#xF059;</span>
2D5A  |<span class='utn normal'>&#x2D5A;</span>| <span class='utn normal'>&#xFD5A;</span> | <span class='utn normal'>&#xF05A;</span>|<span class='utn normal'>&#xF15A;</span>
2D5B  |<span class='utn normal'>&#x2D5B;</span>| <span class='utn normal'>&#xFD5B;</span> | <span class='utn normal'>&#xF05B;</span>|<span class='utn normal'>&#xF15B;</span>
2D5C  |<span class='utn normal'>&#x2D5C;</span>| <span class='utn normal'>&#x2D5C;</span> | <span class='utn normal'>&#xF05C;</span>|<span class='utn normal'>&#xF05C;</span>
2D5D  |<span class='utn normal'>&#x2D5D;</span>| <span class='utn normal'>&#x2D5D;</span> | <span class='utn normal'>&#xF05D;</span>|<span class='utn normal'>&#xF05D;</span>
2D5E  |<span class='utn normal'>&#x2D5E;</span>| <span class='utn normal'>&#xFD5E;</span> | <span class='utn normal'>&#xF05E;</span>|<span class='utn normal'>&#xF15E;</span>
2D5F  |<span class='utn normal'>&#x2D5F;</span>| <span class='utn normal'>&#xFD5F;</span> | <span class='utn normal'>&#xF05F;</span>|<span class='utn normal'>&#xF15F;</span>
2D60  |<span class='utn normal'>&#x2D60;</span>| <span class='utn normal'>&#x2D60;</span> | <span class='utn normal'>&#xF060;</span>|<span class='utn normal'>&#xF160;</span>
2D61  |<span class='utn normal'>&#x2D61;</span>| <span class='utn normal'>&#x2D61;</span> | <span class='utn normal'>&#xF061;</span>|<span class='utn normal'>&#xF161;</span>
2D62  |<span class='utn normal'>&#x2D62;</span>| <span class='utn normal'>&#xFD62;</span> | <span class='utn normal'>&#xF062;</span>|<span class='utn normal'>&#xF162;</span>
2D63  |<span class='utn normal'>&#x2D63;</span>| <span class='utn normal'>&#x2D63;</span> | <span class='utn normal'>&#xF063;</span>|<span class='utn normal'>&#xF063;</span>
2D64  |<span class='utn normal'>&#x2D64;</span>| <span class='utn normal'>&#xFD64;</span> | <span class='utn normal'>&#xF064;</span>|<span class='utn normal'>&#xF164;</span>
2D65  |<span class='utn normal'>&#x2D65;</span>| <span class='utn normal'>&#x2D65;</span> | <span class='utn normal'>&#xF065;</span>|<span class='utn normal'>&#xF065;</span>
2D66  |<span class='utn normal'>&#x2D66;</span>| <span class='utn normal'>&#xFD66;</span> | <span class='utn normal'>&#xF066;</span>|<span class='utn normal'>&#xF166;</span>
2D67  |<span class='utn normal'>&#x2D67;</span>| <span class='utn normal'>&#x2D67;</span> | <span class='utn normal'>&#xF067;</span>|<span class='utn normal'>&#xF067;</span>

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

_Source_: <a href="#ircam">Tifinaghe-IRCAM</a>, [Omniglot](https://omniglot.com/writing/tamazight.htm), <a href="#ishida_zgh">Tamazight: Neo-Tifinagh orthography notes</a>, and <a href="#sahraoui">Souad Sahraoui (pages 307-308)</a>

_Language tags:_ `tzm-Tfng`, `zgh`

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


### <a id="kab"></a>Kabyle, Amazigh, Taqbaylit

_Source_: [Omniglot](https://omniglot.com/writing/kabyle.php) and <a href="#snima">SNIMA 2004</a>

_Language tag_: `kab-Tfng`

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

A variant of U+2D4D is used: <span class='utn normal'>&#xE00E;</span>

#### Bi-consonants

Bi-consonants are not “required” in Neo-Tifinagh. If a font supports bi-consonants, the two consonants separated by the ZWJ should thus form a bi-consonant. If a font does not support bi-consonants, they should simply appear as separate consonants.

#### Collation

<span class='nototif normal'>&#x2D30;</span> &lt; <span class='nototif normal'>&#x2D31;</span> &lt;&lt; <span class='nototif normal'>&#x2D31;&#x2D6F;</span> &lt; <span class='nototif normal'>&#x2D5B;</span> &lt; <span class='nototif normal'>&#x2D5E;</span> &lt; <span class='nototif normal'>&#x2D37;</span> &lt;&lt; <span class='nototif normal'>&#x2D37;&#x2D65;</span> &lt; <span class='nototif normal'>&#x2D39;</span> &lt; <span class='nototif normal'>&#x2D3B;</span> &lt; <span class='nototif normal'>&#x2D44;</span> &lt; <span class='nototif normal'>&#x2D3C;</span> &lt; <span class='nototif normal'>&#x2D33;</span> &lt;&lt; <span class='nototif normal'>&#x2D33;&#x2D6F;</span> &lt; <span class='nototif normal'>&#x2D35;</span> &lt; <span class='nototif normal'>&#x2D56;</span> &lt;&lt; <span class='nototif normal'>&#x2D56;&#x2D6F;</span> &lt; <span class='nototif normal'>&#x2D41;</span> &lt; <span class='nototif normal'>&#x2D43;</span> &lt; <span class='nototif normal'>&#x2D49;</span> &lt; <span class='nototif normal'>&#x2D4A;</span> &lt; <span class='nototif normal'>&#x2D3D;</span> &lt;&lt; <span class='nototif normal'>&#x2D3D;&#x2D6F;</span> &lt; <span class='nototif normal'>&#x2D4D;</span> &lt; <span class='nototif normal'>&#x2D4E;</span> &lt; <span class='nototif normal'>&#x2D4F;</span> &lt; <span class='nototif normal'>&#x2D47;</span> &lt;&lt; <span class='nototif normal'>&#x2D47;&#x2D6F;</span> &lt; <span class='nototif normal'>&#x2D54;</span> &lt; <span class='nototif normal'>&#x2D55;</span> &lt; <span class='nototif normal'>&#x2D59;</span> &lt; <span class='nototif normal'>&#x2D5A;</span> &lt; <span class='nototif normal'>&#x2D5C;</span> &lt;&lt; <span class='nototif normal'>&#x2D5C;&#x2D59;</span>  &lt; <span class='nototif normal'>&#x2D5F;</span> &lt; <span class='nototif normal'>&#x2D53;</span> &lt; <span class='nototif normal'>&#x2D61;</span> &lt; <span class='nototif normal'>&#x2D45;</span> &lt;&lt; <span class='nototif normal'>&#x2D45;&#x2D6F;</span> &lt; <span class='nototif normal'>&#x2D62;</span> &lt; <span class='nototif normal'>&#x2D63;</span> &lt; <span class='nototif normal'>&#x2D65;</span>

### <a id="rif"></a>Tarifit, Riffian

_Source_: [Omniglot](https://omniglot.com/writing/riffian.htm) and <a href="#2009">Tarifit New Testament</a>

_Language tag:_ `rif-Tfng`

_Opentype language system tag:_ `BBR `

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

#### Known glyph variants

The Unicode chart glyphs are based on Neo-Tifinagh shapes; thus, no glyph variants are required.

#### Bi-consonants

Bi-consonants are not “required” in Neo-Tifinagh. If a font supports bi-consonants, the two consonants separated by the ZWJ should thus form a bi-consonant. If a font does not support bi-consonants, they should simply appear as separate consonants.

#### Contextual Shaping

Neo-Tifinagh does not use contextual shaping for the “l” and “n”. This is because the glyphs are distinguishable from each other when side by side.

#### Collation

<span class='nototif normal'>&#x2D30;</span> &lt; <span class='nototif normal'>&#x2D31;</span> &lt; <span class='nototif normal'>&#x2D33;</span> &lt;&lt; <span class='nototif normal'>&#x2D33;&#x2D6F;</span> &lt; <span class='nototif normal'>&#x2D37;</span> &lt; <span class='nototif normal'>&#x2D39;</span> &lt; <span class='nototif normal'>&#x2D3B;</span> &lt; <span class='nototif normal'>&#x2D3C;</span> &lt; <span class='nototif normal'>&#x2D3D;</span> &lt;&lt; <span class='nototif normal'>&#x2D3D;&#x2D6F;</span> &lt; <span class='nototif normal'>&#x2D40;</span> &lt; <span class='nototif normal'>&#x2D43;</span> &lt; <span class='nototif normal'>&#x2D44;</span> &lt; <span class='nototif normal'>&#x2D45;</span> &lt; <span class='nototif normal'>&#x2D47;</span> &lt; <span class='nototif normal'>&#x2D49;</span> &lt; <span class='nototif normal'>&#x2D4A;</span> &lt; <span class='nototif normal'>&#x2D4D;</span> &lt; <span class='nototif normal'>&#x2D4E;</span> &lt; <span class='nototif normal'>&#x2D4F;</span> &lt; <span class='nototif normal'>&#x2D53;</span> &lt; <span class='nototif normal'>&#x2D54;</span> &lt; <span class='nototif normal'>&#x2D55;</span> &lt; <span class='nototif normal'>&#x2D56;</span> &lt; <span class='nototif normal'>&#x2D59;</span> &lt; <span class='nototif normal'>&#x2D5A;</span> &lt; <span class='nototif normal'>&#x2D5B;</span> &lt; <span class='nototif normal'>&#x2D5E;</span> &lt; <span class='nototif normal'>&#x2D5C;</span> &lt; <span class='nototif normal'>&#x2D5F;</span> &lt; <span class='nototif normal'>&#x2D61;</span> &lt; <span class='nototif normal'>&#x2D62;</span> &lt; <span class='nototif normal'>&#x2D63;</span> &lt; <span class='nototif normal'>&#x2D65;</span>

_Sample graphic_</br><img src="assets/images/rif_NT_John1_1-4.png" title="fig:" style="width:80%;height:80%;" alt="Tarafit sample" />
<figcaption>John 1:1-4 (<a href="#2009">Tarifit (rif) New Testament</a>).</figcaption>

### <a id="shi"></a>Tachelhit

_Source_: [shi](https://github.com/silnrsi/sldr/blob/master/sldr/s/shi.xml) (SLDR)

_Language tag:_ `shi`

_Opentype language system tag:_ `BBR `

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

#### Known glyph variants

The Unicode chart glyphs are based on Neo-Tifinagh shapes; thus, no glyph variants are required.

#### Bi-consonants

Bi-consonants are not “required” in Neo-Tifinagh. If a font supports bi-consonants, the two consonants separated by the ZWJ should thus form a bi-consonant. If a font does not support bi-consonants, they should simply appear as separate consonants.

#### Contextual Shaping

Neo-Tifinagh does not use contextual shaping for the “l” and “n”. This is because the glyphs are distinguishable from each other when side by side.

#### Collation

<span class='nototif normal'>&#x2D30;</span> &lt; <span class='nototif normal'>&#x2D31;</span> &lt; <span class='nototif normal'>&#x2D33;</span> &lt;&lt; <span class='nototif normal'>&#x2D33;&#x2D6F;</span> <span class='nototif normal'>&#x2D37;</span> &lt; <span class='nototif normal'>&#x2D39;</span> &lt; <span class='nototif normal'>&#x2D3B;</span> &lt; <span class='nototif normal'>&#x2D3C;</span> &lt; <span class='nototif normal'>&#x2D3D;</span> &lt;&lt; <span class='nototif normal'>&#x2D3D;&#x2D6F;</span> &lt; <span class='nototif normal'>&#x2D40;</span> &lt; <span class='nototif normal'>&#x2D43;</span> &lt; <span class='nototif normal'>&#x2D44;</span> &lt; <span class='nototif normal'>&#x2D45;</span> &lt; <span class='nototif normal'>&#x2D47;</span> &lt; <span class='nototif normal'>&#x2D49;</span> &lt; <span class='nototif normal'>&#x2D4A;</span> &lt; <span class='nototif normal'>&#x2D4D;</span> &lt; <span class='nototif normal'>&#x2D4E;</span> &lt; <span class='nototif normal'>&#x2D4F;</span> &lt; <span class='nototif normal'>&#x2D53;</span> &lt; <span class='nototif normal'>&#x2D54;</span> &lt; <span class='nototif normal'>&#x2D55;</span> &lt; <span class='nototif normal'>&#x2D56;</span> &lt; <span class='nototif normal'>&#x2D59;</span> &lt; <span class='nototif normal'>&#x2D5A;</span> &lt; <span class='nototif normal'>&#x2D5B;</span> &lt; <span class='nototif normal'>&#x2D5C;</span> &lt; <span class='nototif normal'>&#x2D5F;</span> &lt; <span class='nototif normal'>&#x2D61;</span> &lt; <span class='nototif normal'>&#x2D62;</span> &lt; <span class='nototif normal'>&#x2D63;</span> &lt; <span class='nototif normal'>&#x2D65;</span>


## <a id="trad"></a>Languages Using Traditional Tifinagh script

### <a id="cnu"></a> Chenoua, Tacenwit

_Source_: [Savage, 2003 pages 2-3](#savage2003)

This source lists a set of characters that are used in a Algerian school text book entitled “Adlis” printed in 1988 (pages 12,13). It is unknown how widely used this book (or the characters) are actually used.

_Language tag_: `cnu-Tfng`

Characters | | | | | | | | | &#x0020;
:------- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :--
Tfng | <span class='akatab normal'>&#x2D30;</span> | <span class='akatab normal'>&#x2D30;&#x0302;</span> | <span class='nototif normal'>&#x2D33;</span> | <span class='nototif normal'>&#x2D35;</span> | <span class='nototif normal'>&#x2D37;</span> | <span class='nototif normal'>&#x2D39;</span> | <span class='utn normal'>&#xED3B;</span> | <span class='akatab normal'>&#x2D3C;</span> | <span class='nototif normal'>&#x2D3D;</span>
USV  | 2D30 | 2D30 0302 | 2D33 | 2D35        | 2D37 | 2D39 | 2D3B | 2D3C | 2D3D
Latn | /a/  | /&#x025b;/  | /g/  | /g&#x030C;/ | /d/  | /ḍ/  | /c/  | /f/  | /k/ 
| | | | | | | | |
Tfng | <span class='nototif normal'>&#x2D40;</span> | <span class='nototif normal'>&#x2D43;</span> | <span class='nototif normal'>&#x2D45;</span> | <span class='nototif normal'>&#x2D47;</span> | <span class='utn normal'>&#xED49;</span> | <span class='nototif normal'>&#x2D4A;</span> | <span class='akatab normal'>&#x2D4D;</span> | <span class='nototif normal'>&#x2D4E;</span> | <span class='nototif normal'>&#x2D4F;</span>
USV  | 2D40 | 2D43        | 2D45 | 2D47 | 2D49 | 2D4A | 2D4D | 2D4E | 2D4F
Latn | /b/  | /h&#x0323;/ | /x/  | /q/  | /i/  | /j/  | /l/  | /m/  | /n/ 
| | | | | | | | |
Tfng | <span class='akatab normal'>&#x2D53;</span> | <span class='nototif normal'>&#x2D54;</span> | <span class='nototif normal'>&#x2D59;</span> | <span class='akatab normal'>&#x2D5B;</span> | <span class='akatab normal'>&#x2D5C;</span> | <span class='nototif normal'>&#x2D5F;</span> | <span class='nototif normal'>&#x2D61;</span> | <span class='utn normal'>&#xE03B;</span> | <span class='nototif normal'>&#x2D63;</span>
USV  | 2D53 | 2D54 | 2D59 | 2D5B | 2D5C | 2D5F        | 2D61 | 2D62 | 2D63
Latn | /u/  | /r/  | /s/  | /c/  | /t/  | /t&#x0323;/ | /w/  | /y/  | /z/ 

#### Glyph variants

USV |&#x0020; | &#x0020; | &#x0020;
:--  | :--  | :--  | :--
2D30 | <span class='nototif normal'>&#x2D30;</span>|&#x003E;|<span class='akatab normal'>&#x2D30;</span>
2D3B | <span class='nototif normal'>&#x2D3B;</span>|&#x003E;|<span class='utn normal'>&#xED3B;</span>
2D3C | <span class='nototif normal'>&#x2D3C;</span>|&#x003E;|<span class='akatab normal'>&#x2D3C;</span>
2D49 | <span class='nototif normal'>&#x2D49;</span>|&#x003E;|<span class='utn normal'>&#xED49;</span>
2D4D | <span class='nototif normal'>&#x2D4D;</span>|&#x003E;|<span class='akatab normal'>&#x2D4D;</span>
2D53 | <span class='nototif normal'>&#x2D53;</span>|&#x003E;|<span class='akatab normal'>&#x2D53;</span>
2D5B | <span class='nototif normal'>&#x2D5B;</span>|&#x003E;|<span class='akatab normal'>&#x2D5B;</span>
2D5C | <span class='nototif normal'>&#x2D5C;</span>|&#x003E;|<span class='akatab normal'>&#x2D5C;</span>
2D62 | <span class='nototif normal'>&#x2D62;</span>|&#x003E;|<span class='utn normal'>&#xE03B;</span>

### <a id="gho"></a>Ghomara, Shilha

_Source_: [Omniglot](https://omniglot.com/writing/shilha.htm)

_Language tag_: `gho-Tfng`

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

A variant of U+2D4d is used: <span class='utn normal'>&#xE00E;</span>

#### Bi-consonants

Unknown.

#### Collation

<span class='nototif normal'>&#x2D30;</span> &lt; <span class='nototif normal'>&#x2D31;</span> &lt; <span class='nototif normal'>&#x2D33;</span> &lt;&lt; <span class='nototif normal'>&#x2D33;&#x2D6F;</span> &lt; <span class='nototif normal'>&#x2D37;</span> &lt; <span class='nototif normal'>&#x2D39;</span> &lt; <span class='nototif normal'>&#x2D3C;</span> &lt; <span class='nototif normal'>&#x2D3D;</span> &lt;&lt; <span class='nototif normal'>&#x2D3D;&#x2D6F;</span> &lt;
<span class='nototif normal'>&#x2D40;</span> &lt; <span class='nototif normal'>&#x2D43;</span> &lt; <span class='nototif normal'>&#x2D44;</span> &lt; <span class='nototif normal'>&#x2D45;</span> &lt;&lt; <span class='nototif normal'>&#x2D45;&#x2D6F;</span>
&lt; <span class='nototif normal'>&#x2D47;</span> &lt; <span class='nototif normal'>&#x2D49;</span> &lt; <span class='nototif normal'>&#x2D4A;</span> &lt; <span class='nototif normal'>&#x2D4D;</span> &lt; <span class='nototif normal'>&#x2D4E;</span> &lt; <span class='nototif normal'>&#x2D4F;</span> &lt; <span class='nototif normal'>&#x2D53;</span> &lt; <span class='nototif normal'>&#x2D54;</span> &lt; <span class='nototif normal'>&#x2D55;</span> &lt; <span class='nototif normal'>&#x2D56;</span> &lt;&lt; <span class='nototif normal'>&#x2D56;&#x2D6F;</span> 
&lt; <span class='nototif normal'>&#x2D59;</span> &lt; <span class='nototif normal'>&#x2D5A;</span> &lt; <span class='nototif normal'>&#x2D5B;</span> &lt; <span class='nototif normal'>&#x2D5C;</span> &lt; <span class='nototif normal'>&#x2D5F;</span> &lt; <span class='nototif normal'>&#x2D61;</span> &lt; <span class='nototif normal'>&#x2D62;</span> &lt; <span class='nototif normal'>&#x2D63;</span> &lt; <span class='nototif normal'>&#x2D65;</span>

### <a id="mzb"></a>Tumzabt

_Source_: [Savage, 2003 pages 2-3](#savage2003)

This source lists a set of characters that are used in a Algerian school text book entitled “Adlis” printed in 1988 (pages 12,13). It is unknown how widely used this book (or the characters) are actually used.

_Language tag_: `mzb-Tfng`

Characters | | | | | | | | | &#x0020;
:------- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :--
Tfng | <span class='akatab normal'>&#x2D30;</span> | <span class='akatab normal'>&#x2D30;&#x0302;</span> | <span class='nototif normal'>&#x2D33;</span> | <span class='nototif normal'>&#x2D35;</span> | <span class='nototif normal'>&#x2D37;</span> | <span class='nototif normal'>&#x2D39;</span> | <span class='utn normal'>&#xED3B;</span> | <span class='akatab normal'>&#x2D3C;</span> | <span class='nototif normal'>&#x2D3D;</span>
USV  | 2D30 | 2D30 0302 | 2D33 | 2D35        | 2D37 | 2D39 | 2D3B | 2D3C | 2D3D
Latn | /a/  | /&#x025b;/  | /g/  | /g&#x030C;/ | /d/  | /ḍ/  | /c/  | /f/  | /k/ 
| | | | | | | | |
Tfng | <span class='nototif normal'>&#x2D40;</span> | <span class='nototif normal'>&#x2D43;</span> | <span class='nototif normal'>&#x2D45;</span> | <span class='nototif normal'>&#x2D47;</span> | <span class='utn normal'>&#xED49;</span> | <span class='nototif normal'>&#x2D4A;</span> | <span class='akatab normal'>&#x2D4D;</span> | <span class='nototif normal'>&#x2D4E;</span> | <span class='nototif normal'>&#x2D4F;</span>
USV  | 2D40 | 2D43        | 2D45 | 2D47 | 2D49 | 2D4A | 2D4D | 2D4E | 2D4F
Latn | /b/  | /h&#x0323;/ | /x/  | /q/  | /i/  | /j/  | /l/  | /m/  | /n/ 
| | | | | | | | |
Tfng | <span class='akatab normal'>&#x2D53;</span> | <span class='nototif normal'>&#x2D54;</span> | <span class='nototif normal'>&#x2D59;</span> | <span class='akatab normal'>&#x2D5B;</span> | <span class='akatab normal'>&#x2D5C;</span> | <span class='nototif normal'>&#x2D5F;</span> | <span class='nototif normal'>&#x2D61;</span> | <span class='utn normal'>&#xE03B;</span> | <span class='nototif normal'>&#x2D63;</span>
USV  | 2D53 | 2D54 | 2D59 | 2D5B | 2D5C | 2D5F        | 2D61 | 2D62 | 2D63
Latn | /u/  | /r/  | /s/  | /c/  | /t/  | /t&#x0323;/ | /w/  | /y/  | /z/ 

#### Glyph variants

USV |&#x0020; | &#x0020; | &#x0020;
:--  | :--  | :--  | :--
2D30 | <span class='nototif normal'>&#x2D30;</span>|&#x003E;|<span class='akatab normal'>&#x2D30;</span>
2D3B | <span class='nototif normal'>&#x2D3B;</span>|&#x003E;|<span class='utn normal'>&#xED3B;</span>
2D3C | <span class='nototif normal'>&#x2D3C;</span>|&#x003E;|<span class='akatab normal'>&#x2D3C;</span>
2D49 | <span class='nototif normal'>&#x2D49;</span>|&#x003E;|<span class='utn normal'>&#xED49;</span>
2D4D | <span class='nototif normal'>&#x2D4D;</span>|&#x003E;|<span class='akatab normal'>&#x2D4D;</span>
2D53 | <span class='nototif normal'>&#x2D53;</span>|&#x003E;|<span class='akatab normal'>&#x2D53;</span>
2D5B | <span class='nototif normal'>&#x2D5B;</span>|&#x003E;|<span class='akatab normal'>&#x2D5B;</span>
2D5C | <span class='nototif normal'>&#x2D5C;</span>|&#x003E;|<span class='akatab normal'>&#x2D5C;</span>
2D62 | <span class='nototif normal'>&#x2D62;</span>|&#x003E;|<span class='utn normal'>&#xE03B;</span>

### <a id="shy"></a>Tachawit, Tacawit

_Source_: [Savage, 2003 pages 2-3](#savage2003)

This source lists a set of characters that are used in a Algerian school text book entitled “Adlis” printed in 1988 (pages 12,13). It is unknown how widely used this book (or the characters) are actually used.

_Language tag_: `shy-Tfng`

Characters | | | | | | | | | &#x0020;
:------- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :--
Tfng | <span class='akatab normal'>&#x2D30;</span> | <span class='akatab normal'>&#x2D30;&#x0302;</span> | <span class='nototif normal'>&#x2D33;</span> | <span class='nototif normal'>&#x2D35;</span> | <span class='nototif normal'>&#x2D37;</span> | <span class='nototif normal'>&#x2D39;</span> | <span class='utn normal'>&#xED3B;</span> | <span class='akatab normal'>&#x2D3C;</span> | <span class='nototif normal'>&#x2D3D;</span>
USV  | 2D30 | 2D30 0302 | 2D33 | 2D35        | 2D37 | 2D39 | 2D3B | 2D3C | 2D3D
Latn | /a/  | /&#x025b;/  | /g/  | /g&#x030C;/ | /d/  | /ḍ/  | /c/  | /f/  | /k/ 
| | | | | | | | |
Tfng | <span class='nototif normal'>&#x2D40;</span> | <span class='nototif normal'>&#x2D43;</span> | <span class='nototif normal'>&#x2D45;</span> | <span class='nototif normal'>&#x2D47;</span> | <span class='utn normal'>&#xED49;</span> | <span class='nototif normal'>&#x2D4A;</span> | <span class='akatab normal'>&#x2D4D;</span> | <span class='nototif normal'>&#x2D4E;</span> | <span class='nototif normal'>&#x2D4F;</span>
USV  | 2D40 | 2D43        | 2D45 | 2D47 | 2D49 | 2D4A | 2D4D | 2D4E | 2D4F
Latn | /b/  | /h&#x0323;/ | /x/  | /q/  | /i/  | /j/  | /l/  | /m/  | /n/ 
| | | | | | | | |
Tfng | <span class='akatab normal'>&#x2D53;</span> | <span class='nototif normal'>&#x2D54;</span> | <span class='nototif normal'>&#x2D59;</span> | <span class='akatab normal'>&#x2D5B;</span> | <span class='akatab normal'>&#x2D5C;</span> | <span class='nototif normal'>&#x2D5F;</span> | <span class='nototif normal'>&#x2D61;</span> | <span class='utn normal'>&#xE03B;</span> | <span class='nototif normal'>&#x2D63;</span>
USV  | 2D53 | 2D54 | 2D59 | 2D5B | 2D5C | 2D5F        | 2D61 | 2D62 | 2D63
Latn | /u/  | /r/  | /s/  | /c/  | /t/  | /t&#x0323;/ | /w/  | /y/  | /z/ 

#### Glyph variants

USV |&#x0020; | &#x0020; | &#x0020;
:--  | :--  | :--  | :--
2D30 | <span class='nototif normal'>&#x2D30;</span>|&#x003E;|<span class='akatab normal'>&#x2D30;</span>
2D3B | <span class='nototif normal'>&#x2D3B;</span>|&#x003E;|<span class='utn normal'>&#xED3B;</span>
2D3C | <span class='nototif normal'>&#x2D3C;</span>|&#x003E;|<span class='akatab normal'>&#x2D3C;</span>
2D49 | <span class='nototif normal'>&#x2D49;</span>|&#x003E;|<span class='utn normal'>&#xED49;</span>
2D4D | <span class='nototif normal'>&#x2D4D;</span>|&#x003E;|<span class='akatab normal'>&#x2D4D;</span>
2D53 | <span class='nototif normal'>&#x2D53;</span>|&#x003E;|<span class='akatab normal'>&#x2D53;</span>
2D5B | <span class='nototif normal'>&#x2D5B;</span>|&#x003E;|<span class='akatab normal'>&#x2D5B;</span>
2D5C | <span class='nototif normal'>&#x2D5C;</span>|&#x003E;|<span class='akatab normal'>&#x2D5C;</span>
2D62 | <span class='nototif normal'>&#x2D62;</span>|&#x003E;|<span class='utn normal'>&#xE03B;</span>

### <a id="siz"></a>Siwi

_Source_: [Omniglot](https://omniglot.com/writing/siwi.htm)

_Language tag_: `siz-Tfng`

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

_Language tag_: `taq-Tfng`

_Opentype language system tag:_ `TAQ ` (preferred) or `TMH `

Characters | | | | | | | | | &#x0020;
:------- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :--
Tfng       | <span class='nototif normal'>&#x2D30;</span> | <span class='nototif normal'>&#x2D31;</span> | <span class='nototif normal'>&#x2D34;</span> | <span class='nototif normal'>&#x2D36;</span> | <span class='nototif normal'>&#x2D37;</span> | <span class='nototif normal'>&#x2D39;</span> | <span class='nototif normal'>&#x2D3C;</span> | <span class='nototif normal'>&#x2D3E;</span> | <span class='nototif normal'>&#x2D42;</span> 
USV        | 2D30 | 2D31 | 2D34 | 2D36 | 2D37 | 2D39 | 2D3C | 2D3E | 2D42 
Latn        | /a/ | /b/ | /g/ | /j/ | /d/ | /ḍ/ | /f/ | /k/ | /h/ 
| | | | | | | | |
 Tfng       |<span class='nototif normal'>&#x2D43;</span> |<span class='nototif normal'>&#x2D44;</span> | <span class='nototif normal'>&#x2D46;</span> | <span class='nototif normal'>&#x2D48;</span> | <span class='nototif normal'>&#x2D49;</span> | <span class='nototif normal'>&#x2D4B;</span> |<span class='nototif normal'>&#x2D4C;</span> | <span class='nototif normal'>&#x2D4D;</span> | <span class='nototif normal'>&#x2D4E;</span>  
USV        | 2D43 | 2D44| 2D46 | 2D48 | 2D49 | 2D4B | 2D4C | 2D4D | 2D4E 
Latn        | /h&#x0323;/ | /&#x025B;/ | /x/ | /q/ | /i/ | /z&#x030C;/ | /z&#x0323;/ | /l/ | /m/ 
| | | | | | | | |
Tfng       | <span class='nototif normal'>&#x2D4F;</span>| <span class='nototif normal'>&#x2D51;</span> | <span class='nototif normal'>&#x2D53;</span> |<span class='nototif normal'>&#x2D54;</span> |<span class='nototif normal'>&#x2D57;</span>| <span class='nototif normal'>&#x2D59;</span> | <span class='nototif normal'>&#x2D5A;</span> | <span class='nototif normal'>&#x2D5B;</span> | <span class='nototif normal'>&#x2D5C;</span> 
USV         | 2D4F | 2D51 | 2D53 | 2D54 | 2D57 | 2D59 | 2D5A | 2D5B | 2D5C 
Latn        | /n/ | /&#x014B;/ | /o/ /u/ | /r/ | /&#x0263;/ | /s/ | /s&#x0323;/ | /s&#x030C;/ | /t/ 
| | | | | | | | |
Tfng       | <span class='nototif normal'>&#x2D5F;</span> | <span class='nototif normal'>&#x2D61;</span> | <span class='nototif normal'>&#x2D62;</span> | <span class='nototif normal'>&#x2D63;</span> | <span class='nototif normal'>&#x2D65;</span> |<span class='nototif normal'>&#x2D66;</span> |
USV         | 2D5F | 2D61 | 2D62 | 2D63 | 2D65 | 2D66 | 
Latn        | /t&#x0323;/| /w/ | /y/ | /z/ | /z&#x0323;/ | /e/ /&#x01DD;/| 

#### Glyph variants and Bi-consonants

Unknown.

#### Collation

<span class='nototif normal'>&#x2D30;</span> &lt; <span class='nototif normal'>&#x2D31;</span> &lt; <span class='nototif normal'>&#x2D34;</span> &lt; <span class='nototif normal'>&#x2D36;</span> &lt; <span class='nototif normal'>&#x2D37;</span> &lt; <span class='nototif normal'>&#x2D39;</span> &lt; <span class='nototif normal'>&#x2D3C;</span> &lt; <span class='nototif normal'>&#x2D3E;</span> &lt; <span class='nototif normal'>&#x2D42;</span> &lt; <span class='nototif normal'>&#x2D43;</span> &lt; <span class='nototif normal'>&#x2D44;</span> &lt; <span class='nototif normal'>&#x2D46;</span> &lt; <span class='nototif normal'>&#x2D48;</span> &lt; <span class='nototif normal'>&#x2D49;</span> &lt; <span class='nototif normal'>&#x2D4C;</span> &lt; <span class='nototif normal'>&#x2D4B;</span> &lt;  <span class='nototif normal'>&#x2D4D;</span> &lt; <span class='nototif normal'>&#x2D4E;</span> &lt; <span class='nototif normal'>&#x2D4F;</span> &lt; <span class='nototif normal'>&#x2D51;</span> &lt; <span class='nototif normal'>&#x2D53;</span> &lt; <span class='nototif normal'>&#x2D54;</span> &lt; <span class='nototif normal'>&#x2D57;</span> &lt; <span class='nototif normal'>&#x2D59;</span> &lt; <span class='nototif normal'>&#x2D5A;</span> &lt; <span class='nototif normal'>&#x2D5B;</span> &lt; <span class='nototif normal'>&#x2D5C;</span> &lt; <span class='nototif normal'>&#x2D5F;</span> &lt; <span class='nototif normal'>&#x2D61;</span> &lt; <span class='nototif normal'>&#x2D62;</span> &lt; <span class='nototif normal'>&#x2D63;</span> &lt; <span class='nototif normal'>&#x2D65;</span> &lt; <span class='nototif normal'>&#x2D66;</span>

### <a id="taq-ML"></a>Tamasheq (Mali)

_Source_: [Savage, 2000](#savage2000) (pages 145-147, 154)

_Language tag_: `taq-Tfng-ML`

_Opentype language system tag:_ `TAQ ` (preferred) or `TMH `

Characters | | | | | | | | | &#x0020;
:------- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :--
Tfng       | <span class='akatab normal' style='font-feature-settings: "cv01" 1'>&#x2D30;</span> | <span class='akatab normal'>&#x2D31;</span> | <span class='akatab normal'>&#x2D36;</span> | <span class='akatab normal'>&#x2D37;</span> | <span class='akatab normal'>&#x2D39;</span> |<span class='akatab normal' style='font-feature-settings: "cv02" 1'>&#x2D3C;</span> | <span class='akatab normal'>&#x2D3E;</span> | <span class='akatab normal'>&#x2D42;</span> | <span class='utn normal'>&#x2D46;</span> 
USV        | 2D30 | 2D31 | 2D36 | 2D37 | 2D39 | 2D3C | 2D3E | 2D42 | 2D46
Latn        | /&#x0251;/ | /b/ | /&#x0261;/ | /d/ | /ḍ/ | /f/ | /k/ | /h/ | /x/ 
| | | | | | | | |
 Tfng       | <span class='akatab normal'>&#x2D48;</span> | <span class='akatab normal'>&#x2D49;</span> | <span class='akatab normal'>&#x2D4B;</span> | <span class='akatab normal'>&#x2D4C;</span> | <span class='akatab normal'>&#x2D4D;</span> |<span class='akatab normal'>&#x2D4E;</span> | <span class='akatab normal'>&#x2D4F;</span> | <span class='akatab normal'>&#x2D53;</span>| <span class='akatab normal'>&#x2D54;</span>
USV        | 2D48 | 2D49 | 2D4B | 2D4C | 2D4D | 2D4E | 2D4F | 2D53 |2D54
Latn        | /q/ | /y/ | /z&#x030C;/ | /z&#x0323;/ | /l/ | /m/ | /n/ | /w/ | /r/
| | | | | | | | |
Tfng        | <span class='akatab normal'>&#x2D57;</span> | <span class='akatab normal'>&#x2D58;</span> | <span class='akatab normal'>&#x2D59;</span> | <span class='akatab normal'>&#x2D5A;</span> | <span class='akatab normal' style='font-feature-settings: "cv12" 1'>&#x2D5B;</span> | <span class='akatab normal'>&#x2D5C;</span> | <span class='akatab normal' style='font-feature-settings: "cv13" 1'>&#x2D5F;</span> | <span class='akatab normal'>&#x2D63;</span> | <span class='utn normal'>&#xE03A;</span>
USV         | 2D57 | 2D58 | 2D59 | 2D5A | 2D5B | 2D5C | 2D5F | 2D63 | unencoded?
Latn        | /&#x0263;/ | /j&#x030c;/ | /s/ | /s&#x0323;/ | /s&#x030c;/ | /t/ | /t&#x0323;/ | /z/ |  /ḷ/


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
<span class='utn normal'>&#xE03A;</span> &lt;
<span class='akatab normal'>&#x2D53;</span> &lt;
<span class='akatab normal'>&#x2D49;</span>

### <a id="tda"></a>Tuareg (Azawagh dialect of Niger-Mali), Tagdal

_Source_: <a href="#Andries2004">L2/04-142</a> (pages 8 & 31)

_Language tag_: `tda-Tfng`

Characters | | | | | | | | | &#x0020;
:------- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :--
Tfng       | <span class='akatab normal'>&#x2D30;</span> | <span class='akatab normal'>&#x2D36;</span> | <span class='akatab normal'>&#x2D39;</span> | <span class='akatab normal'>&#x2D3C;</span> | <span class='akatab normal'>&#x2D3E;</span> |<span class='akatab normal'>&#x2D40;</span> | <span class='akatab normal'>&#x2D42;</span> | <span class='akatab normal'>&#x2D46;</span> | <span class='akatab normal'>&#x2D48;</span> 
USV        | 2D30 | 2D36 | 2D39 | 2D3C | 2D3E | 2D40 | 2D42 | 2D46 | 2D48
Latn       | /a/  | /g/  | /d/  | /f/  | /k/  | /b/  | /h/  | /q/  | /x/ 
| | | | | | | | |
Tfng       | <span class='akatab normal'>&#x2D4C;</span> | <span class='akatab normal'>&#x2D4D;</span> | <span class='akatab normal'>&#x2D4E;</span> | <span class='akatab normal'>&#x2D4F;</span> | <span class='akatab normal'>&#x2D53;</span> |<span class='akatab normal'>&#x2D54;</span> | <span class='akatab normal'>&#x2D57;</span> | <span class='akatab normal'>&#x2D59;</span> | <span class='akatab normal'>&#x2D5B;</span> 
USV        | 2D4C | 2D4D | 2D4E | 2D4F | 2D53 | 2D54 | 2D57 | 2D59 | 2D5B
Latn       | /j/  | /l/  | /m/  | /n/  | /w/  | /r/  | /&#x0263;/  | /s/  | /s&#x030C;/ 
| | | | | | | | |
Tfng       | <span class='akatab normal'>&#x2D5C;</span> | <span class='akatab normal'>&#x2D62;</span> | <span class='akatab normal'>&#x2D63;</span> | <span class='akatab normal'>&#x2D64;</span> | | | | |  
USV        | 2D5C | 2D62 | 2D63 | 2D64 |  |  |  |  | 
Latn       | /t/  | /y/  | /z/  | /z&#x0323;/  |  |  |   |   | / 

#### Glyph variants

USV |&#x0020; | &#x0020; | &#x0020;
:--  | :--  | :--  | :--
2D30 | <span class='nototif normal'>&#x2D30;</span>|&#x003E;|<span class='akatab normal'>&#x2D30;</span>
2D3C | <span class='nototif normal'>&#x2D3C;</span>|&#x003E;|<span class='akatab normal'>&#x2D3C;</span>
2D4D | <span class='nototif normal'>&#x2D4D;</span>|&#x003E;|<span class='akatab normal'>&#x2D4D;</span>
2D53 | <span class='nototif normal'>&#x2D53;</span>|&#x003E;|<span class='akatab normal'>&#x2D53;</span>

#### Bi-consonants

Unknown.

#### Collation

<span class='akatab normal'>&#x2D30;</span> &lt;
<span class='akatab normal'>&#x2D40;</span> &lt;
<span class='akatab normal'>&#x2D39;</span> &lt;
<span class='akatab normal'>&#x2D3C;</span> &lt;
<span class='akatab normal'>&#x2D36;</span> &lt;
<span class='akatab normal'>&#x2D57;</span> &lt;
<span class='akatab normal'>&#x2D42;</span> &lt;
<span class='akatab normal'>&#x2D4C;</span> &lt;
<span class='akatab normal'>&#x2D3E;</span> &lt;
<span class='akatab normal'>&#x2D4D;</span> &lt;
<span class='akatab normal'>&#x2D4E;</span> &lt;
<span class='akatab normal'>&#x2D4F;</span> &lt;
<span class='akatab normal'>&#x2D46;</span> &lt;
<span class='akatab normal'>&#x2D54;</span> &lt;
<span class='akatab normal'>&#x2D59;</span> &lt;
<span class='akatab normal'>&#x2D5B;</span> &lt;
<span class='akatab normal'>&#x2D5C;</span> &lt;
<span class='akatab normal'>&#x2D53;</span> &lt;
<span class='akatab normal'>&#x2D48;</span> &lt;
<span class='akatab normal'>&#x2D62;</span> &lt;
<span class='akatab normal'>&#x2D63;</span> &lt;
<span class='akatab normal'>&#x2D64;</span>

### <a id="thv"></a> Tahaggart Tamahaq, Tamahaq (Tuareg)

_Source_: Alphabet Chart (personal files)

_Language tag:_ `thv-Tfng`

_Opentype language system tag:_ `THV ` (preferred) or `TMH `

_Keyman keyboard:_ [Tuareg Tifinagh](https://keyman.com/keyboards/tuareg_tifinagh) [taq, thv]

_Font:_ [Akatab](https://software.sil.org/akatab/)

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

#### Collation

<span class='akatab normal'>&#x2D30;</span> &lt;
<span class='akatab normal'>&#x2D53;</span> &lt;
<span class='akatab normal'>&#x2D57;</span> &lt;
<span class='akatab normal'>&#x2D48;</span> &lt;
<span class='akatab normal'>&#x2D3E;</span> &lt;
<span class='akatab normal'>&#x2D42;</span> &lt;
<span class='akatab normal'>&#x2D46;</span> &lt;
<span class='akatab normal'>&#x2D5B;</span> &lt;
<span class='akatab normal'>&#x2D59;</span> &lt;
<span class='akatab normal'>&#x2D54;</span> &lt;
<span class='akatab normal'>&#x2D31;</span> &lt;
<span class='akatab normal'>&#x2D5C;</span> &lt;
<span class='akatab normal'>&#x2D4F;</span> &lt;
<span class='akatab normal'>&#x2D4D;</span> &lt;
<span class='akatab normal'>&#x2D4E;</span> &lt;
<span class='akatab normal'>&#x2D37;</span> &lt;
<span class='akatab normal'>&#x2D3C;</span> &lt;
<span class='akatab normal'>&#x2D39;</span> &lt;
<span class='akatab normal'>&#x2D5F;</span> &lt;
<span class='akatab normal'>&#x2D49;</span> &lt;
<span class='akatab normal'>&#x2D4B;</span> &lt;
<span class='akatab normal'>&#x2D63;</span> &lt;
<span class='akatab normal'>&#x2D4C;</span> &lt;
<span class='akatab normal'>&#x2D50;</span> &lt;
<span class='akatab normal' style='font-feature-settings: "cv03" 1'>&#x2D34;</span> &lt;
<span class='akatab normal'>&#x2D36;</span>

_Sample graphic (right-to-left)_</br><img src="assets/images/thv_TamahaqHoggar_1231.png" title="fig:" style="width:80%;height:80%;" alt="Tamahaq: Hoggar sample" />
<figcaption>Mark 1:1-4 (UBS).</figcaption>

### <a id="thz"></a>Tayart Tamajeq, Tuareg (Aïr dialect of Niger)

_Source_: [Omniglot](https://omniglot.com/writing/tayarttamajeq.htm) and <a href="#Andries2004">L2/04-142</a> (pages 8 & 31)

_Language tag_: `thz-Tfng`

_Opentype language system tag:_ `THZ ` (preferred) or `TMH `

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

_Sample graphic_</br><img src="assets/images/thz_TamahaqAir_1230.png" title="fig:" style="width:80%;height:80%;" alt="Tamahaq: Aïr sample" />
<figcaption>John 1:1-4 (UBS).</figcaption>

### <a id="ttq"></a>Tawallammat Tamajaq

_Source_: <a href="#abdoussamed">Abdoussamed</a>, and characters which are included in Tagmukay font and the keyboard below.

_Language tag_: `ttq-Tfng`, `tmh-Tfng` (macrolanguage)

_Opentype language system tag:_ `TTQ ` (preferred) or `TMH `

_Keyman keyboard:_ [Tawallammat Tifinagh (SIL)](https://keyman.com/keyboards/sil_tawallammat) [ttq, tzm]

_Font:_ [Tagmukay](https://software.sil.org/tagmukay/)

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

See sample images at bottom of this section.

Vowels |     |     |     |     |     |
:--    | :-- | :-- | :-- | :-- | :-- | :--
Tfng   | <span class='akatab normal'>&#x2D30;&#x0302;</span> | <span class='akatab normal'>&#x2D30;&#x0306;</span> | <span class='akatab normal'>&#x2D62;&#x0323;</span> | <span class='akatab normal'>&#x2D62;&#x0302;</span> | <span class='akatab normal'>&#x2D53;&#x0302;</span> | <span class='akatab normal'>&#x2D67;&#x0302;</span>
USV    | 2D30 + 0302 | 2D30 + 0306 | 2D62 + 0323 | 2D62 + 0302 | 2D53 + 0302 | 2D67 + 0302
Latn | /ɑ/ | /ǝ/ | /i/ | /e/ | /u/ | /o/


##### _APT_

Vowels |     |     |     |     |     |
:--    | :-- | :-- | :-- | :-- | :-- | :--
Tfng   | <span class='utn normal'>&#xED30;</span>    | <span class='utn normal'>&#x2D66;</span>    | <span class='utn normal'>&#xED62;</span>    | <span class='utn normal'>&#x2D67;</span> | <span class='utn normal'>&#xE014;</span> | <span class='utn normal'>&#xED67;</span>
USV  | 2D30 | 2D66 | 2D62 | 2D67 | 2D53 | not encoded? 
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
:-- | :----  | :-- | :-- 
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

_Sample graphic (Reading Book)_</br><img src="assets/images/ttq_ReadingBook_1997.png" title="fig:" style="width:80%;height:80%;" alt="Lisons le Temajeq sample" />
<figcaption><a href="#abdoussamed">Lisons le tǝmajǝq en shifinagh vocalisé (1997).</a></figcaption>

_Sample graphic_</br><img src="assets/images/ttq_Health_2005.png" title="fig:" style="width:80%;height:80%;" alt="Ahol y aɣaywan fəl ataɣalla sample" />
<figcaption><a href="#alhassane">Ahol y aɣaywan fəl ataɣalla (2005), p. 15.</a></figcaption>

## <a id="other"></a>Other languages with little or no information

These language are reported to have used or are using Tifinagh script. However, no further information is available.

### <a id="auj"></a>Awjilah

_Language tag_: `auj-Tfng` 	

### <a id="gha"></a>Ghadamès

_Language tag_: `gha-Tfng`

### <a id="grr"></a>Taznatit

_Language tag_: `grr-Tfng`


### <a id="jbn"></a>Nafusi (Zuwara dialect)

_Source_: [Omniglot](https://www.omniglot.com/writing/zuwara.htm)

_Language tag_: `jbn-Tfng`

Omniglot indicates this language can be written with Tifinagh, but no further information is given.

### <a id="nxm"></a>Numidian

_Language tag_: `nxm-Tfng`

### <a id="tez"></a>Tetserret

_Language tag_: `tez-Tfng`

### <a id="zen"></a>Zenaga

_Language tag_: `zen-Tfng`

## Other Berber languages

These are Berber languages which do not appear to have ever used the Tifinagh script:

- Judeo-Berber `[jbe]`
- Tagargrent, Ouargli `[oua]`
- Sened `[sds]`
- Senhaja Berber `[sjs]`
- Sawknah `[swn]`
- Tidikelt Tamazight `[tia]`
- Temacine Tamazight `[tjo]`

## <a id="ack"></a>Acknowledgements

The following people have kindly offered feedback for this document: Juan Luis Blanco, Peter Constable, Ned Holbrook, Richard Ishida, Neil Patel, and Roozbeh Pournader. In addition, the authors are grateful to Patrick Andries and Andrew Savage for their generous help in contributing to our understanding of the Tifinagh script.

## <a id="ref"></a>References

[Omniglot - Central Atlas Tamazight &#x28;Tamaziɣt / ⵜⴰⵎⴰⵣⵉⵖⵜ&#x29; &#x5B;tzm&#x5D;](https://omniglot.com/writing/tamazight.htm)

[Omniglot - Kabyle &#x28;Taqbaylit / ⵜⴰⵇⴱⴰⵢⵍⵉⵜ&#x29; &#x5B;kab&#x5D;](https://omniglot.com/writing/kabyle.php)

[Omniglot - Riffian &#x28;Tarifit / ⵜⴰⵔⵉⴼⵉⵜ&#x200E; / تاريفيت&#x200e;&#x29; &#x5B;rif&#x5D;](https://omniglot.com/writing/riffian.htm)

[Omniglot - Shilha &#x28;Tašəlḥiyt / ⵜⴰⵛⵍⵃⵉⵢⵜ&#x29; &#x5B;gho&#x5D;](https://omniglot.com/writing/shilha.htm)

[Omniglot - Siwi &#x28;ⴶⵍⴰⵏⵏⵉⵙⵉⵡⴰⵏ / Jlan n isiwan&#x29; &#x5B;siz&#x5D;](https://omniglot.com/writing/siwi.htm)

[Omniglot - Tamasheq &#x28;Tafaghist&#x29; &#x5B;taq&#x5D;](https://omniglot.com/writing/tamasheq.htm) 

[Omniglot - Tayart Tamajeq &#x28;Tamajeq, ⵜⵎⵌⵆ, ثمجق&#x200e;&#x29; &#x5B;thz&#x5D;](https://omniglot.com/writing/tayarttamajeq.htm)

<a id="abdoussamed"></a>Abdoussamed, Ghomar; Weber, Christiane. 1997. Lisons le tǝmajǝq en shifinagh vocalisé.

<a id="Andries2004"></a>Andries, P (on behalf of Morocco-Canada-France). 2004-06-06. Proposal to add the Tifinagh Script. [L2/04-142](https://www.unicode.org/L2/L2004/04142r-n2739r-tifinagh.pdf) (accessed 19-Jul-2024)

____. 2005. [Inventaire des oeils de la police pan-berbère Hapax Berbère](http://hapax.qc.ca/polices/inventaire-des-oeils.pdf) (accessed 19-Jul-2024)

Blanco, Juan Luis. 2014. [Tifinagh & the IRCAM. Explorations in Cursiveness and Bicameralism in the Tifinagh Script](https://www.academia.edu/16657385/Tifinagh_and_the_IRCAM_Explorations_in_Cursiveness_and_Bicamelarism_in_the_Tifinagh_script). [Unpublished Master’s thesis]. University of Reading. (accessed 21-Aug-2024)

<a id="2009"></a>DHIMH Multimedia. 2009. [Tarifit (rif) New Testament](https://archive.org/details/newtestament-tarifit) (accessed 19-Jul-2024)

<a id="alhassane"></a>Hamed-Ittyoube, Alhassane. 2005. Ahol y aɣaywan fəl ataɣalla (Conseils pour la famille sur le paludisme). SIL Niger.

<a id="ishida_zgh"></a>Ishida, Richard. [Tamazight: Neo-Tifinagh orthography notes](https://r12a.github.io/scripts/tfng/zgh.html) (accessed 19-Jul-2024)

<a id="savage2000"></a>Savage, Andrew. 2000. Writing Tuareg Vowels. Advantages and Disadvantages of the Three Script Options: Arabic, Tifinagh and Roman. Submitted in partial fulfillment of the requirements for the degree of Master of Letters in Linguistics from the Univerisity of New England, New South Wales, Australia.

<a id="savage2003"></a>Savage, Andrew. 2003. Tifinagh Unicode Propositions, Stanthorpe, [L2/03-143](http://www.unicode.org/L2/L2003/03143-tifinagh-samples.pdf) (accessed 19-Jul-2024)

<a id="sahraoui"></a>Sahraoui, Souad. 2021. [English and the Languages of Algeria: Suggestions towards a New Language Policy](https://www.academia.edu/75532503/English_and_the_Languages_of_Algeria_Suggestions_towards_a_New_Language_Policy) (accessed 19-Jul-2024)

<a id="snima"></a>Snima. 2004. [Projet de norme marocaine: Alphabet tifinaghe](https://www.unicode.org/L2/L2004/04195-pnm-17.1.100.pdf) (accessed 19-Jul-2024)

<a id="ircam"></a>[Tifinaghe-IRCAM &#x5B;tzm&#x5D;](https://www.win.tue.nl/~aeb/natlang/berber/tifinagh/tifinagh-ircam.html) (accessed 19-Jul-2024)

<a id="unicode"></a>[Unicode (chapter 19)](https://unicode-org.github.io/core-spec/chapter-19/#G18607) The Unicode Consortium. The Unicode Standard, Version 16.0.0 (South San Francisco, CA: The Unicode Consortium, 2024.)

United Bible Societies. 1972. [The Book of a Thousand Tongues](https://archive.org/details/B-001-001-424/page/2/mode/2up)

<a id="unknown"></a>Unknown. undated. A Shifinagh Handbook. Unit 2. An Introduction to Shifinagh, the Tamajeq Writing. (This document is specifically for use in Niger. filename:Anonymous A Shifinagh Handbook 1717.pdf)
