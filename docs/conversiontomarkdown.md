# Technique G: **Convert the document to Markdown format**

A well-known open source conversion tool, [pandoc](http://pandoc.org), seems to be the best to convert the .docx to Markdown in this case because of different types of table support in Markdown.

I believe that using an intermediate Markdown format can be useful. I tried direct conversions from .docx to .html and there were a few issues. These can be fixed with 2 steps, the first to Markdown and the second to HTML.

On the PC, I use the Bash Terminal and environment variables are useful. The first is to set one to the processing folder that is the copy of this GitHub repo for this documentation.

    PDIR=/z/PCShare/DevEx
    cd $PDIR

The directory location that you use needs to replace the "/z/PCShare/DevEx" used on my VirtualPC.

Now to switch to the intermediate folder where we stored the upgrated Word files. You may need to make appropriate subfolder to work for other documents.

    cd $PDIR/intermediate/081-16-e
    DOCLANG=en

The DOCLANG is used to select templates for pandoc for the appropriate language in a later HTML conversion phase. Now set the DOCNAME to the original filename before the addition of suffix "word" and "ac" from previous processing.

    DOCNAME=report
    pandoc  -f docx -t markdown --atx-headers --wrap=none  -s  --extract-media=media  --metadata=lang:${DOCLANG}  -o ${DOCNAME}wordac.md ${DOCNAME}wordac.docx

The pandoc program does the conversion to .md file in the same directory/folder. You can look at the file in Visual Studio Code and find the open preview to the side feature and it will give an approximate preview.

A key piece is the "--extract-media=media" that extracts any images into a folder. This folder needs to accompany any .md or HTML subsequently created.