
## About 

Data Transfer is an extension to MediaWiki that both exports data,
based on the current contents of pages in a wiki; and imports pages.
In both cases, it uses template calls, and the fields within them,
to define the data structure.

The export is done in XML format, while the import can be done in
either XML, CSV or spreadsheet (.xls, .ods etc.) formats.

For the export, any text that is not within a template call gets
placed into one or more "free text" fields.

For more information on Data Transfer, see the extension
homepage at
https://www.mediawiki.org/wiki/Extension:Data_Transfer

Notes on installing Data Transfer can be found in the file INSTALL.

## Credits 

Data Transfer was mostly written by Yaron Koren. The spreadsheet import
functionality was written by Stephan Gambke.

The spreadsheet import functionality makes use of the PhpSpreadsheet
and/or PHPExcel libraries, if either is available.

## Contact 

Comments, questions, suggestions and bug reports should be
sent to Yaron at yaron57@gmail.com.

## Version History
Version 2.0, Melissa Janine Newman, 2022-12-12, MediaWiki 1.39
TODO:
- Add configuration for csv delimter (not done)
- Add prepend/append option. (not done)
- Add section number option (not done)
- Add subpage option (not done)
- Add option to import XML using simple title and content format. Still have not figured out how the XML import works.  (not done)
- Change wfGetDB to 1.39 class call (See extension:Metadata for example code).

Version 1.5, Yaron, 2022-11-16

- Removed support for MW < 1.34; improved support for MW >= 1.36; added Composer loading of PhpSpreadsheet; more use of OOUI in display

Version 1.4, Yaron, 2022-02-17

- Added support for importing XML into alternate Multi-Content Revisions slots; fixed spreadsheet importing, accidentally broken in version 1.1; improved handling for MW 1.37+

Version 1.3, Yaron, 2021-11-16

- Removed DataTransfer.php; removed support for MW < 1.32; improved handling for MW 1.34+

Version 1.2, Yaron, 2021

- Changed from using PHPExcel to PhpSpreadsheet for spreadsheet importing; added read-access check to Special:ViewXML; improved parsing of links within wikitext content to import; improved handling for MW 1.32+; code improvements
- Removed DataTransfer.php; removed support for MW < 1.32; improved handling for MW 1.34+

Version 1.1, Yaron, 2020

- Removed support for MW < 1.29; fixed "merging" into pages that have sub-templates; fixed support for UTF-16LE format; improved support for MW >= 1.34
- Simplified and improved querying of categories and namespaces in Special:ViewXML

Version 1.0, Yaron, 2018-2019

- Added extension.json; removed SMW special properties; removed support for MW 1.18 - 1.22; code improvements
- Fixes for MW >= 1.31; fix for PHP >= 7.2; other improvements
