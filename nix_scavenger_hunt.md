# *nix Scavenger Hunt

Complete the following challenges using the command-line interface on your favorite
Unix or Linux operating system. You are welcome and encouraged to consult any
additional documentation online or in books.

Please add your answers/responses/text pastes to the document after each prompt.

Note: For some of the challenges you will need to reference files included with
this repository, so you will need to fork the repo into your own Github account
and then clone it to your development environment.

## The Challenges

### Navigating the Filesystem

* Get an idea of where you are in the operating system. Use the `pwd` command to find your "path to working directory"--your current location in the filesystem of your devbox. *Paste the output of the `pwd` command here:*
/projects/wats1030-intro-to-unix
user@1e7e519cc4c8:/projects/wats1030-intro-to-unix$

* Discover more about this filesystem. Use `ls` (the "list" command)to see what is in this directory. *What directories and files do you see when you run `ls`?* 
challenge_files  LICENSE  nix_scavenger_hunt.md  nix_scavenger_hunt_stretch.md  README.md  super_scavengers.md
user@1e7e519cc4c8:/projects/wats1030-intro-to-unix$

* You can use *options* to modify how a command runs. Try using `ls -alh` to see the contents of your current directory. *How are the results different when you use the `-alh` options?* 
total 36K
drwxr-xr-x 5 user user  178 Jul  6 02:20 .
drwxr-xr-x 5 user root   87 Jul  6 02:20 ..
drwxr-xr-x 7 user user 8.0K Jul  6 02:20 challenge_files
drwxr-xr-x 2 user user    6 Jul  6 02:20 .che
drwxr-xr-x 7 user user  131 Jul  6 02:20 .git
-rw-r--r-- 1 user user 1.1K Jul  6 02:20 LICENSE
-rw-r--r-- 1 user user 5.7K Jul  6 02:23 nix_scavenger_hunt.md
-rw-r--r-- 1 user user  317 Jul  6 02:20 nix_scavenger_hunt_stretch.md
-brings up more info.

