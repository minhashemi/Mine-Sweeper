# MineSweeper CLI Version
## Video Demo:
https://youtu.be/ppbeVFmIp8U
## About:
The Project is developed by Amin Hashemi (@minhashemi)
CS50P, Spring 2021

## Description:

Main Page
---------

Open as many cells as you can without hitting a bomb 💣

By running the project, the following menu will be shown in which you will see name of the project written in ASCII art using the pyfiglet module and 4 choices as mentioned below:

1.  Login
2.  Sign Up
3.  Score Board
4.  Exit

Login
-----

here you will have a choice to enter credentials to login, go to sign up menu or to return into main menu

when you try to enter credentials to login, you will be asked for your username and if the username doesn't exists in user database, you will be asked to register first. Unless you will be asked for your password and if the password matches, you are welcome to select game level and play.

Note that if no users exist in the user database, you will be asked to register first.

Sign Up
-------

In this menu, you will have a choice to enter your credentials or to get back to main menu

if you choose to enter your credentials, you will be asked to choose a username. If the username already exists in user database you will be prompted to try again by choosing another username. Unless you will be prompted to choose a password. CS50 Podcast encouraged me to encrypt passwords. So in this program, passwords are encrypted using base64 library. So not easily breakable :)
all user data is kept in a csv file.

Game Play
---------

Game is developed in 3 levels.

-   Beginner: $10\times10$ game board
-   Intermediate: $15\times15$ game board
-   Advanced: $25\times25$ game board

game board is instantiated from the GameBoard class which manages to create, display and manage all game logic.

<aside> 🛠 To Developers: you can easily config the game to have a $x \times y$ table by making the game board instantiation optional in `play` function.

</aside>

<br />

in the beginning, all cells are hidden with `*` sign and you can enter the coordinate of the cell you want to open as `<row> <col>` or flag a cell by `<row> <col> F`

the game logic is like the classic MineSweeper game. and bombs are shown with `x`. at least 10% and at most 30% of cells are bombs.

for each cell you open and that is not a bomb, you will gain 10 points.

after you lose or get a victory, you will be shown the updated score board.

Score Board
-----------

Score board is sorted and saved each time the score changes based on scores and if there exists some users with same score, they will be sorted based on usernames alphabetically.
all sorting stuff of this menu, will be done by `pandas` library.

scoreboard style is printed using tabulate module.

Exit
----
Will always quit the game using `sys.exit`

requirements.txt
----------------

all required pip installable modules are being written in this file which is available in the source directory of the project.

`pip install pandas`

`pip install pyfiglet`

`pip install tabulate`

test_project.py
---------------

you can test some of the functions of this project using pre-written functions using the `pytest test_project.py`
you are welcome to implement your own test cases as well.

userdb.csv
----------
Username, encrypted password and total score of a user is kept inside this file. If it doesn't exist, the program will make it first.
