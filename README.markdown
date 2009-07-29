Clojure Mac OS X Setup
======================

My set up for Clojure on Mac OS X Leopard.

Set Up Instructions
-------------------

	$ git clone git://github.com/carlism/Clojure-MacOSX.git Clojure
	$ cd Clojure

Grab the dependancies (Clojure, Clojure-contrib, jline):

	$ git submodule init
	$ git submodule update

Build the dependancies:
	
	$ ant

Make the `clj` script executable and link to it from somewhere in your `$PATH`. (I use `~/bin` and have added it to my `$PATH` in my `~/.bash_profile`):

	$ chmod u+x clj
	$ ln -s <Full path to wherever you put this project>/clj ~/bin/clj

Usage
-----

The `clj` command can be used to open an interactive session:

	$ clj
	Clojure
	user=> 

or it can be used to run a script:

	$ clj test.clj 
	Hello, Clojure!

or it can be used to make a script file executable by starting your file with this line:

	#!/usr/bin/env clj

then chmod u+x your file and run it.
	
To add extra jar files to the Clojure's classpath on a project-by-prject basis, just create a `.clojure` file in the project's directory with the text to add to the classpath. 

For example, in my `~/code/clojure/cafe` project directory, I can add the Grinder and Frother jars from the `~/code/clojure/cafe/lib` directory by putting their relative paths, separated by a colon, into a `.clojure` file:

	$ cd ~/code/clojure/cafe
	$ echo "lib/grinder.jar:lib/frother.jar" > .clojure
