# ECE 388 Board Submission Standards

## Directory Layout
In the base Directory should be your Eagle project files, a directory called "cam" that contains the DRC files and CAM job files (You will use the ones in this repository), and a directory called "renders" which contains the output files from your project. If you want to also version control your firmware (which you probably should) you can have a folder called "software" or "firmware" to manage code.  You must also add the gitignore from this repo.  

## Submissions
Submissions should be in the form of Github Releases.  When a deadline comes around whatever the latest release on your repo is will be taken as your submission.  You should not email me submissions, moving forward email submissions will not be graded.  

Documentation on how to create a release can be found [HERE](https://docs.github.com/en/free-pro-team@latest/github/administering-a-repository/managing-releases-in-a-repository).

#### BOM Submission
You will create a release titled "BOM Submission"

We will be using [LCSC](https://lcsc.com) as out preferred supplier.  As such, all parts should be sourceable from LCSC unless previously discussed with myself.  Once submitted each group will meet with me for a BOM review.  BOM's should be exported from Eagle with a list type of values and a format of CSV.  This can be done by clicking the RUN ULP button, selecting the necessary settings, and saving the output into the base directory.  

![runUlp](/readmeImg/runUlp.png).
![ulpSelect](/readmeImg/ulpSelect.png).
![bomUlp](/readmeImg/bomUlp.png).

After Eagle generates a BOM file you need to open it in a CSV editor of your choice, excel, open office, atom if your a cool kid, and patch in the additional data needed to submit.  This includes price breakdowns, LCSC part numbers and links.  If a part is not available from LCSC and you have discussed this with me you can enter data into the DigiKey fields, otherwise they are unnessary.  Note price breakdowns are for the cost of 1 part at the listed quantity, not the extended price.  

**All parts necessary for production of you board must be on the BOM** this included displays, connectors, wiring, etc.  If you need it for your board to be functional it needs to be on the BOM. Components that are not physical parts, ex mounting holes, fiducials, etc, should not be included.  

**We are ordering parts from LCSC.  BOMs that do not have LSCS part numbers will be rejected**

#### Schematics Submission
You will create a release called "Schematic Submission"

ERC must be run on all schematic before submission.  ERC errors will not only make your board not work, it will also make your design get rejected.  Schematics should be submitted as a PDF located in the "renders" folder.  To get Eagle to produce a PDF of your schematic, go to File > Print and select the following settings.  

![schematicToPDF](/readmeImg/exportToPDF.png)

It's important that if you have more than one page that you select to export all pages.

#### Board Layout
It is important that the first thing you do when you start to layout your board is to setup your DRCs.  DRCs are the minimum checks you can do to make sure your board will have the possibility of being manufacturable.  They do not however verify your board will work correctly.  DRC files are provided in the "cam" folder of this repository.  Depending on which board manufacturer we decide to use will reflect which of the two we use.  To load a DRC file type "drc" in the eagle command window.  This will open a dialog where you can load in a DRC file.  We will be using the Dirty8TS.dru, this will set the minimum trace width and space between traces to 8mil.  Power traces should be set to a minimum trace widht of 12 mil or larger depending on current consumption.  

![drcLoad](/readmeImg/loadDRC.png)

Periodically while  laying out your board you should run a DRC to verify there are no manufacturing issues.  Ideally you would see the output below.  

![drc](/readmeImg/drc.png)

Notice my DRC has 0 Errors and 12 Approved.  That means there were 12 errors that have been reviewed and deemed acceptable.  You should consult myself, Dr. Forier, or Dr. Viall before approving DRC faults.  

To verify you read this put a text file in the CAM folder titled "Verification.txt" that contains the line "This Board contains no Green M&Ms" and nothing else.  

#### Board Submission
You will create a release called "Gerber Submission"

DRC must be run on your board prior to submitting.  Any DRC errors will result in your design being rejected.  
**Boards with critical DRC errors are unmanufacturable**

Boards will be submitted in a folder containing gerber files produced with the provided CAM files.  To Load the CAM file open the CAM Processor and click the LOAD button.

![camFileSelect](/readmeImg/camFileSelect.png)


I can not recommend strongly enough that you have everything in as early as possible.  Your designs will likely get rejected the first time and you need time to be able to get a manufacturable board in before the deadline to order.  
