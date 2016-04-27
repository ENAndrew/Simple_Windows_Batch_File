# Simple Windows Batch File
A very quick tutorial for opening multiple command prompt actions with a .cmd file

This is a basic way to use a .cmd file to perform multiple Windows command line activities at once.

I am using this particular script to start mongod in one command prompt, open a second in which to run nodemon for a specific set of project files.  

1. Open notepad
2. Save a new document as a .cmd file. 
    - Make sure the name doesn't overlap with any other executable programs
    - I named mine projectNameRun.cmd so it does what it says on the box
    - This should be saved as type - All Files (\*.\*)
3. Enter your commands (see below)
4. Save your .cmd file to a place you can find it - I just threw mine on the desktop as it's only temporarily being used for this project. 
5. Double-click on the file to run

Here is the full text of the file (your paths will be different):
```
@echo off

cd "C:\Users\Erica Andrew\Desktop\Mongo\bin"
start mongod --dbpath ./data/db

cd "C:\Users\Erica Andrew\Desktop\NewClassProjects\ecommerce\server"
start nodemon
```

And what each part does: 
```
@echo off
```
- Tells the program not to display any of the following lines.  "echo off" itself will be displayed unless preceeded by the @ symbol.

```
cd "C:\Users\Erica Andrew\Desktop\Mongo\bin"
start mongod --dbpath ./data/db
```
- Follow the file path in quotes, 'start' opens a command prompt and initiates the following command.

- (You may have a different command to run mongod.)

```
cd "C:\Users\Erica Andrew\Desktop\NewClassProjects\ecommerce\server"
start nodemon
```
- Follow the file path in quotes, opens a second command prompt and initiates nodemon in that location. 

Update 04/26/16:  

If you need to ensure that one command finishes executing prior to others running add the /wait 
For instance, I need webpack to finish it's operation prior to running other things, so: 

```
cd "C:\Users\Erica\Desktop\AfterHoursProjects\react-blog"
start /wait webpack
```
