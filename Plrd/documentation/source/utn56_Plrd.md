---
title: Unicode Technical Note 56 - Representing Miao in Unicode
---

_Lorna Evans, SIL International (25-Nov-2024)_

_Additional information is most welcome._

- <a href="#over">Overview</a>
   - <a href="#store">Character storage</a>
   - <a href="#punct">Punctuation and Digits</a>
   - <a href="#break">Line breaking and word breaking</a>
   - <a href="#rend">Rendering</a>
      - <a href="#tone">Tone mark positioning</a>
      - <a href="#asp">Aspiration mark</a>
      - <a href="#kern">Kerning</a>
      - <a href="#glyph">Glyph variants</a>
- <a href="#lang">Languages currently using Miao/Pollard script</a> <a href="#1">[1]</a>
   - <a href="#hmd">Large Flowery Miao / Dahua Miao / A-Hmao &#x005B;hmd&#x005D;</a>
   - <a href="#hmz">Sinicized Miao / Waishu Miao / Hmong Shua &#x005B;hmz&#x005D;</a>
   - <a href="#lpo">Lipo / Dong Lisu / Eastern Lisu &#x005B;lpo&#x005D;</a>
   - <a href="#sfm">Xiaohua Miao / Small Flowery Miao &#x005B;sfm&#x005D;</a>
   - <a href="#ygp">Bai Yi / Gepo &#x005B;ygp&#x005D;</a>
   - <a href="#yna">Gan Yi / Dry Yi / Aluo / Laka &#x005B;yna&#x005D;</a>
   - <a href="#ywq">Hei Yi / Black Yi / Wuding-Luquan Yi / Nasu &#x005B;ywq&#x005D;</a>
- <a href="#former">Languages formerly using Miao/Pollard script</a> <a href="#1">[1]</a>
   - <a href="#ktp">Kaduo / Kado &#x005B;ktp&#x005D;</a>
   - <a href="#mww">Hmong Daw / White Miao / Sichuan Miao &#x005B;mww&#x005D;</a>
- <a href="#ack">Acknowledgements</a>
- <a href="#ref">References</a>

## <a id="over"></a>Overview

This document provides an introduction and overview on how to encode Miao/Pollard script text. It also gives information on the languages using the script and resources which are available.

### <a id="store"></a>Character storage

Each syllable is divided into an initial and a final. The initial is the initial consonant and the final consists of the vowel cluster<a href="#2">[2]</a> and the tone. The positioning of the vowels indicates the tone of a syllable. Nasalization and voicing are considered as initial rather than final.

