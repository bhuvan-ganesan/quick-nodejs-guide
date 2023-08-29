<div align="center">
  <h1>Node.js Module</h1>
<sub>Author:
<a href="https://www.linkedin.com/in/bhuvanaganesan-l-2209047a" target="_blank">Bhuvan Ganesan</a><br>
</sub>
</div>

## Node.js Module

 Module in Node.js is a simple or complex functionality organized in single or multiple JavaScript files which can be reused throughout the Node.js application.
Each module in Node.js has its own context, so it cannot interfere with other modules or pollute global scope. Also, each module can be placed in a separate .js file under a separate folder.
Node.js implements [CommonJS modules standard] (http://requirejs.org/docs/commonjs.html). CommonJS is a group of volunteers who define JavaScript standards for web server, desktop, and console application. 

### Node.js Module Types

Node.js includes three types of modules:

    1.Core Modules
    2.Local Modules
    3.Third Party Modules

### Node.js Core Modules

Node.js is a light weight framework. The core modules include bare minimum functionalities of Node.js. These core modules are compiled into its binary distribution and load automatically when Node.js process starts. However, you need to import the core module first in order to use it in your application.

The following table lists some of the important core modules in Node.js.

<table>
  <tr>
    <td>Core Module </td>
    <td>Description </td>
  </tr>
  <tr>
    <td>[http](https://nodejs.org/api/http.html)</td>
    <td>http module includes classes, methods and events to create Node.js http server. </td>
  </tr>
  <tr>
    <td>[URL](https://nodejs.org/api/url.html)</td>
    <td>url module includes methods for URL resolution and parsing. </td>
  </tr>
  <tr>
    <td>[QueryString](https://nodejs.org/api/querystring.html)</td>
    <td>querystring module includes methods to deal with query string. </td>
  </tr>
  <tr>
    <td>[Path](https://nodejs.org/api/path.html)</td>
    <td>path module includes methods to deal with file paths. </td>
  </tr>
 <tr>
    <td>[util](https://nodejs.org/api/util.html)</td>
    <td>util module includes utility functions useful for programmers.  </td>
  </tr>
 <tr>
    <td>[fs](https://nodejs.org/api/fs.html)</td>
    <td>fs module includes classes, methods, and events to work with file I/O.  </td>
  </tr>
</table>

### Loading Core Modules

In order to use Node.js core or NPM modules, you first need to import it using require() function as shown below.
```
var module = require('module_name');
```
As per above syntax, specify the module name in the require() function. The require() function will return an object, function, property or any other JavaScript type, depending on what the specified module returns.

The following example demonstrates how to use Node.js http module to create a web server. 
```
var http = require('http');
var server = http.createServer(function(req, res){
  //write code here
});
server.listen(5000); 
```
above example, require() function returns an object because http module returns its functionality as an object, you can then use its properties and methods using dot notation e.g. http.createServer().

In this way, you can load and use Node.js core modules in your application. We will be using core modules throughout these tutorials. 

### Node.js Local Module

Local modules are modules created locally in your Node.js application. These modules include different functionalities of your application in separate files and folders. You can also package it and distribute it via NPM, so that Node.js community can use it. For example, if you need to connect to MongoDB and fetch data then you can create a module for it, which can be reused in your application. 

#### Writing Simple Module

Let's write simple logging module which logs the information, warning or error to the console.

In Node.js, module should be placed in a separate JavaScript file. So, create a Log.js file and write the following code in it.
```
var log = {
            info: function (info) { 
                console.log('Info: ' + info);
            },
            warning:function (warning) { 
                console.log('Warning: ' + warning);
            },
            error:function (error) { 
                console.log('Error: ' + error);
            }
    };
module.exports = log
```
above example of logging module, we have created an object with three functions - info(), warning() and error(). At the end, we have assigned this object to module.exports. The module.exports in the above example exposes a log object as a module.

The module.exports is a special object which is included in every JS file in the Node.js application by default. Use module.exports or exports to expose a function, object or variable as a module in Node.js.

Now, let's see how to use the above logging module in our application.

#### Loading Local Module

To use local modules in your application, you need to load it using require() function in the same way as core module. However, you need to specify the path of JavaScript file of the module.

The following example demonstrates how to use the above logging module contained in Log.js.
```
var myLogModule = require('./Log.js');
myLogModule.info('Node.js started');
```
above example, app.js is using log module. First, it loads the logging module using require() function and specified path where logging module is stored. Logging module is contained in Log.js file in the root folder. So, we have specified the path './Log.js' in the require() function. The '.' denotes a root folder.

The require() function returns a log object because logging module exposes an object in Log.js using module.exports. So now you can use logging module as an object and call any of its function using dot notation e.g myLogModule.info() or myLogModule.warning() or myLogModule.error()

Run the above example using command prompt (in Windows) as shown below.
```
C:\> node app.js
Info: Node.js started 
```
Thus, you can create a local module using module.exports and use it in your application.

## Export Module in Node.js

 The module.exports is a special object which is included in every JavaScript file in the Node.js application by default. The module is a variable that represents the current module, and exports is an object that will be exposed as a module. So, whatever you assign to module.exports will be exposed as a module.

Let's see how to expose different types as a module using module.exports.
#### Export Literals

As mentioned above, exports is an object. So it exposes whatever you assigned to it as a module. For example, if you assign a string literal then it will expose that string literal as a module.
The following example exposes simple string message as a module in **Message.js**.
```
module.exports = 'Hello world';
```
Now, import this message module and use it as shown below (app.js).
```
var msg = require('./Message.js');
console.log(msg);
```
Run the above code 
```
C:\> node app.js
Hello World 
```

**Note **
You must specify ./ as a path of root folder to import a local module. 
However, you do not need to specify the path to import Node.js core modules or NPM modules in the require() function.
