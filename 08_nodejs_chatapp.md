<div align="center">
  <h1>Chat app - Node.js  </h1>
  <sub>Author:
<a href="https://www.linkedin.com/in/bhuvanaganesan-l-2209047a" target="_blank">Bhuvan Ganesan</a><br>
</sub>
</div>

<hr>

## What We Will Be Using to Build?
We will be using Node.js for the back end, which will be responsible for creating rooms and managing users in those rooms. Additionally, we will be using Socket.io to enable real-time, bidirectional communication between the web server and the client (browser).

## WebSocket and Socket.io
WebSocket is a communication protocol for having real-time, bidirectional, and low-latency communication between the web server and the browser. Socket.io is basically a JavaScript library built using the WebSocket API to enable all of this.

```
Browser/       -----------------------> Nodejs 
Nodejs Client <------------------------ Serve 
```

To learn more about WebSocket and Socket.io, visit the following:

[Wiki](https://en.wikipedia.org/wiki/WebSocket?source=post_page)

[SocketJS](https://socket.io/?source=post_page)


## Let's Build Chat application 

### Initialize package.json

Using **npm init** create a **package.json** file. This file holds project-related information like name, author, version, etc. After entering the above command, enter the information as it appears in the terminal.

###  Install Packages

We will use four Node packages for our project.

    **Express** —>  a web application framework for building web applications in Node
    **Socket.io** —> enables real-time communication between server and browser
    **EJS (Embedded JavaScript)** —>  a templating language to build HTML markup for your front end
    **body-parser**  —>  for reading the body of and incoming JSON object from req.body

Now let's import the above packages. Run the following command in the terminal to import.

```
npm install express socket.io ejs body-parser --save
```

Create **app.js** file and include the above packages to our code. Also, set other options like body-parser, view engine, public directory, and port address.

```

```





