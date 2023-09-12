# A strategy for deprecating SIL PUA characters

<- [Back to Intro](https://github.com/silnrsi/silpua/)

## Overview

Some of the character assignments made by the SIL PUA committee are temporary — intended to be used only until such time as the character is accepted into the Unicode standard. As part of such acceptance process, however, official (non-PUA) codepoints are assigned. At this point the original PUA character assignments should be deprecated and a strategy effected to transition to using the new codepoints.

It is our perspective that we should never render someone's data as useless. Totally removing a character from the PUA, or even putting a box around it, would make the data impossible to publish or print without going back to find a copy of the font that has the character as it was originally intended.

This paper proposes elements of the strategy to transition to using the new codepoints without losing data that used the PUA codepoints.

## Background and rationale

At present there are over 260 characters assigned to the SIL corporate PUA area of Unicode. The Doulos SIL font, along with various keyboards and mapping tables, implement support for these PUA characters. However, included in our PUA assignments are about 225 characters that are now in Unicode and one character that is in the pipeline for Unicode and is expected to be part of the Unicode 16.0 release.

We desire tools and procedures that facilitate and encourage the transition to using the official codepoints for such characters without unduly burdening existing projects for which it might be inappropriate to make this transition.

The following components are affected by PUA character deprecation:

 - **fonts** — obviously fonts have to be altered to accommodate the new codepoints. But should the old codepoints be removed? What other design implications are there?
- **keyboards** — keyboards need to be modified to generate the new data.
- **conversion tools** — existing conversion mappings, such as from legacy to Unicode, that happen to map to deprecated PUA codepoints will need to change. Should old mappings be maintained? How do people migrate existing data from PUA to official encoding?

## PUA Codepoint reuse?

An assumption made in creating this document is that PUA codepoints will never be reused. As in the Unicode standard itself, once a character is assigned as SIL PUA codepoint, that assignment is never changed or altered. We may deprecate the codepoint, but we won't ever assume that all data that may use the codepoint has now disappeared and that, therefore, it is safe to reuse the codepoint for some other character. One of the benefits of Unicode is that archived data can be understood independently of external metadata such as specific fonts or file dates.

## SIL PUA Version Identification

Before digging into the details of what has to change when deprecating PUA characters, we should address the issue of version identification. We can expect that with each new version of Unicode, we may have another batch of PUA characters that should, from thence forward, be deprecated. With Unicode 4.1 140+ characters were deprecated. Another 45 characters were deprecated with the release of Unicode 5.0. The next release of Unicode may cause, say, another 13 to be deprecated, and the following release maybe another bunch. When looking at any given release of a component (font, keyboard, etc.), how is the user to know which version of our PUA the component is designed for?

That information is still maintained in the **DeprecatedAssignments** sheet of the spreadsheet that is found in [this download](SILCorpPUAAssign.zip).


## Fonts

When updating a font to account for PUA character deprecation, the obvious question is: Should the updated font include both the new and the old codepoints or just the new? If both, should both codepoints map to the same glyph or to different (though perhaps identical looking) glyphs?

If the updated font is going to have the same font name (e.g., "Doulos SIL"), then it won't be possible for users to have both the old font and the new one installed simultaneously. To maximize compatibility, therefore (i.e., in order to support both new and old encodings on the same system), the new font must include both the new and old codepoints.

This leaves us with the question of glyph names: Should the two codepoints point to the same glyph (this is called double-encoding the glyph) or to different glyphs? PUA deprecation is not the only reason one might be tempted to double encode a glyph — U+0041  LATIN CAPITAL LETTER A and U+0410  CYRILLIC CAPITAL LETTER A look identical and we might consider using the same glyph for these characters. As a general rule, we avoid double-encoding glyphs primarily for the reason that there exist some rare situations where it becomes helpful to be able to reconstruct the original character sequence from the rendered glyph sequence. As this is accomplished by inspecting the names of the glyphs, it is normally important that distinct codepoints refer to distinct glyphs.

In the case of deprecated PUA codepoints, however, there is a benefit to double encoding: it would provide a type of normalization in that it wouldn't matter which codepoint was originally used; when the character sequence is deduced from the glyph sequence, then only a single (preferably official) codepoint is generated.

Font implementations based on smart-font technologies such as Graphite may implement a font feature that draws attention (e.g., by an enclosing box) to PUA characters that have been deprecated. If this is done, the feature should be off by default. SIL fonts no longer have this feature as it proved to not be useful.

**Recommendation**: We recommend that the following changes occur to the font after PUA codepoint deprecation:

- The names of the glyphs for the deprecated characters should be changed to reflect the now-official Unicode codepoint.
- The PUA glyph should be inverted — it should now be made white on black in order to draw attention to the need to convert the data to Unicode.
- The font name should stay the same (in order to support both new and old encodings on the same system), though its internal version should be changed.

## Keyboards

Any keyboards that allow typing of the deprecated PUA codepoints will need to be upgraded. Because systems can support multiple keyboards simultaneously there isn't the same kind of need as there is with fonts; i.e., it isn't necessary that one keyboard support both encodings.

However, users will need to be aware of the encoding being used in any given document. It will be quite easy to end up with mixed encodings — some use of a now-deprecated PUA character along with use of the now-official codepoint. This, in turn, could cause confusing results search results or word lists, etc.

**Recommendation**: Keyboards should be updated as soon as a character is added to Unicode **and** when a font is released that supports that codepoint.

## Conversion

Any existing data conversion mappings (e.g., the TECkit mappings for SIL legacy encodings like IPA93) that reference newly deprecated PUA characters will need to be updated. As in the case of keyboards, multiple encoding mappings can be installed simultaneously on the same system, so it will be important for file and mapping names to reflect the PUA version they implement.

However there are two further considerations for mapping tables: PUA version folding and transliteration.

### PUA version folding

Consider a mapping rule such as the following from the current IPA93 mapping:
```
0xCB   <>   U+F181   ; superscript nya
```
In Unicode 4.1, this PUA character was allocated to U+1DAE. That means an obvious change to the mapping:
```
0xCB   <>   U+1DAE   ; superscript nya
```
But there is a further step we can take. When this mapping is used to convert Unicode to legacy, it should, for maximum benefit, handle either of the possible Unicode codepoints. The above should therefore be changed to:
```
0xCB   <>   U+1DAE   ; superscript nya
0xCB   <    U+F181   ; former PUA assignment
```
(The general name for this kind of mapping construction is "folding" — it folds two Unicode codepoints to a single legacy codepoint, thus eliminating the distinction in the Unicode space. Because this folding is due to PUA versioning, we have called it PUA version folding.)

### PUA version transliteration

What should users do with existing documents that use the PUA codes? To facilitate users transitioning to the official encodings, we should supply transliterator mappings that convert between the various versions of our PUA. For example, the change to Unicode 4.1 might be implemented in a TECkit transliterator such as:
```
LHSName    'SIL-PUA-4.0'
RHSName    'SIL-PUA-4.1'

pass(Unicode)
...
U+F181   <>   U+1DAE   ; superscript nya
```
**Recommendation:** When PUA codes are deprecated, mappings that refer to those codes should be updated not only to reference the official codepoints, but to fold deprecated PUA codes when doing the conversion back to legacy. Updated mappings should be designed to coexist with the older mappings. Further, a transliterator should be created to facilitate conversion of existing data between the PUA and official encoding. For this transliterator, the LHS should be the old PUA version, while the RHS be the new version (so that the default "forward" use of the transliterator updates data to the new version). Finally, in the forward direction, the transliterator should transform all characters deprecated in any previous PUA version (e.g., the 4.1 <> 4.2 transliterator should incorporate rules that transform 4.0 > 4.2).

A PUA to Unicode mapping file is available here: [SIL-PUA mapping file](https://github.com/silnrsi/wsresources/tree/master/scripts/Latn/mappings/sil-pua).

More information about versioning and deprecating can be found on [this page](https://scripts.sil.org/PUA_deprecation). Many of our original recommendations have changed, and we no longer ask people to track the PUA version in a font or keyboard.

<- [Back to Intro](https://github.com/silnrsi/silpua/)
