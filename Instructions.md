## Target for Instructions ##
The following guidelines are given under the assumption that new helpers need to know three things:
  * How to edit Shika
  * How to share edits
  * How to compile the book (aka how to make a PDF)
**Note:** Below is simply a basic outline of instructions; you may find you need more guidance than what is given here. As this is a work in progress, greater clarifications will come in time.

# How to edit Shika #
### Download and install TortoiseHG or MacHG ###
Windows and Ubuntu users should use TortoiseHG. Mac users can use MacHG (assuming they are using at least Snow Leopard 10.6).
  * Windows: go to TortoiseHG's [Bitbucket page](http://tortoisehg.bitbucket.org/download/index.html), download the most recent version and install
  * Ubuntu: open Ubuntu Software Centre, search for TortoiseHG and install
  * Mac: go to MacHG's [Download page](http://jasonfharris.com/machg/downloads/downloads.html), download the most recent version and install
If you are using an older version of Ubuntu that does not have the Software Centre, use Synaptic instead.
### Download Shika within TortoiseHG/MacHG ###
For TortoiseHG:
  * From the menu, File > Clone Repository...
  * In the Source box, enter the address https://code.google.com/p/shika-na-mikono.shika-tz
  * In the Destination box, pick a place on your computer where you want to save the files (ie a folder like "Shika-TZ" in your Documents folder)
  * Click Clone
For MacHG:
  * From the menu, Repository > Add Server Repository...
  * In the Short Name box, pick a name to help you identify the repository (ie "Shika TZ Server")
  * In the Server URL box, enter https://code.google.com/p/shika-na-mikono.shika-tz
  * If you are planning to share your edits with others, you should enter your Google credentials here (details on this coming)
  * Click OK
  * Highlight the repository in the left-hand pane
  * From the menu, Repository > Clone...
  * In the Local Path box, pick a folder where you want to save the files (ie a folder like "Shika-TZ" in your Documents folder)
  * In the Short Name box, pick a name to help you identify the repository (ie "Shika TZ Local")
**Note:** The source files for the other Shika manuals may be obtained by repeating the steps above using the following addresses. It is recommended to have a separate folder for each repository (e.g. "Shika-TZ"; "Shika-Phys" etc.)
  * Biology: https://code.google.com/p/shika-na-mikono.shika-bio
  * Chemistry: https://code.google.com/p/shika-na-mikono.shika-chem
  * Physics: https://code.google.com/p/shika-na-mikono.shika-phys
  * Math: https://code.google.com/p/shika-na-mikono.shika-math
To get the files for the LASM manuals, use these:
  * LASM Biology: https://code.google.com/p/shika-na-mikono.lasm-bio
  * LASM Chemistry: https://code.google.com/p/shika-na-mikono.lasm-chem
  * LASM Physics: https://code.google.com/p/shika-na-mikono.lasm-phys
### Edit Shika's .tex files ###
You now have a local copy of Shika on your computer. To open the folder containing these files:
  * In TortoiseHG, right-click the repository in the left-hand pane and select Explore
  * In MacHG, right-click the LOCAL repository in the left-hand pane and select Open in Finder
**Note:** when editing these files in Windows without a proper LaTeX editor, please use Wordpad as opposed to Notepad. A proper LaTeX editor, however, is more helpful and recommended.

In the folder named "tex", you will find .tex files named as chapters in the book. In these files, you'll find the text of the book along with esoteric LaTeX commands that, as long as the changes you make don't concern the format (just the content), you don't have to understand.
### Optional: Install a LaTeX editor ###
Shika's .tex files are just plain text files, and as such can be edited in any normal text editor. If, however, you'd like to be able to perform some simple things like bolding or italicizing text without needing to know the LaTeX commands behind them, you will find having a LaTeX editor helpful. The editor we like to use is called Texmaker because it can be installed on Windows, Mac, and Ubuntu.

