# Alt Text review and removing text from tables and shapes

The goal is to bring all the text to the top flow in the word document. It is often inside a table and or a shape to help with page layout but this interferes with the conversion tools because they cannot deduce the order of the text that is required for HTML flow order.

Here are some typical operations from the sample project file:

- delete the Object that contains the html we have extracted previously

![delete Object](images/3-accessibilitypart1-1.png)

- use the accessibility checker to move to the next picture and repair the Alt Text.

![edit Alt Text on Logo](images/3-accessibilitypart1-2.png)

![enter correct Alt Text on Logo](images/3-accessibilitypart1-3.png)

- the image is also needing to be placed inline with the text flow as recommended by the checker

![make image inLine with text](images/3-accessibilitypart1-4.png)

- moving on to the next checker item we find some item inside a table for formatting reasons only.  First copy all the contents.

![copy all text inside a table](images/3-accessibilitypart1-5.png)

- paste the text after the table and then delete the table

![paste the text outside the table](images/3-accessibilitypart1-6.png)

It is a good idea to save the file now as it is easier to revert to a saved copy if you accidentally do some incorrect delete.