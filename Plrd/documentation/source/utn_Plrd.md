---
title: Representing Miao in Unicode - Unicode Technical Note (proposed draft)
---

- <a href="#over">Overview</a>
   - <a href="#store">Character storage</a>
   - <a href="#punct">Punctuation and Digits</a>
   - <a href="#break">Line breaking and word breaking</a>
   - <a href="#rend">Rendering</a>
      - <a href="#tone">Tone mark positioning</a>
      - <a href="#lig">Ligatures</a>
      - <a href="#kern">Kerning</a>
      - <a href="#glyph">Glyph variants</a>
      - <a href="#wart">“wart” vs “dot”</a>
- <a href="#lang">Languages currently using Miao/Pollard script</a>
   - <a href="#hmd">Large Flowery Miao / Dahua Miao / A-Hmao &#x005B;hmd&#x005D;</a>
   - <a href="#hmz">Sinicized Miao / Waishu Miao / Hmong Shua &#x005B;hmz&#x005D;</a>
   - <a href="#lpo">Lipo / Dong Lisu / Eastern Lisu &#x005B;lpo&#x005D;</a>
   - <a href="#ygp">Bai Yi / Gepo &#x005B;ygp&#x005D;</a>
   - <a href="#ywq">Hei Yi / Wuding-Luquan Yi / Nasu &#x005B;ywq&#x005D;</a>
- <a href="#former">Languages formerly using Miao/Pollard script</a>
   - <a href="#cqd">Chuanqiandian Cluster Miao &#x005B;cqd&#x005D;</a>
   - <a href="#ktp">Kaduo / Kado &#x005B;ktp&#x005D;</a>
   - <a href="#lbc">Lakkia &#x005B;lbc&#x005D;</a>
   - <a href="#mww">Hmong Daw &#x005B;mww&#x005D;</a>
   - <a href="#sfm">Xiaohua Miao / Small Flowery Miao &#x005B;sfm&#x005D;</a>
   - <a href="#yna">Gan Yi / Aluo &#x005B;yna&#x005D;</a>
- <a href="#ref">References</a>

## <a id="over"></a>Overview

### <a id="store"></a>Character storage

Each syllable is divided into an initial and a final. The initial is the initial consonant and the final consists of the vowel cluster and the tone. The positioning of the vowels indicates the tone of a syllable. Nasalization and voicing are considered as initial rather than final.

The syllable structure is: (N)C(M)V(V(V))(S/T), where N is the nasalizer (U+16F50), C is the obligatory consonant (U+16F00.0U+16F4A), M is a modifier (U+16F51 is an aspiration mark in current use and U+16F52..U+16F53 are two archaic voicing marks), V is one obligatory vowel mark which may be followed by two more (U+16F54..U+16F87), S is a “shifting” character which controls the height of the vowel (U+16F8F..U+16F92), and T (U+16F93..U+16F9F) is a tone mark; **S and T do not co-occur on a syllable.**

**Rendering Example**

Setting        | Sample 
:--- | :--------------- 
default | <span class='shim normal'>&#x16F10;&#x16F4F;&#x16F7B;&#x16F91;&#x16F50;&#x16F2E;&#x16F54;&#x16F91;&#x16F07;&#x16F79;&#x16F26;&#x16F58;&#x16F8F;&#x16F28;&#x16F51;&#x16F7B;&#x16F43;&#x16F66;&#x16F91;&#x16F3B;&#x16F7A;&#x16F90;&#x16F1E;&#x16F59;&#x16F7E;&#x16F91;&#x16F21;&#x16F60;&#x16F1A;&#x16F5C;&#x16F91;&#x16F16;&#x16F73;&#x16F90;&#x16F18;&#x16F61;&#x16F90;&#x16F04;&#x16F77;&#x16F10;&#x16F75;&#x16F91;&#x16F23;&#x16F71;&#x16F90;&#x16F00;&#x16F6A;&#x16F8F;&#x16F35;&#x16F62;&#x16F91;&#x16F3A;&#x16F6B;&#x16F90;&#x16F33;&#x16F68;&#x16F0A;&#x16F6A;&#x16F57;&#x16F91;&#x16F0E;&#x16F5E;&#x16F8F;&#x16F37;&#x16F5F;&#x16F42;&#x16F61;&#x16F79;&#x16F91;&#x16F08;&#x16F64;&#x16F3D;&#x16F61;&#x16F7B;&#x16F91;&#x16F2F;&#x16F61;&#x16F5D;&#x16F8F;&#x16F1F;&#x16F61;&#x16F73;&#x16F91;&#x16F01;&#x16F6A;&#x16F90;&#x16F0B;&#x16F6A;&#x16F58;&#x16F91;&#x16F38;&#x16F6A;&#x16F5E; </span>
USV | <span class='affects'>U+16F10 U+16F4F U+16F7B U+16F91 U+16F50 U+16F2E U+16F54 U+16F91 U+16F07 U+16F79 U+16F26 U+16F58 U+16F8F U+16F28 U+16F51 U+16F7B U+16F43 U+16F66 U+16F91 U+16F3B U+16F7A U+16F90 U+16F1E U+16F59 U+16F7E U+16F91 U+16F21 U+16F60 U+16F1A U+16F5C U+16F91 U+16F16 U+16F73 U+16F90 U+16F18 U+16F61 U+16F90 U+16F04 U+16F77 U+16F10 U+16F75 U+16F91 U+16F23 U+16F71 U+16F90 U+16F00 U+16F6A U+16F8F U+16F35 U+16F62 U+16F91 U+16F3A U+16F6B U+16F90 U+16F33 U+16F68 U+16F0A U+16F6A U+16F57 U+16F91 U+16F0E U+16F5E U+16F8F U+16F37 U+16F5F U+16F42 U+16F61 U+16F79 U+16F91 U+16F08 U+16F64; U+16F3D U+16F61 U+16F7B U+16F91 U+16F2F U+16F61 U+16F5D U+16F8F U+16F1F U+16F61 U+16F73 U+16F91 U+16F01 U+16F6A U+16F90 U+16F0B U+16F6A U+16F58 U+16F91 U+16F38 U+16F6A U+16F5E </span>

### <a id="punct"></a>Punctuation and Digits

Users of the Miao script freely use the same punctuation marks as Chinese and Latin. 

All languages use these: . , / " = + - ( ) 

Most Miao script users seem to follow the Chinese convention for indicating proper nouns:

- names of people -- single underline
- names of places -- double underline
- book titles -- wavy underline

Miao script users use Western-style digits 0-9.

### <a id="break"></a>Line breaking and word breaking

Word breaking occurs only before an initial consonant. Syllables of consonant, vowels and tone are never split. Line breaks at spaces or after punctuation. A line break may not be inserted
between any syllable, or before punctuation.

When the Big Flowery Miao &#x005B;hmd&#x005D; Bible was typeset, the translation team introduced word breaks. Earlier texts were written without word breaks, and this caused problems in typesetting. Word breaks were introduced in trial editions and were well accepted. Based on this positive feedback, the team included word breaks in the Miao Bible (YU SUEE YAN).

### <a id="rend"></a>Rendering

**<a id="tone"></a>Tone mark positioning**

Four positioning tone marks are encoded. The default position for the vowels and finals is on the baseline. If another position is required a tone positioning mark is required.

Setting | Sample 
:---    | :--------------- 
default | <span class='shim normal'>&#x16F23;&#x16F6A;&#x16F57;</span>
<span class='affects'>U+16F8F MIAO TONE RIGHT</span> | <span class='shim normal'>&#x16F23;&#x16F6A;&#x16F57;&#x16F8F; </span>
<span class='affects'>U+16F90 MIAO TONE TOP RIGHT</span> | <span class='shim normal'>&#x16F23;&#x16F6A;&#x16F57;&#x16F90; </span>
<span class='affects'>U+16F91 MIAO TONE ABOVE</span> | <span class='shim normal'>&#x16F23;&#x16F6A;&#x16F57;&#x16F91; </span>
<span class='affects'>U+16F92 MIAO TONE BELOW</span> | <span class='shim normal'>&#x16F23;&#x16F6A;&#x16F57;&#x16F92; </span>

However, for Xiaohua Miao / Small Flowery Miao &#x005B;sfm&#x005D; the four tone positions are used right of initial.

USV       | default | sfm variant 
:------------- | :--- | :--- 
<span class='affects'>U+16F90, U+16F8F, U+16F92, none</span> | <span class='shim normal'>&#x16F00;&#x16F6A;&#x16F90; &#x16F00;&#x16F6A;&#x16F8F; &#x16F00;&#x16F6A;&#x16F92; &#x16F00;&#x16F6A;</span> |<span class='sfm normal'>&#x16F00;&#x16F6A;&#x16F90; &#x16F00;&#x16F6A;&#x16F8F; &#x16F00;&#x16F6A;&#x16F92; &#x16F00;&#x16F6A;</span> 

**<a id="lig"></a>Ligatures**

Sinicized Miao &#x005B;hmz&#x005D;, Xiaohua Miao / Small Flowery Miao &#x005B;sfm&#x005D;, and sometimes Large Flowery Miao / Dahua Miao / A-Hmao &#x005B;hmd&#x005D;, puts the aspiration mark (U+16F51) in front of the consonant rather than the default position of after. It is possible other languages would also do this.

Setting        | default | hmz, sfm, hmd
:------------- | :--- | :---
<span class='affects'>U+16F04 U+16F51</span> | <span class='shim normal'>&#x16F04;&#x16F51;</span> | <span class='hmz normal'>&#x16F04;&#x16F51;</span>
<span class='affects'>U+16F10 U+16F51</span> | <span class='shim normal'>&#x16F10;&#x16F51;</span> | <span class='hmz normal'>&#x16F10;&#x16F51;</span>
<span class='affects'>U+16F23 U+16F51</span> | <span class='shim normal'>&#x16F23;&#x16F51;</span> | <span class='hmz normal'>&#x16F23;&#x16F51;</span>

**<a id="kern"></a>Kerning**

In general, aspiration and finals are kerned into the initial. Additionally, finals are usually kerned under aspiration. There are some languages which do not follow this behavior. These are listed in the table below.

Setting        | default | variant | language
:--- | :--- | :--- | :---
<span class='affects'>Final not kerned into initial</span> | <span class='shim normal'>&#x16F19;&#x16F66;&#x16F90; &#x16F32;&#x16F6B;&#x16F8F; &#x16F32;&#x16F6B;&#x16F92; &#x16F07;&#x16F68; &#x16F37;&#x16F6A; &#x16F0A;&#x16F71; &#x16F08;&#x16F7B; &#x16F43;&#x16F61;</span> |<span class='sfm normal'>&#x16F19;&#x16F66;&#x16F90; &#x16F32;&#x16F6B;&#x16F8F; &#x16F32;&#x16F6B;&#x16F92; &#x16F07;&#x16F68; &#x16F37;&#x16F6A; &#x16F0A;&#x16F71; &#x16F08;&#x16F7B; &#x16F43;&#x16F61;</span> | <span class='affects'>hmd normalised, sfm, ygp</span>
<span class='affects'>Final not kerned into aspiration</span> | <span class='shim normal'>&#x16F2E;&#x16F51;&#x16F59; &#x16F20;&#x16F51;&#x16F5F;</span> |<span class='sfm normal'>&#x16F2E;&#x16F51;&#x16F59; &#x16F20;&#x16F51;&#x16F5F;</span> | <span class='affects'>sfm, ygp</span>
<span class='affects'>Aspiration not kerned into initial</span> | <span class='shim normal'>&#x16F16;&#x16F51; &#x16F18;&#x16F51; &#x16F3D;&#x16F51; &#x16F1A;&#x16F51; &#x16F16;&#x16F51; &#x16F18;&#x16F51; &#x16F3D;&#x16F51; &#x16F1A;&#x16F51;</span> |<span class='hmdd normal'>&#x16F16;&#x16F51; &#x16F18;&#x16F51; &#x16F3D;&#x16F51; &#x16F1A;&#x16F51; &#x16F16;&#x16F51; &#x16F18;&#x16F51; &#x16F3D;&#x16F51; &#x16F1A;&#x16F51;</span> | <span class='affects'>hmd normalised</span>
<span class='affects'>Single final at foot position right-aligned with aspiration if enough space</span> | <span class='shim normal'>&#x16F37;&#x16F51;&#x16F6A; &#x16F0A;&#x16F51;&#x16F71;</span> |<span class='yna normal'>&#x16F37;&#x16F51;&#x16F6A; &#x16F0A;&#x16F51;&#x16F71;</span> | <span class='affects'>hmd, yna</span>

**<a id="glyph"></a>Glyph variants**

“wart” vs “dot” variants are listed below this table. 