For Windows and Mac:
  * Go to the [Texmaker homepage](http://www.xm1math.net/texmaker)
  * Download and install the latest version for your computer
For Ubuntu:
  * Open Ubuntu Software Centre and search for Texmaker
  * Install
If you're interested in using Texmaker to compile the book, go to the section on [Compiling the book](Instructions#How_to_compile_the_book.md).
# How to share edits #
**First and foremost, contact [David Berg](mailto:dberg918@gmail.com) to get commit privileges!**
### Configure your Mercurial client ###
For Windows/Ubuntu, in TortoiseHG:
  * Right-click your shika-tz repository in the left-hand window and select Settings...
  * Click the Commit tab on the left, enter "Your Name <youremail@address.com>" in the Username box.
  * Click OK to save changes.
  * From the menu, View > Synchronize
  * Highlight the lone entry in "Paths in Repository Settings" and click the lock icon
  * Under User Authentication, enter your Google username and **GOOGLE CODE PASSWORD**, not your normal password:
    * Sign into your Google account at google.com
    * Go to code.google.com/p/shika-na-mikono
    * In the top right corner, click Profile
    * Click Settings
    * Copy your password into the Password box under User Authentication in TortoiseHG
  * Once your password is entered, click Save
**Note:** If the option "Verify with Certificate Authority certificates (best)" is not available to you, just select "Verify with stored host fingerprint (good)", click Query and wait until a string of characters shows up in the box, then fill in your username/password.

For Mac, in MacHG:
  * Assuming you entered your credentials when adding the server repository, you should be good to go.
### Commit your edits ###
First you have to _actually make edits_. Change something in Shika's .tex files, but NOT in shika-tz.tex!! Then you'll have something to commit.

For Windows/Ubuntu, in TortoiseHG:
  * From the menu, View > Commit
  * Check the list of modified files to see the edits you made
  * Double (and triple) check your changes, additions, deletions, etc.
  * Enter a commit message in the Commit Message box (box below the Commit button)
  * Click Commit; your new changes should show up in the Revision History pane at the top
For Mac, in MacHG:
  * Select the [Browser View](http://jasonfharris.com/machg/MacHgHelp/pgs/AboutTheBrowserView.html) from the Document View Selector
  * Check the list of files to see the edits you made
  * Double (and triple) check your changes, additions, etc.
  * To commit everything you changed:
    * Select Action > Commit All Files...
    * Enter a commit message
  * To commit just one file or a subset of files:
    * Select only the files you want to commit
    * Action > Commit Selected Files...
    * Enter a commit message
  * Your new changes should show up in the History View
### Push to Google Code ###
For Windows/Ubuntu, in TortoiseHG:
  * From the menu, View > Synchronize
  * Click Pull (Pull incoming changesets from remote repository)
  * If TortoiseHG pulls new changes, [Merge](Instructions#Merging_changes.md) those changes and Commit again
  * Click Push (Push outgoing changesets to remote repository)
For Mac, in MacHG:
  * With your local repository selected (Shika TZ Local), click Pull
  * Select the Google Code repo from the drop down (Shika TZ Server)
  * If MacHG pulls new changes, [Merge](Instructions#Merging_changes.md) the changes and Commit again
  * Click Push
### Setting up the edit workflow ###
Once you've tried cloning and pushing for the first time, it's a good idea to understand what your workflow will be like beyond this starting point. A normal workflow with Mercurial, after cloning the repository, looks like this:
  1. Make changes
  1. Commit (these first two can be repeated many times)
  1. Pull (always pull before you push!)
  1. Merge (if necessary)
  1. Push
Then rinse and repeat.
### Merging changes ###
The reason you always Pull before you Push is because there's always the possibility someone else has pushed changes while you were making your own. In the cases where there were no changes pushed, you can simply push without worry. If there were changes pushed, then you have to merge those changes into yours before you can push yourself. If you end up pulling changes from others before you push your own, this is the procedure for merging.

For Windows/Ubuntu, in TortoiseHG:
  * Look for the changes you pulled in the Revision History window (should be near the top)
  * Right-click on the most recent and select "Merge with local..."
  * Check the dialog that pops up. The new change you pulled should be the one on top, and your most recent edit should be on the bottom
  * Click Next
TortoiseHG should be able to merge most changes itself automatically. In the special case where the changes you pulled overlap with the changes you just made, Tortoise will tell you there is a problem it can't resolve on its own. You will then have to physically go into the file that has the problem and make a decision.

# How to compile the book #
Compiling the book requires a LaTeX compiler.
### Obtain and install LaTeX ###
LaTeX is quite large (the full set of packages is nearly 3 GB), so it can be rather difficult to obtain through Tanzania's limited infrastructure. A small number of Volunteers have a DVD image of the full range of software, and we are currently trying to make this more readily available to Volunteers that want it.
  * Obtain the TeX Live DVD image from a fellow Volunteer
For Windows:
  * Download and install [DAEMON Tools](http://www.daemon-tools.cc/eng/downloads) (needed to create a virtual disk drive)
  * Mount the TeX Live DVD image onto the new virtual drive
  * DVD should auto-run the installer, look for the executable on the DVD if it doesn't
  * Perform a full install
For Mac or Ubuntu:
  * Put the DVD image in your Home folder
  * Open a Terminal (press Ctrl+Alt+T in Ubuntu, search "Terminal" in Spotlight on a Mac)
  * Type (or copy and paste) the following command into the Terminal (don't copy the '$'):
```
$ sudo mount -t iso9660 texlive2012-20120701.iso /mnt && cd /mnt && sudo ./install-tl
```
**Note:** Double-check the date in the filename; your DVD image may be named differently.
  * Select Options (press 'o' then 'Enter')
  * Select "create symlinks in standard directories" (L)
  * Press 'Enter' three times to select the defaults
  * Return to the main menu (R)
  * Install (I)

If you want a minimal installation (because you don't have the space for a full install), it is possible to trim down your LaTeX environment to about 850 MB. You can select the following packages from the normal installation process for Mac and Ubuntu, but in Windows you need to run a different installer than the one that auto-runs. To do this, open the DVD image in Windows Explorer and open "install-tl-advanced.bat". From here, do the following (instructions in parentheses are for Mac and Ubuntu):
  * Select Collections (press 'c' then 'Enter')
  * Deselect everything (press '-' then 'Enter')
  * Select the following collections (they are case-sensitive!):
    * Essential programs and files (a)
    * Extra generic packages (k)
    * Recommended generic packages (l)
    * Plain TeX supplementary packages (E)
    * Basic LaTeX packages (o)
    * LaTeX supplementary packages (p) - contains `mhchem`, very important!
    * LaTeX recommended packages (s)
    * Graphics packages and programs (x)
  * Optional choices:
    * The TeXworks Editor (A) - nice, barebones alternative to Texmaker
    * Windows support programs (B) - select if you're running Windows
  * For Mac and Ubuntu, follow the instructions above on creating symlinks before installing

### Install Texmaker ###
In addition to providing an excellent environment to edit LaTeX files, Texmaker (like other LaTeX editors) can compile PDFs with a single click.

For Windows and Mac:
  * Go to the [Texmaker homepage](http://www.xm1math.net/texmaker)
  * Download and install the latest version for your computer
For Ubuntu:
  * Open Ubuntu Software Centre and search for Texmaker
  * Install
### Compile the PDF ###
Once LaTeX and Texmaker is installed, you are ready to compile.
  * Open shika-tz.tex from Texmaker
  * From the drop-down menu in the toolbar ("Quick Build"), select "PDFLaTeX" and click the arrow to the left
  * If this is your first time compiling the manual, click the arrow again to compile a second time
  * After the compilation finishes, click the arrow to the left of "View PDF"
Texmaker may use its own built-in PDF viewer to show you the compiled manual. The actual PDF can be found in the top directory where the _Shika_ files are stored (the same folder that the shika-tz.tex file is in).

**Note:** The reason the manual initially needs to be compiled twice is because LaTeX requires two runs in order to sort through citations and links in the document, as well as to build the table of contents. If you only compile once, the table of contents will be missing and internal links between chapters will not work correctly. As a rule of thumb: When in doubt, compile twice.