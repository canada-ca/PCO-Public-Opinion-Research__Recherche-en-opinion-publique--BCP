# Making reports accessible

## Context

The goal of the work is to make reports accessible. The initial application is to [Public Opinion Research Reports , PORR.](http://www.bac-lac.gc.ca/eng/porr/Pages/porr.aspx)

The [Instructions for submitting public opinion research reports to Library and Archives Canada](http://www.bac-lac.gc.ca/eng/porr/Pages/help-submit-a-report.aspx)

The [Requirements for submitting public opinion research final reports](https://www.tpsgc-pwgsc.gc.ca/rop-por/lvfpor-porfrc-eng.html) contain the guidance for these reports. **The best solution is to improve this guidance to allow the archiving of more accessible data, for now and for reference in the future.**

There may be cases where less accessible formats need to be supplemented with formats that are best practices.
The [Guidance on Implementing the Standard on Web Accessibility](https://www.canada.ca/en/treasury-board-secretariat/services/government-communications/guidance-implementing-standard-web-accessibility.html) is to publish in HTML5 and aiming at [WCAG 2.0 AA](https://www.w3.org/TR/WCAG20/).

## Proposed Solution

My approach involves using various existing tools to attempt the conversion and see where they fall short of achieving the goal. I did find many useful tools that could be employed, but they needed to be used in combination and often different sequences/steps were required for each of the required documents. I will describe some general techniques and why I think they are useful and then comment on each specific document to illustrate how they are applied to each case.

### Technique A: Upgrade

Many documents are Microsoft Office documents. This step involves converting the document to the latest Office file format. This is done by a menu command in the applicable Office Word or Excel application. This technique can be automated but is already easy.

### Technique B: Use Microsoft Accessibility Check and Repair

Microsoft and other application vendors are under pressure to make their documents more accessible. Someday, their applications may be better at accessing information than HTML screen readers that benefit from WCAG recommendations.  So this technique should be used before archiving to make possible any future improved access.
This check also reveals the missing information that is hindering accessibility.
 -  A common item is missing alternate text for images. 
   My approach is to manually repair this by just deleting images that add no archive value. Decorative graphics, corporate logos, and pretty stock photos that are not key to the report.
   Add the suitable alt-text to the remaining images using the Microsoft properties editing tools.
   
### Technique C: Extract text from shapes that are being used for page layout

Some documents have header pages that have been made pretty by some brute force page layout. These items can be missed by subsequent extraction tools.  So the easiest thing is to copy the text from the shapes or grouped objects and paste it into the text of the document. When all the useful text is now in the document directly, the shape can be deleted.
Some items need to be set to be inline with text to be in the proper flow.

### Technique D: Try to get tables to a single header form.

The most challenging items are tables with overly-complex formatting.  WCAG techniques are available for a limited complexity of table.
Some tables just require a title header row to be placed into alt-text property and deleted to make simple column headers. Simplifying these tables makes extraction/conversion tools work.
Some files have the title, and a description in the narrative and this can be copied to the table alt text properties to improve WCAG conversion.

### Technique E: Throw up your hands because the table has multiple column headers and complex row groupings.

The good news is that these tables are barely accessible to fully sighted people. The information is too densely packed and even if formatted with the best WCAG techniques, will not be easily comprehended.
I suggest requesting that future reports not have these tables until they are accessible in the native app.
I can only suggest that these tables are duplicated and then reduced to simple tables.  This is labor intensive.
Maybe just having a proper table description and maybe a warning that it was supplied in a difficult format.
The extraction tools work, but the resulting HTML is a table, but the screen reader may not be able to properly navigate the table.

### Technique F: Fix the document headers and title order.

Microsoft Word has a layout to define the section and chapter levels, but the originator did not use them fully. This makes the table of contents generation and header levels incomplete when converted to HTML.  This should also be fixed in the Word document as well.

### Technique G: **Convert the document to Markdown format**

Markdown is a pure text file that is a simple format commonly used to enter info into content management systems.  Github uses it to help publish documentation pages (like the one you are reading).  It turns out that it is simple enough that it can be used as an accessibility solution to help some people enter internet content.  It is likely that archiving this format may be useful as well as HTML publication. And eventually when there is a WCAG 4.0 that even better HTML can be generated from the basic Markdown files.
A well-known open source conversion tool, [pandoc](http://pandoc.org), seems to be the best to convert the .docx to Markdown in this case because of different types of table support in Markdown.

### Technique H: **Convert the Markdown format to HTML5**

Again, there are many Markdown to HTML tools but because of the table complexity I have found it best to use pandoc for this conversion as well because of the advanced table options.
Pandoc has the capability to specify the HTML template.  I have enhanced the default template to add some WCAG 2.0 features. This is also where any special CSS can be added.

### Technique I: Convert a table using .csv

Some doc files are really just tables that were probably just copied from an Excel document. The best path for these is to copy and paste them back into an Excel file. Then export them to a .csv file. There is an internet tool to convert the .csv file to HTML. This tool allows the generation of some of the useful WCAG table markup.
One of the files used a grouped row header. This has no WCAG solution. So I used an Excel formula to locate and repeat the header label. Then continue with the .csv to HTML conversion. http://convertcsv.com/csv-to-html.htm
The Archives also accepts .csv files so these can be used.

### Technique J: Test the resulting HTML using accessibility test tools.

One tool is http://wave.webaim.org  that will look for any basic accessibility items.  Other checks could be done. Fixes can be applied to some of the intermediate working documents and retested.
There also accessibility extensions that can be added to Google Chrome web browser to access these testing tools.

### Technique K: Icons linking  embedded-content cannot be found.

Unfortunately, the guidance encourages these final reports to be one document with appendices for specific data.  These data appendices can be linked objects in the Microsoft Word file. They do not convert well.
Ask for the file from the source and then either post the file separately or add it to the html at a later stage.

## Trade offs

### Better accessibility versus More manual steps

I initially was attempting to find a pure computer script to download the LAC archive pages and the convert each file depending on its file type.  This would have worked and been probably what was imagined by the originators of the procurement.

After assembling the solution, I ran into the exceptions where the conversion was not ideal. The **"Root need"** of this project is actually **accessibility** and not simplicity of automation. I chose to continue to improve accessibility and arrived at the many techniques described above. I chose to submit this mixed mess of techniques as the solution as I was convinced a purely automated solution would never adapt to the ability of humans to misuse Microsoft Word and Excel.