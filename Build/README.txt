Word frequency counter for Office 2007/2010.

More information here: http://blogs.cs.st-andrews.ac.uk/angus/2008/11/word-2007-add-in-word-frequency-counter/
Contact Address: angus AT cs.st-andrews.ac.uk

-- PROGRAM NOTES --

Once installed the program can be accessed from the 'REVIEW' tab of Microsoft Word.


IGNORE LIST

An ignore list file is generated when the program is first run. It is located in your Documents folder and is called 'wordFrequencyCounterIgnoreList.txt'. 

Add words to this file if you wish them to be ignored by the application.

Special option: if you want numbers to be ignored then you should include the line <numbers> in the ignore list file. Please note that this will make the add-in run slowly because it
must check whether each word is a number.

-- SOURCE CODE NOTES --

The source for this project was created in Visual Studio 2010, but it should compile in Visual Studio 2007 as well.

Documentation is contained within the project source. The following points summarise its structure:
- The Ribbon class is the entry point into the add-in. This class calls the Worker Manager class which creates the task pane and asynchronously starts the computation running.
- The frequency calculator (executing asynchronously) continually updates the progress bar in the task pane and places the result of the frequency count in the ResultContainer class.
- IgnoreList is used to find, load and save the ignore list. It also contains a default ignore list.