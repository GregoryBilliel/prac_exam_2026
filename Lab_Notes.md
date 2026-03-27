pwd : print working directory

directory : similar to a folder, things that contains other things like folders or files

ls : list, shows everything that is in the directory/folder you are currently in

cd : goes towards a chosen directory

cd ../ : steps back one directory, each "../" adds one step back

clear : just clears the terminal screen

ls ' : if you do this just put "'" to end it

Ctrl + C : cancels what you are doing/the current running command

Tab Complete : if you hit tab it will auto complete what you have typed, click it twice and it will show all the options that the autocomplete has

ls -F : lists but also tells you more data, "/" on names means they are directories you can enter into

man ls : manual list, tells you what options you have

ls -lrth : list with a bunch of extra metadata info like when and who made what along with permissions

head : shows you the header of the chosen file, sneak peek without fully opening it

cat : prints the whole to the screen

conda : environment manager, doubt I will need this info now but I will write it down anyways

cd ~ : goes back to base user page, can also do cd $HOME

relative paths : cd whatever is the path relative to where you are

absolute paths : pwd which starts at the start of the computer and takes the literal step by step path to wherever you are trying to go and traces it out

rm : deletes anything at RON you haven't pushed to GitHub

rm -fR : removes directory and everything in it

echo : evaluate a variable

history : shows command history 

grep : search command for within a file (Global Regular Expression Print), put the search query in '' and then the location after. Put ^ before your query inside the '' to search at the beginning of each line. Put > at the end followed by a file name to create a new file with what you searched

ls *fastq : lists everything that has fastq on the end of it, doesn't need to be fastq just whatever and you can put stuff before the * as well, * just means "whatever you can put here" 

"|" : pipes the output of a first command into the input of a second command

wc -l : word count, counts the number of lines in a given output

wc : word count basic, line, word and characters in order

ls /bin/c* | wc -l : takes all of the files from bin that start with c and then counts them 

ls /bin/ | grep '^c' | wc -l : lists bin, greps that search to look for starting c, word counts that output and gives you the line count

less file-c-prog : gives you a scrollable list of the files that starts with c in whatever director you are in

pwd gives the absolute path for the directory/folder/file you are currently in

cd with nothing after it takes to the home directory, also cd ~ or cd $HOME

cd ~/[tab] tells you what is in your home, easy way to navigate around

cd ../ is a backspace, can chain them together

ls -a : lists all the files, including hidden ones, could also do ls --all

ls .* : lists just all the hidden files and tells what is inside them

ls -laF : lists the files, user and permissions as well as when it was created

drwxrwxrwx : permissions

d = directory

r = read

w = write

execute = x

the order of the rwx trios indicates who has permissions, first three are for the owner I remember that much at least

second gruop in for group 

last gruop is for others

ls /usr/bin/c* | wc -l : piped command, doubt you'll need this again but fuck it here it is

tail : looks at the end of a file

less -S : shows a window of the file in an easy way

touch : makes file, put name after with .txt

mkdir : makes directory, put name after

cp : copies, put source file then destination next, can put a directory path as well

cp -r: recursive copy of everything that is in a directory

rm : removes a file

rmdir : removes a directory

rm -r :removes a nonempty directory 

ls -lh: human readable, shows file size data

ls -l: long format to view file permissions

chmod: change mode, changes permissions

chmod -w [filename]: takes away write priv from the file, user only change

rm -rf: removes a directory/file and then everything in it cause it is recursive and forced

ls -lh: human readable format to show file sizes

chmod -w *backup.fastq when in the backup directory

Also did the same command but with +w to add them all back and remove them again to double check

Before: 
-rw-r--r--. 1 gjb1039 domain users 47552 Feb 20 15:46 SRR097977_backup.fastq
-rw-r--r--. 1 gjb1039 domain users 43332 Feb 20 15:47 SRR098026_backup.fastq

After:
-r--r--r--. 1 gjb1039 domain users 47552 Feb 20 15:46 SRR097977_backup.fastq
-r--r--r--. 1 gjb1039 domain users 43332 Feb 20 15:47 SRR098026_backup.fastq

For chmod, you can put ugo options before the +/-rwx option to change for user group and others

conda activate genomics: activates conda

conda deactivate: deactivates conda

fastqc *.fastq in untrimmed_fastq ran the fastqc, downloaded and openned the files

ls -lrth: lists files with human readable sizes smallest to largest

which: tells you where a command is in ron, is you do "which cp" it will tell you where the copy command is (/usr/bin/cp)

conda activate genomics: activates the genomics conda environment

ctrl + r: lets you reverse search previous commands

history | grep conda: goes through your history and looks for commands where you used conda and lists them

/: starts an absolute pathway

ctrl + c: exits out if you accidentally mess up and get stuck in something like a "wc -l" command

grep -B[#] -A[#] [command]: shows the lines before and after the grepped line

- `grep` is a powerful search tool with many options for customization.
- `>`, `>>`, and `|` are different ways of redirecting output.
- `command > file` redirects a command's output to a file.
- `command >> file` redirects a command's output to a file without overwriting the existing contents of the file.
- `command_1 | command_2` redirects the output of the first command as input to the second command.
- `for` loops are used for iteration.
- `basename` gets rid of repetitive parts of names.

61 generationsm I just counted the file though

cut -f2 -d',' [filename]

-f2 -d cuts out the second section (our generations) and lists them in our file

cut -f2 -d',' Ecoli_metadata_composite.csv | sort | uniq | grep -v 'gen' | wc -l

This selects the generation line in the data, sorts it, takes out all the uniques, greps out the generations header, and then counts the number of lines

cat -n gives row number

tr ',' '\n'

head -n1 EcoliMetaData.csv | tr ',', '\n' | wc -l 

head -n1 gives only the first line of the file, which we know is the header, separated by commas, we pipe this into tr ',' '\n' which turns the commas into breaks for new lines, then wc -l just counts it

ctrl + d highlights everything that matches what you are highlighting currently, good to change multiple things at once

Could also do ctrl + f, search for your thing, then replace them all at once that way