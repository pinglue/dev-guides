
General developer guide
===================================

Here is a collection of tips and tricks for developers working on Pinglue org projects. A must read!

>> **Note:** If you have some interesting and useful topic to add here please make a PR. Same if you have suggestions and improvement regarding the existing topics.


Generate API doc for packages
---------------------------------
Did you know that all (or most) of our packages has a nice documentation on the web? 

- Really? where? 
- in typedoc.
- what is typedoc?

typedoc is a tool that generates documentation website by reading the typescript source codes and the comments you leave there (these comments: `/** */`). We are constantly adding jsdoc/typedoc comments to our codebase. All the packages should have *typedoc* installed as a dev dependency. To generate API doc for the package:

*from package root*:
```shell
typedoc --options typedoc.json
```

The generated html files will in the `./man` folder at the project root. Open the index.html file. 

**Note:** If the file `typedoc.json` was missing from a package please make a PR to add the file with the following content:

```json
{
    "entryPoints": ["src/"],
    "out": "man"
}
```

Of course you can refer to the source code directly, but this doc website makes it easier to see a list of classes, methods, modules, etc. You can even search for your class name and find the reference page for it. 

We strongly recommend that you use the this tool.


Use debugger
--------------------
Do not use `console.log` for debugging! This is for amateur and beginners. Experience developers never use `alert` or `console.log` to find the bug; they use a *debugger*. 

For in-browser code you can use Chrome dev tool. VSCode also has built-in debugger for javascript/typescript projects. Learn about these tools. They will save plenty of time and energy. Debugging is considered as an essential tool for any developer.

To learn more about debugging Node or typescript projects in VSCode see:

https://code.visualstudio.com/docs/nodejs/nodejs-debugging
https://code.visualstudio.com/docs/typescript/typescript-debugging

It is very straightforward. The summary is this: you can set *breakpoints* on any line for your ts/js files (just click beside the line number, you should see a small red circle). Once setting your breakpoints, open a *Javascript debug terminal* in your VScode and run your command in it (which is normally a `node` command), that's it! The debugger will attach itself to this node process and the code will stop at each breakpoint you set and you can inspect the value of any variable you want (some extra info like the value of variables in the closure will show up on the left pane). This way you can easily run your code line by line and see what went wrong with the logic. 

Now as you use debugger in VSCode you may notice the debugger might get into some system files which is outside of your codebase. To make debugger focus on your codebase add this setting to your vscode:

```json
"debug.javascript.terminalOptions": {
    "skipFiles": [
        "<node_internals>/**",
        "**/node_modules/**"          
    ]
}
```

This tells the js debugger to only analyse your own code. 

You need to learn about common debugging tasks and operations (like step over, step in, step out, etc.) The whole topic takes half an hour to learn but will save you hours of writing console.logs and pulling hairs.

**Tip:** You can also learn about debug *launches* on VSCode which basically allows you to define your frequent debug scenario into a config file and then just pick them from the debug menu to launch.

