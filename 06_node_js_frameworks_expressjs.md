<div align="center">
  <h1>Node.js Frameworks and Express.js</h1>
  <sub>Author:
<a href="https://www.linkedin.com/in/bhuvanaganesan-l-2209047a" target="_blank">Bhuvan Ganesan</a><br>
</sub>
</div>

<hr>

## Frameworks for Node.js

There are various third party open-source frameworks available in Node Package Manager which makes Node.js application development faster and easy. 
You can choose an appropriate framework as per your application requirements.

The following table lists frameworks for Node.js.

<table>
   <thead>
      <tr>
         <th class="w-25">Open-Source Framework
         </th>
         <th class="w-75">Description
         </th>
      </tr>
   </thead>
   <tbody>
      <tr>
         <td><a href="http://expressjs.com" target="_blank">Express.js</a>
         </td>
         <td>Express is a minimal and flexible Node.js web application framework that provides a robust set of features for web and mobile applications. This is the most popular framework as of now for Node.js.
         </td>
      </tr>
      <tr>
         <td><a href="http://geddyjs.org/" target="_blank">Geddy</a>
         </td>
         <td>Geddy is a simple, structured web application framework for Node.js based on MVC architecture. 
         </td>
      </tr>
      <tr>
         <td><a href="http://locomotivejs.org" target="_blank">Locomotive</a>
         </td>
         <td>Locomotive is MVC web application framework for Node.js. It supports MVC patterns, RESTful routes, and convention over configuration, while integrating seamlessly with any database and template engine. Locomotive builds on Express, preserving the power and simplicity you've come to expect from Node.
         </td>
      </tr>
      <tr>
         <td><a href="http://koajs.com" target="_blank">Koa</a>
         </td>
         <td>Koa is a new web framework designed by the team behind Express, which aims to be a smaller, more expressive, and more robust foundation for web applications and APIs.
         </td>
      </tr>
      <tr>
         <td><a href="https://www.totaljs.com" target="_blank">Total.js</a>
         </td>
         <td>Totaljs is free web application framework for building web sites and web applications using JavaScript, HTML and CSS on Node.js
         </td>
      </tr>
      <tr>
         <td><a href="http://hapijs.com/" target="_blank">Hapi.js</a>
         </td>
         <td>Hapi is a rich Node.js framework for building applications and services.
         </td>
      </tr>
      <tr>
         <td><a href="http://keystonejs.com/" target="_blank">Keystone</a>
         </td>
         <td>Keystone is the open source framework for developing database-driven websites, applications and APIs in Node.js. Built on Express and MongoDB.
         </td>
      </tr>
      <tr>
         <td><a href="http://derbyjs.com" target="_blank">Derbyjs</a>
         </td>
         <td>Derby support single-page apps that have a full MVC structure, including a model provided by&nbsp;Racer, a template and styles based view, and controller code with application logic and routes.
         </td>
      </tr>
      <tr>
         <td><a href="http://sailsjs.org/" target="_blank">Sails.js</a>
         </td>
         <td>Sails makes it easy to build custom, enterprise-grade Node.js apps. It is designed to emulate the familiar MVC pattern of frameworks like Ruby on Rails, but with support for the requirements of modern apps: data-driven APIs with a scalable, service-oriented architecture. It's especially good for building chat, realtime dashboards, or multiplayer games; but you can use it for any web application project - top to bottom.
         </td>
      </tr>
      <tr>
         <td><a href="https://www.meteor.com/" target="_blank">Meteor</a>
         </td>
         <td>Meteor is a complete open source platform for building web and mobile apps in pure JavaScript.
         </td>
      </tr>
      <tr>
         <td><a href="https://github.com/yahoo/mojito" target="_blank">Mojito</a>
         </td>
         <td>This HTML5 framework for the browser and server from Yahoo offers direct MVC access to the server database through the local routines. One clever feature allows the code to migrate. If the client can't run JavaScript for some reason, Mojito will run it on the server -- a convenient way to handle very thin clients.
         </td>
      </tr>
      <tr>
         <td><a href="http://mcavage.me/node-restify/" target="_blank">Restify</a>
         </td>
         <td>Restify is a node.js module built specifically to enable you to build correct REST web services.
         </td>
      </tr>
      <tr>
         <td><a href="http://loopback.io/" target="_blank">Loopback</a>
         </td>
         <td>Loopback is an open-source Node.js API framework. 
         </td>
      </tr>
      <tr>
         <td><a href="http://www.actionherojs.com/" target="_blank">ActionHero</a>
         </td>
         <td>actionhero.js is a multi-transport Node.JS API Server with integrated cluster capabilities and delayed tasks.
         </td>
      </tr>
      <tr>
         <td><a href="http://frisbyjs.com" target="_blank">Frisby</a>
         </td>
         <td>Frisby is a REST API testing framework built on node.js and Jasmine that makes
            testing API endpoints easy, fast, and fun.
         </td>
      </tr>
      <tr>
         <td><a href="https://chocolatejs.org/" target="_blank">Chocolate.js</a>
         </td>
         <td>Chocolate is a simple webapp framework built on Node.js using Coffeescript.
         </td>
      </tr>
   </tbody>
