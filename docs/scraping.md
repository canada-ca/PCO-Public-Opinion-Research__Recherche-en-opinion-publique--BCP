# Fetching the files from the Library and Archives (LAC)

## Get ready

The original thought was that I might be able to automate the conversion of the POR report files, so I spent a few hours figuring out how to fetch the files. LAC has a clever but hackable pop-up challenge page.

The first step is to use the Cygwin Terminal that comes with the wget install.

## Make a directory to store the website copy
 
    mkdir scrape
    cd scrape

## Run the wget mirror command for each report that you wish to work on

    wget --mirror --convert-links --adjust-extension --page-requisites --no-parent --no-cookies --header "Cookie: notice; path=/100/200/301;"  http://epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/privy_council/2017/030-16-e/index.html

You can consult the wget manual online to get explanations of all the options. The `--header "Cookie: notice; path=/100/200/301;"` part is the magic that supplies the cookie to dodge the popup warning page.

For this challenge there is another report and the French counterparts.

    wget --mirror --convert-links --adjust-extension --page-requisites --no-parent --no-cookies --header "Cookie: notice; path=/100/200/301;"  http://epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/privy_council/2017/030-16-f/index.html

    wget --mirror --convert-links --adjust-extension --page-requisites --no-parent   --no-cookies --header "Cookie: notice; path=/100/200/301;" http://epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/privy_council/2017/081-16-e/index.html

    wget --mirror --convert-links --adjust-extension --page-requisites --no-parent --no-cookies --header "Cookie: notice; path=/100/200/301;"   http://epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/privy_council/2017/081-16-f/index.html