Setting        | default | variant | language
:------------- | :--- | :--- | :---
<span class='affects'>U+3001</span> | <span class='shim normal'>&#x3001;</span> |<span class='lpo normal'>&#x3001;</span> | <span class='affects'>lpo</span>
<span class='affects'>U+16F02</span> | <span class='shim normal'>&#x16F02;</span> |<span class='ygp normal'>&#x16F02;</span> | <span class='affects'>ygp</span>
<span class='affects'>U+16F04</span> | <span class='shim normal'>&#x16F04;</span> |<span class='hmdd normal'>&#x16F04;</span> | <span class='affects'>hmd normalised</span>
<span class='affects'>U+16F04</span> | <span class='shim normal'>&#x16F04;</span> |<span class='lpo normal'>&#x16F04;</span> | <span class='affects'>lpo</span>
<span class='affects'>U+16F04</span> | <span class='shim normal'>&#x16F04;</span> | <span class='ygp normal'>&#x16F04;</span> | <span class='affects'>ygp, ywq normalized</span>
<span class='affects'>U+16F05</span> | <span class='shim normal'>&#x16F05;</span> |<span class='hmdd normal'>&#x16F05;</span> | <span class='affects'>hmd normalised</span>
<span class='affects'>U+16F10</span> | <span class='shim normal'>&#x16F10;</span> |<span class='hmdd normal'>&#x16F10;</span> | <span class='affects'>hmd normalised</span>
<span class='affects'>U+16F10</span> | <span class='shim normal'>&#x16F10;</span> |<span class='lpo normal'>&#x16F10;</span> | <span class='affects'>lpo</span>
<span class='affects'>U+16F10</span> | <span class='shim normal'>&#x16F10;</span> | <span class='ygp normal'>&#x16F10;</span> | <span class='affects'>ygp, ywq normalized</span>
<span class='affects'>U+16F11</span> | <span class='shim normal'>&#x16F11;</span> |<span class='hmdd normal'>&#x16F11;</span> | <span class='affects'>hmd normalised</span>
<span class='affects'>U+16F14</span> | <span class='shim normal'>&#x16F14;</span> |<span class='hmdd normal'>&#x16F14;</span> | <span class='affects'>hmd normalised</span>
<span class='affects'>U+16F14</span> | <span class='shim normal'>&#x16F14;</span> |<span class='ygp normal'>&#x16F14;</span> | <span class='affects'>ygp</span>
<span class='affects'>U+16F15</span> | <span class='shim normal'>&#x16F15;</span> |<span class='hmdd normal'>&#x16F15;</span> | <span class='affects'>hmd normalised</span>
<span class='affects'>U+16F23</span> | <span class='shim normal'>&#x16F23;</span> |<span class='hmdd normal'>&#x16F23;</span> | <span class='affects'>hmd normalised</span>
<span class='affects'>U+16F23</span> | <span class='shim normal'>&#x16F23;</span> |<span class='lpo normal'>&#x16F23;</span> | <span class='affects'>lpo</span>
<span class='affects'>U+16F23</span> | <span class='shim normal'>&#x16F23;</span> |<span class='ygp normal'>&#x16F23;</span> | <span class='affects'>ygp</span>
<span class='affects'>U+16F24</span> | <span class='shim normal'>&#x16F24;</span> |<span class='hmdd normal'>&#x16F24;</span> | <span class='affects'>hmd normalised</span>
<span class='affects'>U+16F2F</span> | <span class='shim normal'>&#x16F2F;</span> | <span class='ywqa normal'>&#x16F2F;</span> | <span class='affects'>ywq normalized</span>
<span class='affects'>U+16F33</span> | <span class='shim normal'>&#x16F33;</span> |<span class='lpo normal'>&#x16F33;</span> | <span class='affects'>lpo</span>
<span class='affects'>U+16F35</span> | <span class='shim normal'>&#x16F35;</span> | <span class='ywqa normal'>&#x16F35;</span> | <span class='affects'>ywq normalized</span>

_Currently there is a question of whether the default glyph in the codecharts should be the one in the **default** column here. It is the author's belief that this should be changed as most languages use that form._

_There is a request to encode the glyph found in the **variant** column for U+16F35. Although both glyphs represent the same character, this is a significant variant, and that request should at least be considered._

Setting        | default | variant | language
:------------- | :--- | :--- | :---
<span class='affects'>U+16F57</span> | <span class='shim normal'>&#x16F57;</span> | <span class='shim normal'   lang='hmd'>&#x16F57;</span> (flat bottom) | <span class='affects'>hmd traditional, hmd normalized, hmz, lpo</span>
<span class='affects'>U+16F58</span> | <span class='shim normal'>&#x16F58;</span> | <span class='shim normal'   lang='lpo'>&#x16F58;</span> | <span class='affects'>lpo</span>
<span class='affects'>U+16F5C</span> | <span class='shim normal'>&#x16F5C;</span> | <span class='ygp normal'>&#x16F5C;</span> (near-centre stem)| <span class='affects'>ygp</span>
<span class='affects'>U+16F5E</span> | <span class='shim normal'>&#x16F5E;</span> |<span class='hmdd normal'>&#x16F5E;</span> (flat top)| <span class='affects'>hmd normalised</span>
<span class='affects'>U+16F5F</span> | <span class='shim normal'>&#x16F5F;</span> |<span class='hmdd normal'>&#x16F5F;</span> (flat top)| <span class='affects'>hmd normalised</span>
<span class='affects'>U+16F60</span> | <span class='shim normal'>&#x16F60;</span> | <span class='ygp normal'>&#x16F60;</span> (near-centre stem) | <span class='affects'>ygp</span>
<span class='affects'>U+16F73</span> | <span class='shim normal'>&#x16F73;</span> | <span class='ygp normal'>&#x16F73;</span> (near-centre stem) | <span class='affects'>ygp</span>
<span class='affects'>U+16F7A</span> | <span class='shim normal'>&#x16F7A;</span> | <span class='hmd normal'>&#x16F7A;</span> (pointed hook) | <span class='affects'>hmd traditional, hmd normalized, hmz, sfm</span>

**<a id="wart"></a>“wart” vs “dot”**

Some Miao consonants appear in the code charts with a “wart” attached to the glyph, usually on the left-hand side. In the Chuxiong orthography, a dot appears instead of the wart on these consonants. Because the user communities consider the appearance of the wart or dot to be a different way to write the same characters and not a difference of the character’s identity, the differences in appearance are a matter of font style.

<span class='affects'>Affects: U+16F01 U+16F05 U+16F09 U+16F0B U+16F0F U+16F11 U+16F15 U+16F17 U+16F19 U+16F1B U+16F1D U+16F1F U+16F22 U+16F24 U+16F29 U+16F2B U+16F2D U+16F2F U+16F36 U+16F38 U+16F3C U+16F3E U+16F41 U+16F44 U+16F45 U+16F46 U+16F47</span>

Setting         | Sample          
:-------------   | :---------------  
default (wart)  | <span class='shim normal'>&#x16F01; &#x16F05; &#x16F09; &#x16F0B; &#x16F0F; &#x16F11; &#x16F15; &#x16F17; &#x16F19; &#x16F1B; &#x16F1D; &#x16F1F; &#x16F22; &#x16F24; &#x16F29; &#x16F2B; &#x16F2D; &#x16F2F; &#x16F36; &#x16F38; &#x16F3C; &#x16F3E; &#x16F41; &#x16F44; &#x16F45; &#x16F46; &#x16F47;</span> 
alternate (dot) | <span class='hmdd normal'>&#x16F01; &#x16F05; &#x16F09; &#x16F0B; &#x16F0F; &#x16F11; &#x16F15; &#x16F17; &#x16F19; &#x16F1B; &#x16F1D; &#x16F1F; &#x16F22; &#x16F24; &#x16F29; &#x16F2B; &#x16F2D; &#x16F2F; &#x16F36; &#x16F38; &#x16F3C; &#x16F3E; &#x16F41; &#x16F44; &#x16F45; &#x16F46; &#x16F47;</span>

## <a id="lang"></a>Languages currently using Miao/Pollard script

### <a id="hmd"></a>Large Flowery Miao / Dahua Miao / A-Hmao &#x005B;hmd&#x005D;

The Large Flowery Miao / Dahua Miao / A-Hmao language is the primary language that uses the Miao script.

**Resources**

_Language tag:_ `hmd`

_Opentype language system tag:_ `HMD `

