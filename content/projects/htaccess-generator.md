---
title: htaccess-generator
type: page
date: 2019-07-30T23:56+02:00
---
htaccess-generator is a NodeJS project.

htaccess-generator is a command-line software to generating file .htaccess for your web-server simply passing parameters and arguments.

### USAGE:

htgen \[OPTION1\] \[OPTION2\]... arg1 arg2...

The following options are supported:

-w,	--www	\[ARG1\]	Redirects example.com to www.example.com
-o,	--oldfile	\[ARG1\] \[ARG2\] 	Redirects 301 old-file.html to new-file.html
-O,	--olddir	\[ARG1\] \[ARG2\] 	301 Redirect Entire Directory old-dir/ to new-dir/
-c,	--cache 	\[ARG1\]...\[ARGN\] 	Cache System with separate arguments for extensions
-p,	--cachepublic 		Option PUBLIC in cache system
-P, 	--cacheprivate 		Option PRIVATE in cache system
-b, 	--blockhtaccess 		Prevent viewing of .htaccess file
-B, 	--blockdirindex 		Prevent directory listings
-d, 	--defaultindex 	\[ARG1\] 	Change default directory page

### USE CASE:

I personally use this tool to generate file .htaccess directly.

./htgen -w example.com > .htaccess

... And put this file in home directory of example.com website. Ready-To-Use!

### DOWNLOAD:

*   [BitBucket Git Repository](https://bitbucket.org/nuke_admi/htaccess-generator/overview)

In the source code version you have to **install** a module of dipendence:

npm install stdio

### SETUP:

After download binary, if you want to install **htgen** as a command-line default program, use this:

sudo ln -s /dir/where/htgen-file/is /usr/bin/htgen
Password: (digit your root password)

Ok, now you can launch command **htgen** from any positions (and directories) in your command-line.
