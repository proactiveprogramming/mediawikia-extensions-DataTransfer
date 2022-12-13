
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

## Example files
The following are properly formatted example files.  The names are 
case sensative.

### CSV Import file
<pre>
Title,Cheese[Country],Cheese[Texture],Free Text
Mozarella,Italy,Semi-soft,It's good on pizzas!
Cheddar,England,Hard/semi-hard,"Often sharp, but not always."
Gorgonzola,Italy,"buttery or firm, crumbly","salty, with a ""bite"" from its blue veining"
Stilton,,"",needs more data
</pre>

### xlsx Spreadsheet Import file.
It has the same column formats as the CSV file, except the file is saved as a xlsx file instead of a csv file.

### XML Import file without slots
<pre>
<Pages>
<Page Title="Limburger">
  <Free_Text>
<p><b>Limburger</b> is a cheese that originated in the Herve area of the historical Duchy of Limburg.</p>
  </Free_Text>
</Page>
</Pages>
</pre>

### XML Import file with slots
<pre>
<Pages>
<Page Title="Limburger" Slot="text-notes">
  <Free_Text>
<p><b>Limburger</b> is a cheese that originated in the Herve area of the historical Duchy of Limburg.</p>
  </Free_Text>
</Page>
</Pages>
</pre>

## Credits 

Data Transfer was mostly written by Yaron Koren. The spreadsheet import
functionality was written by Stephan Gambke.

The spreadsheet import functionality makes use of the PhpSpreadsheet
and/or PHPExcel libraries, if either is available.

## Contact 

Comments, questions, suggestions and bug reports should be
sent to Yaron at yaron57@gmail.com.

## Version History
### Version 2.0, 
  MediaWiki Version: 1.39.x LTS
  Author: Melissa Janine Newman (Proactive Programming, 2022-12-12)
  Status: Under development.
  
TODO:
- Add configuration for csv delimter (not done)
- Add section number option (not done)
- Add subpage option (not done)
- Change wfGetDB to 1.39 class call (See extension:Metadata for example code). (not done)
- Add option to target section by section header.  (Note: Requires SectionHeader extension to be completed first). (not done)
- Allow column names to be case insensative. (not done)
- Allow XML tags to be case insensative. (not done)
- If Free_Text is indented in the XML file, the file should still process the records correctly. (not done)

### Version 1.5.1 
  MediaWiki Version: 1.39.x LTS
  Author: Melissa Janine Newman (Proactive Programming)
  
- Started from DataTransfer 1.5
- Changed csv to "|" delimeter.
- Added prepend option.

### Version 1.5, Yaron, 2022-11-16
  MediaWiki Version: 1.34 - 1.39.x LTS
  Author: Yaron Koren

- Removed support for MW < 1.34; improved support for MW >= 1.36; added Composer loading of PhpSpreadsheet; more use of OOUI in display

### Version 1.4, Yaron, 2022-02-17
  MediaWiki Version: 1.32+
  Author: Yaron Koren

- Added support for importing XML into alternate Multi-Content Revisions slots; fixed spreadsheet importing, accidentally broken in version 1.1; improved handling for MW 1.37+

### Version 1.3, Yaron, 2021-11-16
  MediaWiki Version: 1.32+
  Author: Yaron Koren

- Removed DataTransfer.php; removed support for MW < 1.32; improved handling for MW 1.34+

### Version 1.2, Yaron, 2021
  MediaWiki Version: 1.29+
  Author: Yaron Koren

- Changed from using PHPExcel to PhpSpreadsheet for spreadsheet importing; added read-access check to Special:ViewXML; improved parsing of links within wikitext content to import; improved handling for MW 1.32+; code improvements
- Removed DataTransfer.php; removed support for MW < 1.32; improved handling for MW 1.34+

### Version 1.1, Yaron, 2020
  MediaWiki Version: 1.29+
  Author: Yaron Koren

- Removed support for MW < 1.29; fixed "merging" into pages that have sub-templates; fixed support for UTF-16LE format; improved support for MW >= 1.34
- Simplified and improved querying of categories and namespaces in Special:ViewXML

### Version 1.0, Yaron, 2018-2019
  MediaWiki Version: 1.27+
  Author: Yaron Koren

- Added extension.json; removed SMW special properties; removed support for MW 1.18 - 1.22; code improvements
- Fixes for MW >= 1.31; fix for PHP >= 7.2; other improvements
