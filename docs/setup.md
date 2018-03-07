# Setup tools and reference to Web resources

## [Visual Studio Code](https://code.visualstudio.com/docs#vscode)

A key intermediate text file in the proposed solution is the use of [Markdown](https://daringfireball.net/projects/markdown/) format.  It is handy to use a text editor that can preview Markdown files.

My recommendation is [Visual Studio Code](https://code.visualstudio.com/docs#vscode) as it is supported on many platforms and it seems fitting to use a Microsoft tool to dig out of a Microsoft Office accessibility problem. To give credit it is built on a fine base called [Electron](https://electronjs.org) by the folks at GitHub. These are free tools.

In testing the Windows install, the [git](https://git-scm.com/) install was suggested when Code was launched.  I did the install with all the suggested defaults.  You may already have git if you have been using GitHub. It does install Git Bash, a terminal tool that may be useful to run some commands.


## [wget](http://www.gnu.org/software/wget/)

**Don't bother with this if you have the files that you wish to convert already**

I used this command line tool to make mirror copies of the LAC POR archive files. This could be more painful to install on Windows. You can get the original files to work on in any manner, but it is best to work on copies on your own computer.

I decided to use the [Cygwin](https://cygwin.com/install.html) installer that has many linux style tools but I just did a search for wget and selected the one in the web category to install. **Be careful here to only install wget for now.

You get a Cygwin Terminal tool with the install and launching this terminal and typing
> which wget

should return 
>/usr/bin/wget

## [pandoc](https://github.com/jgm/pandoc)

This is the best markdown converter that I found to address the conversion from .docx files that seem to be the most challenging.

The [install instructions](https://github.com/jgm/pandoc/blob/master/INSTALL.md) where I used the Windows installer .msi download.  I selected the install only for this user option as it may be more likely to work on a managed PC.

This command is available from the Windows Command Prompt terminal for those keeping track.

## [Microsoft Office](https://products.office.com/en-ca/home)

Not a free open source tool here but it is required to update .doc files to the latest .docx format that works with pandoc.  It is also maybe the best place to attack the first layer of accessibility.

I used a recent Office 365 version that I will document here as the future users of this guide will likely be the firms creating the POR documentation that will be asked for accessible HTML5.