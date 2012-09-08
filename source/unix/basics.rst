=============
UNIX Basics
=============

Terms
=====

boot process
------------
1. ROM/firmware's loading of programs for booting (bootstrapping)
    I. bootstrap phase only identifies the hardware avalible for booting and whether it is usable
2. unix kernel is loaded (resides in root partition of system -> /boot/vmlinuz
3. initialization phase - system processes and scripts are started
	I. init process starts first (is parent of all other processes)
	II. init looks at /etc/inittab which identifies how init should interpret diffrent run levels
		a. run level is a grouping of processes or daemons (processes that run all the time)


Commmands
=========
jobs
    processess
    
kill %n
    kill job
    
whereis app
    location of app ex. /usr/bin/gedit

w
    users logged on

uptime
    uptime

top
    most CPU-intensive tasks running on the server

htop
    TODO
    
free
    memory usage

iostat
    CPU+IO statistics

kill
    TODO
    
killall
    TODO
dmesg
    TODO
    
pgrep
    TODO
    
pkill
    TODO
    
lsof
    TODO
	
tail -f error_log
    Show the last 10 lines of error_log and continue to output any new data added to the end of the file.
    
sudo !!
    run the previous command with superuser privileges.
    
$ cd !$
    the "!$" is a shortcut for the argument used in the last command. So if you create a directory in one like using mkdir, you can type this command to change to that directory without needing to type out the whole directory name. Handy!
    
$ ^save^dave^
    re-run the previous command, replacing the first instance of "save" with "dave".

~
   short hand for usr home dir

?
   substitue for symbol for any single character::
         $ ls
         foo
         bar
         baz

         $ rm ba?
         $ ls
         foo
pwd
   dir your in

ls -a
   includes hidden files

ls -l
   includes extra info

wc -l foo
   gives you word count

ls | wc -l
   lists number of files

ls | xargs wc -l
   number of lines for each file

file
   finds file type

cp -l
   copy, ask before overwrite

Bash Shortcuts/Hot Keys
-----------------------

Commands are similar to emacs::

    Ctrl-a 	        Move to the start of the line.
    Ctrl-e 	        Move to the end of the line.
    Alt-] x 	    Moves the cursor forward to the next occurrence of x.
    Alt-Ctrl-] x 	Moves the cursor backwards to the previous occurrence of x.
    Ctrl-u 	        Delete from the cursor to the beginning of the line.
    Ctrl-k 	        Delete from the cursor to the end of the line.
    Ctrl-w 	        Delete from the cursor to the start of the word.
    Ctrl-y 	        Pastes text from the clipboard.
    Ctrl-l 	        Clear the screen leaving the current line at the top of the screen.
    Ctrl-x Ctrl-u 	Undo the last changes. Ctrl-_
    Alt-r 	        Undo all changes to the line.
    Alt-Ctrl-e 	    Expand command line.
    Ctrl-r 	        Incremental reverse search of history.
    Alt-p 	        Non-incremental reverse search of history.
    !! 	            Execute last command in history
    !abc 	        Execute last command in history beginning with abc
    !n 	            Execute nth command in history
    ^abc^xyz 	    Replace first occurrence of abc with xyz in last command and execute it


FIND
====

starting with the root directory, look for the file containing the string fname::

   find / -name {*fname*}

look in current directory for T.java::

   find . -name T.java

look for files ending in .conf in the /etc folder::

   find /etc -name '*conf'

quotes keep shell from expanding wildcards::

   find . -not -name '*.java' -maxdepth 4

find files::

   find . -type f

find directories::

   find . -type d                          

find links::

   find . -type l                          

changed within a day::

   find . -mtime -1

changed within 15 minutes::

   find . -mmin -15                        

compare to filea::

   find . -newer foo.txt                

compare to date::

   find . -type f -newermt '2010-01-01'    

find file between dates::

   find . -type f -newermt '2010-01-01' ! -newermt '2010-06-01'    

find via permissions::

   find . -perm 644        
   find . -perm -ug=w

find via permissions::

   find . -size -1k        

find with size more than 100MB::

   find . -size +100M      


Grep
====

Lookup "AccessFileName .htaccess"::

   grep -n "AccessFileName .htaccess" /etc/httpd/conf/http.conf

search command history::

   history | grep http_load

search Bananamans home folder recursively and case-insensitively for all files containing "superted".::

   $ grep -iR "superted" /home/bananaman/

search the file Skeletor.txt for lines containing "Panthro"
(case-sensitive).::

   $ grep "Panthro" Skeletor.txt

replace all instances of "Superman" with "Batman" in SuperheroLeagueTable.csv and output.::

   $ sed 's/Superman/Batman/g' SuperheroLeagueTable.csv

Output the 15th line of BabyGotBack.txt.::

   $ awk 'NR==15' BabyGotBack.txt

search for word matches and display the line number::
   
   grep -nr 'new Foo()' src