The syllable structure is: (N)C(M&#x2081;)(M&#x2082;)(M&#x2083;)V(V(V))(S/T):

- N is the nasalizer (16F50)
- C is the obligatory consonant (16F00..16F4A)
- M&#x2081; is the nukta (16F4F)
- M&#x2082; is either aspiration or reformed voicing (16F51 or 16F52)
- M&#x2083; is reformed aspiration (16F53)
- V is one obligatory vowel mark which may be followed by two more (16F54..16F87)
- S is a “shifting” character which controls the height of the vowel (16F8F..16F92)
- T is a tone mark (16F93..16F9F)
- **S and T do not co-occur on a syllable.**

**Rendering Example**

Setting        | Sample 
:--- | :--------------- 
default | <span class='shim normal'>&#x16F10;&#x16F4F;&#x16F7B;&#x16F91;&#x16F50;&#x16F2E;&#x16F54;&#x16F91;&#x16F07;&#x16F79;&#x16F26;&#x16F58;&#x16F8F;&#x16F28;&#x16F51;&#x16F7B;&#x16F43;&#x16F66;&#x16F91;&#x16F3B;&#x16F7A;&#x16F90;&#x16F1E;&#x16F59;&#x16F7E;&#x16F91;&#x16F21;&#x16F60;&#x16F1A;&#x16F5C;&#x16F91;&#x16F16;&#x16F73;&#x16F90;&#x16F18;&#x16F61;&#x16F90;&#x16F04;&#x16F77;&#x16F10;&#x16F75;&#x16F91;&#x16F23;&#x16F71;&#x16F90;&#x16F00;&#x16F6A;&#x16F8F;&#x16F35;&#x16F62;&#x16F91;&#x16F3A;&#x16F6B;&#x16F90;&#x16F33;&#x16F68;&#x16F0A;&#x16F6A;&#x16F57;&#x16F91;&#x16F0E;&#x16F5E;&#x16F8F;&#x16F37;&#x16F5F;&#x16F42;&#x16F61;&#x16F79;&#x16F91;&#x16F08;&#x16F64;&#x16F3D;&#x16F61;&#x16F7B;&#x16F91;&#x16F2F;&#x16F61;&#x16F5D;&#x16F8F;&#x16F1F;&#x16F61;&#x16F73;&#x16F91;&#x16F01;&#x16F6A;&#x16F90;&#x16F0B;&#x16F6A;&#x16F58;&#x16F91;&#x16F38;&#x16F6A;&#x16F5E; </span>
Code Points | <span class='affects'>16F10 16F4F 16F7B 16F91 16F50 16F2E 16F54 16F91 16F07 16F79 16F26 16F58 16F8F 16F28 16F51 16F7B 16F43 16F66 16F91 16F3B 16F7A 16F90 16F1E 16F59 16F7E 16F91 16F21 16F60 16F1A 16F5C 16F91 16F16 16F73 16F90 16F18 16F61 16F90 16F04 16F77 16F10 16F75 16F91 16F23 16F71 16F90 16F00 16F6A 16F8F 16F35 16F62 16F91 16F3A 16F6B 16F90 16F33 16F68 16F0A 16F6A 16F57 16F91 16F0E 16F5E 16F8F 16F37 16F5F 16F42 16F61 16F79 16F91 16F08 16F64; 16F3D 16F61 16F7B 16F91 16F2F 16F61 16F5D 16F8F 16F1F 16F61 16F73 16F91 16F01 16F6A 16F90 16F0B 16F6A 16F58 16F91 16F38 16F6A 16F5E</span>

### <a id="punct"></a>Punctuation and Digits

Users of the Miao script freely use the same punctuation marks as Chinese and Latin. 

Commonly used punctuation: <span class='shim normal'>. , : ; ? ! ' " - / = + - ( ) [ ] * / _ __ &#x201C; &#x201D;</span>

<span class='shim normal'>&#x3001;</span> 3001 IDEOGRAPHIC COMMA (or FF64 HALFWIDTH IDEOGRAPHIC COMMA)
 
<span class='shim normal'>&#x3002;</span> 3002 IDEOGRAPHIC FULL STOP or (FF61 HALFWIDTH IDEOGRAPHIC FULL STOP)

Additionally, most Miao script users seem to follow the Chinese convention for indicating proper nouns:

- names of people -- single underline
- names of places -- double underline
- book titles -- wavy underline

Miao script users use Western-style digits 0-9.

### <a id="break"></a>Line breaking and word breaking

Earlier texts were written without spaces, but later texts may employ spaces as visible word breaks. Either way, a syllable of consonant, vowel(s) and tone is never split, and word breaks only occur at syllable boundaries. Line breaks can occur where words break, at spaces, or after non-open punctuation. A line break may not be inserted within a syllable or before non-open punctuation.

### <a id="rend"></a>Rendering

**<a id="tone"></a>Tone mark positioning**

Four positioning tone marks are encoded. The default position for the vowels and finals is on the baseline. If another position is required, a tone positioning mark is utilized.

Setting     | Sample | Code Points
:---------- | :--- | :--------------
default     | <span class='shim normal'>&#x16F23;&#x16F6A;&#x16F57;</span> | 16F23 16F6A 16F57
<span class='affects'>16F8F MIAO TONE RIGHT</span> | <span class='shim normal'>&#x16F23;&#x16F6A;&#x16F57;&#x16F8F; </span> | 16F23 16F6A 16F57 16F8F
<span class='affects'>16F90 MIAO TONE TOP RIGHT</span> | <span class='shim normal'>&#x16F23;&#x16F6A;&#x16F57;&#x16F90; </span> | 16F23 16F6A 16F57 16F90
<span class='affects'>16F91 MIAO TONE ABOVE</span> | <span class='shim normal'>&#x16F23;&#x16F6A;&#x16F57;&#x16F91; </span> | 16F23 16F6A 16F57 16F91
<span class='affects'>16F92 MIAO TONE BELOW</span> | <span class='shim normal'>&#x16F23;&#x16F6A;&#x16F57;&#x16F92; </span> | 16F23 16F6A 16F57 16F92

For Xiaohua Miao / Small Flowery Miao &#x005B;sfm&#x005D; the four tone positions are used right of initial.

Code Points | default | sfm variant 
:--- | :--- | :--- 
<span class='affects'>16F90, 16F8F, 16F92, none</span> | <span class='shim normal'>&#x16F00;&#x16F6A;&#x16F90; &#x16F00;&#x16F6A;&#x16F8F; &#x16F00;&#x16F6A;&#x16F92; &#x16F00;&#x16F6A;</span> |<span class='sfm normal'>&#x16F00;&#x16F6A;&#x16F90; &#x16F00;&#x16F6A;&#x16F8F; &#x16F00;&#x16F6A;&#x16F92; &#x16F00;&#x16F6A;</span> 

**<a id="asp"></a>Aspiration mark**

Sinicized Miao &#x005B;hmz&#x005D;, Xiaohua Miao / Small Flowery Miao &#x005B;sfm&#x005D;, and sometimes Large Flowery Miao / Dahua Miao / A-Hmao &#x005B;hmd&#x005D;, put the aspiration mark (16F51) in front of the consonant rather than the default position of after. It is possible other languages would also do this.

Code Points       | default | variant | language
:--- | :--- | :--- | :---
<span class='affects'>16F04 16F51</span> | <span class='shim normal'>&#x16F04;&#x16F51;</span> | <span class='hmz normal'>&#x16F04;&#x16F51;</span> |<span class='affects'>hmz, sfm</span>
<span class='affects'>16F10 16F51</span> | <span class='shim normal'>&#x16F10;&#x16F51;</span> | <span class='hmz normal'>&#x16F10;&#x16F51;</span> | <span class='affects'>hmd, hmz, sfm</span>
<span class='affects'>16F23 16F51</span> | <span class='shim normal'>&#x16F23;&#x16F51;</span> | <span class='hmz normal'>&#x16F23;&#x16F51;</span>| <span class='affects'>hmz</span>

**<a id="kern"></a>Kerning**

In general, aspiration and finals are kerned into the initial. Additionally, finals are usually kerned under aspiration. There are some languages which do not follow this behavior. These are listed in the table below.

default | variant | language
:--- | :-------   | :---
<span class='shim normal'>&#x16F19;&#x16F66;&#x16F90; &#x16F32;&#x16F6B;&#x16F8F; &#x16F32;&#x16F6B;&#x16F92; &#x16F37;&#x16F6A; &#x16F0A;&#x16F71; &#x16F08;&#x16F7B; &#x16F43;&#x16F61;</span> |<span class='sfm normal'>&#x16F19;&#x16F66;&#x16F90; &#x16F32;&#x16F6B;&#x16F8F; &#x16F32;&#x16F6B;&#x16F92; &#x16F37;&#x16F6A; &#x16F0A;&#x16F71; &#x16F08;&#x16F7B; &#x16F43;&#x16F61;</span> <span class='affects'>(final not kerned into initial)</span> | <span class='affects'>hmd normalised</span>
<span class='shim normal'>&#x16F19;&#x16F66;&#x16F90; &#x16F32;&#x16F6B;&#x16F8F; &#x16F32;&#x16F6B;&#x16F92; &#x16F07;&#x16F68; &#x16F37;&#x16F6A; &#x16F0A;&#x16F71; &#x16F08;&#x16F7B; &#x16F43;&#x16F61;</span> |<span class='sfm normal'>&#x16F19;&#x16F66;&#x16F90; &#x16F32;&#x16F6B;&#x16F8F; &#x16F32;&#x16F6B;&#x16F92; &#x16F07;&#x16F68; &#x16F37;&#x16F6A; &#x16F0A;&#x16F71; &#x16F08;&#x16F7B; &#x16F43;&#x16F61;</span> <span class='affects'>(final not kerned into initial)</span> | <span class='affects'>sfm, ygp</span>
<span class='shim normal'>&#x16F2E;&#x16F51;&#x16F59; &#x16F20;&#x16F51;&#x16F5F;</span> |<span class='sfm normal'>&#x16F2E;&#x16F51;&#x16F59; &#x16F20;&#x16F51;&#x16F5F;</span> <span class='affects'>(final not kerned into aspiration)</span> | <span class='affects'>sfm, ygp</span>
<span class='shim normal'>&#x16F16;&#x16F51; &#x16F18;&#x16F51; &#x16F3D;&#x16F51; &#x16F1A;&#x16F51; &#x16F16;&#x16F51; &#x16F18;&#x16F51; &#x16F3D;&#x16F51; &#x16F1A;&#x16F51;</span> |<span class='hmdd normal'>&#x16F16;&#x16F51; &#x16F18;&#x16F51; &#x16F3D;&#x16F51; &#x16F1A;&#x16F51; &#x16F16;&#x16F51; &#x16F18;&#x16F51; &#x16F3D;&#x16F51; &#x16F1A;&#x16F51;</span> <span class='affects'>(aspiration not kerned into initial)</span>| <span class='affects'>hmd normalised</span>
<span class='shim normal'>&#x16F37;&#x16F51;&#x16F6A; &#x16F0A;&#x16F51;&#x16F71;</span> |<span class='yna normal'>&#x16F37;&#x16F51;&#x16F6A; &#x16F0A;&#x16F51;&#x16F71;</span> <span class='affects'>(single final at foot position right-aligned with aspiration if enough space)</span> | <span class='affects'>hmd, yna</span>

**<a id="glyph"></a>Glyph variants**

_The recommendation on whether or not to encode variants, and especially the “wart” and “dot” separately or as variants, was made in the Miao Ad-Hoc Meeting Report [L2/09-415](https://www.unicode.org/L2/L2009/09415-n3730.pdf)._  

**<a id="wart"></a>“wart” vs “dot” variants**

Some Miao consonants appear in the code charts with a “wart” attached to the glyph, usually on the left-hand side. In the Chuxiong orthography, a dot appears instead of the wart on these consonants. Because the user communities consider the appearance of the wart or dot to be a different way to write the same characters and not a difference of the character’s identity, the differences in appearance are a matter of font style. There is one other variant for 16F2F MIAO LETTER DZHA in the **Other variants** table below.

This “wart” represents a pronunciation which may be voicing or half voicing or lenition or some other sort of “reduced tension”. 

The dot-like mark containing characters and “wart” characters are never used together. 

<span class='affects'>Affects: 16F01 16F05 16F09 16F0B 16F0F 16F11 16F15 16F17 16F19 16F1B 16F1D 16F1F 16F22 16F24 16F29 16F2B 16F2D 16F2F 16F36 16F38 16F3C 16F3E 16F41 16F44 16F45 16F46 16F47</span>

Setting         | Sample          
:---   | :---------------  
default (wart)  | <span class='shim normal'>&#x16F01; &#x16F05; &#x16F09; &#x16F0B; &#x16F0F; &#x16F11; &#x16F15; &#x16F17; &#x16F19; &#x16F1B; &#x16F1D; &#x16F1F; &#x16F22; &#x16F24; &#x16F29; &#x16F2B; &#x16F2D; &#x16F2F; &#x16F36; &#x16F38; &#x16F3C; &#x16F3E; &#x16F41; &#x16F44; &#x16F45; &#x16F46; &#x16F47;</span> 
alternate (dot) | <span class='hmdd normal'>&#x16F01; &#x16F05; &#x16F09; &#x16F0B; &#x16F0F; &#x16F11; &#x16F15; &#x16F17; &#x16F19; &#x16F1B; &#x16F1D; &#x16F1F; &#x16F22; &#x16F24; &#x16F29; &#x16F2B; &#x16F2D; &#x16F2F; &#x16F36; &#x16F38; &#x16F3C; &#x16F3E; &#x16F41; &#x16F44; &#x16F45; &#x16F46; &#x16F47;</span> 

**Other variants**

Code Points        | default | variant | language
:-- | :-- | :--- | :------
<span class='affects'>3001</span> | <span class='shim normal'>&#x3001;</span> |<span class='lpo normal'>&#x3001;</span> | <span class='affects'>lpo</span>
<span class='affects'>16F02</span> | <span class='shim normal'>&#x16F02;</span> |<span class='ygp normal'>&#x16F02;</span> | <span class='affects'>ygp</span>
<span class='affects'>16F04</span> | <span class='shim normal'>&#x16F04;</span> |<span class='hmdd normal'>&#x16F04;</span> | <span class='affects'>hmd normalised</span>
<span class='affects'>16F04</span> | <span class='shim normal'>&#x16F04;</span> |<span class='lpo normal'>&#x16F04;</span> | <span class='affects'>lpo</span>
<span class='affects'>16F04</span> | <span class='shim normal'>&#x16F04;</span> | <span class='ygp normal'>&#x16F04;</span> | <span class='affects'>ygp, ywq</span>
<span class='affects'>16F05</span> | <span class='shim normal'>&#x16F05;</span> |<span class='hmdd normal'>&#x16F05;</span> | <span class='affects'>hmd normalised</span>
<span class='affects'>16F10</span> | <span class='shim normal'>&#x16F10;</span> |<span class='hmdd normal'>&#x16F10;</span> | <span class='affects'>hmd normalised</span>
<span class='affects'>16F10</span> | <span class='shim normal'>&#x16F10;</span> |<span class='lpo normal'>&#x16F10;</span> | <span class='affects'>lpo</span>
<span class='affects'>16F10</span> | <span class='shim normal'>&#x16F10;</span> | <span class='ygp normal'>&#x16F10;</span> | <span class='affects'>ygp, ywq</span>
<span class='affects'>16F11</span> | <span class='shim normal'>&#x16F11;</span> |<span class='hmdd normal'>&#x16F11;</span> | <span class='affects'>hmd normalised</span>
<span class='affects'>16F14</span> | <span class='shim normal'>&#x16F14;</span> |<span class='hmdd normal'>&#x16F14;</span> | <span class='affects'>hmd normalised</span>
<span class='affects'>16F14</span> | <span class='shim normal'>&#x16F14;</span> |<span class='ygp normal'>&#x16F14;</span> | <span class='affects'>ygp</span>
<span class='affects'>16F15</span> | <span class='shim normal'>&#x16F15;</span> |<span class='hmdd normal'>&#x16F15;</span> | <span class='affects'>hmd normalised</span>
<span class='affects'>16F23</span> | <span class='shim normal'>&#x16F23;</span> |<span class='hmdd normal'>&#x16F23;</span> | <span class='affects'>hmd normalised</span>
<span class='affects'>16F23</span> | <span class='shim normal'>&#x16F23;</span> |<span class='lpo normal'>&#x16F23;</span> | <span class='affects'>lpo</span>
<span class='affects'>16F23</span> | <span class='shim normal'>&#x16F23;</span> |<span class='ygp normal'>&#x16F23;</span> | <span class='affects'>ygp</span>
<span class='affects'>16F24</span> | <span class='shim normal'>&#x16F24;</span> |<span class='hmdd normal'>&#x16F24;</span> | <span class='affects'>hmd normalised</span>
<span class='affects'>16F2F</span> | <span class='shim normal'>&#x16F2F;</span> | <span class='ywqa normal'>&#x16F2F;</span> | <span class='affects'>ywq</span>
<span class='affects'>16F33</span> | <span class='shim normal'><font color="red">&#x16F33;</font></span><a href="#3">[3]</a> |<span class='lpo normal'>&#x16F33;</span> | <span class='affects'>lpo</span>
<span class='affects'>16F35</span> | <span class='shim normal'>&#x16F35;</span> | <span class='ywqa normal'>&#x16F35;</span><a href="#4">[4]</a> | <span class='affects'>one subgroup of ywq</span>

&#x00A0;

Code Points  | default | variant | language
:-- | :-- | :--- | :------
<span class='affects'>16F57</span> | <span class='shim normal'>&#x16F57;</span> | <span class='shim normal'   lang='hmd'>&#x16F57;</span> <span class='affects'>(flat bottom)</span> | <span class='affects'>hmd traditional, hmd normalized, hmz, lpo</span>
<span class='affects'>16F58</span> | <span class='shim normal'>&#x16F58;</span> | <span class='shim normal'   lang='lpo'>&#x16F58;</span> | <span class='affects'>lpo</span>
<span class='affects'>16F5C</span> | <span class='shim normal'>&#x16F5C;</span> | <span class='ygp normal'>&#x16F5C;</span> <span class='affects'>(near-centre stem)</span>| <span class='affects'>ygp</span>
<span class='affects'>16F5E</span> | <span class='shim normal'>&#x16F5E;</span> |<span class='hmdd normal'>&#x16F5E;</span> <span class='affects'>(flat top)</span>| <span class='affects'>hmd normalised</span>
<span class='affects'>16F5F</span> | <span class='shim normal'>&#x16F5F;</span> |<span class='hmdd normal'>&#x16F5F;</span> <span class='affects'>(flat top)</span>| <span class='affects'>hmd normalised</span>
<span class='affects'>16F60</span> | <span class='shim normal'>&#x16F60;</span> | <span class='ygp normal'>&#x16F60;</span> <span class='affects'>(near-centre stem)</span> | <span class='affects'>ygp</span>
<span class='affects'>16F73</span> | <span class='shim normal'>&#x16F73;</span> | <span class='ygp normal'>&#x16F73;</span> <span class='affects'>(near-centre stem)</span> | <span class='affects'>ygp</span>
<span class='affects'>16F74</span> | <span class='shim normal'>&#x16F74;</span> | <span class='ygp normal'>&#x16F74;</span> <span class='affects'>(near-centre stem)</span><a href="#5">[5]</a> | <span class='affects'>ygp</span>
<span class='affects'>16F7A</span> | <span class='shim normal'>&#x16F7A;</span> | <span class='hmd normal'>&#x16F7A;</span> <span class='affects'>(pointed hook)</span> | <span class='affects'>hmd traditional, hmd normalized, hmz, sfm</span>


## <a id="lang"></a>Languages currently using Miao/Pollard script

### <a id="hmd"></a>Large Flowery Miao / Dahua Miao / A-Hmao &#x005B;hmd&#x005D;

The Large Flowery Miao / Dahua Miao / A-Hmao language is the primary language that uses the Miao script.

**Resources**

_Language tag:_ `hmd`

_Opentype language system tag:_ `HMD `

_SLDR:_ [hmd](https://github.com/silnrsi/sldr/blob/master/sldr/h/hmd.xml)

_[A-Hmao (draft): Pollard/Miao script orthography notes](https://r12a.github.io/scripts/plrd/hmd.html)_

_Keyman keyboard:_ [Ahmao (SIL)](https://keyman.com/keyboards/sil_hmd_plrd)

_Picker:_ [A-Hmao picker](https://r12a.github.io/pickers/plrd-hmd/index.html)

_Keyboard.cool:_ [Miao block](https://keyboard.cool/db/miao/)

_Font:_ [Sapushan](https://software.sil.org/shimenkan/) - traditional orthography

_Font:_ [Shimenkan Guifan](https://software.sil.org/shimenkan/) - normalised orthography

_Generic Miao fonts:_ [Noto Miao](https://fonts.google.com/noto/fonts?noto.script=Plrd) and [Miao Unicode](https://github.com/phjamr/MiaoUnicode)

**_Augmented Traditional character set (Enwall version plus wart with minor changes)_**

Consonant onsets | | | | | | | | |
:-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :--
<span class='hmd normal'>&#x16F00;</span> |<span class='hmd normal'>&#x16F01;</span> | <span class='hmd normal'>&#x16F04;</span> | <span class='hmd normal'>&#x16F05;</span> | <span class='hmd normal'>&#x16F07;</span> | <span class='hmd normal'>&#x16F08;</span> | <span class='hmd normal'>&#x16F09;</span> | <span class='hmd normal'>&#x16F0A;</span> | <span class='hmd normal'>&#x16F0B;</span> | <span class='hmd normal'>&#x16F0E;</span>
16F00 | 16F01 | 16F04 | 16F05 | 16F07 | 16F08 | 16F09 | 16F0A | 16F0B | 16F0E
<span class='hmd normal'>&#x16F0F;</span> | <span class='hmd normal'>&#x16F10;</span> | <span class='hmd normal'>&#x16F11;</span> | <span class='hmd normal'>&#x16F16;</span> | <span class='hmd normal'>&#x16F17;</span> | <span class='hmd normal'>&#x16F18;</span> | <span class='hmd normal'>&#x16F19;</span> | <span class='hmd normal'>&#x16F1A;</span> | <span class='hmd normal'>&#x16F1B;</span> | <span class='hmd normal'>&#x16F1E;</span>
16F0F | 16F10 | 16F11 | 16F16 | 16F17 | 16F18 | 16F19 | 16F1A | 16F1B | 16F1E
<span class='hmd normal'>&#x16F1F;</span> | <span class='hmd normal'>&#x16F21;</span> | <span class='hmd normal'>&#x16F22;</span> | <span class='hmd normal'>&#x16F23;</span> | <span class='hmd normal'>&#x16F24;</span> | <span class='hmd normal'>&#x16F26;</span> | <span class='hmd normal'>&#x16F28;</span> | <span class='hmd normal'>&#x16F29;</span> | <span class='hmd normal'>&#x16F2E;</span> | <span class='hmd normal'>&#x16F2F;</span>
16F1F | 16F21 | 16F22 | 16F23 | 16F24 | 16F26 | 16F28 | 16F29 | 16F2E | 16F2F
<span class='hmd normal'>&#x16F33;</span> | <span class='hmd normal'>&#x16F35;</span> | <span class='hmd normal'>&#x16F37;</span> | <span class='hmd normal'>&#x16F38;</span> | <span class='hmd normal'>&#x16F3A;</span> | <span class='hmd normal'>&#x16F3B;</span> | <span class='hmd normal'>&#x16F3C;</span> | <span class='hmd normal'>&#x16F3D;</span> | <span class='hmd normal'>&#x16F3E;</span> | <span class='hmd normal'>&#x16F42;</span>
16F33 | 16F35 | 16F37 | 16F38 | 16F3A | 16F3B | 16F3C | 16F3D | 16F3E | 16F42
<span class='hmd normal'>&#x16F43;</span> | | | | | | | | |
16F43 | | | | | | | | |

Modifiers | Nasalization | Aspiration
:-- | :-- | :-- 
&#x0020; | <span class='hmd normal'>&#x16F50;</span> | <span class='hmd normal'>&#x16F51;</span>
&#x0020; | 16F50 | 16F51

Vowels and finals | | | | | | | | | &#x0020;
:-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- 
<span class='hmd normal'>&#x16F54;</span> | <span class='hmd normal'>&#x16F57;</span> | <span class='hmd normal'>&#x16F58;</span> | <span class='hmd normal'>&#x16F59;</span> | <span class='hmd normal'>&#x16F5C;</span> | <span class='hmd normal'>&#x16F5D;</span> | <span class='hmd normal'>&#x16F5E;</span> | <span class='hmd normal'>&#x16F5F;</span> | <span class='hmd normal'>&#x16F60;</span> | <span class='hmd normal'>&#x16F61;</span> 
16F54 | 16F57 | 16F58 | 16F59 | 16F5C | 16F5D | 16F5E | 16F5F | 16F60 | 16F61 
<span class='hmd normal'>&#x16F62;</span> | <span class='hmd normal'>&#x16F64;</span> | <span class='hmd normal'>&#x16F66;</span> | <span class='hmd normal'>&#x16F68;</span> | <span class='hmd normal'>&#x16F6A;</span> | <span class='hmd normal'>&#x16F6B;</span> | <span class='hmd normal'>&#x16F71;</span> | <span class='hmd normal'>&#x16F73;</span> | <span class='hmd normal'>&#x16F75;</span> | <span class='hmd normal'>&#x16F77;</span>
16F62 | 16F64 | 16F66 | 16F68 | 16F6A | 16F6B | 16F71 | 16F73 | 16F75 | 16F77
<span class='hmd normal'>&#x16F79;</span> | <span class='hmd normal'>&#x16F7A;</span> | <span class='hmd normal'>&#x16F7B;</span> | <span class='hmd normal'>&#x16F7E;</span> | | | | | |
16F79 | 16F7A | 16F7B | 16F7E | | | | | |

Positioning tone marks | |&#x0020;
:-- | :-- | :--
MIAO TONE RIGHT | MIAO TONE TOP RIGHT | MIAO TONE ABOVE 
16F8F | 16F90 | 16F91 

**_Normalised character set ([L2/10-093](https://www.unicode.org/L2/L2010/10093-n3789-miao.pdf), figure 1)_**

Consonant onsets | | | | | | | | | &#x0020;
:-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :--
<span class='hmdd normal'>&#x16F00;</span> | <span class='hmdd normal'>&#x16F01;</span> | <span class='hmdd normal'>&#x16F04;</span> | <span class='hmdd normal'>&#x16F05;</span> | <span class='hmdd normal'>&#x16F07;</span> | <span class='hmdd normal'>&#x16F08;</span> | <span class='hmdd normal'>&#x16F09;</span> | <span class='hmdd normal'>&#x16F0A;</span> | <span class='hmdd normal'>&#x16F0B;</span> | <span class='hmdd normal'>&#x16F0E;</span>     
16F00 | 16F01 | 16F04 | 16F05 | 16F07 | 16F08 | 16F09 | 16F0A | 16F0B | 16F0E
<span class='hmdd normal'>&#x16F0F;</span> | <span class='hmdd normal'>&#x16F10;</span> | <span class='hmdd normal'>&#x16F11;</span> | <span class='hmdd normal'>&#x16F14;</span> | <span class='hmdd normal'>&#x16F15;</span> | <span class='hmdd normal'>&#x16F16;</span> | <span class='hmdd normal'>&#x16F17;</span> | <span class='hmdd normal'>&#x16F18;</span> | <span class='hmdd normal'>&#x16F19;</span> | <span class='hmdd normal'>&#x16F1A;</span>
16F0F | 16F10 | 16F11 | 16F14 | 16F15 | 16F16 | 16F17 | 16F18 | 16F19 | 16F1A
<span class='hmdd normal'>&#x16F1B;</span> | <span class='hmdd normal'>&#x16F1C;</span> | <span class='hmdd normal'>&#x16F1D;</span> | <span class='hmdd normal'>&#x16F1E;</span> | <span class='hmdd normal'>&#x16F1F;</span> | <span class='hmdd normal'>&#x16F21;</span> | <span class='hmdd normal'>&#x16F22;</span> | <span class='hmdd normal'>&#x16F23;</span> | <span class='hmdd normal'>&#x16F24;</span> | <span class='hmdd normal'>&#x16F26;</span>
16F1B | 16F1C | 16F1D | 16F1E | 16F1F | 16F21 | 16F22 | 16F23 | 16F24 | 16F26
<span class='hmdd normal'>&#x16F28;</span> | <span class='hmdd normal'>&#x16F29;</span> | <span class='hmdd normal'>&#x16F2A;</span> | <span class='hmdd normal'>&#x16F2B;</span> | <span class='hmdd normal'>&#x16F2C;</span> | <span class='hmdd normal'>&#x16F2D;</span> | <span class='hmdd normal'>&#x16F2E;</span> | <span class='hmdd normal'>&#x16F2F;</span> | <span class='hmdd normal'>&#x16F33;</span> | <span class='hmdd normal'>&#x16F34;</span>
16F28 | 16F29 | 16F2A | 16F2B | 16F2C | 16F2D | 16F2E | 16F2F | 16F33 | 16F34
<span class='hmdd normal'>&#x16F35;</span> | <span class='hmdd normal'>&#x16F37;</span> | <span class='hmdd normal'>&#x16F38;</span> | <span class='hmdd normal'>&#x16F3A;</span> | <span class='hmdd normal'>&#x16F3B;</span> | <span class='hmdd normal'>&#x16F3C;</span> | <span class='hmdd normal'>&#x16F3D;</span> | <span class='hmdd normal'>&#x16F3E;</span> | <span class='hmdd normal'>&#x16F40;</span> | <span class='hmdd normal'>&#x16F41;</span>
16F35 | 16F37 | 16F38 | 16F3A | 16F3B | 16F3C | 16F3D | 16F3E | 16F40 | 16F41
<span class='hmdd normal'>&#x16F42;</span> | <span class='hmdd normal'>&#x16F43;</span> | <span class='hmdd normal'>&#x16F44;</span>
16F42 | 16F43 | 16F44 | | | | |

Modifiers | Nasalization | Aspiration
:-- | :-- | :-- 
&#x0020; | <span class='shim normal'>&#x16F50;</span> | <span class='shim normal'>&#x16F51;</span>
&#x0020; | 16F50 | 16F51

Vowels and finals | | | | | | | | | &#x0020;
:-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- 
<span class='hmdd normal'>&#x16F54;</span> | <span class='hmdd normal'>&#x16F57;</span> | <span class='hmdd normal'>&#x16F58;</span> | <span class='hmdd normal'>&#x16F59;</span> | <span class='hmdd normal'>&#x16F5C;</span> | <span class='hmdd normal'>&#x16F5E;</span> | <span class='hmdd normal'>&#x16F5F;</span> | <span class='hmdd normal'>&#x16F60;</span> | <span class='hmdd normal'>&#x16F61;</span> | <span class='hmdd normal'>&#x16F62;</span> 
16F54 | 16F57 | 16F58 | 16F59 | 16F5C | 16F5E | 16F5F | 16F60 | 16F61 | 16F62
<span class='hmdd normal'>&#x16F66;</span> | <span class='hmdd normal'>&#x16F68;</span> | <span class='hmdd normal'>&#x16F6A;</span> | <span class='hmdd normal'>&#x16F6B;</span> | <span class='hmdd normal'>&#x16F71;</span> | <span class='hmdd normal'>&#x16F73;</span> | <span class='hmdd normal'>&#x16F75;</span> | <span class='hmdd normal'>&#x16F77;</span> | <span class='hmdd normal'>&#x16F79;</span> | <span class='hmdd normal'>&#x16F7A;</span>
16F66 | 16F68 | 16F6A | 16F6B | 16F71 | 16F73 | 16F75 | 16F77 | 16F79 | 16F7A 
<span class='hmdd normal'>&#x16F7B;</span> | <span class='hmdd normal'>&#x16F7E;</span> | | | | | | | |
16F7B | 16F7E | | | | | | | |

Baseline tone marks | &#x0020; |&#x0020;|&#x0020;|&#x0020;|&#x0020;|&#x0020;
:-- | :-- | :-- | :-- | :-- | :-- | :--
<span class='hmdd normal'>&#x16F93;</span> | <span class='hmdd normal'>&#x16F94;</span> |<span class='hmdd normal'>&#x16F95;</span> |<span class='hmdd normal'>&#x16F96;</span> |<span class='hmdd normal'>&#x16F97;</span> |<span class='hmdd normal'>&#x16F98;</span> |<span class='hmdd normal'>&#x16F99;</span>  
16F93 | 16F94 | 16F95 | 16F96 | 16F97 | 16F98 | 16F99 

**_Sorting ([L2/10-093](https://www.unicode.org/L2/L2010/10093-n3789-miao.pdf), figure 1)_**

&#x26;<span class='hmdd normal'>&#x16F00;</span> &lt; <span class='hmdd normal'>&#x16F01;</span> &lt;&lt; <span class='hmdd normal'>&#x16F00;&#x16F51;</span> &lt;&lt; <span class='hmdd normal'>&#x16F50;&#x16F00;</span> &lt;&lt; <span class='hmdd normal'>&#x16F50;&#x16F01;</span> &lt;&lt; <span class='hmdd normal'>&#x16F50;&#x16F00;&#x16F51;</span> <br/>
&#x26;<span class='hmdd normal'>&#x16F0A;</span> &lt; <span class='hmdd normal'>&#x16F0B;</span> &lt;&lt; <span class='hmdd normal'>&#x16F0A;&#x16F51;</span> &lt;&lt; <span class='hmdd normal'>&#x16F50;&#x16F0A;</span> &lt;&lt; <span class='hmdd normal'>&#x16F50;&#x16F0B;</span> &lt;&lt; <span class='hmdd normal'>&#x16F50;&#x16F0A;&#x16F51;</span><br/>
&#x26;<span class='hmdd normal'>&#x16F1E;</span> &lt; <span class='hmdd normal'>&#x16F1F;</span> &lt;&lt; <span class='hmdd normal'>&#x16F1E;&#x16F51;</span> &lt;&lt; <span class='hmdd normal'>&#x16F50;&#x16F1E;</span> &lt;&lt; <span class='hmdd normal'>&#x16F50;&#x16F1F;</span> &lt;&lt; <span class='hmdd normal'>&#x16F50;&#x16F1E;&#x16F51;</span><br/>
&#x26;<span class='hmdd normal'>&#x16F2E;</span> &lt; <span class='hmdd normal'>&#x16F2F;</span> &lt;&lt; <span class='hmdd normal'>&#x16F2E;&#x16F51;</span> &lt;&lt; <span class='hmdd normal'>&#x16F50;&#x16F2E;</span> &lt;&lt; <span class='hmdd normal'>&#x16F50;&#x16F2F;</span> &lt;&lt; <span class='hmdd normal'>&#x16F50;&#x16F2E;&#x16F51;</span><br/>
&#x26;<span class='hmdd normal'>&#x16F2A;</span> &lt; <span class='hmdd normal'>&#x16F2B;</span> &lt;&lt; <span class='hmdd normal'>&#x16F2A;&#x16F51;</span> &lt;&lt; <span class='hmdd normal'>&#x16F50;&#x16F2A;</span> &lt;&lt; <span class='hmdd normal'>&#x16F50;&#x16F2B;</span> &lt;&lt; <span class='hmdd normal'>&#x16F50;&#x16F2A;&#x16F51;</span><br/>
&#x26;<span class='hmdd normal'>&#x16F1A;</span> &lt; <span class='hmdd normal'>&#x16F1B;</span> &lt;&lt; <span class='hmdd normal'>&#x16F1A;&#x16F51;</span> &lt;&lt; <span class='hmdd normal'>&#x16F50;&#x16F1A;</span> &lt;&lt; <span class='hmdd normal'>&#x16F50;&#x16F1B;</span> &lt;&lt; <span class='hmdd normal'>&#x16F50;&#x16F1A;&#x16F51;</span><br/>
&#x26;<span class='hmdd normal'>&#x16F1C;</span> &lt; <span class='hmdd normal'>&#x16F1D;</span> &lt;&lt; <span class='hmdd normal'>&#x16F1C;&#x16F51;</span> &lt;&lt; <span class='hmdd normal'>&#x16F50;&#x16F1C;</span> &lt;&lt; <span class='hmdd normal'>&#x16F50;&#x16F1D;</span> &lt;&lt; <span class='hmdd normal'>&#x16F50;&#x16F1C;&#x16F51;</span><br/>
&#x26;<span class='hmdd normal'>&#x16F37;</span> &lt; <span class='hmdd normal'>&#x16F38;</span> &lt;&lt; <span class='hmdd normal'>&#x16F37;&#x16F51;</span> &lt;&lt; <span class='hmdd normal'>&#x16F50;&#x16F37;</span> &lt;&lt; <span class='hmdd normal'>&#x16F50;&#x16F38;</span> &lt;&lt; <span class='hmdd normal'>&#x16F50;&#x16F37;&#x16F51;</span><br/>
&#x26;<span class='hmdd normal'>&#x16F0E;</span> &lt; <span class='hmdd normal'>&#x16F0F;</span> &lt;&lt; <span class='hmdd normal'>&#x16F0E;&#x16F51;</span> &lt;&lt; <span class='hmdd normal'>&#x16F50;&#x16F0E;</span> &lt;&lt; <span class='hmdd normal'>&#x16F50;&#x16F0F;</span> &lt;&lt; <span class='hmdd normal'>&#x16F50;&#x16F0E;&#x16F51;</span><br/>
&#x26;<span class='hmdd normal'>&#x16F21;</span> &lt; <span class='hmdd normal'>&#x16F22;</span> &lt;&lt; <span class='hmdd normal'>&#x16F21;&#x16F51;</span> &lt;&lt; <span class='hmdd normal'>&#x16F50;&#x16F21;</span> &lt;&lt; <span class='hmdd normal'>&#x16F50;&#x16F22;</span> &lt;&lt; <span class='hmdd normal'>&#x16F50;&#x16F21;&#x16F51;</span><br/>
&#x26;<span class='hmdd normal'>&#x16F43;</span> &lt; <span class='hmdd normal'>&#x16F44;</span> &lt;&lt; <span class='hmdd normal'>&#x16F43;&#x16F51;</span> &lt;&lt; <span class='hmdd normal'>&#x16F50;&#x16F43;</span> &lt;&lt; <span class='hmdd normal'>&#x16F50;&#x16F44;</span> &lt;&lt; <span class='hmdd normal'>&#x16F50;&#x16F43;&#x16F51;</span><br/>
&#x26;<span class='hmdd normal'>&#x16F08;</span> &lt; <span class='hmdd normal'>&#x16F09;</span> &lt;&lt; <span class='hmdd normal'>&#x16F08;&#x16F51;</span><br/>
&#x26;<span class='hmdd normal'>&#x16F3D;</span> &lt; <span class='hmdd normal'>&#x16F3E;</span> &lt;&lt; <span class='hmdd normal'>&#x16F3D;&#x16F51;</span><br/>
&#x26;<span class='hmdd normal'>&#x16F40;</span> &lt; <span class='hmdd normal'>&#x16F41;</span> &lt;&lt; <span class='hmdd normal'>&#x16F40;&#x16F51;</span><br/>
&#x26;<span class='hmdd normal'>&#x16F16;</span> &lt; <span class='hmdd normal'>&#x16F17;</span> &lt;&lt; <span class='hmdd normal'>&#x16F16;&#x16F51;</span><br/>
&#x26;<span class='hmdd normal'>&#x16F18;</span> &lt; <span class='hmdd normal'>&#x16F19;</span> &lt;&lt; <span class='hmdd normal'>&#x16F18;&#x16F51;</span><br/>
&#x26;<span class='hmdd normal'>&#x16F04;</span> &lt; <span class='hmdd normal'>&#x16F05;</span> &lt;&lt; <span class='hmdd normal'>&#x16F04;&#x16F51;</span><br/>
&#x26;<span class='hmdd normal'>&#x16F10;</span> &lt; <span class='hmdd normal'>&#x16F11;</span> &lt;&lt; <span class='hmdd normal'>&#x16F10;&#x16F51;</span><br/>
&#x26;<span class='hmdd normal'>&#x16F3B;</span> &lt; <span class='hmdd normal'>&#x16F3C;</span> &lt;&lt; <span class='hmdd normal'>&#x16F3B;&#x16F51;</span><br/>
&#x26;<span class='hmdd normal'>&#x16F2C;</span> &lt; <span class='hmdd normal'>&#x16F2D;</span> &lt;&lt; <span class='hmdd normal'>&#x16F2C;&#x16F51;</span><br/>
&#x26;<span class='hmdd normal'>&#x16F14;</span> &lt; <span class='hmdd normal'>&#x16F15;</span> &lt;&lt; <span class='hmdd normal'>&#x16F14;&#x16F51;</span><br/>
&#x26;<span class='hmdd normal'>&#x16F23;</span> &lt; <span class='hmdd normal'>&#x16F24;</span> &lt;&lt; <span class='hmdd normal'>&#x16F23;&#x16F51;</span><br/>
&#x26;<span class='hmdd normal'>&#x16F28;</span> &lt; <span class='hmdd normal'>&#x16F29;</span> &lt;&lt; <span class='hmdd normal'>&#x16F28;&#x16F51;</span><br/>
&#x26;<span class='hmdd normal'>&#x16F33;</span> &lt; <span class='hmdd normal'>&#x16F34;</span> &lt; <span class='hmdd normal'>&#x16F3A;</span> &lt; <span class='hmdd normal'>&#x16F07;</span> &lt; <span class='hmdd normal'>&#x16F26;</span> &lt; <span class='hmdd normal'>&#x16F35;</span> &lt; <span class='hmdd normal'>&#x16F42;</span><br/>
&#x26; <span class='hmdd normal'>&#x16F54;</span> &lt; <span class='hmdd normal'>&#x16F59;</span> &lt;&lt; <span class='hmdd normal'>&#x16F59;</span><span class='hmdd normal'>&#x16F6A;</span> &lt;&lt; <span class='hmdd normal'>&#x16F59;</span><span class='hmdd normal'>&#x16F7E;</span><br/>
&#x26; <span class='hmdd normal'>&#x16F73;</span> &lt; <span class='hmdd normal'>&#x16F61;</span> &lt;&lt; <span class='hmdd normal'>&#x16F61;</span><span class='hmdd normal'>&#x16F59;</span> &lt;&lt; <span class='hmdd normal'>&#x16F61;</span><span class='hmdd normal'>&#x16F57;</span> &lt;&lt; <span class='hmdd normal'>&#x16F61;</span><span class='hmdd normal'>&#x16F5E;</span> &lt;&lt; <span class='hmdd normal'>&#x16F61;</span><span class='hmdd normal'>&#x16F57;</span><span class='hmdd normal'>&#x16F7E;</span> &lt;&lt; <span class='hmdd normal'>&#x16F61;</span><span class='hmdd normal'>&#x16F59;</span><span class='hmdd normal'>&#x16F7E;</span> &lt;&lt; <span class='hmdd normal'>&#x16F61;</span><span class='hmdd normal'>&#x16F7B;</span> &lt;&lt; <span class='hmdd normal'>&#x16F61;</span><span class='hmdd normal'>&#x16F60;</span><br/>
&#x26; <span class='hmdd normal'>&#x16F6A;</span> &lt;&lt; <span class='hmdd normal'>&#x16F6A;</span><span class='hmdd normal'>&#x16F59;</span> &lt;&lt; <span class='hmdd normal'>&#x16F6A;</span><span class='hmdd normal'>&#x16F79;</span> &lt;&lt; <span class='hmdd normal'>&#x16F6A;</span><span class='hmdd normal'>&#x16F7A;</span> &lt;&lt; <span class='hmdd normal'>&#x16F6A;</span><span class='hmdd normal'>&#x16F57;</span> &lt;&lt; <span class='hmdd normal'>&#x16F6A;</span><span class='hmdd normal'>&#x16F5E;</span> &lt;&lt; <span class='hmdd normal'>&#x16F6A;</span><span class='hmdd normal'>&#x16F57;</span><span class='hmdd normal'>&#x16F7E;</span> &lt;&lt; <span class='hmdd normal'>&#x16F6A;</span><span class='hmdd normal'>&#x16F5F;</span><br/>
&#x26; <span class='hmdd normal'>&#x16F71;</span> &lt;&lt; <span class='hmdd normal'>&#x16F71;</span><span class='hmdd normal'>&#x16F57;</span> &lt;&lt; <span class='hmdd normal'>&#x16F71;</span><span class='hmdd normal'>&#x16F7E;</span> &lt;&lt; <span class='hmdd normal'>&#x16F71;</span><span class='hmdd normal'>&#x16F7A;</span><br/>
&#x26; <span class='hmdd normal'>&#x16F79;</span> &lt; <span class='hmdd normal'>&#x16F7A;</span> &lt; <span class='hmdd normal'>&#x16F7B;</span> &lt; <span class='hmdd normal'>&#x16F60;</span> &lt; <span class='hmdd normal'>&#x16F5C;</span><br/>
&#x26; <span class='hmdd normal'>&#x16F57;</span> &lt;&lt; <span class='hmdd normal'>&#x16F57;</span><span class='hmdd normal'>&#x16F7E;</span><br/>
&#x26; <span class='hmdd normal'>&#x16F58;</span> &lt; <span class='hmdd normal'>&#x16F66;</span> &lt; <span class='hmdd normal'>&#x16F68;</span> &lt; <span class='hmdd normal'>&#x16F75;</span> &lt; <span class='hmdd normal'>&#x16F77;</span> &lt; <span class='hmdd normal'>&#x16F62;</span> &lt; <span class='hmdd normal'>&#x16F6B;</span> &lt; <span class='hmdd normal'>&#x16F5E;</span> &lt; <span class='hmdd normal'>&#x16F5F; </span>

**Rendering**

See also <a href="#wart">“wart” vs “dot”</a> for special behavior. The traditional orthography uses the “wart” and the normalised orthography uses the “dot”.

See also <a href="#kern">Kerning</a> for special behavior.

See also <a href="#asp">Aspiration mark</a> for special behavior.

_Glyph variants_ (see also <a href="#glyph">Glyph variants</a>)

Setting        | Sample
:------------- | :--------------- 
default        | <span class='shim normal'>&#x16F04; &#x16F05; &#x16F10; &#x16F11; &#x16F14; &#x16F15; &#x16F23; &#x16F24; &#x16F57; &#x16F5E; &#x16F5F; &#x16F7A;</span> |
hmd alternates  | <span class='hmd normal'>&#x16F04; &#x16F05; &#x16F10; &#x16F11; &#x16F14; &#x16F15; &#x16F23; &#x16F24; &#x16F57; &#x16F5E; &#x16F5F; &#x16F7A;</span>
normalized orthography alternates      | <span class='hmdd normal'>&#x16F04; &#x16F05; &#x16F10; &#x16F11; &#x16F14; &#x16F15; &#x16F23; &#x16F24; &#x16F57; &#x16F5E; &#x16F5F; &#x16F7A;</span>

_Sample graphic (traditional orthography)_</br><img src="assets/images/hmd_MiaoHwa_861.png" title="fig:" style="width:80%;height:80%;" alt="Miao: Hwa sample" />
<figcaption>Mark 1:1-4 (UBS).</figcaption>

### <a id="hmz"></a>Sinicized Miao / Waishu Miao / Hmong Shua &#x005B;hmz&#x005D;

_Language tag:_ `hmz-Plrd`

_Opentype language system tag:_ `HMZ `

_SLDR:_ [hmz_Plrd](https://github.com/silnrsi/sldr/blob/master/sldr/h/hmz_Plrd.xml)

_Keyboard:_ none

_Font:_ [Shimenkan MGS](https://software.sil.org/shimenkan/)

**Character set**

Consonant onsets | | | | | | | | | &#x0020;
:-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :--
<span class='hmz normal'>&#x16F00;</span> | <span class='hmz normal'>&#x16F03;</span> | <span class='hmz normal'>&#x16F04;</span> | <span class='hmz normal'>&#x16F07;</span> | <span class='hmz normal'>&#x16F08;</span> | <span class='hmz normal'>&#x16F0A;</span> | <span class='hmz normal'>&#x16F0E;</span> | <span class='hmz normal'>&#x16F10;</span> | <span class='hmz normal'>&#x16F16;</span> | <span class='hmz normal'>&#x16F18;</span> 
16F00 | 16F03 | 16F04 | 16F07 | 16F08 | 16F0A | 16F0E | 16F10 | 16F16 | 16F18
<span class='hmz normal'>&#x16F1A;</span> | <span class='hmz normal'>&#x16F1E;</span> | <span class='hmz normal'>&#x16F21;</span> | <span class='hmz normal'>&#x16F23;</span> | <span class='hmz normal'>&#x16F26;</span> | <span class='hmz normal'>&#x16F28;</span> | <span class='hmz normal'>&#x16F2E;</span> | <span class='hmz normal'>&#x16F33;</span> | <span class='hmz normal'>&#x16F35;</span> | <span class='hmz normal'>&#x16F37;</span> 
16F1A | 16F1E | 16F21 | 16F23 | 16F26 | 16F28 | 16F2E | 16F33 | 16F35 | 16F37
<span class='hmz normal'>&#x16F3A;</span> | <span class='hmz normal'>&#x16F3B;</span> | <span class='hmz normal'>&#x16F3D;</span> | <span class='hmz normal'>&#x16F42;</span> | <span class='hmz normal'>&#x16F43;</span> | | | | | 
16F3A | 16F3B | 16F3D | 16F42 | 16F43 | | | | | 

Vowels and finals | | | | | | | | | &#x0020;
:-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- 
<span class='hmz normal'>&#x16F54;</span> | <span class='hmz normal'>&#x16F57;</span> | <span class='hmz normal'>&#x16F58;</span> | <span class='hmz normal'>&#x16F59;</span> | <span class='hmz normal'>&#x16F5D;</span> | <span class='hmz normal'>&#x16F5E;</span> | <span class='hmz normal'>&#x16F5F;</span> | <span class='hmz normal'>&#x16F60;</span> | <span class='hmz normal'>&#x16F61;</span> | <span class='hmz normal'>&#x16F62;</span> 
16F54 | 16F57 | 16F58 | 16F59 | 16F5D | 16F5E | 16F5F | 16F60 | 16F61 | 16F62
<span class='hmz normal'>&#x16F66;</span> | <span class='hmz normal'>&#x16F68;</span> | <span class='hmz normal'>&#x16F6A;</span> | <span class='hmz normal'>&#x16F6B;</span> | <span class='hmz normal'>&#x16F71;</span> | <span class='hmz normal'>&#x16F75;</span> | <span class='hmz normal'>&#x16F77;</span> | <span class='hmz normal'>&#x16F7A;</span> | <span class='hmz normal'>&#x16F7B;</span> | <span class='hmz normal'>&#x16F7E;</span> 
16F66 | 16F68 | 16F6A | 16F6B | 16F71 | 16F75 | 16F77 | 16F7A | 16F7B | 16F7E

Modifiers | Nasalization | Aspiration
:-- | :-- | :-- 
&#x0020; | <span class='hmz normal'>&#x16F50;</span> | <span class='hmz normal'>&#x16F51;</span>
&#x0020; | 16F50 | 16F51

Positioning tone marks | |&#x0020;
:-- | :-- | :-- 
MIAO TONE RIGHT | MIAO TONE TOP RIGHT | MIAO TONE ABOVE 
16F8F | 16F90 | 16F91 

**Rendering**

See also <a href="#asp">Aspiration mark</a> for special behavior.

_Glyph variants_ (see also <a href="#glyph">Glyph variants</a>)

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

**_Character set_**

Consonant onsets | | | | | | | | | &#x0020;
:-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :--
<span class='lpo normal'>&#x16F00;</span> | <span class='lpo normal'>&#x16F02;</span> | <span class='lpo normal'>&#x16F04;</span> | <span class='lpo normal'>&#x16F07;</span> | <span class='lpo normal'>&#x16F08;</span> | <span class='lpo normal'>&#x16F0A;</span> | <span class='lpo normal'>&#x16F0D;</span> | <span class='lpo normal'>&#x16F10;</span> | <span class='lpo normal'>&#x16F16;</span> | <span class='lpo normal'>&#x16F18;</span>
16F00 | 16F02 | 16F04 | 16F07 | 16F08 | 16F0A | 16F0D | 16F10 | 16F16 | 16F18 
<span class='lpo normal'>&#x16F1E;</span> | <span class='lpo normal'>&#x16F20;</span> | <span class='lpo normal'>&#x16F23;</span> | <span class='lpo normal'>&#x16F26;</span> | <span class='lpo normal'>&#x16F28;</span> | <span class='lpo normal'>&#x16F2E;</span> | <span class='lpo normal'>&#x16F30;</span> | <span class='lpo normal'>&#x16F33;</span> | <span class='lpo normal'>&#x16F35;</span> | <span class='lpo normal'>&#x16F37;</span>
16F1E | 16F20 | 16F23 | 16F26 | 16F28 | 16F2E | 16F30 | 16F33 | 16F35 | 16F37
<span class='lpo normal'>&#x16F39;</span> | <span class='lpo normal'>&#x16F3A;</span> | <span class='lpo normal'>&#x16F3B;</span> | <span class='lpo normal'>&#x16F3D;</span> | <span class='lpo normal'>&#x16F42;</span> |<span class='lpo normal'>&#x16F43;</span> |
16F39 | 16F3A | 16F3B | 16F3D | 16F42 | 16F43 | 

Modifiers | Aspiration
:-- | :--  
&#x0020; | <span class='hmd normal'>&#x16F51;</span>
&#x0020; | 16F51

Vowels and finals | | | | | | | | |&#x0020;
:-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- 
<span class='lpo normal'>&#x16F54;</span> | <span class='lpo normal'>&#x16F55;</span> | <span class='lpo normal'>&#x16F57;</span>| <span class='lpo normal'>&#x16F58;</span>| <span class='lpo normal'>&#x16F59;</span> | <span class='lpo normal'>&#x16F5A;</span> | <span class='lpo normal'>&#x16F5C;</span> | <span class='lpo normal'>&#x16F5D;</span> | <span class='lpo normal'>&#x16F61;</span> | <span class='lpo normal'>&#x16F62;</span> 
16F54 | 16F55 | 16F57 | 16F58 | 16F59 | 16F5A | 16F5C | 16F5D | 16F61 | 16F62  
<span class='lpo normal'>&#x16F66;</span> |<span class='lpo normal'>&#x16F67;</span> | <span class='lpo normal'>&#x16F68;</span> | <span class='lpo normal'>&#x16F6A;</span> | <span class='lpo normal'>&#x16F6B;</span> | <span class='lpo normal'>&#x16F6E;</span> | <span class='lpo normal'>&#x16F71;</span> | <span class='lpo normal'>&#x16F72;</span> | <span class='lpo normal'>&#x16F73;</span> | <span class='lpo normal'>&#x16F74;</span>
16F66 | 16F67 | 16F68 | 16F6A | 16F6B | 16F6E | 16F71 | 16F72 | 16F73 | 16F74 
<span class='lpo normal'>&#x16F76;</span> | <span class='lpo normal'>&#x16F78;</span> | <span class='lpo normal'>&#x16F79;</span> | <span class='lpo normal'>&#x16F7A;</span> | <span class='lpo normal'>&#x16F7B;</span> | <span class='lpo normal'>&#x16F7E;</span> | | | |
16F76 | 16F78 | 16F79 | 16F7A | 16F7B | 16F7E | | | |

Positioning tone marks |&#x0020;
:-- | :-- 
MIAO TONE TOP RIGHT | MIAO TONE ABOVE 
16F90 | 16F91 

**Rendering**

_Glyph variants_ (see also <a href="#glyph">Glyph variants</a>)

Setting        | Sample
:------ | :---------------
default        | <span class='shim normal'>&#x16F04; &#x16F10; &#x16F23; &#x16F33; &#x16F57; &#x16F58; &#x3001;</span>
alternate      | <span class='lpo normal'>&#x16F04; &#x16F10; &#x16F23; &#x16F33; &#x16F57; &#x16F58; &#x3001;</span>

_Sample graphic_</br><img src="assets/images/lpo_LisuEastern_735.png" title="fig:" style="width:80%;height:80%;" alt="Lisu: Eastern sample" />
<figcaption>Mark 1:1-4 (UBS).</figcaption>

### <a id="sfm"></a>Xiaohua Miao / Small Flowery Miao &#x005B;sfm&#x005D;

**Resources**

_Language tag:_ `sfm`

_Opentype language system tag:_ `SFM `

_SLDR:_ [sfm](https://github.com/silnrsi/sldr/blob/master/sldr/s/sfm.xml)

_Keyman keyboard:_ none

_Font:_ [Shimenkan MAS](https://software.sil.org/shimenkan/) 

**_Character set ([L2/17-345](https://www.unicode.org/L2/L2017/17345-n4845-miao-add.pdf), figure 11)_**

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

Positioning tone marks | | &#x0020;
:-- | :-- | :-- 
MIAO TONE RIGHT | MIAO TONE TOP RIGHT | MIAO TONE ABOVE 
16F8F | 16F90 | 16F91

**_Sorting ([L2/17-345](https://www.unicode.org/L2/L2017/17345-n4845-miao-add.pdf), figure 11)_**

_Ordering of vowel digraphs is not the same as the chart, but it seemed to make the most sense to the author._

&#x26;<span class='sfm normal'>&#x16F2E;</span> &lt;&lt;<span class='sfm normal'>&#x16F2E;&#x16F51;</span> &lt;&lt; <span class='sfm normal'>&#x16F2F;</span> &lt;&lt;<span class='sfm normal'>&#x16F50;&#x16F2E;</span> &lt;&lt; <span class='sfm normal'>&#x16F50;&#x16F2E;&#x16F51;</span> &lt;&lt; <span class='sfm normal'>&#x16F50;&#x16F2F;</span></br> 
&#x26;<span class='sfm normal'>&#x16F07;</span> &lt; <span class='sfm normal'>&#x16F26;</span> &lt;&lt; <span class='sfm normal'>&#x16F26;&#x16F51;</span></br> 
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
&#x26;<span class='sfm normal'>&#x16F3A;</span> &lt; <span class='sfm normal'>&#x16F0A;</span> &lt;&lt; <span class='sfm normal'>&#x16F0A;&#x16F51;</span> &lt;&lt; <span class='sfm normal'>&#x16F0B;</span> &lt;&lt; <span class='sfm normal'>&#x16F50;&#x16F0A;</span> &lt;&lt; <span class='sfm normal'>&#x16F50;&#x16F0A;&#x16F51;</span> &lt;&lt; <span class='sfm normal'>&#x16F50;&#x16F0B;</span></br> 
&#x26;<span class='sfm normal'>&#x16F0E;</span> &lt;&lt; <span class='sfm normal'>&#x16F0E;&#x16F51;</span> &lt;&lt; <span class='sfm normal'>&#x16F0F;</span> &lt;&lt; <span class='sfm normal'>&#x16F50;&#x16F0E;</span> &lt;&lt; <span class='sfm normal'>&#x16F50;&#x16F0E;&#x16F51;</span> &lt;&lt; <span class='sfm normal'>&#x16F50;&#x16F0F;</span></br> 
&#x26;<span class='sfm normal'>&#x16F37;</span> &lt;&lt; <span class='sfm normal'>&#x16F37;&#x16F51;</span> &lt;&lt; <span class='sfm normal'>&#x16F38;</span> &lt;&lt; <span class='sfm normal'>&#x16F50;&#x16F37;</span> &lt;&lt; <span class='sfm normal'>&#x16F50;&#x16F37;&#x16F51;</span> &lt;&lt; <span class='sfm normal'>&#x16F50;&#x16F38;</span></br> 
&#x26;<span class='sfm normal'>&#x16F42;</span> &lt; <span class='sfm normal'>&#x16F08;</span> &lt; <span class='sfm normal'>&#x16F3D;</span></br> 
&#x26;<span class='sfm normal'>&#x16F32;</span> &lt;&lt; <span class='sfm normal'>&#x16F32;&#x16F51;</span> &lt;&lt; <span class='sfm normal'>&#x16F47;</span> &lt;&lt; <span class='sfm normal'>&#x16F50;&#x16F32;</span> &lt;&lt; <span class='sfm normal'>&#x16F50;&#x16F32;&#x16F51;</span> &lt;&lt; <span class='sfm normal'>&#x16F50;&#x16F47;</span></br> 
&#x26;<span class='sfm normal'>&#x16F54;</span> &lt; <span class='sfm normal'>&#x16F79;</span> &lt; <span class='sfm normal'>&#x16F7B;</span> &lt; <span class='sfm normal'>&#x16F5D;&#x16F66;</span></br> 
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

See also <a href="#asp">Aspiration mark</a> for special behavior.

_Glyph variants_ (see also <a href="#glyph">Glyph variants</a>)

Setting        | Sample
:------ | :---------------
default        | <span class='shim normal'>&#x16F7A;</span>
alternate      | <span class='sfm normal'>&#x16F7A;</span>

_Sample graphic_</br><img src="assets/images/sfm_XiaohuaMiao_Fig14.png" title="fig:" style="width:80%;height:80%;" alt="Xiaohua Miao sample" />
<figcaption>John (Figure 14, [L2/17-345](https://www.unicode.org/L2/L2017/17345-n4845-miao-add.pdf)).</figcaption>

### <a id="ygp"></a>Bai Yi / Gepo &#x005B;ygp&#x005D;

_Language tag:_ `ygp`

_Opentype language system tag:_ `YGP `

_SLDR:_ [ygp](https://github.com/silnrsi/sldr/blob/master/sldr/y/ygp.xml)

_Keyman keyboard:_ [ygp](https://keyman.com/keyboards/sil_ygp_plrd)

_Font:_ [Shimenkan GSM](https://software.sil.org/shimenkan/)

**_Character set ([L2/17-345](https://www.unicode.org/L2/L2017/17345-n4845-miao-add.pdf), figure 2)_**

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

**_Sorting ([L2/17-345](https://www.unicode.org/L2/L2017/17345-n4845-miao-add.pdf), figure 2)_**

&#x26;<span class='ygp normal'>&#x16F43;</span> &lt; <span class='ygp normal'>&#x16F16;</span></br>
&#x26;<span class='ygp normal'>&#x16F00;</span> &lt;&lt; <span class='ygp normal'>&#x16F00;&#x16F51;</span> &lt;&lt; <span class='ygp normal'>&#x16F50;&#x16F00;</span></br>
&#x26;<span class='ygp normal'>&#x16F02;</span> &lt; <span class='ygp normal'>&#x16F48;</span></br>
&#x26;<span class='ygp normal'>&#x16F0A;</span> &lt;&lt; <span class='ygp normal'>&#x16F0A;&#x16F51;</span> &lt;&lt; <span class='ygp normal'>&#x16F50;&#x16F0A;</span></br>
&#x26;<span class='ygp normal'>&#x16F49;</span> &lt; <span class='ygp normal'>&#x16F37;</span> &lt;&lt; <span class='ygp normal'>&#x16F37;&#x16F51;</span> &lt;&lt; <span class='ygp normal'>&#x16F50;&#x16F37;</span></br>
&#x26;<span class='ygp normal'>&#x16F07;</span> &lt; <span class='ygp normal'>&#x16F18;</span> &lt; <span class='ygp normal'>&#x16F32;</span></br>
&#x26;<span class='ygp normal'>&#x16F2E;</span> &lt;&lt; <span class='ygp normal'>&#x16F2E;&#x16F51;</span> &lt;&lt; <span class='ygp normal'>&#x16F50;&#x16F2E;</span></br>
&#x26;<span class='ygp normal'>&#x16F2A;</span> &lt; <span class='ygp normal'>&#x16F1E;</span> &lt;&lt; <span class='ygp normal'>&#x16F1E;&#x16F51;</span> &lt;&lt; <span class='ygp normal'>&#x16F50;&#x16F1E;</span></br>
&#x26;<span class='ygp normal'>&#x16F4A;</span> &lt; <span class='ygp normal'>&#x16F0E;</span> &lt;&lt; <span class='ygp normal'>&#x16F0E;&#x16F51;</span> &lt;&lt; <span class='ygp normal'>&#x16F50;&#x16F0E;</span></br>
&#x26;<span class='ygp normal'>&#x16F08;</span> &lt; <span class='ygp normal'>&#x16F3D;</span> &lt; <span class='ygp normal'>&#x16F42;</span> &lt; <span class='ygp normal'>&#x16F04;</span> &lt; <span class='ygp normal'>&#x16F10;</span> &lt; <span class='ygp normal'>&#x16F14;</span> &lt; <span class='ygp normal'>&#x16F12;</span> &lt; <span class='ygp normal'>&#x16F3B;</span> &lt; <span class='ygp normal'>&#x16F3A;</span> &lt; <span class='ygp normal'>&#x16F33;</span></br>
&#x26;<span class='ygp normal'>&#x16F26;</span> &lt;&lt; <span class='ygp normal'>&#x16F26;&#x16F51;</span></br>
&#x26;<span class='ygp normal'>&#x16F28;</span> &lt; <span class='ygp normal'>&#x16F23;</span> &lt; <span class='ygp normal'>&#x16F35;</span></br>
&#x26;<span class='ygp normal'>&#x16F54;</span> &lt; <span class='ygp normal'>&#x16F7A;</span></br>
&#x26;<span class='ygp normal'>&#x16F61;</span> &lt;&lt; <span class='ygp normal'>&#x16F61;&#x16F54;</span> &lt;&lt; <span class='ygp normal'>&#x16F61;&#x16F7A;</span> &lt;&lt; <span class='ygp normal'>&#x16F61;&#x16F79;</span> &lt;&lt; <span class='ygp normal'>&#x16F61;&#x16F59;</span> &lt;&lt; <span class='ygp normal'>&#x16F61;&#x16F7B;</span> &lt;&lt; <span class='ygp normal'>&#x16F61;&#x16F66;</span> &lt;&lt; <span class='ygp normal'>&#x16F61;&#x16F57;</span> &lt;&lt; <span class='ygp normal'>&#x16F61;&#x16F58;</span> &lt;&lt; <span class='ygp normal'>&#x16F61;&#x16F7E; </span></br>
&#x26;<span class='ygp normal'>&#x16F79; </span> &lt; <span class='ygp normal'>&#x16F59;</span> &lt;&lt; <span class='ygp normal'>&#x16F59;&#x16F7E;</span></br>
&#x26;<span class='ygp normal'>&#x16F6A;</span> &lt;&lt; <span class='ygp normal'>&#x16F6A;&#x16F54;</span> &lt;&lt; <span class='ygp normal'>&#x16F6A;&#x16F7A;</span> &lt;&lt; <span class='ygp normal'>&#x16F6A;&#x16F79;</span> &lt;&lt; <span class='ygp normal'>&#x16F6A;&#x16F59;</span> &lt;&lt; <span class='ygp normal'>&#x16F6A;&#x16F7B;</span> &lt;&lt; <span class='ygp normal'>&#x16F6A;&#x16F66;</span> &lt;&lt; <span class='ygp normal'>&#x16F6A;&#x16F57;</span> &lt;&lt; <span class='ygp normal'>&#x16F6A;&#x16F58;</span> &lt;&lt; <span class='ygp normal'>&#x16F6A;&#x16F7E; </span></br>
&#x26;<span class='ygp normal'>&#x16F71;</span> &lt; <span class='ygp normal'>&#x16F5D;</span></br>
&#x26;<span class='ygp normal'>&#x16F5C;</span> &lt;&lt; <span class='ygp normal'>&#x16F5C;&#x16F5D;</span></br>
&#x26;<span class='ygp normal'>&#x16F73;</span> &lt; <span class='ygp normal'>&#x16F60;</span> &lt; <span class='ygp normal'>&#x16F86;</span> &lt; <span class='ygp normal'>&#x16F85;</span> &lt; <span class='ygp normal'>&#x16F76;</span> &lt; <span class='ygp normal'>&#x16F7B;</span> &lt; <span class='ygp normal'>&#x16F66;</span> &lt; <span class='ygp normal'>&#x16F84;</span> &lt; <span class='ygp normal'>&#x16F83;</span> &lt; <span class='ygp normal'>&#x16F77;</span> &lt; <span class='ygp normal'>&#x16F75;</span> &lt; <span class='ygp normal'>&#x16F81;</span> &lt; <span class='ygp normal'>&#x16F57;</span> &lt; <span class='ygp normal'>&#x16F58;</span> &lt; <span class='ygp normal'>&#x16F68;</span> &lt; <span class='ygp normal'>&#x16F87;</span>

**Rendering**

See also <a href="#kern">Kerning</a> for special behavior.

_Glyph variants_ (see also <a href="#glyph">Glyph variants</a>)

Setting        | Sample
:------ | :---------------
default        | <span class='shim normal'>&#x16F02; &#x16F04; &#x16F10; &#x16F14; &#x16F23; &#x16F5C; &#x16F60; &#x16F73;</span>
alternate      | <span class='ygp normal'>&#x16F02; &#x16F04; &#x16F10; &#x16F14; &#x16F23; &#x16F5C; &#x16F60; &#x16F73;</span>

_Sample text taken from [L2/17-345](https://www.unicode.org/L2/L2017/17345-n4845-miao-add.pdf), figure 1._

Setting        | Sample           | Code Points
:-- | :--- | :---------
ygp | <span class='ygp normal'>&#x16F48;&#x16F66;&#x16F90; &#x16F2A;&#x16F5C;&#x16F91; &#x16F48;&#x16F85; &#x16F2E;&#x16F51;&#x16F5C;&#x16F91; &#x16F32;&#x16F61;&#x16F7B;&#x16F90;</span> | 16F48 16F66 16F90 0020 16F2A 16F5C 16F91 0020 16F48 16F85 0020 16F2E 16F51 16F5C 16F91 0020 16F32 16F61 16F7B 16F90

_Sample graphic_</br><img src="assets/images/ygp_Kopu_674.png" title="fig:" style="width:80%;height:80%;" alt="Kopu sample" />
<figcaption>Mark 1:1-4 (UBS).</figcaption>

### <a id="yna"></a>Gan Yi / Dry Yi / Aluo / Laka &#x005B;yna&#x005D;

**Resources**

_Language tag:_ `yna`

_Opentype language system tag:_ `YNA `

_SLDR:_ [yna](https://github.com/silnrsi/sldr/blob/master/sldr/y/yna.xml)

_Keyman keyboard:_ [yna](https://keyman.com/keyboards/sil_yna_plrd)

_Font:_ [Shimenkan Zonghe](https://software.sil.org/shimenkan/)

**_Character set ([L2/17-345](https://www.unicode.org/L2/L2017/17345-n4845-miao-add.pdf), figure 10)_**

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

Vowels and finals | | | | | | | | |&#x0020;
:-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- | :-- 
<span class='yna normal'>&#x16F54;</span> | <span class='yna normal'>&#x16F58;</span> | <span class='yna normal'>&#x16F59;</span> | <span class='yna normal'>&#x16F5C;</span> | <span class='yna normal'>&#x16F5D;</span> | <span class='yna normal'>&#x16F5E;</span> | <span class='yna normal'>&#x16F61;</span> | <span class='yna normal'>&#x16F62;</span> | <span class='yna normal'>&#x16F66;</span> | <span class='yna normal'>&#x16F67;</span> 
16F54 | 16F58 | 16F59 | 16F5C | 16F5D | 16F5E | 16F61 | 16F62 | 16F66 | 16F67
<span class='yna normal'>&#x16F68;</span> | <span class='yna normal'>&#x16F6A;</span> | <span class='yna normal'>&#x16F6B;</span> | <span class='yna normal'>&#x16F6E;</span> | <span class='yna normal'>&#x16F71;</span> | <span class='yna normal'>&#x16F73;</span> | <span class='yna normal'>&#x16F74;</span> | <span class='yna normal'>&#x16F75;</span> | <span class='yna normal'>&#x16F76;</span> | <span class='yna normal'>&#x16F77;</span>
16F68 | 16F6A | 16F6B | 16F6E | 16F71 | 16F73 | 16F74 | 16F75 | 16F76 | 16F77
<span class='yna normal'>&#x16F79;</span> | <span class='yna normal'>&#x16F7B;</span> | <span class='yna normal'>&#x16F7E;</span> | <span class='yna normal'>&#x16F81;</span> | <span class='yna normal'>&#x16F82;</span>
16F79 | 16F7B | 16F7E | 16F81 | 16F82

Positioning tone marks | | |&#x0020;
:-- | :-- | :-- | :-- 
MIAO TONE RIGHT | MIAO TONE TOP RIGHT | MIAO TONE ABOVE | MIAO TONE BELOW
16F8F | 16F90 | 16F91 | 16F92

**_Sorting ([L2/17-345](https://www.unicode.org/L2/L2017/17345-n4845-miao-add.pdf), figure 10)_**

&#x26;<span class='yna normal'>&#x16F00;</span> &lt;&lt; <span class='yna normal'>&#x16F02;</span> &lt;&lt; <span class='yna normal'>&#x16F00;&#x16F51;</span><br/>
&#x26;<span class='yna normal'>&#x16F0A;</span> &lt;&lt; <span class='yna normal'>&#x16F0D;</span> &lt;&lt; <span class='yna normal'>&#x16F0A;&#x16F51;</span><br/>
&#x26;<span class='yna normal'>&#x16F1E;</span> &lt;&lt; <span class='yna normal'>&#x16F20;</span> &lt;&lt; <span class='yna normal'>&#x16F1E;&#x16F51;</span><br/>
&#x26;<span class='yna normal'>&#x16F2E;</span> &lt;&lt; <span class='yna normal'>&#x16F0E;</span> &lt;&lt; <span class='yna normal'>&#x16F2E;&#x16F51;</span><br/>
&#x26;<span class='yna normal'>&#x16F37;</span> &lt;&lt; <span class='yna normal'>&#x16F39;</span> &lt;&lt; <span class='yna normal'>&#x16F37;&#x16F51;</span><br/>
&#x26;<span class='yna normal'>&#x16F08;</span> &lt; <span class='yna normal'>&#x16F07;</span><br/>
&#x26;<span class='yna normal'>&#x16F26;</span> &lt;&lt; <span class='yna normal'>&#x16F26;&#x16F51;</span><br/>
&#x26;<span class='yna normal'>&#x16F04;</span> &lt; <span class='yna normal'>&#x16F10;</span> &lt;&lt; <span class='yna normal'>&#x16F10;&#x16F51;</span> &lt;&lt; <span class='yna normal'>&#x16F10;&#x16F4F;</span><br/>
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

_Sample text taken from [L2/17-345](https://www.unicode.org/L2/L2017/17345-n4845-miao-add.pdf), figure 8._

Setting        | Sample           | Code Points
:-- | :-- | :---------
yna | <span class='yna normal'>&#x16F10;&#x16F4F;&#x16F7B;&#x16F91; &#x16F2E;&#x16F51;&#x16F5C;&#x16F90; &#x16F2E;&#x16F61;&#x16F59;</span> | 16F10 16F4F 16F7B 16F91 0020 16F2E 16F51 16F5C 16F90 0020 16F2E 16F61 16F59

_Sample graphic_</br><img src="assets/images/yna_Laka_713.png" title="fig:" style="width:80%;height:80%;" alt="Laka sample" />
<figcaption>Mark 1:1-4 (UBS).</figcaption>

### <a id="ywq"></a>Hei Yi / Black Yi / Wuding-Luquan Yi / Nasu &#x005B;ywq&#x005D;

**Resources**

_Language tag:_ `ywq`

_Opentype language system tag:_ `YWQ `

_SLDR:_ [ywq](https://github.com/silnrsi/sldr/blob/master/sldr/y/ywq.xml)

_Keyman keyboard:_ [ywq](https://keyman.com/keyboards/sil_ywq_plrd)

_Font:_ [Salaowu](https://software.sil.org/shimenkan/) - normalised orthography

**_Character set ([L2/17-345](https://www.unicode.org/L2/L2017/17345-n4845-miao-add.pdf), figure 5)_**

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

**_Sorting ([L2/17-345](https://www.unicode.org/L2/L2017/17345-n4845-miao-add.pdf), figure 5)_**

_Some of the vowel "digraphs" are what made sense to the author, not as the chart listed them._

&#x26;<span class='shim normal'>&#x16F43;</span> &lt; <span class='shim normal'>&#x16F28;</span></br>
&#x26;<span class='shim normal'>&#x16F00;</span> &lt; <span class='shim normal'>&#x16F02;</span> &lt;&lt; <span class='shim normal'>&#x16F50;&#x16F00;</span> &lt;&lt; <span class='shim normal'>&#x16F00;&#x16F51;</span></br>
&#x26;<span class='shim normal'>&#x16F07;</span> &lt; <span class='shim normal'>&#x16F26;</span> &lt;&lt; <span class='shim normal'>&#x16F26;&#x16F51;</span></br>
&#x26;<span class='shim normal'>&#x16F16;</span> &lt; <span class='shim normal'>&#x16F18;</span></br>
&#x26;<span class='shim normal'>&#x16F2E;</span> &lt; <span class='shim normal'>&#x16F50;&#x16F2E;</span> &lt;&lt; <span class='shim normal'>&#x16F2E;&#x16F51;</span></br>
&#x26;<span class='shim normal'>&#x16F1E;</span> &lt;&lt; <span class='shim normal'>&#x16F50;&#x16F1E;</span> &lt;&lt; <span class='shim normal'>&#x16F1E;&#x16F51;</span></br>
&#x26;<span class='shim normal'>&#x16F21;</span> &lt; <span class='shim normal'>&#x16F30;</span></br>
&#x26;<span class='shim normal'>&#x16F31;</span> &lt;&lt; <span class='shim normal'>&#x16F31;&#x16F51;</span></br>
&#x26;<span class='shim normal'>&#x16F0E;</span> &lt;&lt; <span class='shim normal'>&#x16F50;&#x16F0E;</span> &lt;&lt; <span class='shim normal'>&#x16F0E;&#x16F51;</span></br>
&#x26;<span class='shim normal'>&#x16F39;</span> &lt; <span class='shim normal'>&#x16F37;</span> &lt;&lt; <span class='shim normal'>&#x16F50;&#x16F37;</span> &lt;&lt; <span class='shim normal'>&#x16F37;&#x16F51;</span></br>
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

_Glyph variants_ (see also <a href="#glyph">Glyph variants</a>)

Setting        | Sample
:------ | :--------------- 
default        | <span class='shim normal'>&#x16F04; &#x16F10; &#x16F2F; &#x16F35;</span>
traditional      | <span class='shim normal'>&#x16F04; &#x16F10; &#x16F2F; &#x16F35;</span>
normalized      | <span class='ywqa normal'>&#x16F04; &#x16F10; &#x16F2F; &#x16F35;</span>

_Sample text taken from [L2/17-345](https://www.unicode.org/L2/L2017/17345-n4845-miao-add.pdf), figure 7._

Setting        | Sample           | Code Points
:-- | :-- | :---------
ywq | <span class='shim normal'>&#x16F0D;&#x16F73;&#x16F90; &#x16F21;&#x16F58; &#x16F12;&#x16F7B;&#x16F91; &#x16F30;&#x16F59;&#x16F5C;&#x16F91;</span> | 16F0D 16F73 16F90 0020 16F21 16F58 0020 16F12 16F7B 16F91 0020 16F30 16F59 16F5C 16F91

_Sample graphic_</br><img src="assets/images/ywq_Nosu_972.png" title="fig:" style="width:80%;height:80%;" alt="Nosu sample" />
<figcaption>Mark 1:1-4 (UBS).</figcaption>

## <a id="former"></a>Languages formerly using Miao/Pollard script

### <a id="ktp"></a>Kaduo / Kado &#x005B;ktp&#x005D;

**Resources**

_Language tag:_ `ktp`

**Character set**

Unknown

Modifiers | Nasalization | Aspiration
:-- | :-- | :-- 
&#x0020; | <span class='shim normal'>&#x16F50;</span> | <span class='shim normal'>&#x16F51;</span>
&#x0020; | 16F50 | 16F51

Positioning tone marks  |&#x0020;
:-- | :-- 
MIAO TONE TOP RIGHT | MIAO TONE ABOVE 
16F90 | 16F91

**Rendering**

Unknown

_Sample graphic_</br><img src="assets/images/ktp_Kado_600.png" title="fig:" style="width:80%;height:80%;" alt="Kado sample" />
<figcaption>Luke 3:1-4 (UBS).</figcaption>

### <a id="mww"></a>Hmong Daw / White Miao / Sichuan Miao &#x005B;mww&#x005D;

**Resources**

_Language tag:_ `mww-Plrd`

_Opentype language system tag:_ `MWW `

_No further information_

## <a id="ack"></a>Acknowledgements

The following people have generously offered feedback for this document: Eiso Chan, Adrian Cheuk, Martin Hosken, and Richard Ishida.

## <a id="ref"></a>References

Chung, Jeremiah Y.S. and Eric Drewry. undated. 2012 (or later). [The Uses and Users of the Miao Script](https://www.academia.edu/93203752/The_Uses_and_Users_of_the_Miao_Script).

Enwall, Joakim. 1994/1995. _A myth become reality: History and development of the Miao written
language._ Volumes 1 and 2. Stockholm East Asian monographs no. 5-6., Institute of Oriental
Languages, Stockholm University, Sweden.

United Bible Societies. 1972. [The Book of a Thousand Tongues](https://archive.org/details/B-001-001-424/page/2/mode/2up)

[L2/97-104](http://www.unicode.org/L2/L1997/97104-Pollard.pdf) John H. Jenkins.  21 May 1997. Proposal to add Pollard to Unicode/ISO-IEC 10646

[L2/07-299](http://www.unicode.org/cgi-bin/GetMatchingDocs.pl?L2/07-299) China. 2007-09-14. Preliminary proposal for encoding the Northeastern Yunnan Simple Miao script 

[L2/09-253](https://www.unicode.org/L2/L2009/09253r-n3669r-miao.pdf) China. 2009-10-01. Proposal for encoding the Miao script 

[L2/09-415](https://www.unicode.org/L2/L2009/09415-n3730.pdf) Miao Ad‐hoc committee. 2009-10-28. Miao Ad-Hoc Meeting Report 

[L2/10-049](http://www.unicode.org/cgi-bin/GetMatchingDocs.pl?L2/10-049) Michael Everson, Erich Fickle, and Martin Hosken. 2010-01-28. Toward a proposal for encoding the Miao script in the SMP of the UCS 

[L2/10-093](https://www.unicode.org/L2/L2010/10093-n3789-miao.pdf) China, Ireland, and UK. 2010-03-26. Final proposal for encoding the Miao script in the SMP of the UCS 

[L2/17-345](https://www.unicode.org/L2/L2017/17345-n4845-miao-add.pdf) Adrian Cheuk. 2017-10-03. Proposal for additions to the Miao script 

---

<a id="1">1</a> The distinctions made here for languages with &#x201c;current&#x201d; use and &#x201c;former&#x201d; use are based on information found in [The Uses and Users of the Miao Script](https://www.academia.edu/93203752/The_Uses_and_Users_of_the_Miao_Script). However, that document wrongly indicates that `sfm` and `yna` are not in modern use.

<a id="2">2</a> A _vowel cluster_ may include a nasal coda (the third V), but for rendering purposes it is treated the same as a vowel.

<a id="3">3</a> This variant glyph is more common than the one in the Unicode codecharts.

<a id="4">4</a> This rare, but distinctive, variant glyph is so different, perhaps it could be considered for encoding.

<a id="5">5</a> Current fonts do not support this variant glyph.