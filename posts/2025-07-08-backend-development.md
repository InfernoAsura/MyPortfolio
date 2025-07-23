---
title: Backend Development
lastmod: 2025-07-23
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

## API (Application Programming Interface)

API are set of rules and tools that allow communication between two different softwares. In simplest words, it allows a client (website/app) to interact with a server or a service. 

![](https://voyager.postman.com/illustration/diagram-what-is-an-api-postman-illustration.svg)


### Web API & Library API

Web APIs like REST, GraphQL are a set of rules and endpoints that allows different applications to communicate with each other over the internet.  
Library API like python's Math module, openmp, etc. are a set of functions, directives that allow us to perform specific tasks in our code.

### Endpoints, Path and Query parameters

So every API has a base url and multiple endpoints. So it is like this, `https://base-url.com/Endpoint`. Now there can different endpoints for different APIs for different functionality.  

Path parameters are part of the URL itself. They’re used to identify a specific resource. `https://base-url.com/Endpoint/path-parameter`. Path parameter can be a unique key for each resource.  

Query parameters are key-value pair added to the end of URL to filter, sort or customize the request. `https://base-url.com/Endpoint?type1=value1&type2=value2`.

## Authentication

### Environment variables
We have variables like database details (name of the database, type of database, password and port etc.) in our code. And we need to hide them when we push our code to github. So we use a `.env` file (.env is the name of the file), where we use the following format `VARNAME=VALUE` and store our important data here and then replace the values in the original code with these varnames. `dotenv` package from npm is used to do this. You import the env from the package in the .js file and write `env.config()`, and then use `process.env.VARNAME` to call the value from the .env file. Put the `.env` file in the `.gitignore` file while pushing. 

## Websockets
A communication protocol allowing persistent, two way connection between the client and server over a single TCP connection. `socket.io` is the npm package used to do this in node.js. 