_SLDR:_ [hmd](https://github.com/silnrsi/sldr/blob/master/sldr/h/hmd.xml)

_Keyman keyboard:_ [hmd](https://keyman.com/keyboards/sil_hmd_plrd)

_Picker:_ [A-Hmao picker](https://r12a.github.io/pickers/plrd-hmd/index.html)

_Font:_ [Sapushan](https://software.sil.org/shimenkan/) - traditional orthography

_Font:_ [Shimenkan Guifan](https://software.sil.org/shimenkan/) - normalised orthography

_Generic Miao fonts:_ [Noto Miao](https://fonts.google.com/noto/fonts?noto.script=Plrd) and [Miao Unicode](https://github.com/phjamr/MiaoUnicode)

**Character set**

Consonant onsets | | | | | | | | | &#x0020;
:-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :--
<span class='hmd normal'>&#x16F00;</span> | <span class='hmd normal'>&#x16F01;</span> | <span class='hmd normal'>&#x16F04;</span> | <span class='hmd normal'>&#x16F05;</span> | <span class='hmd normal'>&#x16F07;</span> | <span class='hmd normal'>&#x16F08;</span> | <span class='hmd normal'>&#x16F09;</span> | <span class='hmd normal'>&#x16F0A;</span> | <span class='hmd normal'>&#x16F0B;</span> | <span class='hmd normal'>&#x16F0E;</span>     
16F00 | 16F01 | 16F04 | 16F05 | 16F07 | 16F08 | 16F09 | 16F0A | 16F0B | 16F0E
<span class='hmd normal'>&#x16F0F;</span> | <span class='hmd normal'>&#x16F10;</span> | <span class='hmd normal'>&#x16F11;</span> | <span class='hmd normal'>&#x16F14;</span> | <span class='hmd normal'>&#x16F15;</span> | <span class='hmd normal'>&#x16F16;</span> | <span class='hmd normal'>&#x16F17;</span> | <span class='hmd normal'>&#x16F18;</span> | <span class='hmd normal'>&#x16F19;</span> | <span class='hmd normal'>&#x16F1A;</span>
16F0F | 16F10 | 16F11 | 16F14 | 16F15 | 16F16 | 16F17 | 16F18 | 16F19 | 16F1A
<span class='hmd normal'>&#x16F1B;</span> | <span class='hmd normal'>&#x16F1C;</span> | <span class='hmd normal'>&#x16F1D;</span> | <span class='hmd normal'>&#x16F1E;</span> | <span class='hmd normal'>&#x16F1F;</span> | <span class='hmd normal'>&#x16F21;</span> | <span class='hmd normal'>&#x16F22;</span> | <span class='hmd normal'>&#x16F23;</span> | <span class='hmd normal'>&#x16F24;</span> | <span class='hmd normal'>&#x16F26;</span>
16F1B | 16F1C | 16F1D | 16F1E | 16F1F | 16F21 | 16F22 | 16F23 | 16F24 | 16F26
<span class='hmd normal'>&#x16F28;</span> | <span class='hmd normal'>&#x16F29;</span> | <span class='hmd normal'>&#x16F2A;</span> | <span class='hmd normal'>&#x16F2B;</span> | <span class='hmd normal'>&#x16F2C;</span> | <span class='hmd normal'>&#x16F2D;</span> | <span class='hmd normal'>&#x16F2E;</span> | <span class='hmd normal'>&#x16F2F;</span> | <span class='hmd normal'>&#x16F33;</span> | <span class='hmd normal'>&#x16F34;</span>
16F28 | 16F29 | 16F2A | 16F2B | 16F2C | 16F2D | 16F2E | 16F2F | 16F33 | 16F34
<span class='hmd normal'>&#x16F35;</span> | <span class='hmd normal'>&#x16F37;</span> | <span class='hmd normal'>&#x16F38;</span> | <span class='hmd normal'>&#x16F3A;</span> | <span class='hmd normal'>&#x16F3B;</span> | <span class='hmd normal'>&#x16F3C;</span> | <span class='hmd normal'>&#x16F3D;</span> | <span class='hmd normal'>&#x16F3E;</span> | <span class='hmd normal'>&#x16F40;</span> | <span class='hmd normal'>&#x16F41;</span>
16F35 | 16F37 | 16F38 | 16F3A | 16F3B | 16F3C | 16F3D | 16F3E | 16F40 | 16F41
<span class='hmd normal'>&#x16F42;</span> | <span class='hmd normal'>&#x16F43;</span> | <span class='hmd normal'>&#x16F44;</span>
16F42 | 16F43 | 16F44 | | | | |

Modifiers | Nasalization | Aspiration
:-- | :-- | :-- 
&#x0020; | <span class='shim normal'>&#x16F50;</span> | <span class='shim normal'>&#x16F51;</span>
&#x0020; | 16F50 | 16F51

_The keyboard includes U+16F5D_ <span class='hmd normal'>&#x16F5D;</span> _and U+16F74_ <span class='hmd normal'>&#x16F74;</span> _although they are not in Figure 1 [L2/10-093](https://www.unicode.org/L2/L2010/10093-n3789-miao.pdf)._

Vowels and finals | | | | | | | | | &#x0020;
:-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- 
<span class='hmd normal'>&#x16F54;</span> | <span class='hmd normal'>&#x16F57;</span> | <span class='hmd normal'>&#x16F58;</span> | <span class='hmd normal'>&#x16F59;</span> | <span class='hmd normal'>&#x16F5C;</span> | <span class='hmd normal'>&#x16F5E;</span> | <span class='hmd normal'>&#x16F5F;</span> | <span class='hmd normal'>&#x16F60;</span> | <span class='hmd normal'>&#x16F61;</span> | <span class='hmd normal'>&#x16F62;</span> 
16F54 | 16F57 | 16F58 | 16F59 | 16F5C | 16F5E | 16F5F | 16F60 | 16F61 | 16F62
<span class='hmd normal'>&#x16F66;</span> | <span class='hmd normal'>&#x16F68;</span> | <span class='hmd normal'>&#x16F6A;</span> | <span class='hmd normal'>&#x16F6B;</span> | <span class='hmd normal'>&#x16F71;</span> | <span class='hmd normal'>&#x16F73;</span> | <span class='hmd normal'>&#x16F75;</span> | <span class='hmd normal'>&#x16F77;</span> | <span class='hmd normal'>&#x16F79;</span> | <span class='hmd normal'>&#x16F7A;</span>
16F66 | 16F68 | 16F6A | 16F6B | 16F71 | 16F73 | 16F75 | 16F77 | 16F79 | 16F7A 
<span class='hmd normal'>&#x16F7B;</span> | | | | | | | | |
16F7B | | | | | | | | |

Positioning tone marks | &#x0020; |&#x0020;
:-- | :-- | :--
MIAO TONE RIGHT | MIAO TONE TOP RIGHT | MIAO TONE ABOVE
16F8F | 16F90 | 16F91 

_Punctuation_

See also <a href="#punct">Punctuation and Digits</a>.

Additional punctuation: <span class='hmd normal'>: ; ? [ ] _ __</span>

**_Sorting (China, Ireland, and UK. Figure 1)_**

&#x26;<span class='hmd normal'>&#x16F00;</span> &lt; <span class='hmd normal'>&#x16F01;</span> &lt;&lt; <span class='hmd normal'>&#x16F00;&#x16F51;</span> &lt;&lt; <span class='hmd normal'>&#x16F50;&#x16F00;</span> &lt;&lt; <span class='hmd normal'>&#x16F50;&#x16F01;</span> &lt;&lt; <span class='hmd normal'>&#x16F50;&#x16F00;&#x16F51;</span> <br/>
&#x26;<span class='hmd normal'>&#x16F0A;</span> &lt; <span class='hmd normal'>&#x16F0B;</span> &lt;&lt; <span class='hmd normal'>&#x16F0A;&#x16F51;</span> &lt;&lt; <span class='hmd normal'>&#x16F50;&#x16F0A;</span> &lt;&lt; <span class='hmd normal'>&#x16F50;&#x16F0B;</span> &lt;&lt; <span class='hmd normal'>&#x16F50;&#x16F0A;&#x16F51;</span><br/>
&#x26;<span class='hmd normal'>&#x16F1E;</span> &lt; <span class='hmd normal'>&#x16F1F;</span> &lt;&lt; <span class='hmd normal'>&#x16F1E;&#x16F51;</span> &lt;&lt; <span class='hmd normal'>&#x16F50;&#x16F1E;</span> &lt;&lt; <span class='hmd normal'>&#x16F50;&#x16F1F;</span> &lt;&lt; <span class='hmd normal'>&#x16F50;&#x16F1E;&#x16F51;</span><br/>
&#x26;<span class='hmd normal'>&#x16F2E;</span> &lt; <span class='hmd normal'>&#x16F2F;</span> &lt;&lt; <span class='hmd normal'>&#x16F2E;&#x16F51;</span> &lt;&lt; <span class='hmd normal'>&#x16F50;&#x16F2E;</span> &lt;&lt; <span class='hmd normal'>&#x16F50;&#x16F2F;</span> &lt;&lt; <span class='hmd normal'>&#x16F50;&#x16F2E;&#x16F51;</span><br/>
&#x26;<span class='hmd normal'>&#x16F2A;</span> &lt; <span class='hmd normal'>&#x16F2B;</span> &lt;&lt; <span class='hmd normal'>&#x16F2A;&#x16F51;</span> &lt;&lt; <span class='hmd normal'>&#x16F50;&#x16F2A;</span> &lt;&lt; <span class='hmd normal'>&#x16F50;&#x16F2B;</span> &lt;&lt; <span class='hmd normal'>&#x16F50;&#x16F2A;&#x16F51;</span><br/>
&#x26;<span class='hmd normal'>&#x16F1A;</span> &lt; <span class='hmd normal'>&#x16F1B;</span> &lt;&lt; <span class='hmd normal'>&#x16F1A;&#x16F51;</span> &lt;&lt; <span class='hmd normal'>&#x16F50;&#x16F1A;</span> &lt;&lt; <span class='hmd normal'>&#x16F50;&#x16F1B;</span> &lt;&lt; <span class='hmd normal'>&#x16F50;&#x16F1A;&#x16F51;</span><br/>
&#x26;<span class='hmd normal'>&#x16F1C;</span> &lt; <span class='hmd normal'>&#x16F1D;</span> &lt;&lt; <span class='hmd normal'>&#x16F1C;&#x16F51;</span> &lt;&lt; <span class='hmd normal'>&#x16F50;&#x16F1C;</span> &lt;&lt; <span class='hmd normal'>&#x16F50;&#x16F1D;</span> &lt;&lt; <span class='hmd normal'>&#x16F50;&#x16F1C;&#x16F51;</span><br/>
&#x26;<span class='hmd normal'>&#x16F37;</span> &lt; <span class='hmd normal'>&#x16F38;</span> &lt;&lt; <span class='hmd normal'>&#x16F37;&#x16F51;</span> &lt;&lt; <span class='hmd normal'>&#x16F50;&#x16F37;</span> &lt;&lt; <span class='hmd normal'>&#x16F50;&#x16F38;</span> &lt;&lt; <span class='hmd normal'>&#x16F50;&#x16F37;&#x16F51;</span><br/>
&#x26;<span class='hmd normal'>&#x16F0E;</span> &lt; <span class='hmd normal'>&#x16F0F;</span> &lt;&lt; <span class='hmd normal'>&#x16F0E;&#x16F51;</span> &lt;&lt; <span class='hmd normal'>&#x16F50;&#x16F0E;</span> &lt;&lt; <span class='hmd normal'>&#x16F50;&#x16F0F;</span> &lt;&lt; <span class='hmd normal'>&#x16F50;&#x16F0E;&#x16F51;</span><br/>
&#x26;<span class='hmd normal'>&#x16F21;</span> &lt; <span class='hmd normal'>&#x16F22;</span> &lt;&lt; <span class='hmd normal'>&#x16F21;&#x16F51;</span> &lt;&lt; <span class='hmd normal'>&#x16F50;&#x16F21;</span> &lt;&lt; <span class='hmd normal'>&#x16F50;&#x16F22;</span> &lt;&lt; <span class='hmd normal'>&#x16F50;&#x16F21;&#x16F51;</span><br/>
&#x26;<span class='hmd normal'>&#x16F43;</span> &lt; <span class='hmd normal'>&#x16F44;</span> &lt;&lt; <span class='hmd normal'>&#x16F43;&#x16F51;</span> &lt;&lt; <span class='hmd normal'>&#x16F50;&#x16F43;</span> &lt;&lt; <span class='hmd normal'>&#x16F50;&#x16F44;</span> &lt;&lt; <span class='hmd normal'>&#x16F50;&#x16F43;&#x16F51;</span><br/>
&#x26;<span class='hmd normal'>&#x16F08;</span> &lt; <span class='hmd normal'>&#x16F09;</span> &lt;&lt; <span class='hmd normal'>&#x16F08;&#x16F51;</span><br/>
&#x26;<span class='hmd normal'>&#x16F3D;</span> &lt; <span class='hmd normal'>&#x16F3E;</span> &lt;&lt; <span class='hmd normal'>&#x16F3D;&#x16F51;</span><br/>
&#x26;<span class='hmd normal'>&#x16F40;</span> &lt; <span class='hmd normal'>&#x16F41;</span> &lt;&lt; <span class='hmd normal'>&#x16F40;&#x16F51;</span><br/>
&#x26;<span class='hmd normal'>&#x16F16;</span> &lt; <span class='hmd normal'>&#x16F17;</span> &lt;&lt; <span class='hmd normal'>&#x16F16;&#x16F51;</span><br/>
&#x26;<span class='hmd normal'>&#x16F18;</span> &lt; <span class='hmd normal'>&#x16F19;</span> &lt;&lt; <span class='hmd normal'>&#x16F18;&#x16F51;</span><br/>
&#x26;<span class='hmd normal'>&#x16F04;</span> &lt; <span class='hmd normal'>&#x16F05;</span> &lt;&lt; <span class='hmd normal'>&#x16F04;&#x16F51;</span><br/>
&#x26;<span class='hmd normal'>&#x16F10;</span> &lt; <span class='hmd normal'>&#x16F11;</span> &lt;&lt; <span class='hmd normal'>&#x16F10;&#x16F51;</span><br/>
&#x26;<span class='hmd normal'>&#x16F3B;</span> &lt; <span class='hmd normal'>&#x16F3C;</span> &lt;&lt; <span class='hmd normal'>&#x16F3B;&#x16F51;</span><br/>
&#x26;<span class='hmd normal'>&#x16F2C;</span> &lt; <span class='hmd normal'>&#x16F2D;</span> &lt;&lt; <span class='hmd normal'>&#x16F2C;&#x16F51;</span><br/>
&#x26;<span class='hmd normal'>&#x16F14;</span> &lt; <span class='hmd normal'>&#x16F15;</span> &lt;&lt; <span class='hmd normal'>&#x16F14;&#x16F51;</span><br/>
&#x26;<span class='hmd normal'>&#x16F23;</span> &lt; <span class='hmd normal'>&#x16F24;</span> &lt;&lt; <span class='hmd normal'>&#x16F23;&#x16F51;</span><br/>
&#x26;<span class='hmd normal'>&#x16F28;</span> &lt; <span class='hmd normal'>&#x16F29;</span> &lt;&lt; <span class='hmd normal'>&#x16F28;&#x16F51;</span><br/>
&#x26;<span class='hmd normal'>&#x16F33;</span> &lt; <span class='hmd normal'>&#x16F34;</span> &lt; <span class='hmd normal'>&#x16F3A;</span> &lt; <span class='hmd normal'>&#x16F07;</span> &lt; <span class='hmd normal'>&#x16F26;</span> &lt; <span class='hmd normal'>&#x16F35;</span> &lt; <span class='hmd normal'>&#x16F42;</span></br>
&#x26;<span class='hmd normal'>&#x16F54;</span> &lt; <span class='hmd normal'>&#x16F59;</span> &lt; <span class='hmd normal'>&#x16F73;</span> &lt; <span class='hmd normal'>&#x16F61;</span> &lt; <span class='hmd normal'>&#x16F6A;</span> &lt; <span class='hmd normal'>&#x16F71;</span> &lt; <span class='hmd normal'>&#x16F79;</span> &lt; <span class='hmd normal'>&#x16F7A;</span> &lt; <span class='hmd normal'>&#x16F7B;</span> &lt; <span class='hmd normal'>&#x16F60;</span> &lt; <span class='hmd normal'>&#x16F5C;</span> &lt; <span class='hmd normal'>&#x16F57;</span> &lt; <span class='hmd normal'>&#x16F58;</span> &lt; <span class='hmd normal'>&#x16F66;</span> &lt; <span class='hmd normal'>&#x16F68;</span> &lt; <span class='hmd normal'>&#x16F75;</span> &lt; <span class='hmd normal'>&#x16F77;</span> &lt; <span class='hmd normal'>&#x16F62;</span> &lt; <span class='hmd normal'>&#x16F6B;</span> &lt; <span class='hmd normal'>&#x16F5E;</span> &lt; <span class='hmd normal'>&#x16F5F; </span>

**Rendering**

See also <a href="#wart">“wart” vs “dot”</a> for special behavior. The traditional orthography uses the “wart” and the normalised orthography uses the “dot”.

See also <a href="#kern">Kerning</a> for special behavior.

See also <a href="#lig">Ligatures</a> for special behavior.

_Glyph variants_

Setting        | Sample
:------------- | :--------------- 
default        | <span class='shim normal'>&#x16F04; &#x16F05; &#x16F10; &#x16F11; &#x16F14; &#x16F15; &#x16F23; &#x16F24; &#x16F57; &#x16F5E; &#x16F5F; &#x16F7A;</span> |
hmd alternates  | <span class='hmd normal'>&#x16F04; &#x16F05; &#x16F10; &#x16F11; &#x16F14; &#x16F15; &#x16F23; &#x16F24; &#x16F57; &#x16F5E; &#x16F5F; &#x16F7A;</span>
normalized orthography alternates      | <span class='hmdd normal'>&#x16F04; &#x16F05; &#x16F10; &#x16F11; &#x16F14; &#x16F15; &#x16F23; &#x16F24; &#x16F57; &#x16F5E; &#x16F5F; &#x16F7A;</span>

_Sample graphic_

<img src="assets/images/hmd_MiaoHwa_861.png" title="fig:" style="width:80%;height:80%;" alt="Miao: Hwa sample" />
<figcaption>Mark 1:1-4 (UBS).</figcaption>

### <a id="hmz"></a>Sinicized Miao / Waishu Miao / Hmong Shua &#x005B;hmz&#x005D;

_Language tag:_ `hmz-Plrd`

_Opentype language system tag:_ `HMZ `

_SLDR:_ none

_Keyboard:_ none

_Font:_ [Shimenkan MGS](https://software.sil.org/shimenkan/)

**Character set**

Unknown

**Rendering**

See also <a href="#lig">Ligatures</a> for special behavior.

_Glyph variants_

Setting        | Sample
:------- | :--------------- 
default        | <span class='shim normal'>&#x16F57; &#x16F7A;</span> 
alternate      | <span class='hmz normal'>&#x16F57; &#x16F7A;</span>

### <a id="lpo"></a>Lipo / Dong Lisu / Eastern Lisu &#x005B;lpo&#x005D;

_Language tag:_ `lpo`

_Opentype language system tag:_ `LPO `

_SLDR:_ [lpo](https://github.com/silnrsi/sldr/blob/master/sldr/l/lpo.xml)

_Keyman keyboard:_ [lpo](https://keyman.com/keyboards/sil_lpo_plrd)

_Font:_ [Taogu](https://software.sil.org/shimenkan/)

**Character set**

Consonant onsets | | | | | | | | | &#x0020;
:-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :--
<span class='lpo normal'>&#x16F00;</span> | <span class='lpo normal'>&#x16F02;</span> | <span class='lpo normal'>&#x16F04;</span> | <span class='lpo normal'>&#x16F07;</span> | <span class='lpo normal'>&#x16F08;</span> | <span class='lpo normal'>&#x16F0A;</span> | <span class='lpo normal'>&#x16F0D;</span> | <span class='lpo normal'>&#x16F0E;</span> | <span class='lpo normal'>&#x16F10;</span> | <span class='lpo normal'>&#x16F13;</span> 
16F00 | 16F02 | 16F04 | 16F07 | 16F08 | 16F0A | 16F0D | 16F0E | 16F10 | 16F13
<span class='lpo normal'>&#x16F16;</span> | <span class='lpo normal'>&#x16F18;</span> | <span class='lpo normal'>&#x16F1E;</span> | <span class='lpo normal'>&#x16F21;</span> | <span class='lpo normal'>&#x16F23;</span> | <span class='lpo normal'>&#x16F26;</span> | <span class='lpo normal'>&#x16F28;</span> | <span class='lpo normal'>&#x16F2F;</span> | <span class='lpo normal'>&#x16F30;</span> | <span class='lpo normal'>&#x16F33;</span>
16F16 | 16F18 | 16F1E | 16F21 | 16F23 | 16F26 | 16F28 | 16F2F | 16F30 | 16F33
<span class='lpo normal'>&#x16F35;</span> | <span class='lpo normal'>&#x16F37;</span> | <span class='lpo normal'>&#x16F39;</span> | <span class='lpo normal'>&#x16F3A;</span> | <span class='lpo normal'>&#x16F3B;</span> | <span class='lpo normal'>&#x16F3D;</span> | <span class='lpo normal'>&#x16F43;</span> |
16F35 | 16F37 | 16F39 | 16F3A | 16F3B | 16F3D | 16F43 | 

Modifiers | Aspiration
:-- | :--  
&#x0020; | <span class='hmd normal'>&#x16F51;</span>
&#x0020; | 16F51

Vowels and finals | | | | | | | | |&#x0020;
:-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- 
<span class='lpo normal'>&#x16F54;</span> | <span class='lpo normal'>&#x16F55;</span> | <span class='lpo normal'>&#x16F57;</span>| <span class='lpo normal'>&#x16F58;</span>| <span class='lpo normal'>&#x16F59;</span> | <span class='lpo normal'>&#x16F5A;</span> | <span class='lpo normal'>&#x16F5C;</span> | <span class='lpo normal'>&#x16F5D;</span> | <span class='lpo normal'>&#x16F61;</span> | <span class='lpo normal'>&#x16F62;</span> 
16F54 | 16F55 | 16F57 | 16F58 | 16F59 | 16F5A | 16F5C | 16F5D | 16F61 | 16F62  
<span class='lpo normal'>&#x16F67;</span> | <span class='lpo normal'>&#x16F68;</span> | <span class='lpo normal'>&#x16F6A;</span> | <span class='lpo normal'>&#x16F6B;</span> | <span class='lpo normal'>&#x16F6E;</span> | <span class='lpo normal'>&#x16F71;</span> | <span class='lpo normal'>&#x16F73;</span> | <span class='lpo normal'>&#x16F74;</span> | <span class='lpo normal'>&#x16F76;</span> | <span class='lpo normal'>&#x16F78;</span> 
16F67 | 16F68 | 16F6A | 16F6B | 16F6E | 16F71 | 16F73 | 16F74 | 16F76 | 16F78
<span class='lpo normal'>&#x16F79;</span> | <span class='lpo normal'>&#x16F7A;</span> | <span class='lpo normal'>&#x16F7B;</span> | <span class='lpo normal'>&#x16F7C;</span> | <span class='lpo normal'>&#x16F7E;</span> |
16F79 | 16F7A | 16F7B | 16F7C | 16F7E | 

Positioning tone marks |&#x0020;
:-- | :-- 
MIAO TONE TOP RIGHT | MIAO TONE ABOVE 
16F90 | 16F91 

_Punctuation_

See also <a href="#punct">Punctuation and Digits</a>.

Additional punctuation: <span class='lpo normal'>' - : ; = ?</span>

<span class='lpo normal'>&#x3001;</span> (U+3001 IDEOGRAPHIC COMMA)

**Rendering**

_Glyph variants_

Setting        | Sample
:------ | :---------------
default        | <span class='shim normal'>&#x16F04; &#x16F10; &#x16F23; &#x16F33; &#x16F57; &#x16F58; &#x3001;</span>
alternate      | <span class='lpo normal'>&#x16F04; &#x16F10; &#x16F23; &#x16F33; &#x16F57; &#x16F58; &#x3001;</span>


_Sample graphic_

<img src="assets/images/lpo_LisuEastern_735.png" title="fig:" style="width:80%;height:80%;" alt="Lisu: Eastern sample" />
<figcaption>Mark 1:1-4 (UBS).</figcaption>


### <a id="ygp"></a>Bai Yi / Gepo &#x005B;ygp&#x005D;

_Language tag:_ `ygp`

_Opentype language system tag:_ `YGP `

_SLDR:_ none

_Keyman keyboard:_ [ygp](https://keyman.com/keyboards/sil_ygp_plrd)

_Font:_ [Shimenkan GSM](https://software.sil.org/shimenkan/)

**Character set**

_The keyboard includes U+16F0B_ <span class='ygp normal'>&#x16F0B;</span>_, U+16F0F_ <span class='ygp normal'>&#x16F0F;</span>_, U+16F2F_ <span class='ygp normal'>&#x16F2F;</span>_, and U+16F38_ <span class='ygp normal'>&#x16F38;</span> _although they are not in Figure 2 [L2/17-345](https://www.unicode.org/L2/L2017/17345-n4845-miao-add.pdf). These are warted characters, and it may make sense to include them._

Consonant onsets | | | | | | | | |&#x0020;
:-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :--
<span class='ygp normal'>&#x16F00; | <span class='ygp normal'>&#x16F02; | <span class='ygp normal'>&#x16F04; | <span class='ygp normal'>&#x16F07; | <span class='ygp normal'>&#x16F08; | <span class='ygp normal'>&#x16F0A; | <span class='ygp normal'>&#x16F0E; | <span class='ygp normal'>&#x16F10; | <span class='ygp normal'>&#x16F12; | <span class='ygp normal'>&#x16F14;  
16F00 | 16F02 | 16F04 | 16F07 | 16F08 | 16F0A | 16F0E | 16F10 | 16F12 | 16F14
<span class='ygp normal'>&#x16F16; | <span class='ygp normal'>&#x16F18; | <span class='ygp normal'>&#x16F1E; | <span class='ygp normal'>&#x16F23; | <span class='ygp normal'>&#x16F26; | <span class='ygp normal'>&#x16F28; | <span class='ygp normal'>&#x16F2A; | <span class='ygp normal'>&#x16F2E; | <span class='ygp normal'>&#x16F32; | <span class='ygp normal'>&#x16F33;
16F16 | 16F18 | 16F1E | 16F23 | 16F26 | 16F28 | 16F2A | 16F2E | 16F32 | 16F33
<span class='ygp normal'>&#x16F35; | <span class='ygp normal'>&#x16F37; | <span class='ygp normal'>&#x16F3A; | <span class='ygp normal'>&#x16F3B; | <span class='ygp normal'>&#x16F3D; | <span class='ygp normal'>&#x16F42; | <span class='ygp normal'>&#x16F43; | <span class='ygp normal'>&#x16F48; | <span class='ygp normal'>&#x16F49; | <span class='ygp normal'>&#x16F4A;
16F35 | 16F37 | 16F3A | 16F3B | 16F3D | 16F42 | 16F43 | 16F48 | 16F49 | 16F4A 

Modifiers | Nasalization | Aspiration
:-- | :-- | :-- 
&#x0020; | <span class='shim normal'>&#x16F50;</span> | <span class='shim normal'>&#x16F51;</span>
&#x0020; | 16F50 | 16F51

_The keyboard includes U+16F5B_ <span class='ygp normal'>&#x16F5B;</span>_, U+16F5E_ <span class='ygp normal'>&#x16F5E;</span>_, U+16F5F_ <span class='ygp normal'>&#x16F5F;</span>_, U+16F62_ <span class='ygp normal'>&#x16F62;</span>_, and U+16F63_ <span class='ygp normal'>&#x16F63;</span> _although they are not in Figure 2 [L2/17-345](https://www.unicode.org/L2/L2017/17345-n4845-miao-add.pdf)._

Vowels and finals | | | | | | | | |&#x0020;
:-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- 
<span class='ygp normal'>&#x16F54;</span> | <span class='ygp normal'>&#x16F57;</span> | <span class='ygp normal'>&#x16F58;</span> | <span class='ygp normal'>&#x16F59;</span> | <span class='ygp normal'>&#x16F5C;</span> | <span class='ygp normal'>&#x16F5D;</span> | <span class='ygp normal'>&#x16F60;</span> | <span class='ygp normal'>&#x16F61;</span> | <span class='ygp normal'>&#x16F66;</span> 
16F54 | 16F57 | 16F58 | 16F59 | 16F5C | 16F5D | 16F60 | 16F61 | 16F66
<span class='ygp normal'>&#x16F68;</span> | <span class='ygp normal'>&#x16F6A;</span> | <span class='ygp normal'>&#x16F71;</span> | <span class='ygp normal'>&#x16F73;</span> | <span class='ygp normal'>&#x16F75;</span> | <span class='ygp normal'>&#x16F76;</span> | <span class='ygp normal'>&#x16F77;</span> | <span class='ygp normal'>&#x16F79;</span> | <span class='ygp normal'>&#x16F7A;</span>
16F68 | 16F6A | 16F71 | 16F73 | 16F75 | 16F76 | 16F77 | 16F79 | 16F7A
<span class='ygp normal'>&#x16F7B;</span> | <span class='ygp normal'>&#x16F7E;</span> | <span class='ygp normal'>&#x16F81;</span> | <span class='ygp normal'>&#x16F83;</span> | <span class='ygp normal'>&#x16F84;</span> | <span class='ygp normal'>&#x16F85;</span> | <span class='ygp normal'>&#x16F86;</span> | <span class='ygp normal'>&#x16F87;</span>
16F7B | 16F7E | 16F81 | 16F83 | 16F84 | 16F85 | 16F86 | 16F87 

Positioning tone marks | |&#x0020;
:-- | :-- | :-- 
MIAO TONE RIGHT | MIAO TONE TOP RIGHT | MIAO TONE ABOVE 
16F8F | 16F90 | 16F91 

_Punctuation_

See also <a href="#punct">Punctuation and Digits</a>.

Additional punctuation: <span class='lpo normal'>' ; : - *</span>


**_Sorting ([Cheuk](https://www.unicode.org/L2/L2017/17345-n4845-miao-add.pdf), figure 2)_**

&#x26;<span class='ygp normal'>&#x16F43;</span> &lt; <span class='ygp normal'>&#x16F16;</span></br>
&#x26;<span class='ygp normal'>&#x16F00;</span> &lt;&lt; <span class='ygp normal'>&#x16F00;&#x16F51;</span> &lt;&lt; <span class='ygp normal'>&#x16F50;&#x16F00;</span></br>
&#x26;<span class='ygp normal'>&#x16F02;</span> &lt; <span class='ygp normal'>&#x16F48;</span></br>
&#x26;<span class='ygp normal'>&#x16F0A;</span> &lt;&lt; <span class='ygp normal'>&#x16F0A;&#x16F51;</span> &lt;&lt; <span class='ygp normal'>&#x16F50;&#x16F0A;</span></br>
&#x26;<span class='ygp normal'>&#x16F49;</span></br>
&#x26;<span class='ygp normal'>&#x16F37;</span> &lt;&lt; <span class='ygp normal'>&#x16F37;&#x16F51;</span> &lt;&lt; <span class='ygp normal'>&#x16F50;&#x16F37;</span></br>
&#x26;<span class='ygp normal'>&#x16F07;</span> &lt; <span class='ygp normal'>&#x16F18;</span> &lt; <span class='ygp normal'>&#x16F32;</span></br>
&#x26;<span class='ygp normal'>&#x16F2E;</span> &lt;&lt; <span class='ygp normal'>&#x16F2E;&#x16F51;</span> &lt;&lt; <span class='ygp normal'>&#x16F50;&#x16F2E;</span></br>
&#x26;<span class='ygp normal'>&#x16F2A;</span></br>
&#x26;<span class='ygp normal'>&#x16F1E;</span> &lt;&lt; <span class='ygp normal'>&#x16F1E;&#x16F51;</span> &lt;&lt; <span class='ygp normal'>&#x16F50;&#x16F1E;</span></br>
&#x26;<span class='ygp normal'>&#x16F4A;</span></br>
&#x26;<span class='ygp normal'>&#x16F0E;</span> &lt;&lt; <span class='ygp normal'>&#x16F0E;&#x16F51;</span> &lt;&lt; <span class='ygp normal'>&#x16F50;&#x16F0E;</span></br>
&#x26;<span class='ygp normal'>&#x16F08;</span> &lt; <span class='ygp normal'>&#x16F3D;</span> &lt; <span class='ygp normal'>&#x16F42;</span> &lt; <span class='ygp normal'>&#x16F04;</span> &lt; <span class='ygp normal'>&#x16F10;</span> &lt; <span class='ygp normal'>&#x16F14;</span> &lt; <span class='ygp normal'>&#x16F12;</span> &lt; <span class='ygp normal'>&#x16F3B;</span> &lt; <span class='ygp normal'>&#x16F3A;</span> &lt; <span class='ygp normal'>&#x16F33;</span></br>
&#x26;<span class='ygp normal'>&#x16F26;</span> &lt;&lt; <span class='ygp normal'>&#x16F26;&#x16F51;</span></br>
&#x26;<span class='ygp normal'>&#x16F28;</span> &lt; <span class='ygp normal'>&#x16F23;</span> &lt; <span class='ygp normal'>&#x16F35;</span>
&#x26;<span class='ygp normal'>&#x16F54;</span> &lt; <span class='ygp normal'>&#x16F7A;</span></br>
&#x26;<span class='ygp normal'>&#x16F61;</span> &lt;&lt; <span class='ygp normal'>&#x16F61;&#x16F54;</span> &lt;&lt; <span class='ygp normal'>&#x16F61;&#x16F7A;</span> &lt;&lt; <span class='ygp normal'>&#x16F61;&#x16F79;</span> &lt;&lt; <span class='ygp normal'>&#x16F61;&#x16F59;</span> &lt;&lt; <span class='ygp normal'>&#x16F61;&#x16F7B;</span> &lt;&lt; <span class='ygp normal'>&#x16F61;&#x16F66;</span> &lt;&lt; <span class='ygp normal'>&#x16F61;&#x16F57;</span> &lt;&lt; <span class='ygp normal'>&#x16F61;&#x16F58;</span> &lt;&lt; <span class='ygp normal'>&#x16F61;&#x16F7E; </span></br>
&#x26;<span class='ygp normal'>&#x16F79; </span></br>
&#x26;<span class='ygp normal'>&#x16F59;</span> &lt;&lt; <span class='ygp normal'>&#x16F59;&#x16F7E;</span></br>
&#x26;<span class='ygp normal'>&#x16F6A;</span> &lt;&lt; <span class='ygp normal'>&#x16F6A;&#x16F54;</span> &lt;&lt; <span class='ygp normal'>&#x16F6A;&#x16F7A;</span> &lt;&lt; <span class='ygp normal'>&#x16F6A;&#x16F79;</span> &lt;&lt; <span class='ygp normal'>&#x16F6A;&#x16F59;</span> &lt;&lt; <span class='ygp normal'>&#x16F6A;&#x16F7B;</span> &lt;&lt; <span class='ygp normal'>&#x16F6A;&#x16F66;</span> &lt;&lt; <span class='ygp normal'>&#x16F6A;&#x16F57;</span> &lt;&lt; <span class='ygp normal'>&#x16F6A;&#x16F58;</span> &lt;&lt; <span class='ygp normal'>&#x16F6A;&#x16F7E; </span></br>
&#x26;<span class='ygp normal'>&#x16F71;</span> &lt; <span class='ygp normal'>&#x16F5D;</span></br>
&#x26;<span class='ygp normal'>&#x16F5C;</span> &lt;&lt; <span class='ygp normal'>&#x16F5C;&#x16F5D;</span></br>
&#x26;<span class='ygp normal'>&#x16F73;</span> &lt; <span class='ygp normal'>&#x16F60;</span> &lt; <span class='ygp normal'>&#x16F86;</span> &lt; <span class='ygp normal'>&#x16F85;</span> &lt; <span class='ygp normal'>&#x16F76;</span> &lt; <span class='ygp normal'>&#x16F7B;</span> &lt; <span class='ygp normal'>&#x16F66;</span> &lt; <span class='ygp normal'>&#x16F84;</span> &lt; <span class='ygp normal'>&#x16F83;</span> &lt; <span class='ygp normal'>&#x16F77;</span> &lt; <span class='ygp normal'>&#x16F75;</span> &lt; <span class='ygp normal'>&#x16F81;</span> &lt; <span class='ygp normal'>&#x16F57;</span> &lt; <span class='ygp normal'>&#x16F58;</span> &lt; <span class='ygp normal'>&#x16F68;</span> &lt; <span class='ygp normal'>&#x16F87;</span>

**Rendering**

See also <a href="#kern">Kerning</a> for special behavior.

_Glyph variants_

Setting        | Sample
:------ | :---------------
default        | <span class='shim normal'>&#x16F02; &#x16F04; &#x16F10; &#x16F14; &#x16F23; &#x16F5C; &#x16F60; &#x16F73;</span>
alternate      | <span class='ygp normal'>&#x16F02; &#x16F04; &#x16F10; &#x16F14; &#x16F23; &#x16F5C; &#x16F60; &#x16F73;</span>

_Sample text taken from Figure 1 of [Cheuk](https://www.unicode.org/L2/L2017/17345-n4845-miao-add.pdf)._

Setting        | Sample           | USV
:-- | :-- | :---------
ygp | <span class='ygp normal'>&#x16F48;&#x16F66;&#x16F90; &#x16F2A;&#x16F5C;&#x16F91; &#x16F48;&#x16F85; &#x16F2E;&#x16F51;&#x16F5C;&#x16F91; &#x16F32;&#x16F61;&#x16F7B;&#x16F90;</span> | U+16F48 U+16F66 U+16F90 U+0020 U+16F2A U+16F5C U+16F91 U+0020 U+16F48 U+16F85 U+0020 U+16F2E U+16F51 U+16F5C U+16F91 U+0020 U+16F32 U+16F61 U+16F7B U+16F90

_Sample graphic_

<img src="assets/images/ygp_Kopu_674.png" title="fig:" style="width:80%;height:80%;" alt="Kopu sample" />
<figcaption>Mark 1:1-4 (UBS).</figcaption>

### <a id="ywq"></a>Hei Yi / Wuding-Luquan Yi / Nasu &#x005B;ywq&#x005D;

**Resources**

_Language tag:_ `ywq`

_Opentype language system tag:_ `YWQ `

_SLDR:_ none

_Keyman keyboard:_ [ywq](https://keyman.com/keyboards/sil_ywq_plrd)

_Font:_ [Salaowu](https://software.sil.org/shimenkan/) - normalised orthography

**Character set**

_The keyboard includes U+16F05_ <span class='shim normal'>&#x16F05;</span>_, U+16F13_ <span class='shim normal'>&#x16F13;</span>_, U+16F1A_ <span class='shim normal'>&#x16F1A;</span>_,U+16F1C_ <span class='shim normal'>&#x16F1C;</span>_, U+16F2A_ <span class='shim normal'>&#x16F2A;</span>_, and U+16F2D_ <span class='shim normal'>&#x16F2D;</span> _although they are not in Figure 5 [L2/17-345](https://www.unicode.org/L2/L2017/17345-n4845-miao-add.pdf)._

Consonant onsets | | | | | | | | |&#x0020;
:-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :--
<span class='shim normal'>&#x16F00;</span> | <span class='shim normal'>&#x16F02;</span> | <span class='shim normal'>&#x16F04;</span> | <span class='shim normal'>&#x16F07;</span> | <span class='shim normal'>&#x16F08;</span> | <span class='shim normal'>&#x16F0A;</span> | <span class='shim normal'>&#x16F0C;</span> | <span class='shim normal'>&#x16F0D;</span> | <span class='shim normal'>&#x16F0E;</span> | <span class='shim normal'>&#x16F10;</span>
16F00 | 16F02 | 16F04 | 16F07 | 16F08 | 16F0A | 16F0C | 16F0D | 16F0E | 16F10
<span class='shim normal'>&#x16F12;</span> | <span class='shim normal'>&#x16F14;</span> | <span class='shim normal'>&#x16F16;</span> | <span class='shim normal'>&#x16F18;</span> | <span class='shim normal'>&#x16F1E;</span> | <span class='shim normal'>&#x16F21;</span> | <span class='shim normal'>&#x16F23;</span> | <span class='shim normal'>&#x16F26;</span> | <span class='shim normal'>&#x16F28;</span> | <span class='shim normal'>&#x16F2E;</span>
16F12 | 16F14 | 16F16 | 16F18 | 16F1E | 16F21 | 16F23 | 16F26 | 16F28 | 16F2E
<span class='shim normal'>&#x16F2F;</span> | <span class='shim normal'>&#x16F30;</span> | <span class='shim normal'>&#x16F31;</span> | <span class='shim normal'>&#x16F33;</span> | <span class='shim normal'>&#x16F34;</span> | <span class='shim normal'>&#x16F35;</span> | <span class='shim normal'>&#x16F37;</span> | <span class='shim normal'>&#x16F39;</span> | <span class='shim normal'>&#x16F3A;</span> | <span class='shim normal'>&#x16F3B;</span>
16F2F | 16F30 | 16F31 | 16F33 | 16F34 | 16F35 | 16F37 | 16F39 | 16F3A | 16F3B
<span class='shim normal'>&#x16F3D;</span> | <span class='shim normal'>&#x16F42;</span> | <span class='shim normal'>&#x16F43;</span>
16F3D | 16F42 | 16F43

Modifiers | Nasalization | Aspiration
:-- | :-- | :-- 
&#x0020; | <span class='shim normal'>&#x16F50;</span> | <span class='shim normal'>&#x16F51;</span>
&#x0020; | 16F50 | 16F51

_The keyboard includes U+16F57_ <span class='shim normal'>&#x16F57;</span>_, U+16F5F_ <span class='shim normal'>&#x16F5F;</span>_, and U+16F7E_ <span class='shim normal'>&#x16F7E;</span> _although they are not in Figure 5 [L2/17-345](https://www.unicode.org/L2/L2017/17345-n4845-miao-add.pdf)._

Vowels and finals | | | | | | | | |&#x0020;
:-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- 
<span class='shim normal'>&#x16F54;</span> | <span class='shim normal'>&#x16F58;</span> | <span class='shim normal'>&#x16F59;</span> | <span class='shim normal'>&#x16F5B;</span> | <span class='shim normal'>&#x16F5C;</span> | <span class='shim normal'>&#x16F5D;</span> | <span class='shim normal'>&#x16F61;</span> | <span class='shim normal'>&#x16F62;</span> | <span class='shim normal'>&#x16F66;</span> | <span class='shim normal'>&#x16F68;</span>  
16F54 | 16F58 | 16F59 | 16F5B | 16F5C | 16F5D | 16F61 | 16F62 | 16F66 | 16F68
<span class='shim normal'>&#x16F6A;</span> | <span class='shim normal'>&#x16F6B;</span> | <span class='shim normal'>&#x16F6E;</span> | <span class='shim normal'>&#x16F71;</span> | <span class='shim normal'>&#x16F73;</span> | <span class='shim normal'>&#x16F76;</span> | <span class='shim normal'>&#x16F78;</span> | <span class='shim normal'>&#x16F79;</span> | <span class='shim normal'>&#x16F7A;</span> | <span class='shim normal'>&#x16F7B;</span>
16F6A | 16F6B | 16F6E| 16F71 | 16F73 | 16F76 | 16F78 | 16F79 | 16F7A | 16F7B
<span class='shim normal'>&#x16F7F;</span> | <span class='shim normal'>&#x16F80;</span>
16F7F | 16F80

Positioning tone marks | |&#x0020;
:-- | :-- | :-- 
MIAO TONE RIGHT | MIAO TONE TOP RIGHT | MIAO TONE ABOVE 
16F8F | 16F90 | 16F91 

_Punctuation_

See also <a href="#punct">Punctuation and Digits</a>.

**Sorting ([Cheuk](https://www.unicode.org/L2/L2017/17345-n4845-miao-add.pdf), figure 5)**

_Red signifies unsure of sorting as it seems to be a digraph and should sort elsewhere. Some of the vowel "digraphs" are what made sense to the author, not as the chart listed them._

&#x26;<span class='shim normal'>&#x16F43;</span> &lt; <span class='shim normal'>&#x16F28;</span></br>
&#x26;<span class='shim normal'>&#x16F00;</span> &lt; <span class='shim normal'>&#x16F02;</span> &lt;&lt; <span class='shim normal'>&#x16F50;&#x16F00;</span> &lt;&lt; <span class='shim normal'>&#x16F00;&#x16F51;</span></br>
&#x26;<span class='shim normal'>&#x16F07;</span> &lt; <span class='shim normal'>&#x16F26;</span> &lt;&lt; <span class='shim normal'>&#x16F26;&#x16F51;</span></br>
&#x26;<span class='shim normal'>&#x16F16;</span> &lt; <span class='shim normal'>&#x16F18;</span></br>
&#x26;<span class='shim normal'>&#x16F2E;</span> &lt; <span class='shim normal'>&#x16F50;&#x16F2E;</span> &lt;&lt; <span class='shim normal'>&#x16F2E;&#x16F51;</span></br>
&#x26;<span class='shim normal'>&#x16F1E;</span> &lt;&lt; <span class='shim normal'>&#x16F50;&#x16F1E;</span> &lt;&lt; <span class='shim normal'>&#x16F1E;&#x16F51;</span></br>
&#x26;<span class='shim normal'>&#x16F21;</span> &lt; <span class='shim normal'>&#x16F30;</span></br>
&#x26;<span class='shim normal'>&#x16F31;</span> &lt;&lt; <span class='shim normal'>&#x16F31;&#x16F51;</span></br>
&#x26;<span class='shim normal'>&#x16F0E;</span> &lt;&lt; <span class='shim normal'>&#x16F50;&#x16F0E;</span> &lt;&lt; <span class='shim normal'>&#x16F0E;&#x16F51;</span></br>
&#x26;<span class='shim normal'>&#x16F39;</span></br>
&#x26;<span class='shim normal'>&#x16F37;</span> &lt;&lt; <span class='shim normal'>&#x16F50;&#x16F37;</span> &lt;&lt; <span class='shim normal'>&#x16F37;&#x16F51;</span></br>
&#x26;<span class='shim normal'>&#x16F0A;</span> &lt;&lt; <span class='shim normal'>&#x16F50;&#x16F0A;</span> &lt;&lt; <span class='shim normal'>&#x16F0A;&#x16F51;</span></br>
&#x26;<span class='shim normal'>&#x16F0D;</span> &lt; <span class='shim normal'>&#x16F0C;</span> &lt; <span class='shim normal'><font color="red">&#x16F2F;</font></span> &lt; <span class='shim normal'><font color="red">&#x16F12;&#x16F2E;</font></span> &lt; <span class='shim normal'>&#x16F04;</span> &lt; <span class='shim normal'>&#x16F10;</span> &lt; <span class='shim normal'>&#x16F12;</span> &lt; <span class='shim normal'>&#x16F14;</span> &lt; <span class='shim normal'>&#x16F33;</span> &lt; <span class='shim normal'>&#x16F34;</span> &lt; <span class='shim normal'>&#x16F23;</span> &lt; <span class='shim normal'>&#x16F3A;</span> &lt; <span class='shim normal'>&#x16F42;</span> &lt; <span class='shim normal'>&#x16F08;</span> &lt; <span class='shim normal'>&#x16F3D;</span> &lt; <span class='shim normal'>&#x16F3B;</span> &lt; <span class='shim normal'>&#x16F35;</span></br>
&#x26;<span class='shim normal'>&#x16F54;</span> &lt; <span class='shim normal'>&#x16F79;</span> &lt; <span class='shim normal'>&#x16F66;</span> &lt; <span class='shim normal'>&#x16F7B;</span> &lt; <span class='shim normal'>&#x16F5C;</span></br>
&#x26;<span class='shim normal'>&#x16F59;</span> &lt;&lt; <span class='shim normal'>&#x16F59;&#x16F5C;</span></br>
&#x26;<span class='shim normal'>&#x16F5B;</span> &lt; <span class='shim normal'>&#x16F7F;</span> &lt; <span class='shim normal'>&#x16F78;</span> &lt; <span class='shim normal'>&#x16F76;</span></br>
&#x26;<span class='shim normal'>&#x16F61;</span> &lt;&lt; <span class='shim normal'>&#x16F61;&#x16F7B;</span> &lt;&lt; <span class='shim normal'>&#x16F61;&#x16F59;</span> &lt;&lt; <span class='shim normal'>&#x16F61;&#x16F7A;</span> &lt;&lt; <span class='shim normal'>&#x16F61;&#x16F66;</span> &lt;&lt; <span class='shim normal'>&#x16F61;&#x16F5B;</span> &lt;&lt; <span class='shim normal'>&#x16F61;&#x16F58;</span></br>
&#x26;<span class='shim normal'>&#x16F6A;</span> &lt;&lt; <span class='shim normal'>&#x16F6A;&#x16F5C;</span> &lt;&lt; <span class='shim normal'>&#x16F6A;&#x16F7A;</span> &lt;&lt; <span class='shim normal'>&#x16F6A;&#x16F59;</span> &lt;&lt; <span class='shim normal'>&#x16F6A;&#x16F5D;</span> &lt;&lt; <span class='shim normal'>&#x16F6A;&#x16F66;</span> &lt;&lt; <span class='shim normal'>&#x16F6A;&#x16F58;</span></br>
&#x26;<span class='shim normal'>&#x16F80;</span> &lt; <span class='shim normal'>&#x16F73;</span> &lt; <span class='shim normal'>&#x16F7A;</span> &lt; <span class='shim normal'>&#x16F71;</span></br>
&#x26;<span class='shim normal'>&#x16F5D;</span> &lt;&lt; <span class='shim normal'>&#x16F5D;&#x16F5C;</span></br>
&#x26;<span class='shim normal'>&#x16F62;</span> &lt; <span class='shim normal'>&#x16F6B;</span> &lt; <span class='shim normal'>&#x16F68;</span> &lt; <span class='shim normal'>&#x16F6E;</span> &lt; <span class='shim normal'>&#x16F58;</span></br>




**Rendering**

_Glyph variants_

Setting        | Sample
:------ | :--------------- 
default        | <span class='shim normal'>&#x16F04; &#x16F10; &#x16F2F; &#x16F35;</span>
traditional      | <span class='shim normal'>&#x16F04; &#x16F10; &#x16F2F; &#x16F35;</span>
normalized      | <span class='ywqa normal'>&#x16F04; &#x16F10; &#x16F2F; &#x16F35;</span>

_Sample text taken from Figure 7 of [Cheuk](https://www.unicode.org/L2/L2017/17345-n4845-miao-add.pdf)._

Setting        | Sample           | USV
:-- | :-- | :---------
ywq | <span class='shim normal'>&#x16F0D;&#x16F73;&#x16F90; &#x16F21;&#x16F58; &#x16F12;&#x16F7B;&#x16F91; &#x16F30;&#x16F59;&#x16F5C;&#x16F91;</span> | U+16F0D U+16F73 U+16F90 U+0020 U+16F21 U+16F58 U+0020 U+16F12 U+16F7B U+16F91 U+0020 U+16F30 U+16F59 U+16F5C U+16F91

_Sample graphic_

<img src="assets/images/ywq_Nosu_972.png" title="fig:" style="width:80%;height:80%;" alt="Nosu sample" />
<figcaption>Mark 1:1-4 (UBS).</figcaption>

## <a id="former"></a>Languages formerly using Miao/Pollard script

### <a id="cqd"></a>Chuanqiandian Cluster Miao &#x005B;cqd&#x005D;

**Resources**

_Language tag:_ `cqd-Plrd`

**Character set**

Consonant onsets | | | | | | | | |&#x0020;
:-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :--
Not listed

Modifiers | Nasalization | Aspiration
:-- | :-- | :-- 
&#x0020; | <span class='shim normal'>&#x16F50;</span> | <span class='shim normal'>&#x16F51;</span>
&#x0020; | 16F50 | 16F51

Vowels and finals | | | | | | | | |&#x0020;
:-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- 
Not listed

Positioning tone marks | |&#x0020;
:-- | :-- | :-- 
MIAO TONE RIGHT | MIAO TONE TOP RIGHT | MIAO TONE ABOVE 
16F8F | 16F90 | 16F91 

_Punctuation_

See also <a href="#punct">Punctuation and Digits</a>.

Additional punctuation: <span class='shim normal'>[ ]</span>

**Rendering**

_Sample graphic_

<img src="assets/images/cqd_MiaoChuan_859.png" title="fig:" style="width:80%;height:80%;" alt="Miao: Chuan sample" />
<figcaption>Mark 1:1-4 (UBS).</figcaption>

### <a id="ktp"></a>Kaduo / Kado &#x005B;ktp&#x005D;

**Resources**

_Language tag:_ `ktp`

**Character set**

Consonant onsets | | | | | | | | | &#x0020;
:-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :--
Not listed

Modifiers | Nasalization | Aspiration
:-- | :-- | :-- 
&#x0020; | <span class='shim normal'>&#x16F50;</span> | <span class='shim normal'>&#x16F51;</span>
&#x0020; | 16F50 | 16F51

Vowels and finals | | | | | | | | |&#x0020;
:-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- 
Not listed

Positioning tone marks  |&#x0020;
:-- | :-- 
MIAO TONE TOP RIGHT | MIAO TONE ABOVE 
16F90 | 16F91

_Punctuation_

See also <a href="#punct">Punctuation and Digits</a>.

Additional punctuation: <span class='shim normal'>: ;</span>


**Rendering**

_Sample graphic_

<img src="assets/images/ktp_Kado_600.png" title="fig:" style="width:80%;height:80%;" alt="Kado sample" />
<figcaption>Luke 3:1-4 (UBS).</figcaption>

### <a id="lbc"></a>Lakkia &#x005B;lbc&#x005D;

**Resources**

_Language tag:_ `lbc`

**Character set**

Consonant onsets | | | | | | | ||&#x0020;
:-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :--
Not listed

Vowels and finals | | | | | | | | |&#x0020;
:-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- 
Not listed

Positioning tone marks | | |&#x0020;
:-- | :-- | :-- | :-- 
MIAO TONE RIGHT | MIAO TONE TOP RIGHT | MIAO TONE ABOVE | MIAO TONE BELOW
16F8F | 16F90 | 16F91 | 16F92

_Punctuation_

See also <a href="#punct">Punctuation and Digits</a>.

**Rendering**

_Sample graphic_

<img src="assets/images/lbc_Laka_ill5.png" title="fig:" style="width:80%;height:80%;" alt="Laka sample" />
<figcaption>John (Illustration 5, China 2009).</figcaption>


### <a id="mww"></a>Hmong Daw &#x005B;mww&#x005D;

**Resources**

_Language tag:_ `mww-Plrd`

_Opentype language system tag:_ `MWW `

_No further information_

### <a id="sfm"></a>Xiaohua Miao / Small Flowery Miao &#x005B;sfm&#x005D;

**Resources**

_Language tag:_ `sfm`

_Opentype language system tag:_ `SFM `

_SLDR:_ none

_Keyman keyboard:_ none

_Font:_ [Shimenkan MAS](https://software.sil.org/shimenkan/) 

**Character set**

Consonant onsets | | | | | | | ||&#x0020;
:-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :--
<span class='sfm normal'>&#x16F00;</span> | <span class='sfm normal'>&#x16F01;</span> | <span class='sfm normal'>&#x16F03;</span> | <span class='sfm normal'>&#x16F04;</span> | <span class='sfm normal'>&#x16F07;</span> | <span class='sfm normal'>&#x16F08;</span> | <span class='sfm normal'>&#x16F0A;</span> | <span class='sfm normal'>&#x16F0B;</span> | <span class='sfm normal'>&#x16F0E;</span> | <span class='sfm normal'>&#x16F0F;</span>
 16F00 | 16F01 | 16F03 | 16F04 | 16F07 | 16F08 | 16F0A | 16F0B | 16F0E |  16F0F
 <span class='sfm normal'>&#x16F10;</span> | <span class='sfm normal'>&#x16F11;</span> | <span class='sfm normal'>&#x16F16;</span> | <span class='sfm normal'>&#x16F17;</span> | <span class='sfm normal'>&#x16F18;</span> | <span class='sfm normal'>&#x16F19;</span> | <span class='sfm normal'>&#x16F1E;</span> | <span class='sfm normal'>&#x16F1F;</span> | <span class='sfm normal'>&#x16F21;</span> | <span class='sfm normal'>&#x16F22;</span>
 16F10 | 16F11 | 16F16 | 16F17 | 16F18 | 16F19 | 16F1E | 16F1F | 16F21 | 16F22
 <span class='sfm normal'>&#x16F23;</span> | <span class='sfm normal'>&#x16F26;</span> | <span class='sfm normal'>&#x16F28;</span> | <span class='sfm normal'>&#x16F29;</span> | <span class='sfm normal'>&#x16F2E;</span> | <span class='sfm normal'>&#x16F2F;</span> | <span class='sfm normal'>&#x16F32;</span> | <span class='sfm normal'>&#x16F33;</span> | <span class='sfm normal'>&#x16F35;</span> | <span class='sfm normal'>&#x16F37;</span>
 16F23 | 16F26 | 16F28 | 16F29 | 16F2E | 16F2F | 16F32 | 16F33 | 16F35 | 16F37
 <span class='sfm normal'>&#x16F38;</span> | <span class='sfm normal'>&#x16F3A;</span> | <span class='sfm normal'>&#x16F3D;</span> | <span class='sfm normal'>&#x16F42;</span> | <span class='sfm normal'>&#x16F43;</span> | <span class='sfm normal'>&#x16F45;</span> | <span class='sfm normal'>&#x16F46;</span> | <span class='sfm normal'>&#x16F47;</span>
 16F38 | 16F3A | 16F3D | 16F42 | 16F43 | 16F45 | 16F46 | 16F47 

Modifiers | Nasalization | Aspiration
:-- | :-- | :-- 
&#x0020; | <span class='shim normal'>&#x16F50;</span> | <span class='shim normal'>&#x16F51;</span>
&#x0020; | 16F50 | 16F51

Vowels and finals | | | | | | | | |&#x0020;
:-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- 
<span class='sfm normal'>&#x16F54;</span> | <span class='sfm normal'>&#x16F57;</span> | <span class='sfm normal'>&#x16F58;</span> | <span class='sfm normal'>&#x16F59;</span> | <span class='sfm normal'>&#x16F5C;</span> | <span class='sfm normal'>&#x16F5D;</span> | <span class='sfm normal'>&#x16F5E;</span> | <span class='sfm normal'>&#x16F5F;</span> | <span class='sfm normal'>&#x16F61;</span> | <span class='sfm normal'>&#x16F62;</span>
16F54 | 16F57 | 16F58 | 16F59 | 16F5C | 16F5D | 16F5E | 16F5F | 16F61 | 16F62
<span class='sfm normal'>&#x16F63;</span> | <span class='sfm normal'>&#x16F64;</span> | <span class='sfm normal'>&#x16F66;</span> | <span class='sfm normal'>&#x16F68;</span> | <span class='sfm normal'>&#x16F69;</span> | <span class='sfm normal'>&#x16F6A;</span> | <span class='sfm normal'>&#x16F6B;</span> | <span class='sfm normal'>&#x16F6C;</span> | <span class='sfm normal'>&#x16F6D;</span> | <span class='sfm normal'>&#x16F70;</span>
16F63 | 16F64 | 16F66 | 16F68 | 16F69 | 16F6A | 16F6B | 16F6C | 16F6D | 16F70
<span class='sfm normal'>&#x16F71;</span> | <span class='sfm normal'>&#x16F75;</span> | <span class='sfm normal'>&#x16F77;</span> | <span class='sfm normal'>&#x16F78;</span> | <span class='sfm normal'>&#x16F79;</span> | <span class='sfm normal'>&#x16F7A;</span> | <span class='sfm normal'>&#x16F7B;</span> | <span class='sfm normal'>&#x16F7E;</span> | <span class='sfm normal'>&#x16F82;</span> | <span class='sfm normal'>&#x16F83;</span>
16F71 | 16F75 | 16F77 | 16F78 | 16F79 | 16F7A | 16F7B | 16F7E | 16F82 | 16F83

Positioning tone marks | |
:-- | :-- | :-- 
MIAO TONE RIGHT | MIAO TONE TOP RIGHT | MIAO TONE ABOVE 
16F8F | 16F90 | 16F91

_Punctuation_

See also <a href="#punct">Punctuation and Digits</a>.

**_Sorting ([Cheuk](https://www.unicode.org/L2/L2017/17345-n4845-miao-add.pdf), figure 11)_**

_Ordering of vowel digraphs is not the same as the chart, but it seemed to make the most sense to the author._

&#x26;<span class='sfm normal'>&#x16F2E;</span> &lt;&lt;<span class='sfm normal'>&#x16F2E;&#x16F51;</span> &lt;&lt; <span class='sfm normal'>&#x16F2F;</span> &lt;&lt;<span class='sfm normal'>&#x16F50;&#x16F2E;</span> &lt;&lt; <span class='sfm normal'>&#x16F50;&#x16F2E;&#x16F51;</span> &lt;&lt; <span class='sfm normal'>&#x16F50;&#x16F2F;</span></br> 
&#x26;<span class='sfm normal'>&#x16F07;</span></br> 
&#x26;<span class='sfm normal'>&#x16F26;</span> &lt;&lt; <span class='sfm normal'>&#x16F26;&#x16F51;</span></br> 
&#x26;<span class='sfm normal'>&#x16F28;</span> &lt;&lt;<span class='sfm normal'>&#x16F28;&#x16F51;</span> &lt;&lt; <span class='sfm normal'>&#x16F29;</span> &lt;&lt; <span class='sfm normal'>&#x16F50;&#x16F28;</span></br> 
&#x26;<span class='sfm normal'>&#x16F43;</span> &lt; <span class='sfm normal'>&#x16F35;</span></br> 
&#x26;<span class='sfm normal'>&#x16F1E;</span> &lt;&lt; <span class='sfm normal'>&#x16F1E;&#x16F51;</span> &lt;&lt; <span class='sfm normal'>&#x16F1F;</span> &lt;&lt; <span class='sfm normal'>&#x16F50;&#x16F1E;</span> &lt;&lt; <span class='sfm normal'>&#x16F50;&#x16F1E;&#x16F51;</span> &lt;&lt; <span class='sfm normal'>&#x16F50;&#x16F1F;</span></br> 
&#x26;<span class='sfm normal'>&#x16F21;</span> &lt;&lt; <span class='sfm normal'>&#x16F21;&#x16F51;</span> &lt;&lt; <span class='sfm normal'>&#x16F50;&#x16F21;</span> &lt;&lt; <span class='sfm normal'>&#x16F50;&#x16F21;&#x16F51;</span> &lt;&lt; <span class='sfm normal'>&#x16F50;&#x16F22;</span></br> 
&#x26;<span class='sfm normal'>&#x16F03;</span> &lt;&lt; <span class='sfm normal'>&#x16F03;&#x16F51;</span> &lt;&lt; <span class='sfm normal'>&#x16F45;</span> &lt;&lt; <span class='sfm normal'>&#x16F50;&#x16F03;</span> &lt;&lt; <span class='sfm normal'>&#x16F50;&#x16F03;&#x16F51;</span> &lt;&lt; <span class='sfm normal'>&#x16F50;&#x16F45;</span></br> 
&#x26;<span class='sfm normal'>&#x16F16;</span> &lt;&lt; <span class='sfm normal'>&#x16F18;</span> &lt;&lt; <span class='sfm normal'>&#x16F17;</span> &lt;&lt; <span class='sfm normal'>&#x16F19;</span></br> 
&#x26;<span class='sfm normal'>&#x16F04;</span> &lt;&lt; <span class='sfm normal'>&#x16F04;&#x16F51;</span></br> 
&#x26;<span class='sfm normal'>&#x16F10;</span> &lt;&lt; <span class='sfm normal'>&#x16F10;&#x16F51;</span> &lt;&lt; <span class='sfm normal'>&#x16F11;</span></br> 
&#x26;<span class='sfm normal'>&#x16F23;</span> &lt;&lt; <span class='sfm normal'>&#x16F23;&#x16F51;
</span></br> 
&#x26;<span class='sfm normal'>&#x16F00;</span> &lt;&lt; <span class='sfm normal'>&#x16F00;&#x16F51;</span> &lt;&lt; <span class='sfm normal'>&#x16F01;</span> &lt;&lt; <span class='sfm normal'>&#x16F50;&#x16F00;</span> &lt;&lt; <span class='sfm normal'>&#x16F50;&#x16F00;&#x16F51;</span> &lt;&lt; <span class='sfm normal'>&#x16F50;&#x16F01;
</span></br> 
&#x26;<span class='sfm normal'>&#x16F33;</span> &lt;&lt; <span class='sfm normal'>&#x16F46;</span></br> 
&#x26;<span class='sfm normal'>&#x16F3A;</span></br> 
&#x26;<span class='sfm normal'>&#x16F0A;</span> &lt;&lt; <span class='sfm normal'>&#x16F0A;&#x16F51;</span> &lt;&lt; <span class='sfm normal'>&#x16F0B;</span> &lt;&lt; <span class='sfm normal'>&#x16F50;&#x16F0A;</span> &lt;&lt; <span class='sfm normal'>&#x16F50;&#x16F0A;&#x16F51;</span> &lt;&lt; <span class='sfm normal'>&#x16F50;&#x16F0B;</span></br> 
&#x26;<span class='sfm normal'>&#x16F0E;</span> &lt;&lt; <span class='sfm normal'>&#x16F0E;&#x16F51;</span> &lt;&lt; <span class='sfm normal'>&#x16F0F;</span> &lt;&lt; <span class='sfm normal'>&#x16F50;&#x16F0E;</span> &lt;&lt; <span class='sfm normal'>&#x16F50;&#x16F0E;&#x16F51;</span> &lt;&lt; <span class='sfm normal'>&#x16F50;&#x16F0F;
</span></br> 
&#x26;<span class='sfm normal'>&#x16F37;</span> &lt;&lt; <span class='sfm normal'>&#x16F37;&#x16F51;</span> &lt;&lt; <span class='sfm normal'>&#x16F38;</span> &lt;&lt; <span class='sfm normal'>&#x16F50;&#x16F37;</span> &lt;&lt; <span class='sfm normal'>&#x16F50;&#x16F37;&#x16F51;</span> &lt;&lt; <span class='sfm normal'>&#x16F50;&#x16F38;</span></br> 
&#x26;<span class='sfm normal'>&#x16F42;</span> &lt; <span class='sfm normal'>&#x16F08;</span> &lt; <span class='sfm normal'>&#x16F3D;</span></br> 
&#x26;<span class='sfm normal'>&#x16F32;</span> &lt;&lt; <span class='sfm normal'>&#x16F32;&#x16F51;</span> &lt;&lt; <span class='sfm normal'>&#x16F47;</span> &lt;&lt; <span class='sfm normal'>&#x16F50;&#x16F32;</span> &lt;&lt; <span class='sfm normal'>&#x16F50;&#x16F32;&#x16F51;</span> &lt;&lt; <span class='sfm normal'>&#x16F50;&#x16F47;</span></br> 
&#x26;<span class='sfm normal'>&#x16F54;</span> &lt; <span class='sfm normal'>&#x16F79;</span> &lt; <span class='sfm normal'>&#x16F7B;</span></br> 
&#x26;<span class='sfm normal'>&#x16F5D;&#x16F66;</span></br> 
&#x26;<span class='sfm normal'>&#x16F7A;</span> &lt; <span class='sfm normal'>&#x16F5C;</span></br> 
&#x26;<span class='sfm normal'>&#x16F61;</span> &lt;&lt; <span class='sfm normal'>&#x16F64;</span> (<span class='sfm normal'>&#x16F61;&#x16F58;</span>) &lt;&lt; <span class='sfm normal'>&#x16F63;</span> (<span class='sfm normal'>&#x16F61;&#x16F57;</span>) &lt;&lt; <span class='sfm normal'>&#x16F61;&#x16F79;</span> &lt;&lt; <span class='sfm normal'>&#x16F61;&#x16F7B;</span> &lt;&lt; <span class='sfm normal'>&#x16F61;&#x16F5D;</span> &lt;&lt; <span class='sfm normal'>&#x16F61;&#x16F5C;</span> &lt;&lt; <span class='sfm normal'>&#x16F69;</span>(<span class='sfm normal'>&#x16F61;&#x16F59;</span>) &lt;&lt; <span class='sfm normal'>&#x16F61;&#x16F83;</span> &lt;&lt; <span class='sfm normal'>&#x16F61;&#x16F7A;</span> &lt;&lt; <span class='sfm normal'>&#x16F61;&#x16F7E;</span> &lt;&lt; <span class='sfm normal'>&#x16F61;&#x16F5E;</span> &lt;&lt; <span class='sfm normal'>&#x16F61;&#x16F5F;</span></br> 
&#x26;<span class='sfm normal'>&#x16F78;</span> &lt; <span class='sfm normal'>&#x16F77;</span> &lt; <span class='sfm normal'>&#x16F75;</span></br>
&#x26;<span class='sfm normal'>&#x16F59;</span> &lt;&lt; <span class='sfm normal'>&#x16F59;&#x16F6A;</span></br> 
&#x26;<span class='sfm normal'>&#x16F6A;</span> &lt;&lt; <span class='sfm normal'>&#x16F6A;&#x16F5E;</span> &lt;&lt; <span class='sfm normal'>&#x16F6A;&#x16F5F;</span> &lt;&lt; <span class='sfm normal'>&#x16F6A;&#x16F7E;</span> &lt;&lt; <span class='sfm normal'>&#x16F70;</span></br> 
&#x26;<span class='sfm normal'>&#x16F83;</span> &lt;&lt; <span class='sfm normal'>&#x16F83;&#x16F7E;</span></br>
&#x26;<span class='sfm normal'>&#x16F71;</span> &lt;&lt; <span class='sfm normal'>&#x16F71;&#x16F5D;</span> &lt;&lt; <span class='sfm normal'>&#x16F71;&#x16F7A;</span> &lt;&lt; <span class='sfm normal'>&#x16F71;&#x16F7E;</span> &lt;&lt; <span class='sfm normal'>&#x16F71;&#x16F5E;</span></br>
&#x26;<span class='sfm normal'>&#x16F82;</span> &lt; <span class='sfm normal'>&#x16F62;</span> &lt; <span class='sfm normal'>&#x16F68;</span> &lt; <span class='sfm normal'>&#x16F57;</span> &lt; <span class='sfm normal'>&#x16F58;</span> &lt; <span class='sfm normal'>&#x16F5E;</span> &lt; <span class='sfm normal'>&#x16F5F;</span></br> 
&#x26;<span class='sfm normal'>&#x16F6B;</span> &lt;&lt; <span class='sfm normal'>&#x16F6C;</span> &lt;&lt; <span class='sfm normal'>&#x16F6D;</span>


**Rendering**

See also <a href="#tone">Tone mark positioning</a> for unusual positioning in this language.

See also <a href="#kern">Kerning</a> for special behavior.

See also <a href="#lig">Ligatures</a> for special behavior.

_Sample graphic_

<img src="assets/images/sfm_XiaohuaMiao_Fig14.png" title="fig:" style="width:80%;height:80%;" alt="Xiaohua Miao sample" />
<figcaption>John (Figure 14, [Cheuk](https://www.unicode.org/L2/L2017/17345-n4845-miao-add.pdf)).</figcaption>

### <a id="yna"></a>Gan Yi / Aluo &#x005B;yna&#x005D;

**Resources**

_Language tag:_ `yna`

_Opentype language system tag:_ `YNA `

_SLDR:_ none

_Keyman keyboard:_ [yna](https://keyman.com/keyboards/sil_yna_plrd)

_Font:_ [Shimenkan Zonghe](https://software.sil.org/shimenkan/)

**Character set**

_The keyboard includes U+16F13_ <span class='yna normal'>&#x16F13;</span> _(instead of U+16F42_ <span class='yna normal'>&#x16F42;</span>)_, and U+16F2F_ <span class='yna normal'>&#x16F2F;</span> _although they are not in Figure 10 [L2/17-345](https://www.unicode.org/L2/L2017/17345-n4845-miao-add.pdf)._

Consonant onsets | | | | | | | ||&#x0020;
:-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :--
<span class='yna normal'>&#x16F00;</span> | <span class='yna normal'>&#x16F02;</span> | <span class='yna normal'>&#x16F04;</span> | <span class='yna normal'>&#x16F07;</span> | <span class='yna normal'>&#x16F08;</span> | <span class='yna normal'>&#x16F0A;</span> | <span class='yna normal'>&#x16F0D;</span> | <span class='yna normal'>&#x16F0E;</span> | <span class='yna normal'>&#x16F10;</span> | <span class='yna normal'>&#x16F16;</span>
16F00 | 16F02 | 16F04 | 16F07 | 16F08 | 16F0A | 16F0D | 16F0E | 16F10 | 16F16
<span class='yna normal'>&#x16F18;</span> | <span class='yna normal'>&#x16F1E;</span> | <span class='yna normal'>&#x16F20;</span> | <span class='yna normal'>&#x16F23;</span> | <span class='yna normal'>&#x16F26;</span> | <span class='yna normal'>&#x16F28;</span> | <span class='yna normal'>&#x16F2E;</span> | <span class='yna normal'>&#x16F33;</span> | <span class='yna normal'>&#x16F35;</span> | <span class='yna normal'>&#x16F37;</span>
16F18 | 16F1E | 16F20 | 16F23 | 16F26 | 16F28 | 16F2E | 16F33 | 16F35 | 16F37
<span class='yna normal'>&#x16F39;</span> | <span class='yna normal'>&#x16F3A;</span> | <span class='yna normal'>&#x16F3B;</span> | <span class='yna normal'>&#x16F3D;</span> | <span class='yna normal'>&#x16F42;</span> | <span class='yna normal'>&#x16F43;</span> | 
16F39 | 16F3A | 16F3B | 16F3D | 16F42 | 16F43 | 

Modifiers | Consonant modifier bar | Nasalization | Aspiration
:-- | :-- | :-- | :-- 
&#x0020; | <span class='yna normal'>&#x16F4F;</span> | <span class='shim normal'>&#x16F50;</span> | <span class='shim normal'>&#x16F51;</span>
&#x0020; | 16F4F | 16F50 | 16F51

_The keyboard includes U+16F56_ <span class='yna normal'>&#x16F56;</span>_, U+16F59_ <span class='yna normal'>&#x16F59;</span>_, U+16F5B_ <span class='yna normal'>&#x16F5B;</span>_, U+16F5F_ <span class='yna normal'>&#x16F5F;</span>_, U+16F69_ <span class='yna normal'>&#x16F69;</span>_, U+16F78_ <span class='yna normal'>&#x16F78;</span>_, U+16F7A_ <span class='yna normal'>&#x16F7A;</span>_, and U+16F7C_ <span class='yna normal'>&#x16F7C;</span> _although they are not in Figure 10 [L2/17-345](https://www.unicode.org/L2/L2017/17345-n4845-miao-add.pdf)._

Vowels and finals | | | | | | | | |&#x0020;
:-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- 
<span class='yna normal'>&#x16F54;</span> | <span class='yna normal'>&#x16F58;</span> | <span class='yna normal'>&#x16F59;</span> | <span class='yna normal'>&#x16F5C;</span> | <span class='yna normal'>&#x16F5D;</span> | <span class='yna normal'>&#x16F5E;</span> | <span class='yna normal'>&#x16F61;</span> | <span class='yna normal'>&#x16F62;</span> | <span class='yna normal'>&#x16F66;</span> | <span class='yna normal'>&#x16F67;</span> 
16F54 | 16F58 | 16F59 | 16F5C | 16F5D | 16F5E | 16F61 | 16F62 | 16F66 | 16F67
<span class='yna normal'>&#x16F68;</span> | <span class='yna normal'>&#x16F6A;</span> | <span class='yna normal'>&#x16F6B;</span> | <span class='yna normal'>&#x16F6E;</span> | <span class='yna normal'>&#x16F71;</span> | <span class='yna normal'>&#x16F73;</span> | <span class='yna normal'>&#x16F74;</span> | <span class='yna normal'>&#x16F75;</span> | <span class='yna normal'>&#x16F76;</span> | <span class='yna normal'>&#x16F77;</span>
16F68 | 16F6A | 16F6B | 16F6E | 16F71 | 16F73 | 16F74 | 16F75 | 16F76 | 16F77
<span class='yna normal'>&#x16F79;</span> | <span class='yna normal'>&#x16F7B;</span> | <span class='yna normal'>&#x16F7E;</span> | <span class='yna normal'>&#x16F81;</span> | <span class='yna normal'>&#x16F82;</span>
16F79 | 16F7B | 16F7E | 16F81 | 16F82

Positioning tone marks | | &#x0020;
:-- | :-- | :-- 
MIAO TONE RIGHT | MIAO TONE TOP RIGHT | MIAO TONE ABOVE 
16F8F | 16F90 | 16F91

_Punctuation_

See also <a href="#punct">Punctuation and Digits</a>.

Additional punctuation: <span class='shim normal'>: ; _ ' ? ! *</span>

<span class='yna normal'>&#x3001;</span> (U+3001 IDEOGRAPHIC COMMA)
<span class='yna normal'>&#x3002;</span> (U+3002 IDEOGRAPHIC FULL STOP)

**Sorting (Cheuk, figure 10)**


&#x26;<span class='yna normal'>&#x16F00;</span> &lt;&lt; <span class='yna normal'>&#x16F02;</span> &lt;&lt; <span class='yna normal'>&#x16F00;&#x16F51;</span><br/>
&#x26;<span class='yna normal'>&#x16F0A;</span> &lt;&lt; <span class='yna normal'>&#x16F0D;</span> &lt;&lt; <span class='yna normal'>&#x16F0A;&#x16F51;</span><br/>
&#x26;<span class='yna normal'>&#x16F1E;</span> &lt;&lt; <span class='yna normal'>&#x16F20;</span> &lt;&lt; <span class='yna normal'>&#x16F1E;&#x16F51;</span><br/>
&#x26;<span class='yna normal'>&#x16F2E;</span> &lt;&lt; <span class='yna normal'>&#x16F0E;</span> &lt;&lt; <span class='yna normal'>&#x16F2E;&#x16F51;</span><br/>
&#x26;<span class='yna normal'>&#x16F37;</span> &lt;&lt; <span class='yna normal'>&#x16F39;</span> &lt;&lt; <span class='yna normal'>&#x16F37;&#x16F51;</span><br/>
&#x26;<span class='yna normal'>&#x16F08;</span><br/>
&#x26;<span class='yna normal'>&#x16F07;</span><br/>
&#x26;<span class='yna normal'>&#x16F26;</span> &lt;&lt; <span class='yna normal'>&#x16F26;&#x16F51;</span><br/>
&#x26;<span class='yna normal'>&#x16F04;</span><br/>
&#x26;<span class='yna normal'>&#x16F10;</span> &lt;&lt; <span class='yna normal'>&#x16F10;&#x16F51;</span> &lt;&lt; <span class='yna normal'>&#x16F10;&#x16F4F;</span><br/>
&#x26;<span class='yna normal'>&#x16F16;</span> &lt; <span class='yna normal'>&#x16F18;</span> &lt; <span class='yna normal'>&#x16F23;</span> &lt; <span class='yna normal'>&#x16F42;</span> &lt; <span class='yna normal'>&#x16F35;</span> &lt; <span class='yna normal'>&#x16F33;</span> &lt; <span class='yna normal'>&#x16F3B;</span> &lt; <span class='yna normal'>&#x16F3A;</span> &lt; <span class='yna normal'>&#x16F3D;</span> &lt; <span class='yna normal'>&#x16F43;</span> &lt; <span class='yna normal'>&#x16F28;</span><br/>
&#x26;<span class='yna normal'>&#x16F0E;&#x16F4F;</span> &lt;&lt; <span class='yna normal'>&#x16F50;&#x16F0E;</span> &lt;&lt; <span class='yna normal'>&#x16F0E;&#x16F51;</span><br/>
&#x26;<span class='yna normal'>&#x16F54;</span> &lt; <span class='yna normal'>&#x16F7B;</span> &lt; <span class='yna normal'>&#x16F5C;</span> &lt; <span class='yna normal'>&#x16F5D;</span> &lt; <span class='yna normal'>&#x16F74;</span> &lt; <span class='yna normal'>&#x16F73;</span> &lt; <span class='yna normal'>&#x16F62;</span><br/>
&#x26;<span class='yna normal'>&#x16F71;</span> &lt;&lt; <span class='yna normal'>&#x16F71;&#x16F67;</span> &lt;&lt; <span class='yna normal'>&#x16F71;&#x16F82;</span> &lt;&lt; <span class='yna normal'>&#x16F71;&#x16F66; </span><br/>
&#x26;<span class='yna normal'>&#x16F61;</span> &lt;&lt; <span class='yna normal'>&#x16F61;&#x16F67;</span> &lt;&lt; <span class='yna normal'>&#x16F61;&#x16F7B;</span> &lt;&lt; <span class='yna normal'>&#x16F61;&#x16F82;</span> &lt;&lt; <span class='yna normal'>&#x16F61;&#x16F73;</span> &lt;&lt; <span class='yna normal'>&#x16F61;&#x16F74;</span> &lt;&lt; <span class='yna normal'>&#x16F61;&#x16F5D;</span> &lt;&lt; <span class='yna normal'>&#x16F61;&#x16F6E;</span> &lt;&lt; <span class='yna normal'>&#x16F61;&#x16F59;</span> &lt;&lt; <span class='yna normal'>&#x16F61;&#x16F7E;</span> &lt;&lt; <span class='yna normal'>&#x16F61;&#x16F5C;</span> &lt;&lt; <span class='yna normal'>&#x16F61;&#x16F66;</span> &lt;&lt; <span class='yna normal'>&#x16F61;&#x16F81;</span><br/>
&#x26;<span class='yna normal'>&#x16F6A;</span> &lt;&lt; <span class='yna normal'>&#x16F6A;&#x16F79;</span> &lt;&lt; <span class='yna normal'>&#x16F6A;&#x16F82;</span> &lt;&lt; <span class='yna normal'>&#x16F6A;&#x16F66;</span><br/>
&#x26;<span class='yna normal'>&#x16F82;</span> &lt; <span class='yna normal'>&#x16F75;</span> &lt; <span class='yna normal'>&#x16F77;</span><br/>
&#x26;<span class='yna normal'>&#x16F59;</span> &lt;&lt; <span class='yna normal'>&#x16F59;&#x16F5C;</span><br/>
&#x26;<span class='yna normal'>&#x16F68;</span> &lt; <span class='yna normal'>&#x16F6B;</span> &lt; <span class='yna normal'>&#x16F58;</span> &lt; <span class='yna normal'>&#x16F76;</span> &lt; <span class='yna normal'>&#x16F7E;</span> &lt; <span class='yna normal'>&#x16F81;</span> &lt; <span class='yna normal'>&#x16F6E;</span> &lt; <span class='yna normal'>&#x16F67;</span> &lt; <span class='yna normal'>&#x16F5E;</span> &lt; <span class='yna normal'>&#x16F79;</span> &lt; <span class='yna normal'>&#x16F66; </span>

**Rendering**

See also <a href="#kern">Kerning</a> for special behavior.

_Sample text taken from Figure 8 of Cheuk._

Setting        | Sample           | USV
:-- | :-- | :---------
yna | <span class='yna normal'>&#x16F10;&#x16F4F;&#x16F7B;&#x16F91; &#x16F2E;&#x16F51;&#x16F5C;&#x16F90; &#x16F2E;&#x16F61;&#x16F59;</span> | U+16F10 U+16F4F U+16F7B U+16F91 U+0020 U+16F2E U+16F51 U+16F5C U+16F90 U+0020 U+16F2E U+16F61 U+16F59

_Sample graphic_

<img src="assets/images/yna_Laka_713.png" title="fig:" style="width:80%;height:80%;" alt="Laka sample" />
<figcaption>Mark 1:1-4 (UBS).</figcaption>

## <a id="ref"></a>References

UBS. 1972. [The Book of a Thousand Tongues](https://archive.org/details/B-001-001-424/page/2/mode/2up)

21 May 1997. John H. Jenkins. [Proposal to add Pollard to Unicode/ISO-IEC 10646](http://www.unicode.org/L2/L1997/97104-Pollard.pdf)

China. 2007-09-14. [Preliminary proposal for encoding the Northeastern Yunnan Simple Miao script](https://www.unicode.org/L2/L2007/07299-n3335.pdf)

2009-10-01. China. [Proposal for encoding the Miao script](https://www.unicode.org/L2/L2009/09253r-n3669r-miao.pdf)

China, Ireland, and UK. 2010-03-26. [Final proposal for encoding the Miao script in the SMP of the UCS](https://www.unicode.org/L2/L2010/10093-n3789-miao.pdf)

undated (2011). YU SUEE YAN. [THE STORY OF THE BIG FLOWERY MIAO BIBLE](https://archive.translation.bible/fileadmin/publications/tbt/practical/BT-62-4-2011-Yu.pdf)

undated. 2012 (or later). Jeremiah Y.S. Chung and Eric Drewry. [The Uses and Users of the Miao Script](https://www.academia.edu/93203752/The_Uses_and_Users_of_the_Miao_Script).

2017-10-03. Adrian Cheuk. [Proposal for additions to the Miao script](https://www.unicode.org/L2/L2017/17345-n4845-miao-add.pdf)

