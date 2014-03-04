#Developer guide to installing Node.js on OS X 

Below you will find a series of simple instructions for installing Node, npm, and some preferred packages on your OSX machine.  This guide is written for OS X Maverics but will apply to older verisions of OSX as well as mostly apply to other unix systems.


##Download and install Node.js 

Download the Mac OS X Installer (.pkg) from http://nodejs.org/download/ . You can also choose to compile Node from source, but the simplicity of the OS X Installer is preferred for most use cases.

You can also install Node using Homebrew if preferred:
```
brew install node
```

After the installation is complete, confirm that both the terminal commands 'node' and 'npm' are working by checking their versions in the the terminal and observing the expected output for the version installed.

```
node -v
v0.10.26
```
```
npm -v
1.4.3
```

If these commands are not working, then you may need to add /usr/local/bin to your $PATH.  Examine your $PATH from your terminal:

```
echo $PATH
```

If you don't see /usr/local/bin within that printout then it needs to be added to your $PATH in ~/.bash_profile.

Type the following command into terminal to add /usr/local/bin to your path:

```
echo 'export PATH=/usr/local/bin:$PATH' >> ~/.bash_profile
```

##Install recommended packages

##Write a Node hello world
