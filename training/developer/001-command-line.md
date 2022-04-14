# The command line 

The invention of the mouse was clearly a breakthrough in the history of computing. Without it it is hard to imagine billions of people using the internet to do everything from online banking to choosing a movie. However, as with many of the great inventions humanity’s dependence on the mouse has only grown over time. This is a shame as the mouse restricts how the user can interact with their computer. It is like an English speaker attempting to speak French to a French speaker but being restricted to only using a small fraction of French vocabulary. If you are to interact with your computer (and later your Bitcoin full node) you don’t want to have one arm tied behind your back while you do so. You want to be able to tell your computer exactly what you want from it and express it in a way that the computer doesn’t get confused. To do that you need to learn command line.

On a Mac the Terminal app is installed by default. You just need to open it. Now this is the first challenge that will test whether you have the staying power to the learn the toolkit required to be a skilled sovereign individual. There are various commands you need to practice over and over again until they become second nature.

**Warning: You need to be careful with the rm command. Make sure you always specify the file or directory that you want to remove. If you use the rm command with the `-f` option you can accidentally wipe all the files and directories on your laptop permanently. You do not want to do this!** 

## Some terminology

Directory: A folder that holds files.

Subdirectory: A directory that is located within another directory.

Filesystem: Your computer organizes files into various directories. The entirety of these directories and files would be considered the filesystem.

## Commanding your computer without a mouse

Input the following commands followed by the Enter button.

`pwd` - Print working (current) directory. This will tell you where you are in your filesystem. 

`ls` - This lists the files in your current directory. If there are no files in this directory it won’t return anything.

`mkdir insert_new_directory_name` - Make directory. This will create a new directory in your current location.

`cd insert_new_directory_name` - Change directory. This will move your location into the new directory you just created.

`touch insert_new_file_name.md` - This will create a new file in your current location. 

`ls` - List files (from earlier). You should be able to see your file `insert_new_file_name.md`.

`rm insert_new_file_name.md` - This will remove the new file you just created.

`rmdir insert_new_directory_name` - This will remove the new directory you created.

Repeat the above over and over again until it starts to become second nature. This is the first step towards you organizing your filesystem without relying on your mouse (left clicking, right clicking, double clicking etc)

Note you only created a new file, you didn’t open it. There are various ways to open a file. We will use Vim. But before we introduce Vim get used to the command line. Vim will introduce a large number of new commands and shortcuts so only move onto Vim when you are ready.

## Setting the default shell to bash

Since MacOS Catalina MacOS has set the default shell to Zsh. We will use bash instead so before moving on run the command:

```
chsh -s /bin/bash
```
You will need to enter your computer's password after pressing Enter but you will be prompted when you need to.

## References

Learn command line (Tracy Osborn): <https://hellowebbooks.com/learn-command-line/>

Bite Size Command Line (Julia Evans): <https://wizardzines.com/zines/bite-size-command-line/>
