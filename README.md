#Developer guide to installing Node.js on OS X 

Below you will find a series of simple instructions for installing Node, npm, and some preferred packages on your OSX machine.  This guide is written for OS X Maverics but will apply to older verisions of OSX as well as mostly apply to other unix systems.


##Download and install Node.js 

Download the Mac OS X Installer (.pkg) from:

http://nodejs.org/download/ 

Alternatively, you can choose to compile Node from source, but the simplicity of the OS X Installer is preferred for most use cases.  You can also choose to install Node using Homebrew if preferred:
```sh
$ brew install node
```

After the installation is complete, confirm that both the terminal commands 'node' and 'npm' are working by checking their versions in the the terminal and observing the expected output for the version installed.

```sh
$ node -v
v0.10.26
```
```sh
$ npm -v
1.4.3
```

If these commands are not working, then you may need to add /usr/local/bin to your $PATH.  Examine your $PATH from your terminal:

```sh
$ echo $PATH
```

If you don't see /usr/local/bin within that printout then it needs to be added to your $PATH in ~/.bash_profile.

Type the following command into terminal to add /usr/local/bin to your path:

```sh
$ echo 'export PATH=/usr/local/bin:$PATH' >> ~/.bash_profile
```

##Write a simple example webserver

Further test your Node installation by saving this hello world http server from http://nodejs.org/ into a file named app.js. 

```javascript
var http = require('http');
http.createServer(function (req, res) {
  res.writeHead(200, {'Content-Type': 'text/plain'});
  res.end('Hello World\n');
}).listen(1337, '127.0.0.1');
console.log('Server running at http://127.0.0.1:1337/');
```

```sh
$ node app.js
Server running at http://127.0.0.1:1337/
```

##Install useful npm packages globally

In order to install npm packages globally, you will very likely need to reclaim ownership of the node_modules directory by changing your user to be the owner:

```sh
$ sudo chown -R `whoami` /usr/local/lib/node_modules
```

#### Nodemon
  Nodemon is a simple monitor script for use during development.  It will automatically reload the node server when you save one of your project files. http://github.com/remy/nodemon.git

Install globally with npm:
```sh
$ npm install -g nodemon
```
Run your app.js http server with nodemon:
```sh
$ nodemon app.js
```

#### Node Inspector
  Node Inspector is a debugger interface for Node.js applications.  https://github.com/node-inspector/node-inspector

Install globally with npm:
```sh
$ npm install -g node-inspector
```
Run your app.js http server in the browser using node-inspector:
```sh
$ node-debug app.js
```
