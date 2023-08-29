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