</table>

## Express.js

"Express is a fast, unopinionated minimalist web framework for Node.js" - official web site: Expressjs.com
Express.js is a web application framework for Node.js. It provides various features that make web application development fast and easy which otherwise takes more time using only Node.js.
Express.js is based on the Node.js middleware module called connect which in turn uses http module. So, any middleware which is based on connect will also work with Express.js.


### Advantages of Express.js

- Makes Node.js web application development fast and easy.
- Easy to configure and customize.
- Allows you to define routes of your application based on HTTP methods and URLs.
- Includes various middleware modules which you can use to perform additional tasks on request and response.
- Easy to integrate with different template engines like Jade, Vash, EJS etc.
- Allows you to define an error handling middleware.
- Easy to serve static files and resources of your application.
- Allows you to create REST API server.
- Easy to connect with databases such as MongoDB, Redis, MySQL

### Install Express.js
You can install express.js using npm. The following command will install latest version of express.js globally on your machine so that every Node.js application on your machine can use it.
```
npm install -g express
```
The following command will install latest version of express.js local to your project folder.
```
C:\MyNodeJSApp> npm install express --save
```
As you know, --save will update the package.json file by specifying express.js dependency.

## Express.js Web Application

Express.js provides an easy way to create web server and render HTML pages for different HTTP requests by configuring routes for your application.

### Web Server
First of all, import the Express.js module and create the web server as shown below.

```
var express = require('express');
var app = express();

// define routes here..

var server = app.listen(5000, function () {
    console.log('Node server is running..');
});
```

In the above example, we imported Express.js module using require() function. The express module returns a function. This function returns an object which can be used to configure Express application (app in the above example).

The app object includes methods for routing HTTP requests, configuring middleware, rendering HTML views and registering a template engine.

The app.listen() function creates the Node.js web server at the specified host and port. It is identical to Node's http.Server.listen() method.

Run the above example using node app.js command and point your browser to http://localhost:5000. It will display Cannot GET / because we have not configured any routes yet.

### Configure Routes

Use app object to define different routes of your application. The app object includes get(), post(), put() and delete() methods to define routes for HTTP GET, POST, PUT and DELETE requests respectively.

The following example demonstrates configuring routes for HTTP requests.

```
var express = require('express');
var app = express();

app.get('/', function (req, res) {
    res.send('<html><body><h1>Hello World</h1></body></html>');
});

app.post('/submit-data', function (req, res) {
    res.send('POST Request');
});

app.put('/update-data', function (req, res) {
    res.send('PUT Request');
});

app.delete('/delete-data', function (req, res) {
    res.send('DELETE Request');
});

var server = app.listen(5000, function () {
    console.log('Node server is running..');
});
```

In the above example, app.get(), app.post(), app.put() and app.delete() methods define routes for HTTP GET, POST, PUT, DELETE respectively. The first parameter is a path of a route which will start after base URL. The callback function includes request and response object which will be executed on each request.

Run the above example using node server.js command, and point your browser to http://localhost:5000 and you will see the following result.

