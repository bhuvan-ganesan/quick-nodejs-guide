<div align="center">
  <h1>NPM Serve Fiel</h1>
  <sub>Author:
<a href="https://www.linkedin.com/in/bhuvanaganesan-l-2209047a" target="_blank">Bhuvan Ganesan</a><br>
</sub>
</div>

<hr>

## NPM - Node Package Manager

Node Package Manager (NPM) is a command line tool that installs, updates or uninstalls Node.js packages in your application. It is also an online repository for open-source Node.js packages. 
The node community around the world creates useful modules and publishes them as packages in this repository. 
Official website:  https://www.npmjs.com

NPM is included with Node.js installation. After you install Node.js, verify NPM installation by writing the following command in terminal or command prompt. 
```
C:\> npm -v
2.11.3 
```
If you have an older version of NPM then you can update it to the latest version using the following command.
```
C:\> npm install npm -g 
```
To access NPM help, write npm help in the command prompt or terminal window.
```
C:\> npm help 
```
NPM performs the operation in two modes: global and local. In the global mode, 
NPM performs operations which affect all the Node.js applications on the computer whereas in the local mode, 
NPM performs operations for the particular local directory which affects an application in that directory only.

### Install Package Locally

Use the following command to install any third party module in your local Node.js project folder. 
```
C:\>npm install <package name> 
```
For example, the following command will install ExpressJS into MyNodeProj folder. 
```
C:\MyNodeProj> npm install express 
```
All the modules installed using NPM are installed under node_modules folder.
The above command will create ExpressJS folder under node_modules folder in the root folder of your project and install Express.js there.
### Add Dependency into package.json

Use --save at the end of the install command to add dependency entry into package.json of your application.

For example, the following command will install ExpressJS in your application and also adds dependency entry into the package.json. 
```
C:\MyNodeProj> npm install express --save
```
The package.json of NodejsConsoleApp project will look something like below. 
```
{
  "name": "NodejsConsoleApp",
  "version": "0.0.0",
  "description": "NodejsConsoleApp",
  "main": "app.js",
  "author": {
    "name": "Dev",
    "email": ""
  },
  "dependencies": {
    "express": "^4.13.3"
  }
}
```

### Install Package Globally
 NPM can also install packages globally so that all the node.js application on that computer can import and use the installed packages. 
 NPM installs global packages into /<User>/local/lib/node_modules folder.

Apply -g in the install command to install package globally. For example, the following command will install ExpressJS globally. 

```
C:\MyNodeProj> npm install -g express 
```

#### Update Package
To update the package installed locally in your Node.js project, navigate the command prompt or terminal window path to the project folder and write the following update command. 
```
C:\MyNodeProj> npm update <package name> 
```
The following command will update the existing ExpressJS module to the latest version.
```
C:\MyNodeProj> npm update express 
```

#### Uninstall Packages
 Use the following command to remove a local package from your project.
```
C:\>npm uninstall <package name>
```
The following command will uninstall ExpressJS from the application.
```
C:\MyNodeProj> npm uninstall express 
```

## Node.js Web Server

we will learn how to create a simple Node.js web server and handle HTTP requests.

To access web pages of any web application, you need a web server. The web server will handle all the http requests for the web application e.g IIS is a web server for ASP.NET web applications and Apache is a web server for PHP or Java web applications.

Node.js provides capabilities to create your own web server which will handle HTTP requests asynchronously. You can use IIS or Apache to run Node.js web application but it is recommended to use Node.js web server. 

### Create Node.js Web Server

 Node.js makes it easy to create a simple web server that processes incoming requests asynchronously.

The following example is a simple Node.js web server contained in server.js file. 
```
var http = require('http'); // 1 - Import Node.js core module
var server = http.createServer(function (req, res) {   // 2 - creating server
    //handle incomming requests here..
});
server.listen(5000); //3 - listen for any incoming requests
console.log('Node.js web server at port 5000 is running..')
```
Above example, we import the http module using require() function. The http module is a core module of Node.js, so no need to install it using NPM. The next step is to call createServer() method of http and specify callback function with request and response parameter. Finally, call listen() method of server object which was returned from createServer() method with port number, to start listening to incoming requests on port 5000. You can specify any unused port here.

Run the above web server by writing node server.js command in command prompt or terminal window and it will display message as shown below. 
```
C:\> node server.js
Node.js web server at port 5000 is running..
```
This is how you create a Node.js web server using simple steps. Now, let's see how to handle HTTP request and send response in Node.js web server.

### Handle HTTP Request

The http.createServer() method includes request and response parameters which is supplied by Node.js. The request object can be used to get information about the current HTTP request e.g., url, request header, and data. The response object can be used to send a response for a current HTTP request.
[https://nodejs.org/api/http.html#http_http_incomingmessage]
[https://nodejs.org/api/http.html#http_class_http_serverresponse]
The following example demonstrates handling HTTP request and response in Node.js.
```
var http = require('http'); // Import Node.js core module
var server = http.createServer(function (req, res) {   //create web server
    if (req.url == '/') { //check the URL of the current request
        // set response header
        res.writeHead(200, { 'Content-Type': 'text/html' }); 
        // set response content    
        res.write('<html><body><p>This is home Page.</p></body></html>');
        res.end();
    }
    else if (req.url == "/student") {
        res.writeHead(200, { 'Content-Type': 'text/html' });
        res.write('<html><body><p>This is student Page.</p></body></html>');
        res.end();
    }
    else if (req.url == "/admin") {
        res.writeHead(200, { 'Content-Type': 'text/html' });
        res.write('<html><body><p>This is admin Page.</p></body></html>');
        res.end();

    }
    else
        res.end('Invalid Request!');
});
server.listen(5000); //6 - listen for any incoming requests
console.log('Node.js web server at port 5000 is running..')
```
Above example, req.url is used to check the url of the current request and based on that it sends the response. To send a response, first it sets the response header using writeHead() method and then writes a string as a response body using write() method. Finally, Node.js web server sends the response using end() method.

Now, run the above web server as shown below. 
```
C:\> node server.js
Node.js web server at port 5000 is running.. 
```
To test point your browser to http://localhost:5000 and see the following result. 
The same way, point your browser to http://localhost:5000/student and see the following result.

### Sending JSON Response
The following example demonstrates how to serve JSON response from the Node.js web server.
```
var http = require('http'); 
var server = http.createServer(function (req, res) {   
    if (req.url == '/data') { //check the URL of the current request
            res.writeHead(200, { 'Content-Type': 'application/json' });
            res.write(JSON.stringify({ message: "Hello World"}));  
            res.end();  
    }
});
server.listen(5000);
console.log('Node.js web server at port 5000 is running..')
```

