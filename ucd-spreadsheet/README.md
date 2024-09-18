# UCD Spreadsheets

Unicode Character Database (UCD) spreadsheets

## Current

For the update to Unicode 14.0 and later, a new layout of the spreadsheet was used. Previously, as described below, different tabs showed different files from the UCD. Now, all the data is on one tab, and additional properties (as compared to previous versions) are shown.

## Old

We have taken various files from the UCD and put them into an Excel workbook. The files in the UCD have been designed to be machine-readable. One result of this is that they are not as readable to humans. This is especially true of the original UCD file, UnicodeData.txt. By putting the content into an Excel workbook, the information can be presented in a much more readable way. Moreover, Excel provides some useful functionality that isn't available when reading the files in a text editor. In particular, by using Excel's AutoFilter feature, it becomes easy to do things such as showing only characters with compatibility decompositions, or characters with a canonical combining class of 220, or characters that have "WITH HOOK" in their name.

The content of different files have been placed into separate sheets in the workbook. There are also sheets that provide documentation such as the meanings of various codes used for certain properties (for instance, the values used in the General Category field of UnicodeData).

For some of the files, some minor changes have been made in how the content is organised as an aid to readability. For instance, a column for representative glyphs has been added to UnicodeData. None of the property values has been changed, however.

We have added representative glyphs to the sheet for the UnicodeData file. You will need to find appropriate fonts with which to format the cells containing each character. In some cases, leading spaces may have been added so that combining marks would be more likely to display.

For Unicode 6.1, Blocks.txt was added.

For Unicode 4.1, Scripts.txt was added.

For Unicode 4.0 and later, the contents of the following UCD files are included:

- UnicodeData.txt
- ArabicShaping.txt
- BidiMirroring.txt
- CompositionExclusions.txt
- LineBreak.txt
- DerivedAge.txt

For Unicode 3.2 and earlier version, only the contents of UnicodeData.txt is included.

## Unicode Terms of Use

The [license](LICENSE) is from [Unicode, Inc](https://www.unicode.org/copyright.html).

## Downloads

Unicode 16.0.0

- LibreOffice Calc [ucd.ods](ucd.ods)
- Microsoft Excel [ucd.xlsx](ucd.xlsx)
- CSV [ucd.csv](ucd.csv)
