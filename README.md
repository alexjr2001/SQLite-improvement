# SQLite-improvement




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

How to compile and run?
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
