# SIL’s Private Use Area (PUA)

## Summary:

The Private Use Area (PUA) is a range of codepoints that are reserved in the Unicode for private-use by software developers and end users who need a special set of characters for their own purposes.

Approximately 248 characters, supporting orthographies in many minority languages, have been approved for assignment to the {link:SILPUAassignments SIL corporate PUA}. Many technical linguistic characters have also been approved. Many of these characters are already supported in current versions of the ([SIL Latin, Greek, and Cyrillic Fonts](https://software.sil.org/lcgfonts/)). Future versions of these fonts will include additional approved characters. There are approximately 261 characters assigned codepoints in SIL's Private Use Area.

## SIL Corporate PUA Documentation

- [SIL Private Use Area - Assignments](docs/pua-assignments.md)
- [Deprecated SIL Corporate PUA characters](docs/pua-deprecated.md)
- [SIL Corporate PUA characters that have not been added to Unicode](docs/pua-nondeprecated.md)
- [SIL Private Use Area - Frequently Asked Questions](docs/faq.md)
- [A strategy for deprecating SIL PUA characters](docs/pua-deprecation-strategy)

## Requesting Additions to SIL’s Private Use Area

We are no longer accepting characters into the PUA. We may be willing to work with you on a Unicode proposal.

## About the PUA and SIL 

The [Private Use Area (PUA)](https://scripts.sil.org/cms/scripts/page.php?item_id=Glossary#pua) is a range of codepoints that are reserved in the Unicode for private-use by software developers and end users who need a special set of characters for their own purposes. There are 6400 PUA code points available in the [Basic Multilingual Plane](https://scripts.sil.org/cms/scripts/page.php?item_id=Glossary#bmp). Unicode also reserves the so-called “[supplementary planes](https://scripts.sil.org/cms/scripts/page.php?item_id=Glossary#supplement)” 15 and 16 for private use. The supplementary planes consist of an additional 128K codepoints, but require twice as many bits of information to access them. Click here to go to the {link:PUA_FAQ SIL PUA Fact Page} for additional information.

## Background

Although 6400 codepoints may seem like a lot of “code space,” delegates to the 1998 Computer Technical Conference (CTC) realized that this area needs to be managed so that [BMP](https://scripts.sil.org/cms/scripts/page.php?item_id=Glossary#bmp) codepoints do not run out in the long term. CTC requested WSTech (which was then known as the NRSI: Non-Roman Script Initiative) to develop a plan for entities to follow. The NRSI’s {link:PUA_Corp draft recommendation} presented at that conference allows entities to make free use of the lower portion of the PUA range, while the NRSI manages the upper portion for corporation-wide use. The goal of this strategy is to maximize the freedom of SIL field entities to implement needed characters while maintaining a central information repository to ensure consistency of field data and the ability to share and archive data within SIL. 

Because of the far-reaching effects of its decisions, the NRSI requested that a committee be set up to provide input from other SIL domains. The PUA Committee was chartered in 2004 to be that advisory body to the NRSI. The committee was made up of members representing various academic domains within SIL. This committee is no longer operational.

## Fonts which support the characters in SIL's PUA

Once PUA characters have been added to Unicode, our SIL fonts will add the new codepoint to the fonts and **deprecate** the PUA codepoint. See [Deprecated SIL Corporate PUA characters](pua-deprecated.md) for a list of the PUA codepoint and the official Unicode codepoint.

- [Andika](https://software.sil.org/andika/)
- [Charis SIL](https://software.sil.org/charis/)
- [Doulos SIL](https://software.sil.org/doulos/)
- [Gentium Plus](https://software.sil.org/gentium/)

## Industry and the PUA

- [Handling of PUA Characters in Microsoft Software](https://scripts.sil.org/PUACharsInMSSotware)
- [Use of the Unicode Private Use Areas by Others](https://scripts.sil.org/VendorUseOfPUA)
- [PUA Use in the Adobe Glyph List](https://scripts.sil.org/PUAinAdobeGlyphList)

