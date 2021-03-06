# Mastering Node

[Node](http://nodejs.org) is an exciting new platform developed by _Ryan Dahl_, allowing JavaScript developers to create extremely high performance servers by leveraging [Google V8](http://code.google.com/p/v8/) JavaScript engine, and asynchronous I/O. In _Mastering Node_) we will discover how to write high concurrency web servers, utilizing the CommonJS module system, node's core libraries, third party modules, high level web development and more.

## Why Node?

Node is an evented I/O framework for server-side JavaScript.  What does that mean, though?  In many programming languages, I/O operations are blocking.  This means that when you open a file, no other code executes until that file is fully opened.  

Using a busy office environment as an example, blocking I/O operations are like a very busy and very focussed desk worker name Frank. Work may pile up on the desk, but Frank finishes every task that he starts (however, when he finds the smallest problem, he gives up).  This is traditionally how procedural programming languages perform tasks.

Node.js is more like an office manager. Sure, there are management tasks, but all of those I/O operations are handled fairly well by the operating system or node addons.  So, the manager sees a task, assigns it to Frank.  The manager may check back on Frank from time to time to see how he's doing, but he doesn't need to waste his time on the task because he knows that when it's completed, Frank will give it back.

Don't worry, though.  Node.js isn't a jerk, so look forward to a healthy relationship.

## Why JavaScript?

**JavaScript is a well-known dynamic language.**

In fact, many people who don't consider themselves programmers know JavaScript. Node.js uses [Google's V8 JavaScript engine](http://code.google.com/apis/v8/intro.html).  V8 is an implementation of the JavaScript standards specified in [ECMA-262, Version 3](http://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-262,%203rd%20edition,%20December%201999.pdf). It is a high-performance, garbage-collected execution environment which can be embedded in any stand-alone application.

**Everything in JavaScript is an `Object`.**

Arrays are `Objects`.  Object literals are `Object`s.  Even functions are `Object`s.

**JavaScript supports some fairly advanced functional programming concepts. [?](http://www.ibm.com/developerworks/library/wa-javascript.html#functional)**

Currying, closures, functions-as-arguments, and anonymous functions are concepts typically found in functional programming languages.  There are libraries available, such as [underscore.js](http://documentcloud.github.com/underscore/), which provider more functional programming functionality without changing JavaScript itself.

**It's awesome. I had to say it.**

For a deep understanding of what JavaScript really has to offer, check out [JavaScript Patterns](http://oreilly.com/catalog/9780596806767).

## Hello World!
**Becuase it has to be done**

	// hello.js
	sys = require('sys');
	sys.puts("Hello, World!");

To run the 'Hello, World!' example, execute `node hello.js` on the command line.

## Conventions in this book

**Code Blocks**

There are a few conventions used in the code example blocks (such as the Hello, World! example above).

First, if the example is a script (or a part of a script) that needs to be run from the command line, it will begin with a `//` styled comment of the filename.  These files are located under the `./src` directory of the _Mastering Node_ project.  Running these examples is fairly simple: open a terminal (CTRL+SHIFT+T might do it) and type `node` followed by a space and the relative path of the script.  In other words, if you're in _/home/jim/masteringnode_ and you want to run a script under _/home/jim/masteringnode/scripts/_ which is called _hello.js_, you would run `node scripts/hello.js` or `node ./scripts/hello.js`.  For an example of how this code snippet is displayed, see the Hello, World! example above.

Second, if the example is a command to be entered directly into what will be referred to as a 'node terminal', you should first open a terminal then type `node` and ENTER (assuming the node executable is in your PATH variable, and is called node).  At the prompt, you should enter the commands following the `>` character. Text following the `>` character are commands you should enter, while text on a line that does not begin with `>` is the output.  This is done to closely match what you should see in your terminal.  These examples are not included in files under the _src_ directory.  For instance:

	> console.log("Hello, World!")
	Hello, World.

Third, if an example is to be run from the terminal itself, it is prefixed by a `$`.  This represents a bash environment, and may look differently depending on your configuration.  For instance, my bash terminal displays:

	jim@cr-48:~/projects/masteringnode$

These code examples will look like this:
	
	$ ruby -e "puts 'Hello, World'"

Finally, code without a prefix is a sample of a possible solution or expected output from _stdout_.  This is not necessarily code you should type into your terminal or run as a script, unless of course you want to experiment.  For example, suppose we're discussing CommonJS and we'd like to show how something _would_ be done in CommonJS, we might show an example such as:

	var utils = {};
	utils.merge = function(obj, other) {};

This wouldn't contain a filename unless there is a working example (in which case, it's a concrete example and no longer hypothetical).

**Inline Code**

Occasionally, there will be code or commands that are being explained and displayed inline to separate them visually from the rest of the sentence.  For instance, if we were talking about how to include modules into your code, we may say to add a `var fs = require('fs');` line to the top of your file.  Code displayed like this is generally accompanied by an explanation of the code itself or instructions for where to add the code.  

Functions may be displayed as `require()` or `require`, depending on the context for readability. That is, when we're talking about any JavaScript objects, we'll most likely use `require` since a function is also an object.  

If we're talking about multiple functions, we may say "use the functions: `doSomething1` and `doSomething2`" instead of "use the functions: `doSomething1()` and `doSomething2()`" because the parentheses can be implied and the absence of parentheses is easier on the eyes.

**Files and Directories**

Files and directories will be displayed in italics when inline, or as a relative path to the _Mastering Node_ source directory in code comments when in a code example block.  For instance, if we reference _/home/jim/masteringnode/src/modules/fake.js_ in a code example, it will look like:

	// modules/fake.js
	var num = 1;

