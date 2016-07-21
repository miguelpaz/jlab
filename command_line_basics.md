# How to get started using the Command Line

Before the <a href="https://en.wikipedia.org/wiki/Graphical_user_interface" targe='_blank">graphical user interface</a> we are so accustomed to use in our computers existed, the way of interacting with a computer was to use the Command Line to **command a program to do what you want it to do by writing your orders <a href="https://en.wikipedia.org/wiki/Command-line_interface" target="_blank">"in the form of successive lines of text"</a> or... Command lines :) 

Ok, I know what you are thinking: *Why on earh would I want to learn to use this obscure old school thing if I can just point and click stuff in my computer to open folder, files, move them around, save them, rename them or delet them?* 

Well, it turns out that the Command Line - * formally known as Command Line Interface or Command Language Interpeter (CLI)* - is more ubiquitous and present than ever if you work with information and software.
- It allows you to navigate within directories, folders and files in your computer.
- It is a tool to analyze, clean and organize data.
- A great way to add more power and speed to your research or reporting skills. 
- Its very efficient when you have to process text data and work with it. Specially if your data file is very big (talking about GBs here).
- It is what you have to use to install and setup applications, run local servers, and many times the way to run code to make charts, maps and more.

Bottomline: Is efficient, useful, is text, it works with files you always use like (.csv, .txt, .tsv) and its **free**.

### Ready, set, go

Although it may seem confusing at first, the command line is widely used by developers and more savvy coders to enhance productivity and to run applications. When you really get the hang of it, you can be really faster than navigating around folders in Finder (OSX) or Windows.

The tools of command line are Command Prompt or PowerShell, ain Windows, and Terminal in Linux and Mac. 

This tutorial will include the most basic commands, and, if you want a more complete and technical tutorial, access [this tutorial](https://www.davidbaumgold.com/tutorials/command-line/), by David Baumgold. He called the command line “the ultimate seat of power on your computer”. 

For this tutorial you will need: 

1. Access to Terminal or Command Prompt or PowerShell

___

## Application

The following commands are, basically, a way to get around your computer, create files, delete them and move them. You can do this things in the more friendly user interface of your operating system, but it is a good thing to know these basic commands here. 

* Go to a certain directory

When you start the command line tool, you will generally be within the main user directory. To go to another directory (folder), you have to use the `cd` command:

`cd MyFolder/MuSubfolder/MuSubfolder2`

To come back to the main directory, use just `cd`.

To come back one step, for instance `MuSubfolder2` to `MuSubfolder`, type `cd ..`.

* Check out what is inside your folder

To see what is within a foder, use the `ls` command when you are inside the folder you want. You can also use a more structured command to see a better organized list:

`ls -l ~/MyFolder` in Mac and Linux and `dir` in Windows. 

* Create a directory

Once inside a directory, if you want to create another directory there, the basic command is `mkdir`, or make directory, followed by the name you want to give this directory. 

`mkdir MyNewDirectory`

To create more than one directory at once, just use space between the names of the folders you are creating.

* Create a file

To create a new file within a directory, use the `touch` command, followed by the file name and extension.

`touch ThisIsTextFile.txt` or `touch ThisIsDataFile.csv`

In Windows, use the `copy con` command. 

* Copy a file

To copy a file you will need to use the `cp` command in Mac and Linux and `copy` in Windows, and then the directory you want to copy it to.

`cp ~/Desktop/ThisIsTextFile.txt ~/Documents` or `copy ThisIsTextFile.txt c:/Documents`

* Move a file or directory

To move a file or directory, you have to use the `mv` command, followed by the directory you can send the object to.

`mv ~/Desktop/MyFile.rtf ~/Documents/MyDocFolder

* Remove (Delete) files

To remove or delete files, use the `rm` command. Be very careful to use this command, as all decisions are final - no second change in the trash bin. 

`rm MyFile.rtf` in Mac and Linux and `del MyFile.rtf` in Windows.

* The permission command

To install some applications on your computer, you will need to use `sudo` command in Mac and Linux, of the `runas` command in Windows. 

* Installing stuff

In a Mac or Linux, to install or update applications, you have to use the `apt-get` command.

`sudo apt-get install MySoftware`

To update an existing application: `sudo apt-get upgrade`

* Clear the mess

When you want to clear your command line of all the messy code, use the `clear` command, in Max or Linux, or `cls` in Windows. 

___

For the Windows reference and some other tricks, [visit Master Ruby website](https://masteruby.github.io/productivity-booster/2014/03/26/top-ten-commands-in-terminal-you-will-use-everyday.html#.V1Osi5MrLdT). You can also dig deeper in the [Code Academy course](https://www.codecademy.com/learn/learn-the-command-line), if that is your thing.

