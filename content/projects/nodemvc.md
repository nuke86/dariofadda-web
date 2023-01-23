---
title: NodeMVC
type: page
---

nodeMVC is a minimalistic Model Views Control in Node.JS that uses the minimum energy in the server machine to make up a Web Site very fast and light.

The gol of nodeMVC is the minimal source code in the project and the easy configuration to run.

### THE PROJECT:

nodeMVC is one server file and your contents are stored in files dot ejs (.ejs).

After you have downloaded this project file (node.js), you have to put this in your main website directory and then you have to make new directory, in the same place, named views.

In /views directory you can write your first web page:

echo "Hello Bob website" > index.ejs

Now you have to satisfy dipendences. nodeMVC use the framework Express and the EJS template engine to work. So, in the main directory of website (where you have put the node.js file) launch this command to setup the environment:

npm install express
npm install ejs

No databases are required.

Test your website. Now you are ready, your website is setup. To run launch:

nodejs node.js

#now the server is listening...

Open your web browser, go to: **[http://localhost:8080](http://localhost:8080/)** and see your first webpage.

To work with nodeMVC you are free to use pure **HTML** language in the .ejs files (in views directory), and the EJS template engine language to make it dynamics. One instruction you'll have to use is include, with the EJS language you can include one .ejs file in another .ejs file in this way:

html
body

% include file %

file principale
/body
/html

This instruction include a file named file.ejs (in the same directory of main file) in this main file (es: index.ejs).

### DOWNLOAD & CODE

*   [Github Repository](https://github.com/nuke86/nodeMVC)

Here you can find source code of nodeMVC and I suggest to use **git** for clone this project and stay updated, for future release and development, just with:

git clone https://github.com/nuke86/nodeMVC.git
