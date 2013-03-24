Version Control Using Git
===============================================
Licence
-------
CC-BY

Author
------
* Dan McGlinn
* danmcglinn@gmail.com
* @danmcglinn on Twitter
* 03/23/13
* USU Bootcamp

First Commit
-------------

git init spring_plants

cd spring_plants

git help 

git status

nano plant_list.txt

git status

git add

git add .

git status

git commit -m "Initial commit, add plant list"

git status

nano plant_list.txt

git status

git commit -m "Add a species to the list"

git add plant_list.txt

git commit -m "Add a species to the list"

git status

nano plant_list.txt

git commit plant_list.txt -m "Delete a species from the list"

git log

**Do it Yourself Exercises**

* Add new observations to plant_list.txt

* Create a new file called sites.txt, add this to the repo


Move and Remove Files
-------------

git mv sites.txt site_list.txt

git status

git commit -m "Rename sites.txt to site_list.txt to be consistent"

git status 

nano habitat_list.txt

git add .

git commit habitats.txt -m "Add a habitat data file"

**Do it Yourself Exercises**
* Remove the file site_list.txt

* Create a directory called data

* Move the file plant_list.txt and habitat_list.txt to the directory data

Finding What’s Different
=========================

cd data

nano habitat_list.txt

git diff

git commit -m "Add a site to the habitat_list data"

git diff 

**Do It Yourself Exercises**
* Modify plant_list.txt by adding a species to it

* Examine using git diff to examine what you changed

* Examine how your changes differ from the initial creation of plant_list.txt

Examine the Past
====================

nano bird_list.txt 

git diff

git commit bird_list.txt -m "Add species to the species datafile"

git checkout bird_list.txt

git log

git status

git checkout master

git status

git log

**Do It Yourself Excursuses**
* Change habitat_list.txt and commit your change.

* You decide you would like to see the old habitat_list.txt 

* Checkout the commit just prior to when you removed it

* Examine the status of your repo and habitat_list.txt

* Return to the master branch

Turn Back Time
====================

nano habitat_list.txt

git diff

git status

git checkout habitat_list.txt

git diff

git status

nano habitat_list.txt

git add .

git status

git reset habitat_list.txt

git status

git diff

git checkout habitat_list.txt

git rm species_list.txt 

git commit species_list.txt -m "Remove species data"

git log

git reset --hard 

**Do It Yourself Exercise**

* Modify plant_list.txt
* Return plant_list.txt to the last commit state
* Modify plant_list.txt and stage it
* Return plant_list.txt to the last commit state
* Return the working directory to when habitat_list.txt existed

Working with Remote Repos
==========================

git remote add origin git@github.com:dmcglinn/spring_plants.git

git pull origin master

git push origin master