### Handle POST Request

Here, you will learn how to handle HTTP POST request and get data from the submitted form.
First, create Index.html file in the root folder of your application and write the following HTML code in it.

```
<!DOCTYPE html>

<html xmlns="http://www.w3.org/1999/xhtml">
<head>
    <meta charset="utf-8" />
    <title></title>
</head>
<body>
    <form action="/submit-student-data" method="post">
        First Name: <input name="firstName" type="text" /> <br />
        Last Name: <input name="lastName" type="text" /> <br />
        <input type="submit" />
    </form>
</body>
</html>
```

### Body Parser

To handle HTTP POST request in Express.js version 4 and above, you need to install middleware module called body-parser. The middleware was a part of Express.js earlier but now you have to install it separately.

This body-parser module parses the JSON, buffer, string and url encoded data submitted using HTTP POST request. Install body-parser using NPM as shown below.

```
npm install body-parser --save
```

Now, import body-parser and get the POST request data as shown below.

```
var express = require('express');
var app = express();

var bodyParser = require("body-parser");
app.use(bodyParser.urlencoded({ extended: false }));

app.get('/', function (req, res) {
    res.sendFile('index.html');
});

app.post('/submit-student-data', function (req, res) {
    var name = req.body.firstName + ' ' + req.body.lastName;
    
    res.send(name + ' Submitted Successfully!');
});

var server = app.listen(5000, function () {
    console.log('Node server is running..');
});
```

In the above example, POST data can be accessed using req.body. The req.body is an object that includes properties for each submitted form. Index.html contains firstName and lastName input types, so you can access it using req.body.firstName and req.body.lastName.

Now, run the above example using node server.js command, point your browser to http://localhost:5000 and see the following result.

Fill the First Name and Last Name in the above example and click on submit. For example, enter "James" in First Name textbox and "Bond" in Last Name textbox and click the submit button. The following result is displayed.

### Serving Static Resources in Node.js

you will learn how to serve static resources like images, css, JavaScript or other static files using Express.js and node-static module.

#### Serve Static Resources using Express.js

It is easy to serve static files using built-in middleware in Express.js called express.static. Using express.static() method, you can server static resources directly by specifying the folder name where you have stored your static resources.

The following example serves static resources from the public folder under the root folder of your application.

```
var express = require('express');
var app = express();

//setting middleware
app.use(express.static(__dirname + 'public')); //Serves resources from public folder


var server = app.listen(5000);
```

In the above example, app.use() method mounts the middleware express.static for every request. The express.static middleware is responsible for serving the static assets of an Express.js application. The express.static() method specifies the folder from which to serve all static resources.

tips -- Specify absolute path in express.static() by prepending __dirname. This will not break your application even if you run the express app from another directory.

Now, run the above code using node server.js command and point your browser to http://localhost:5000/myImage.jpg and it will display myImage.jpg from the public folder (public folder should have myImage.jpg).

If you have different folders for different types of resources then you can set express.static middleware as shown below.

```
var express = require('express');
var app = express();

app.use(express.static('public'));

//Serves all the request which includes /images in the url from Images folder
app.use('/images', express.static(__dirname + '/Images'));

var server = app.listen(5000);
```

In the above example, app.use() method mounts the express.static middleware for every request that starts with "/images". It will serve images from images folder for every HTTP requests that starts with "/images". For example, HTTP request http://localhost:5000/images/myImage.png will get myImage.png as a response. All other resources will be served from public folder.

Now, run the above code using node server.js and point your browser to http://localhost:5000/images/myImage.jpg and it will display myImage.jpg from the images folder, whereas http://localhost:5000/myJSFile.js request will be served from public folder. (images folder must include myImage.png and public folder must include myJSFile.js)

You can also create a virtual path in case you don't want to show actual folder name in the url.
```
app.use('/resources',express.static(__dirname + '/images'));
```

So now, you can use http://localhost:5000/resources/myImage.jpg to serve all the images instead of http://localhost:5000/images/myImage.jpg.
In this way, you can use Express.js to server static resources such as images, CSS, JavaScript or other files.