* The `man` ("manual") command tells you more about how any given command works. (*WARNING:* CodeAnywhere does not support the man command. You can click the following link to complete this task: http://man.he.net/). Run `man` to see instructions about how to use `man`. Then use `man` to learn what the `a`, `l`, and `h` options mean when used with the `ls` command. *Write down what those options do?* 
          'a' intro
           Display,  in  succession,  all  of the available intro manual pages
           contained within the manual.  It is possible to quit  between  suc-
           cessive displays or skip any of them.
           -'l' -Tdvi ./foo.1x.gz > ./foo.1x.dvi
           This  command  will  decompress  and format the nroff source manual
           page ./foo.1x.gz into a device independent (dvi) file.   The  redi-
           rection is necessary as the -T flag causes output to be directed to
           stdout with no pager.  The output could be viewed  with  a  program
           such  as  xdvi or further processed into PostScript using a program
           such as dvips.
           !!-'h' have not found 'h'
           
* Commands can also take *arguments*, which are usually the names of files or locations that you want the command to work with. Try running `ls /` to see what files are in the *root* directory of the filesystem. *What files and directories do you see listed?* 
challenge_files  LICENSE  nix_scavenger_hunt.md  nix_scavenger_hunt_stretch.md  README.md  super_scavengers.mduser@1e7e519cc4c8:/projects/wats1030-intro-to-unix$

* A Unix filesystem has a few special shortcuts to refer to specific locations. `/` indicates the *root* of the filesystem, meaning the top-most directory in the filesystem hierarchy. Use the `cd` ("change directory") command to move to the root directory. (Hint: Use `man` to look up the `cd` command if you have any issues) *Then run `pwd` and paste the output here:*

/home/user
user@56dd0412af2e:~$

* Another special shortcut in Unix is the `~` location. This indicates the *user root* directory, meaning the top-most directory in the hierarchy that comes below your user account. Use `cd` to move to `~`. *Run `pwd` and paste the response here:* 
/home/user

* Change directory into the `challenge_files` directory. Use `ls` to find only the files with a `.demo` pattern. *How many files do you find?*
* Use the `cd` command to move "up" one directory. *Where are you in the filesystem now?* same place
* Press the up arrow on your keyboard. *What just happened?* scrolls through cd, ~, and pwd
* Press the up arrow a few more times. *What do you see?* it stops on cd
* Run the `history` command. *What do you see?* user@56dd0412af2e:~$ history
    1  cd
    2  pwd
    3  cd
    4  ~
    5  pwd
    6  cd
    7  pwd
    8  cd
    9  cd
   10  history
user@56dd0412af2e:~$

### Observing the System

* Discover what account you are logged into using the `whoami` command. *What username are you currently using?*user
user@56dd0412af2e:~$
* Discover who else is on your system with the `who` command. *Are any other users using your system?No If so, list them here:*
* How long has your system been running? Use `uptime` to see, and *paste the result here:*user@56dd0412af2e:~$ uptime
 05:41:11 up 7 days, 21:34,  0 users,  load average: 0.12, 0.33, 0.73
user@56dd0412af2e:~$
* Run `ps aux` and review the results. (Hint: Use `man` to learn more about the `ps` command and options.) *How do you interpret what you see here?* I think it's stats about everything I've run. But I don't know what each line is referring to.
* Run `top` and review the results. (Hint: You may need to use `ctrl-c` to get out of this app.) *How do you interpret what you see here?* It keeps changing so something is updating but I don't know what. 

### Finding and Viewing Files

* Make sure you are in the `challenge_files` directory. Use the `*` wildcard to find all the files that have the word "credit" in the filename. *How many files did you find?* credit_cards2.txt  credit_cards.txt 2 files.

* Use the `more` command to view one of the `credit_cards` files you just discovered. (Hint: Type `q` to quit viewing the file. Press the `spacebar` to page down. Use your keyboard arrows to move up/down.) *What is the date in the file you have viewed?* 1-15-2015
 
* Use the `find` command to search for files more effectively. Search the sub-directories under `challenge_files` to find the location of the file named `modi_laboriosam.txt`. *Where is that file located?* Usage: find [-H] [-L] [-P] [-Olevel] [-D help|tree|search|stat|rates|opt|exec|time] [path...] [expression]

* Use the `grep` command to search for text within a file. Use `grep` on all the `.user` files in `challenge_files` to find which files contain "WA" (the abbreviation for Washington state). *How many files did you find?* 2: Britt-Erdman.user:O'Harachester, WA 37261
Lissie-Strosin.user:Jewessfurt, WA 00816-7241

* Use the `-r` option of `grep` to *recursively* find the text "Waldo" hidden in a file somewhere under the `challenge_files` directory. *Paste the result showing the file and line where the word "Waldo" shows up.* serial-numbers/eaque_molestiae.txt:Ut est maiores quia autem. Nisi modi Waldo sed corporis sit explicabo ut est. Et est placeat ea sunt sunt consectetur sunt incidunt. Explicabo v
el esse blanditiis dolorem culpa non quia.

### Pipes and Connecting Commands

* Sometimes it's useful to output the results of a command to a text file for further analysis, reference, or processing. Try running `ls > files.txt`. Notice that the file `files.txt` was created. View that file using `more`. *What do you see in the `files.txt` file?* cherylac.github.io
files.txt
wats1030-intro-to-unix
wats3020-mad-libs
wats3020-sandwich-machine

* Notice that if you run `ls -alh` in the `challenge_files` directory, the files scroll by very quickly. Sometimes it would be better to get the results in a paginated format. Try running `ls -alh | more`. *Describe what you see when you run `ls -alh | more`.* it looks the same as doing 'ls -alh'.

* Earlier, when you viewed the list of active processes on your devbox using `ps aux`, the list was probably really long. You can make this list more manageable by using the pipe (`|`) to filter the results of `ps` using `grep`. Run `ps aux | grep <your_username>` to see what processes are running for your specific user. *Paste the list of processes that reference your username here:* user       592  0.0  0.0  12932   976 pts/0    S+   05:00   0:00 grep --color=auto user@70eda79b9cc3
