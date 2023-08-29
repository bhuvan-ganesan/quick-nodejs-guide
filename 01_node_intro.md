<div align="center">
  <h1>What is Node.JS</h1>
<sub>Author:
<a href="https://www.linkedin.com/in/bhuvanaganesan-l-2209047a" target="_blank">Bhuvan Ganesan</a><br>
</sub>
</div>

## What is Node.js ?
Node.js is an open-source server side runtime environment built on Chrome's V8 JavaScript engine.
It provides an event driven, non-blocking (asynchronous) I/O and cross-platform runtime environment 
for building highly scalable server-side application using JavaScript.
Node.js can be used to build different types of applications such as command line application, web application, 
real-time chat application, REST API server etc. However, it is mainly used to build network programs like web servers, similar to PHP, Java, or ASP.NET. 
Node.js was written and introduced by Ryan Dahl in 2009. 

 Node.js official web site: https://nodejs.org

Node.js on github: https://github.com/nodejs/node

## Advantages of Node.js
 1. Node.js is an open-source framework under MIT license. (MIT license is a free software license originating at the Massachusetts Institute of Technology (MIT).)
 2. Uses JavaScript to build entire server side application.
 3. Lightweight framework that includes bare minimum modules. Other modules can be included as per the need of an application.
 4. Asynchronous by default. So it performs faster than other frameworks.
 5. Cross-platform framework that runs on Windows, MAC or Linux


## Node.js Process Model

 Node.js processes user requests differently when compared to a traditional web server model. Node.js runs in a single process and the application code runs in a single thread and thereby needs less resources than other platforms. All the user requests to your web application will be handled by a single thread and all the I/O work or long running job is performed asynchronously for a particular request. So, this single thread doesn't have to wait for the request to complete and is free to handle the next request. When asynchronous I/O work completes then it processes the request further and sends the response.

An event loop is constantly watching for the events to be raised for an asynchronous job and executing callback function when the job completes. Internally, Node.js uses libev for the event loop which in turn uses internal C++ thread pool to provide asynchronous I/O.

<img src='nodejs-process-model.webp'/>

Node.js process model increases the performance and scalability with a few caveats. Node.js is not fit for an application which performs CPU-intensive operations like image processing or other heavy computation work because it takes time to process a request and thereby blocks the single thread.

## Install Node.js 

In this section, you will learn about the tools required and steps to setup development environment to develop a Node.js application.

Node.js development environment can be setup in Windows, Mac, Linux and Solaris. The following tools/SDK are required for developing a Node.js application on any platform.

    1. Node.js
    2. Node Package Manager (NPM)
    3. IDE (Integrated Development Environment) or TextEditor

NPM (Node Package Manager) is included in Node.js installation since Node version 0.6.0., so there is no need to install it separately. 

### Install Node.js on Windows

Visit Node.js official web site https://nodejs.org. It will automatically detect OS and display download link as per your Operating System. For example, it will display following download link for 64 bit Windows OS. 

Download the installer for windows by clicking on LTS or Current version button. Here, we will install the latest version LTS for windows that has long time support.

### Verify Installation

Once you install Node.js on your computer, you can verify it by opening the command prompt and typing ** node -v**. If Node.js is installed successfully then it will display the version of the Node.js installed on your machine, as shown below. 

## Node.js Basics

Node.js supports JavaScript. So, JavaScript syntax on Node.js is similar to the browser's JavaScript syntax. 

### Primitive Types
 Node.js includes following primitive types:

    1. String
    2. Number
    3. Boolean
    4. Undefined
    5. Null
    6. RegExp

Everything else is an object in Node.js. 
### Loose Typing

JavaScript in Node.js supports loose typing like the browser's JavaScript. Use var keyword to declare a variable of any type. 

### Object Literal

Object literal syntax is same as browser's JavaScript. 

```
var obj = {
    authorName: 'Ryan Dahl',
    language: 'Node.js'
}
```

### Functions

Functions are first class citizens in Node's JavaScript, similar to the browser's JavaScript. A function can have attributes and properties also. It can be treated like a class in JavaScript. 

```
function Display(x) { 
    console.log(x);
}

Display(100);
```

### Buffer

 Node.js includes an additional data type called Buffer (not available in browser's JavaScript). Buffer is mainly used to store binary data, while reading from a file or receiving packets over the network.
#### process object

Each Node.js script runs in a process. It includes process object to get all the information about the current process of Node.js application.

The following example shows how to get process information in REPL using process object.
```
> process.execPath
'C:\\Program Files\\nodejs\\node.exe'
> process.pid
1652
> process.cwd()
'C:\\' 
```

### Defaults to local

Node's JavaScript is different from browser's JavaScript when it comes to global scope. In the browser's JavaScript, variables declared without var keyword become global. In Node.js, everything becomes local by default.

### Access Global Scope
In a browser, global scope is the window object. In Node.js, global object represents the global scope.
To add something in global scope, you need to export it using export or module.export. The same way, import modules/object using require() function to access it from the global scope.
For example, to export an object in Node.js, use exports.name = object. 

```
exports.log = {
    console: function(msg) {
        console.log(msg);
    },
    file: function(msg) {
        // log to file here
      }
}
```
Now, you can import log object using require() function and use it anywhere in your Node.js project. 