search for term foo and surrounding lines::
   
   grep -r -C 2 foo src

show any of the last 10 lines of error_log with "badscript.php" in them, and watch the file for new lines with "badscript.php" in them.::

   tail -f error_log | grep "badscript.php"

List just the sizes of all files in a folder.::

   ls -al | awk '{print $5}'

list files in a folder and replace "123" with "456" in their names.::

   $ ls | sed 's/123/456/g'

show free space on the /dev/sda1 drive.::

   $ df | grep "/dev/sda1" | awk '{print $4}'

output the third item on the third line of vmstat (the amount of virtual memory in use).::

   $ vmstat | awk 'NR==3' | awk '{print $3}'

list all files in a directory with their attributes, reduce that list to just their names, filter for just those containing "Holiday" and, for those, just show their file extensions (yes, a hugely contrived example).::

   $ ls -al | awk '{print $8}' | grep "Holiday" | sed 's/^[^.]*\.//g'
    
Emacs
=====

Alt (AKA META)

Basic Commands::
    Alt-<       Move to beginning of file
    Alt->       Move to end of file

    Ctrl-v      Move forward one page (screen full)
    Alt-v       Move back one screen
    Ctrl-l      Centers screen around cursor

    Ctrl-a      Move to beginning of line
    Ctrl-e      Move to end of line
    Alt-a       Move to beginning of sentence
    Alt-e       Move to end of sentence

    Ctrl-f      Move cursor right
    Ctrl-b      Move Cursor left
    Ctrl-p      Move Cursor up
    Ctrl-n      Move Cursor down
    Alt-f       Move cursor right (by word)
    Alt-b       Move Cursor left (by word)

    Ctrl-d      Backspace/Delete
    Ctrl-k      rm all text on a line
    Ctrl-y      brings back removed text
    Ctrl-x u    Undo

    Ctrl-x Ctrl-f Find a file       Opens new file
    Ctrl-x Ctrl-f Ctrl-g            Cancels minbuffer
    Ctrl-x Ctrl-s Save File


Screen
======

screen -list
   List Screen sessions

screen -r (name)
   Reattach

screen -S (name)
   Creates screen with meaningful name

Crl-a Crl-d
   Detach


Package Management
==================

APT
---

remove program and configuration files associated with it::

   sudo apt-get remove --purge <program>

install latest version of every package, and new dependencies::

   sudo apt-get dist-upgrade

remove packages (not programs)::

   sudo apt-get clean

remove only older packages::

   sudo apt-get autoclean

remove package and dependencies::

   sudo aptitude purge <program>

remove dependencies from old uninstalls, no longer needed::

   sudo apt-get autoremove

Update Alternatives
-------------------



Usefull Programs
================

Quake pull down menu::

   # apt-get install konsole yakuake

Screen Capture
   - xvidcap

Rip DVD's
   - acidrip

Merge pdf's::

   gs -dNOPAUSE -sDEVICE=pdfwrite -sOUTPUTFILE=out.pdf -dBATCH file1.pdf file2.pdf

Keychain
========

Use Ubuntu keychain for ssh logins?::

    [cmd]   apt-get update && apt-get install keychain
    [cmd]   ssh-keygen -t rsa
            edit $HOME/.bash_profile
            add this code:
            
            ### START-Keychain ###
            # Let  re-use ssh-agent and/or gpg-agent between logins
            /usr/bin/keychain $HOME/.ssh/id_dsa
            source $HOME/.keychain/$HOSTNAME-sh
            ### End-Keychain ###


Boot
====

Grub
----

adding "profile" no quotes, to end of kernel line (in grub) enables profiling

Lamp Install
============

.. code-block:: BashSessionLexer

    sudo apt-get install apache2
    sudo apt-get install php5 libapache2-mod-php5
    sudo /etc/init.d/apache2 restart
    sudo apt-get install mysql-server
    sudo apt-get install libapache2-mod-auth-mysql php5-mysql phpmyadmin
    gksudo gedit /etc/php5/apache2/php.ini
        [Change] ;extension=mysql.so
        [To    ]  extension=mysql.so
    sudo /etc/init.d/apache2 restart
    sudo ln -s /usr/share/phpmyadmin/ /var/www/phpmyadmin
    sudo apt-get install php5-curl
    sudo /etc/init.d/apache2 restart


File Coversions
===============

SED
===

replaces \r\n with \n::

   sed 's/.$//' winfile > unixfile      

replaces \n with \r\n::

   sed 's/$/\r/' unixfile > winfile        

trims leading whitespace::

   sed -i 's/^[ \t]*//' t.txt              

trims trailing whitespace::

   sed -i 's/[ \t]*$//' t.txt           

trims leading and trailing whitespace::

   sed -i 's/^[ \t]*//;s/[ \t]*$//' t.txt 

delete's blank lines::

   sed '/^$/ d' file                       

Glib
====
