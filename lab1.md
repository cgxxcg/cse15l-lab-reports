*hello, world, wow this is italics*
# heading1
## what's the difference 



<img width="1092" alt="WechatIMG345" src="https://github.com/cgxxcg/cse15l-lab-reports/assets/146875584/3216be16-58ec-478a-acd7-98e56e000528">

The working directory is "/home/lecture1" when the command was run. 

**cd**\
For cd without arguments, it shows up nothing in the terminal since I didn't specify what directory I want to change to. This is not an error but it will take me to the home diretory.

For cd with a directory argument, it changes the current directory to the one I typed. This is a correct command.

For cd with a file argument, it shows that "Not a directory" since it is a file not an directory. You can only use cd with a directory argument after it. This results in an error because you need to put a directory after cd to tell the command which directory you want to change to. 

**ls**\
For ls without arguments, it displays the files I have in the current directory. ls command doesn't need arguments and it lists all the files and folders in the terminal's current directory. It is not an error.

For ls with directory argument, it displays the files I have in the directory I specify. It is not an error.

For ls with file argument, it prints out the file argument again. This results in an error. ls command is intended for listing the contents of directories and does not accept file arguments.


**cat**\
For cat without arguments, the terminal continues to run and wait for an input. This is becasue cat command reads input file and prints it out in sequence. Since I didn't specify what to print, the terminal will keep running until I write some arguments to print.This is not an error. It will wait for input from the standard input.

For cat with directory argument, it displays the arguments and shows "Is a directory". For cat command, you always want to put some files behind it so it can print out something. This is an error since the cat command is designed to concatenate and display the contents of files, not directories.

For cat with the file argument, it displays Chinese from the txt file since I specify the location of the text file and the cat command will prints the content in the file in sequence. This is not an error. 
