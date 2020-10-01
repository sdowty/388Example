# ECE 388 Board Submission Standards

## Directory Layout
In the base Directory should be your Eagle project files, a directory called "cam" that contains the DRC filed and CAM job files (You will use the ones in this repository), and a directory called "renders" which contains the output files from your project. If you want to also version control your firmware (which you probably should) you can have a folder called "software" or "firmware" to manage code.  

## Submissions
Submissions should be in the form of Github Releases.  When a deadline comes around whatever the latest release on your repo is will be taken as your submission.  

Documentation on how to create a release can be found [HERE](https://docs.github.com/en/free-pro-team@latest/github/administering-a-repository/managing-releases-in-a-repository).

#### Schematics Submission
ERC must be run on all schematic before submission.  ERC errors will not only make your board not work, it will also make your design get rejected.  Schematics should be submitted as a PDF located in the "renders" folder.  To get Eagle to produce a PDF of your schematic, go to File > Print and select the following settings.  

![schematicToPDF](/readmeImg/exportToPDF.png).

It's important that if you have more than one page that you select to export all pages.

#### Board Layout
It is important that the first thing you do when you start to layout your board is to setup your DRCs.  DRCs are the minimum checks you can do to make sure your board will have the possibility of being manufacturable.  They do not however verify your board will work correctly.  DRC files are provided in the "cam" folder of this repository.  Depending on which board manufacturer we decide to use will reflect which of the two we use.  To load a DRC file type "drc" in the eagle command window.  this will open a dialog where you can load in a DRC file

![drcLoad](/readmeImg/loadDRC.png)

Periodically while  laying out your board you should run a DRC to verify there are no manufacturing issues.  Ideally you would see the output below.  

![drc](/readmeImg/drc.png)

Notice my DRC has 0 Errors and 12 Approved.  That means there were 12 errors that have been reviewed and deemed acceptable.  You should consult myself, Dr. Forier, or Dr. Viall before approving DRC faults.  

#### Board Submission

DRC must be run on your board prior to submitting.  Any DRC errors will result in your design being rejected.  
**Boards with critical DRC errors are unmanufacturable**

Boards will be submitted in a folder containing gerber files produced with the provided CAM files.  To Load the CAM file open the CAM Processor and click the LOAD button.

![camFileSelect](/readmeImg/camFileSelect.png)


I can not recommend strongly enough that you have everything in as early as possible.  Your designs will likely get rejected the first time and you need time to be able to get a manufacturable board in before the deadline to order.  
