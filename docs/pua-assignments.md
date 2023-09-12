# SIL Private Use Area - Assignments

<- [Back to Intro](https://github.com/silnrsi/silpua/) 

## Background

The following table gives a list of Unicode _private-use character assignments_ used within SIL International. 

This information is provided for those who work in collaboration with SIL and who may wish to interchange language data. It does not constitute a recommendation for widespread adoption of PUA character assignments.

SIL corporation-wide PUA usage uses the codepoint range U+F100..U+F8FF. Individual SIL field entities might also make independent PUA character assignments in the range U+E000..U+EFFF. Corporate PUA assignments follow the following roadmap:

### Roadmap (Revised 2003-8-11)

Codepoint range | Purpose
---------------- | ---
F000..F0FF|(reserved)
F100..F13F|specials
F140..F15F|(reserved)
F160..F17F|combining marks
F180..F1EF|modifier letters (e.g. superscripts)
F1F0..F1FF|(reserved)
F200..F2FF|Latin
F300..F31F|Hebrew
F320..F33F|Cyrillic
F340..F34F|(reserved)
F350..F6FF|other non-Latin alphabetic characters
F700..F8FF|(reserved)

## SIL Corporate PUA Character Assignments

In preparing fonts to facilitate corporate transition to Unicode, WSTech has attempted to create a font that will meet the character needs of users working with Latin or Cyrillic scripts throughout the corporation. In order to achieve this, it was necessary to identify private-use character needs related to these scripts from all entities. Documented here are the code-points for each of the Private Use Area (PUA) characters which have been assigned to the corporate area of the PUA. The Unicode 15.0 standard includes 225 characters that were previously allocated to codepoints in the **Private Use Area** by SIL’s PUA committee. 

- A [TECkit](https:/software.sil.org/teckit) mapping file for converting from PUA codepoints to Unicode codepoints is provided [here](https://github.com/silnrsi/wsresources/tree/master/scripts/Latn/mappings/sil-pua). 
- [SIL Converters](https:/software.sil.org/silconverters) is an ideal tool to use with the TECKit mapping file to convert files from the PUA codepoint to the official Unicode codepoints.

Character properties are listed in the **UCD-SIL_PUA_-date-.xls** file which is included in the zip archive below. We have also included a worksheet (DeprecatedAssignments) to SIL's PUA UCD (Unicode Character Database) spreadsheet. This worksheet shows the history of every SIL PUA character: what PUA version it was added and what version, if any, it was deprecated. This will help implementers determine which PUA versions a specific keyboard, font, or mapping table supports. 

Also included is a pdf file (and the Word document) describing the PUA characters and some of the history of why they were added to the SIL PUA registry. 

- Download [SILCorpPUAAssign](SILCorpPUAAssign.zip)

## SIL Ethiopia PUA assignments

The **SIL field entities** range was used for the **Abyssinica SIL Ethiopic** font. Documentation for that range of characters is found in the [ethiopia](https://github.com/silnrsi/silpua/tree/main/ethiopia) section of this repo.


<- [Back to Intro](https://github.com/silnrsi/silpua/) 

-> [Forward to Deprecated SIL Corporate PUA characters](pua-deprecated.md)