## Example results
Here is a copy of my terminal window contents:

    steve@DESKTOP-A302BHR ~
    $ pwd
    /home/steve

    steve@DESKTOP-A302BHR ~
    $ mkdir scrape

    steve@DESKTOP-A302BHR ~
    $ ls
    scrape

    steve@DESKTOP-A302BHR ~
    $ SCRAPEDIR=~/scrape

    steve@DESKTOP-A302BHR ~
    $ export SCRAPEDIR

    steve@DESKTOP-A302BHR ~
    $ cd $SCRAPEDIR

    steve@DESKTOP-A302BHR ~/scrape
    $ wget --mirror --convert-links --adjust-extension --page-requisites --no-parent --no-cookies --header "Cookie: notice; path=/100/200/301;"  http://epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/privy_council/2017/030-16-e/index.html
    --2018-03-07 12:35:27--  http://epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/privy_council/2017/030-16-e/index.html
    Resolving epe.lac-bac.gc.ca (epe.lac-bac.gc.ca)... 142.78.40.24
    Connecting to epe.lac-bac.gc.ca (epe.lac-bac.gc.ca)|142.78.40.24|:80... connected.
    HTTP request sent, awaiting response... 200 OK
    Length: 882 [text/html]
    Saving to: ‘epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/privy_council/2017/030-16-e/index.html’

    epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/ 100%[==========================================================================================================>]     882  --.-KB/s    in 0s

    2018-03-07 12:35:27 (13.7 MB/s) - ‘epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/privy_council/2017/030-16-e/index.html’ saved [882/882]

    Loading robots.txt; please ignore errors.
    --2018-03-07 12:35:27--  http://epe.lac-bac.gc.ca/robots.txt
    Reusing existing connection to epe.lac-bac.gc.ca:80.
    HTTP request sent, awaiting response... 302 Found
    Location: http://www.collectionscanada.ca/000/007/000007-404-003008.html [following]
    --2018-03-07 12:35:27--  http://www.collectionscanada.ca/000/007/000007-404-003008.html
    Resolving www.collectionscanada.ca (www.collectionscanada.ca)... 142.78.200.66
    Connecting to www.collectionscanada.ca (www.collectionscanada.ca)|142.78.200.66|:80... connected.
    HTTP request sent, awaiting response... 200 OK
    Length: 7896 (7.7K) [text/html]
    Saving to: ‘epe.lac-bac.gc.ca/robots.txt.html’

    epe.lac-bac.gc.ca/robots.txt.html                 100%[==========================================================================================================>]   7.71K  --.-KB/s    in 0.02s

    2018-03-07 12:35:27 (448 KB/s) - ‘epe.lac-bac.gc.ca/robots.txt.html’ saved [7896/7896]

    --2018-03-07 12:35:27--  http://epe.lac-bac.gc.ca/www-pages/eppp.css
    Connecting to epe.lac-bac.gc.ca (epe.lac-bac.gc.ca)|142.78.40.24|:80... connected.
    HTTP request sent, awaiting response... 302 Found
    Location: http://www.collectionscanada.ca/000/007/000007-404-003008.html [following]
    --2018-03-07 12:35:27--  http://www.collectionscanada.ca/000/007/000007-404-003008.html
    Connecting to www.collectionscanada.ca (www.collectionscanada.ca)|142.78.200.66|:80... connected.
    HTTP request sent, awaiting response... 200 OK
    Length: 7896 (7.7K) [text/html]
    Saving to: ‘epe.lac-bac.gc.ca/www-pages/eppp.css.html’

    epe.lac-bac.gc.ca/www-pages/eppp.css.html         100%[==========================================================================================================>]   7.71K  --.-KB/s    in 0.02s

    Last-modified header missing -- time-stamps turned off.
    2018-03-07 12:35:27 (315 KB/s) - ‘epe.lac-bac.gc.ca/www-pages/eppp.css.html’ saved [7896/7896]

    --2018-03-07 12:35:27--  http://epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/privy_council/2017/030-16-e/report.docx
    Connecting to epe.lac-bac.gc.ca (epe.lac-bac.gc.ca)|142.78.40.24|:80... connected.
    HTTP request sent, awaiting response... 200 OK
    Length: 572885 (559K) [text/plain]
    Saving to: ‘epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/privy_council/2017/030-16-e/report.docx’

    epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/ 100%[==========================================================================================================>] 559.46K  2.02MB/s    in 0.3s

    2018-03-07 12:35:27 (2.02 MB/s) - ‘epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/privy_council/2017/030-16-e/report.docx’ saved [572885/572885]

    --2018-03-07 12:35:27--  http://epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/privy_council/2017/030-16-e/summary.docx
    Reusing existing connection to epe.lac-bac.gc.ca:80.
    HTTP request sent, awaiting response... 200 OK
    Length: 336080 (328K) [text/plain]
    Saving to: ‘epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/privy_council/2017/030-16-e/summary.docx’

    epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/ 100%[==========================================================================================================>] 328.20K  --.-KB/s    in 0.08s

    2018-03-07 12:35:28 (3.87 MB/s) - ‘epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/privy_council/2017/030-16-e/summary.docx’ saved [336080/336080]

    --2018-03-07 12:35:28--  http://epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/privy_council/2017/030-16-e/data.xlsx
    Reusing existing connection to epe.lac-bac.gc.ca:80.
    HTTP request sent, awaiting response... 200 OK
    Length: 1226525 (1.2M) [text/plain]
    Saving to: ‘epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/privy_council/2017/030-16-e/data.xlsx’

    epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/ 100%[==========================================================================================================>]   1.17M  3.07MB/s    in 0.4s

    2018-03-07 12:35:28 (3.07 MB/s) - ‘epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/privy_council/2017/030-16-e/data.xlsx’ saved [1226525/1226525]

    --2018-03-07 12:35:28--  http://epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/privy_council/2017/030-16-e/data.csv
    Reusing existing connection to epe.lac-bac.gc.ca:80.
    HTTP request sent, awaiting response... 200 OK
    Length: 6502714 (6.2M) [text/plain]
    Saving to: ‘epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/privy_council/2017/030-16-e/data.csv’

    epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/ 100%[==========================================================================================================>]   6.20M  2.60MB/s    in 2.4s

    2018-03-07 12:35:31 (2.60 MB/s) - ‘epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/privy_council/2017/030-16-e/data.csv’ saved [6502714/6502714]

    --2018-03-07 12:35:31--  http://epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/privy_council/2017/030-16-e/variable_information.docx
    Reusing existing connection to epe.lac-bac.gc.ca:80.
    HTTP request sent, awaiting response... 200 OK
    Length: 67135 (66K) [text/plain]
    Saving to: ‘epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/privy_council/2017/030-16-e/variable_information.docx’

    epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/ 100%[==========================================================================================================>]  65.56K  --.-KB/s    in 0.001s

    2018-03-07 12:35:31 (80.8 MB/s) - ‘epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/privy_council/2017/030-16-e/variable_information.docx’ saved [67135/67135]

    --2018-03-07 12:35:31--  http://epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/privy_council/2017/030-16-e/variable_values.docx
    Reusing existing connection to epe.lac-bac.gc.ca:80.
    HTTP request sent, awaiting response... 200 OK
    Length: 238293 (233K) [text/plain]
    Saving to: ‘epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/privy_council/2017/030-16-e/variable_values.docx’

    epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/ 100%[==========================================================================================================>] 232.71K  --.-KB/s    in 0.08s

    2018-03-07 12:35:31 (2.81 MB/s) - ‘epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/privy_council/2017/030-16-e/variable_values.docx’ saved [238293/238293]

    FINISHED --2018-03-07 12:35:31--
    Total wall clock time: 4.6s
    Downloaded: 9 files, 8.5M in 3.2s (2.63 MB/s)
    Converting links in epe.lac-bac.gc.ca/100/200/301/pwgsc-tpsgc/por-ef/privy_council/2017/030-16-e/index.html... 7-0
    Converting links in epe.lac-bac.gc.ca/www-pages/eppp.css.html... 2-7
    Converting links in epe.lac-bac.gc.ca/robots.txt.html... 2-7
    Converted links in 3 files in 0.05 seconds.

## Where the files are

This is an image of the report folders:

![directory of file folders](images/scrapingresults.png "The Windows file view of mirrored folders")

This is an image of all the files in one report folder to be processed:

![directory of file folders](images/reportfiles.png "The Windows file view of mirrored files")