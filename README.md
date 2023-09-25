# SQLite-improvement
The SQLite database engine has an R* Tree inside its code which helps for inserting, deleting, searching and updating. However, in databases with higher dimensionality we found some disadvantages in that structure that's why I've created an XTree above the existing Tree to improve performance. 

The XTree has three types of nodes which helps to high dimensionality management (nodes, directory nodes and super-nodes), super nodes help to avoid unneccessary and inefficient splits, high dimensionality is a problem in R*-Tree as it grows. Also it helps to manage so overlapping because in the R* Tree we would make a lot of paths to find the same goal.

<p align="center">
<br> Directory node <br>
<img width=400px src=https://github.com/alexjr2001/SQLite-improvement/assets/63054183/8a3d75fb-3aca-4bf5-8c60-ce51ce354c9e>
<br>
<br> X-tree representation <br>
<img src=https://github.com/alexjr2001/SQLite-improvement/assets/63054183/97749dae-6cd0-4f0a-9e4f-3856c32f07d4>
</p>

In case of queries or deletion the supernodes help to save in memory data continously and have a linear scan. In case of insertion, if there's not overflow we insert as the R*Tree, otherwise we make an hypothetical split to see if the overlap is minimum searching for the minimal overlap split if it is not we create a supernode. The minimal overlap split has a spliting history to know where to perform the split. 

You can find more information about X-tree structure in this [document](https://bib.dbvis.de/uploadedFiles/190.pdf).

In the following part we will see how to compile and run the project. It was the sent document with the code in the project (its structure was requested).

### README file delivered with the project

PROJECT: XTREE INDEXED TO SQLITE
</br>AUTHOR: ALEXANDER SEBASTIÁN GÓMEZ DEL CARPIO

README CONTENT
-----------------------
 * INTRODUCTION AND REQUIREMENTS
 * HOW TO COMPILE AND RUN?
 * CONTACT

Introduction
------------
In this file you find how to compile and execute this final project which is about the SQLite Database but improved. Initially this database worked with an R* tree, however, it has been decided to implement the X tree instead of, aiming to prove that this data engine works better than if it would have an indexed R tree.

Mention that the whole project was worked above the R* tree (approx. 5000 lines). The requirement to work with this new database is to download the entire [amalgamation-folder](https://github.com/alexjr2001/SQLite-improvement/tree/main/sqlite-amalgamation-3380400) which has everything you need.

How to compile and run
--------------------------
First, know that the compilation and execution process is the same as with the R* tree. Then, having downloaded all the necessary documents. It should be compiled in the following way whether in unix systems or in Windows using cygwin or mingw+msys (during the whole process the WSL terminal was used to compile):

```
gcc shell.c sqlite3.c -lpthread -ldl -lm -o sqlite3 -DSQLITE_ENABLE_RTREE=1
```

To run the database we must enter the following:

```
./sqlite3
```

In this way, the database will be ready to work as SQLite normally works. 

Contact
--------
GMAIL: alexsgdc@gmail.com   

Development Date: 04/2022
