# Dealing with embedded content in Word documents

## Technique K: Icons linking embedded-content

When reviewing items in the Microsoft Word accessibility checker you may encounter items labeled "Object"  that reveal an embedded file.  These occur because the report builders were guided to submit a single file and some of the Appendices are tables based on Excel or complex HTML files that would lose their formatting if directly imported into Word.

## Example of extracting some embedded HTML content

One of the reports in the challenge set is illustrated:

= the Object is encountered in the Accessibility Checker

![Object inside the file](images/2-extractembedded-1.png)

- Open the file that turns out to be HTML

![Open the file](images/2-extractembedded-2.png)

- the object opens in a browser. We need to save the html source by selecting the address that is in a temporary directory

![Get the address of the file from the browser address](images/2-extractembedded-3.png)

- open the Bash Terminal application and navigate to the temp folder

      cd ~/AppData/Local/Temp
      ls

![~/AppData/Local/Temp folder](images/2-extractembedded-4.png)

- list the files and copy the name of the HTML file

![PCO Survey questionnaire](images/2-extractembedded-5.png)

- open the file in Visual Studio Code by using the terminal command

      code 'PCO Survey - English Questionnaire.htm'

![use code to open file](images/2-extractembedded-6.png)

- save the source code into the intermediate working folder

![save the file html source](images/2-extractembedded-7.png)
