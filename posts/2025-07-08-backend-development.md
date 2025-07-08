---
title: Backend Development
lastmod: 2025-07-08
toc: true
---

## Node.js

Node is a javascript based backend framework. We need to download it from there website. Once downloaded, there are two ways to use node for running javascript code: The node REPL (Read Eval Print Loop) and using the `node` keyword to run the .js file. 

We type `node` on the terminal and just like in python, a console type thing will start in the terminal, where we can write javascript code like we write in chrome browser console. Use the .help command to get the commands which can be used in REPL. Now, if we have a index.js file, then type `node index.js` on the terminal, and the .js file will be executed. 

### Native modules

Node has native modules in it, which can be used directly by us to get things done. For example, if we want to write in a file or read in a file through the .js file, we can use the `fs` native module. More info can be found on this site: [node](https://nodejs.org/api/documentation.html).  


### Node package manager (npm)

This is also like the native modules, except that this is something that is open source and created by other node users. `npm` comes pre-installed with node. To utilize `npm`, we have to type the command `npm init`, and then fill some details and we will see a `package.json` being created. Go to [npm](https://www.npmjs.com/) and we can see the different packages that there are, out in the market. We can use these packages by choosing a package and then installing it.  

There are two ways to use these modules (native and npm modules) in our .js file, one is through CJS (Common Javascript) and the other is ESM (ECMA Script Modules). CJS uses `require()` while ESM uses `import`.
