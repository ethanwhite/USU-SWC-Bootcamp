Software Carpentry Bootcamp
=========================
Utah State University
March 23-24, 2013
Taught by:
=========
Ethan White (@ethanwhite)

Dan McGlinn (@DanMcGlinn)

Cait Pickens (@caitpickens)
Schedule:
========
* Day 1 Morning - Shell
* Day 1 Afternoon - Version control (it's like a lab notebook for your code)
* Day 2 Morning - Python
* Day 2 Afternoon - SQL

Useful Web Links:
===============
http://swcarpentry.github.com/boot-camps/2013-03-23-utahstate/

https://github.com/ethanwhite/USU-SWC-Bootcamp

softwarecarpentry.org - for video tutorials and online office hours!

programmingforbiologists.org - Ethan's programming for scientists course material, semester long course (usually Fall). Introductory and Advanced courses
Installation:
==========
Windows setup instructions:

* http://software-carpentry.org/setup/windows.html

Mac:

* Install Anaconda CE and select the Make Anaconda the Default Python option. This requires they to run a file from the command line as described in the
* If they don't have git installed (they can check by typing git into the terminal they'll need either install Git (http://code.google.com/p/git-osx-installer/downloads/list?can=3) or XCode (https://developer.apple.com/xcode/)
* Download and install Firefox if you do not already have it installed (http://www.mozilla.org/en-US/firefox/fx/#desktop)
* In Firefox go to Add-ons, search for SQLite Manager and install it
* Install for ipython (mac 10.7)
	* sudo ln -s ~/anaconda/bin/ipython /usr/bin/ipython


Linux:

* Install Anaconda CE or install IPython and IPython Notebook using their package managers.

SQL:
====
Data files:

    https://raw.github.com/ethanwhite/USU-SWC-Bootcamp/master/surveys.csv

    https://raw.github.com/ethanwhite/USU-SWC-Bootcamp/master/species.csv

    https://raw.github.com/ethanwhite/USU-SWC-Bootcamp/master/plots.csv

Cheat sheet:

    https://github.com/swcarpentry/boot-camps/blob/master/sql/cheat-sheet.md

Notes

    * is a wildcard in SQL, too. Putting an * in will return ALL the columns from your table.

    DISTINCT is sql for "unique"

    empty cells are stored as a NULL value (red in sqlite)

    NULL is a special value and is not really the same as an empty string. This may potentially be important when analyzing data!!

    In a database, NULL is probably represented best at simply blank, or NULL typed out

    Sometimes researchers will fill in NULL values with other values, like -999, 999 or 0. These don't work well because you can accidentally average these values in (if they are numeric) and not realize that you've made an important mistake! 

    If you use something like "--", "no data", "missing", you can still run into problems, because now you may have column with both integers and strings in it, which will give you problems in sql and in many coding languages. 

    Whatever you use, be consistent, double check that you haven't made errors, and CLEARLY describe what you've done so in the future, you remember!

    use IS NOT NULL to filter out these values for a column

    use IS NULL to see only rows where NULL values exist in a column

    JOIN is really powerful

    Order of commands does matter - hierarchical, details should be on cheat sheet

Style Guide

    CAPITALIZE keywords (e.g., SELECT, FROM) and write other words in lowercase

    Write sections of your sql on different lines to improve readability, esp. once you get more complex queries

    Use the semicolon because other programs will require it

    import matplotlib as plt

    import numpy as np

    import pandas as pd

    l/cheat-sheet.md

Python
======
Notebook:

    https://raw.github.com/ethanwhite/USU-SWC-Bootcamp/master/intro_to_python/intro_to_python/intro_to_python.ipynb

Data:

    https://raw.github.com/ethanwhite/USU-SWC-Bootcamp/master/intro_to_python/intro_to_python/practice_data.txt

    https://raw.github.com/ethanwhite/USU-SWC-Bootcamp/master/intro_to_python/intro_to_python/practice_data2.txt

    https://raw.github.com/ethanwhite/USU-SWC-Bootcamp/master/intro_to_python/intro_to_python/CO_pollution.csv

Notes:

    ipython notebook shortcuts:

    CNTRL-m-b makes a coding cell below

    SHIFT-Enter runs the code in your current cell

    CNTRL-m-d DELETES a cell, use with caution!

    Get the history of commands using %history

    variable type matters: integers, floats, and strings behave differently

    a list stores variables inside square brackets [ ] 

    variables are indexed within a list, so you can pull out specific values. Python starts counting at 0 instead of 1!

    you can look at, change, or insert values using these index numbers

    Why python?

    open source

    relatively simple, straightforward syntax

    translatable concepts across languages, easier to communicate across disciplines

    LOTS of online support, inviting support for beginners, easy to find tutors

    lots of development for GIS folks

    Python modules (a.k.a. libraries)

    numpy (numerical module), scipy (scientific module), pandas (dataframes for all you R-peeps)

    can avoid using the out_file.close() statement by opening files with a syntax:
    with open("for_advisor.txt, 'w') as file:
      for line in file:

    If you're wondering how to plot in python, see the following file:
        http://www.ast.uct.ac.za/~sarblyth/pythonGuide/PythonPlottingBeginnersGuide.pdf

Shell:
=====
https://github.com/ethanwhite/USU-SWC-Bootcamp/blob/master/shell.md

The shell is one of the most powerful ways to automate data analysis.

We can combine tons of tools in the shell (regardless of what language they are written in)

The shell is how we interact with remote machines (like servers, high performance computing centers)

Useful shell commands

	pwd means "print working directory" and tells us where we are on the computer

	ls means "list" and tells you everything that the current directory contains

	"-" (dash) is a convention in the shell for saying "modify a command" and gives you different options

	ls -f (-F in Git) tells you what is a folder and what is a file

	TAB can be used to auto complete

	cd .. moves up to the parent directory

	mkdir to make a new folder

	nano file_name.txt for creating a new file or editing an existing file

	cp to copy file

	mv to move files

	.. takes you to the directory above the one you are in (ex: cd .. moves up one directory)

	cat to concatenate, show me what's in a file

	sort will sort a file (without additional arguments, sorts on beginning of each line)

	command --help to find help!

	CTRL-c cancels a line/command in the shell

	clear to clear the screen

	history gets your command history

	"*" is a wildcard. It can go at the beginning (*.txt) the end (data*) or in the middle (data*.txt) of an expression that you are searching for

    for datafile in data*

            do
            echo $datafile
            python species_counts.py $datafile
            done

    In the for loop above, the bold are the necessary commands, the other parts are defined by you. You open a for loop with for, tell it what to do, and end it with done.

    .sh indicates a file is a shell script

    bash is a command to run shell scripts

    # indicates that what comes after is a comment. The program will ignore that line

    Note: the shell is just a different way to see your file system (like your finder, which is what you are probably used to using)

    The shell has shortcuts! Use the tab key to reduce the number of mistakes you make when typing :]

    Tip: on a Mac, open . opens your window

    bash is the bourne again shell

    When you have multiple possible completions, autocomplete (with TAB) will try to complete your file as far as it can. hit TAB again, and the shell will display all options for autocompletion

    Cheat sheet for bash commands: http://files.fosswire.com/2007/08/fwunixref.pdf

    Give everything a meaningful name. It makes your life so much easier!

    Google your questions about bash! 

    If the shell doesn't output an error, then you can usually assume that things executed okay (maybe not correctly though, ha).

    history > file.txt -- write history into a text file

    Second most individual 

    sort randomBirdCountData.txt -k 3 -n | tail -2 | head -1

    This combines files then counts species and sorts the result

    cat *.txt  | python species_counts.py | sort

Nano:
=====

    If you don't like nano, just use notepad instead --> there are lots of text editors and everyone has their favorite. some other options are vi, emacs

    Used for reading/editing text files

    Using the text editor in the shell is *exactly the same* as editing with a graphical text editor (which is probably what you're used to)

    CTRL-x exits

    CTRL-o saves

    Cannot CTRL-v to paste data in Git Bash, use edit>paste from menu (icon in upper left corner)

Version Control:
===========

    Lecture Slides:

    https://github.com/ethanwhite/USU-SWC-Bootcamp/blob/master/

    https://github.com/ethanwhite/USU-SWC-Bootcamp/blob/master/version_control_slides.pdf

    Lecture Commands:

    https://github.com/ethanwhite/USU-SWC-Bootcamp/blob/master/version_control.md

    git status check the current status of the repository

    git add

    git add . will add ALL new or modified files in your working directory 

    git add filename will add ONLY the specific file you want

    git commit filename -m "super useful message about what change I made"

    git log shows the history of the repository

    git mv move files while having git know that we want to move it

    git rm remove a file while having git know that we want to remove it

    git diff shows what was added or deleted to a file

    git checkout is your personal time machine, to go back in your history

    can be dangerous, if you're not careful

    checkout can be used when we have a change in the local copy, but we haven't staged it yet. Can checkout the "pristine" version from the repository to discard recent edits (e.g., git checkout filename). However, this a destructive command and it WON'T record those most recent edits, but simply discard them.

    to go back to the most recent copy use: git checkout master

    git reset filename

    takes the changes from the staging area back to the working copy

    soft reset - moves out of staging area, but doesn't throw away changes, unlike checkout

    git reset --hard

    everything goes back to previous version of repo. Changes are gone. Can't go forward again

    Check out GitHub for an online collaborative experience

Python
=====
Why Python.  

    More flexible than bash

    reproducibility

    Open science (platform independent)

    Requires indented code (4 spaces) when using for loops and functions

    makes code more readable

Why iPython notebook (ipynb) IT'S COOL

    Interactive as teaching tool.  Combines code with explanations

    Everything in one place (text, code, images, links, video)

    Don't close the terminal that you used to open the notebook --> your notebook will strop working

    Autosave not in ipython yet , but will likely be soon

    Ipython works by running a single instance of python in the background

    this means that any variable created in the notebook exists until you either forceably remove the object or close the notebook

Basics

    variables

    Basic Operations

    Printing

    "print" use this command to return variables to the console

    Adding

    "+" sign - like a calculator

    adding strings together with "+" concatenates the two strings

    can mix ints and floats with adding

    cannot mix ints and strings when adding

    += can be used to add values to an existing object

    my_int = 1

    my_int += 1

    print my_int  

    2

    Switching between types

    str() to declare an object a string e.g., str(my_int)

    int() to declare an object an int e.g., int(my_string)

    this will work if my_string is something that could be considered a number

    e.g., "1" or "3" but not "hello"

    Data structures

    lists

    [] creates a list

    indexing of the list starts at 0

    [0, 1, 2, 3] so their are 4 items in this list and the first one is at the zero index

    .append()

    concatenates items to a list

    my_list.append(2) adds a two to an existing list

    .insert()

    inserts an element into a list

    my_list.insert(0, "Dan") places the string "Dan" at the front 

    len()

    to return the lenght of a list

    len(my_list) 

    .split

    take a string and split it based on a deliminter

    my_string = "1 2 3 4"

    my_string.split(" ") will break it up 

    Decisions

    Boolean

    test if statment is True or False

    >    greater than

    <    less than

    >=  greater than or equal to 

    <=  less than or equal to 

    <> not equal

    !=   not equal

    ==  equal to 

    Examples

    3 > 4 is False

    use if statments to control program flow

    if True :

    do some stuff

    else:

    do something else

Helpful Ipython Hot Keys 
Run code
  SHIFT ENTER runs block of code selected
Toggle line numbers
  CNTRL m L
Files:
=====

    https://github.com/ethanwhite/USU-SWC-Bootcamp/raw/master/data.txt

    https://github.com/ethanwhite/USU-SWC-Bootcamp/raw/master/data_drycanyon_2013.txt

    https://github.com/ethanwhite/USU-SWC-Bootcamp/raw/master/data_logancanyon_2013.txt

    https://github.com/ethanwhite/USU-SWC-Bootcamp/raw/master/species_counts.py

