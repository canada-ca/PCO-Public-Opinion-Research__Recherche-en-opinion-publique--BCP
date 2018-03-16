# Approach taken for the specific files

This is a list of the documented techniques that were used for the files in this initial conversion request.

## File locations

In this repository are some folders.  

### scrape

Contains the original files scraped from the LAC POR site using the wget tool. The folder depth has been removed from the scrape to make the files easier to access on GitHub.

### intermediate

Contains the intermediate versions of the files and conversions as the cleaning, accessibility improvement, and data format conversions were done.

Keeping access to the intermediate files allows for backtracking if you need to improve accessibility at any of the steps/techniques.

I am also proposing that Markdown files are possibly worth archiving to take advantage of future improvements to the generation of HTML from the Markdown. I am leaving them here instead of in the final folder.

### final

Contains the conversions of the original files. These will be what can be tested with accessibility test tools.

Given that there is always more manual work that could be applied to improve accessibility, I have chosen to do neccessary items in the understanding where feasible. The end result cannot deal with the complexity of some presentation tables that are debatably inaccessible to most people as they are. In an analogy to reading comprehension level there should be some limit on the complexity of data table presentation to solve this in the future. Retroactively changing the report presentation, I felt, was going beyond a "conversion".

## Techniques applied to the files

These files have been copied into the scrape folder. The original links are given here.

http://epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/privy_council/2017/081-16-e/index.html

- this appears to be a file created by the LAC repository. I can do a direct fix for any WCAG problems but it is likely another project to properly fix at the source.

http://epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/privy_council/2017/081-16-e/report.doc
- Techniques A,B,C,E,F,G,H,J

http://epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/privy_council/2017/081-16-e/summary.doc
- Techniques A,B,C,E,F,G,H,J

http://epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/privy_council/2017/081-16-e/tables-jan_2017.doc

http://epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/privy_council/2017/081-16-e/tables-feb_2017.doc

http://epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/privy_council/2017/081-16-e/tables-mar_2017.doc

http://epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/privy_council/2017/081-16-e/tables-jan_2017-mar_2017.rtf
- these files are hopelessly complex tables that are tough to describe and converting them to HTML would not be helpful.
The best solution is to archive the raw .csv data and let it be reprocessed in the future if needed.  This is what the Archives recommends. Unfortunately these files are not in a format that can be reduced to CSV format.  Some reference csv files have been referenced that could be used.

http://epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/privy_council/2017/081-16-e/variable_info-winter_2017.docx

http://epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/privy_council/2017/081-16-e/variable_values-winter_2017.docx
- these 2 files are relatively simple tables that can use Technique I to copy them to Excel, use a formula to repair empty cells and the export to .csv.  An HTML representation is also generated and both files could be submitted.

http://epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/privy_council/2017/030-16-e/index.html
- this appears to be a file created by the LAC repository. I can do a direct fix for any WCAG problems but it is likely another project to properly fix at the source.
  
http://epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/privy_council/2017/030-16-e/report.docx

http://epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/privy_council/2017/030-16-e/summary.docx

http://epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/privy_council/2017/030-16-e/data.xlsx
- a tremendously complex multiple worksheet spreadsheet.  Each table is also beyond the WCAG limits of comprehedability, so CSV is the only possible format. It is the output of a very comprehensive analysis program.
The referenced .csv file appears to be raw input and would have to suffice for archive.

http://epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/privy_council/2017/030-16-e/variable_information.docx

http://epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/privy_council/2017/030-16-e/variable_values.docx
- these 2 files are relatively simple tables that can use Technique I to copy them to Excel, use a formula to repair empty cells and the export to .csv.  An HTML representation is also generated and both files could be submitted.

**French:**

http://epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/privy_council/2017/081-16-f/index.html
- this appears to be a file created by the LAC repository. I can do a direct fix for any WCAG problems, but it is likely another project to properly fix at the source.

http://epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/privy_council/2017/081-16-f/rapport.doc
- Techniques A,B,C,E,F,G,H,J,K (no french file available yet)

http://epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/privy_council/2017/081-16-f/sommaire.doc
- Techniques A,B,C,E,F,G,H,J

http://epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/privy_council/2017/030-16-f/index.html
- this appears to be a file created by the LAC repository. I can do a direct fix for any WCAG problems but it is likely another project to properly fix at the source.

http://epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/privy_council/2017/030-16-f/rapport.docx
- Techniques A,B,C,E,F,G,H,J

http://epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/privy_council/2017/030-16-f/sommaire.docx
- Techniques A,B,C,E,F,G,H,J
 