
# CSE 15L Lab Report 1 - Remote Access and FileSystem
By: Athena Taylor
***

## cd
1. No Arguments
   
![Image](cd1.png)
  
>When I ran the cd command without arguments with home as my working directory, nothing changed. In contrast, when I ran the cd command without arguments with lecture1 as  >my working directory, my working directory changed to home. These outputs are not errors. Since I did not provide a directory to change to as an argument, the computer   >switched my current working directory to the default, which is home.
2. A Directory as an Argument

![Image](cd2.png)

>When I ran the cd command with "/home/lecture1/messages" as the argument and home as my working directory, my current working directory was changed to messages. This >output is not an error. The command worked exactly how it was outlined in Wednesday's handout; the current working directory was switched to the path passed in, which >corresponds to the messages directory.
3. A File as an Argument

![Image](cd3.png)

>When I ran the cd command with "/home/lecture1/messages/en-us.txt" as the argument and home as my working directory, an error occured. This happened because the path >given as an argument corresponds to a file, not a directory. As the name of the command suggests, cd can only change the current working directory to other directories.


## ls
1. No Arguments

![Image](ls1.png)

>When I ran the ls command without arguments with home as my working directory, the contents of home, which were one folder titled lecture1, were listed. This output is >not an error. Since I didn't pass in anything for the computer to list, it defaulted to listing the contents of my current working directory.
2. A Directory as an Argument

![Image](ls2.png)

>When I ran the ls command with "/home/lecture1/messages" as the argument and home as my working directory, the contents of the messages folder were listed out. This >output is not an error. Just as the lecture handout stated, the contents of the path passed in, which corresponds to the messages directory, were listed.
3. A File as an Argument

![Image](ls3.png)

>When I ran the ls command with "/home/lecture1/messages/en-us.txt" as the argument and home as my working directory, the path of the file en-us.txt was displayed. This >output is not an error. Since a file is not a folder, it doesn't contain any files or folders for the computer to list out. This, it listed out the path of the file, >which is the same as the argument passed in.

## cat
1. No Arguments
2. A Directory as an Argument
3. A File as an Argument
