# How to install & Push on SVN
![Résultat de recherche d'images pour "subversion"](http://modelis-tech.com/wp-content/uploads/2016/09/Subversion_Logo.svg_.png)
## Summary of the document
### - Install SVN on your computer
- Mac OS Installation
- Windows Installation
- Linux Installation

### - How to clone the EIP repository

### - Add files and push them on the repository

## Part 1 - Installation of SubVersion (SVN)

### Mac OS 
First of all you'll need the Package Manager of Mac OS, Brew.
See [Brew](https://brew.sh).

Once you installed brew, just run this command :

    brew install svn

That's it, SVN is installed on you Mac.

### Windows

You'll need to install TortoiseSVN.
See [Tortoise Download](https://tortoisesvn.net/downloads.html).

Once tortoise is correctly installed, you are done !
SVN is installed on your Windows PC.

### Linux

To install SVN on Ubuntu or any Debian based linux just run this command :

    sudo apt-get install subversion

Once this command is finished, svn is installed on you computer.

In case you are not on a Debian based linux, or you don't have apt on the computer see [this page](https://subversion.apache.org/packages.html)

## Part 2 - Clone the EIP repository from the server

Just run this command to "clone" the SVN repository :

    svn checkout https://labeip.epitech.eu/svn/2021/terradia/

a directory named "terradia" should be created with all the files pushed inside it.
this is the architecture of the folder created :

```
terradia/
  branches/
	  -> List of the branches made in the SVN
  rendu/
  	  -> List of the files pushed in the SVN
  tags/
  	  -> Releases of the project pushed in SVN
  trunk/
  	  -> master
  www/
  	  -> it's here for a reason
```

All the files needed by the Lab EIP are pushed in the "rendu" directory inside svn.

## Part 3 - Push on SVN server

To push, you need to execute these command : 

First, you need to add the files you want to commit :

    svn add [FILE1] [FILE2] [...]

If you wan to delete files : 

    svn delete [FILE1] [FILE2] [...]

Then you need to commit your changed to SVN:

    svn commit -m "[YOUR COMMIT MESSAGE]"


# That's it, you pushed on SVN :D
