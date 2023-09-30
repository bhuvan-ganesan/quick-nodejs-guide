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
const express = require('express');
const bodyParser = require('body-parser');
const socket = require('socket.io')

const app = express();
app.use(bodyParser.urlencoded({extended: false}));
app.use(express.static('public'));
app.set('view engine', 'ejs');
var port = process.env.PORT || 3000;

//Render Index page
app.get('/', (req, res) => {
    res.render('index')
})

//Get username and roomname from form and pass it to room
app.post('/room', (req, res) => {
    roomname = req.body.roomname;
    username = req.body.username;
    res.redirect(`/room?username=${username}&roomname=${roomname}`)
})

//Rooms
app.get('/room', (req, res)=>{
    res.render('room')
})

//Start Server
const server = app.listen(port, () => {
    console.log(`Server Running on ${port}`)
})

const io = socket(server);
require('./utils/socket')(io);
```
### Code for index.ejs:

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="/style.css">
    <title>Chat App</title>
</head>
<body>
    <div class="content">
        <div>
            <p>Welcome to Chat App</p>
            <form action="/room" method="POST">
                <input type="text" placeholder="Enter your Name" class="username" name="username" required>
                <input type="text" placeholder="Enter Room Name" class="roomname" name="roomname" required>
                <input type="submit" value="Enter">
            </form>
        </div>
    </div>
</body>
</html>

```

Here the user is presented with a form where they can enter their name and a room name.

The user name and room name submitted will be passed to the route room and will render **room.ejs**. Include the following code in the **app.js** file.

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Chat APP</title>
    <link rel="stylesheet" href="/style.css">
    <script src="https://cdnjs.cloudflare.com/ajax/libs/socket.io/2.3.1/socket.io.js"></script>
</head>
<body>
    <h1 class="room-message"></h1>
    <div class="window">
        <div class="chat-message">
            <div id="output"></div>
            <div id="feedback"></div>
        </div>
        <div class='fields'>
            <input type="text" id="message" placeholder="Enter message">
            <button id="send">Send</button>
        </div>
    </div>
    <div class="online">
        <p class="users-online">Users Online</p>
        <div class="users">
        </div>
    </div>
    <script src="/chat.js"></script>
</body>
</html>
```

Style.css 
```
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    background-color: rgb(231, 216, 228);
}
/* -------------- room.ejs -------------- */

h1 {
    text-align: center;
    margin-top: 15px;
}

input {
    width: 100%;
    height: 40px;
    text-indent: 10px;
}

button {
    width: 100%;
    height: 50px;
    background-color: #1a2eda;
    color: white;
    font-size: larger;
    font-weight: bold;
    outline: none;
    cursor: pointer;
    border: none;
}

.fields {
    width: 100%;
}

.window {
    margin: auto;
    margin-top: 20px;
    width: 700px;
    height: 500px;
    border: 2px solid #c2c6b6;
    display: flex;
    flex-direction: column;
    align-content: space-between;
}

.chat-message {
    display: block;
    width: 100%;
    height: 100%;
    overflow: auto;
}

#output, #feedback {
    margin-left: 10px;
}

.online {
    height: 100vh;
    width: 300px;
    position: absolute;
    left: 0px;
    top: 0px;
    background-color: rgb(110, 103, 103);
}

.online .users-online {
    background-color: rgb(110, 103, 103);
    color: white;
    text-align: center;
    font-size: 40px;
    font-weight: bolder;
}

.users {
    margin-left: 40px;
    margin-top: 50px;
}

.users p {
    background-color: rgb(110, 103, 103);
    color: white;
}

/* -------------- index.ejs -------------- */

.content {
    height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

.content p {
    font-size: 40px;
    font-weight: 700;
    margin-bottom: 40px;
}

.content input {
    margin-bottom: 20px;
    height: 50px;
    border: 1px solid black;
    border-radius: 7px;
}

.content input[type="submit"] {
    cursor: pointer;
}

::placeholder {
    font-weight: 700;
}

.content div {
    border: 2px solid black;
    padding: 70px;
    border-radius: 25px;
}
```


Check below link for room js 
http://localhost:3000/room?username=xyz&roomname=friends

## Handling Socket at the server and on the client side

### Client side 
For handling Socket on the client side, create a file chat.js(inside the public folder). Also, include the following scripts in theroom.ejs to import the Socket library and chat.js.

```
const output = document.getElementById('output');
const message = document.getElementById('message');
const send = document.getElementById('send');
const feedback = document.getElementById('feedback');
const roomMessage = document.querySelector('.room-message');
const users = document.querySelector('.users');

//Socket server URL
const socket = io.connect('https://a-chatting-app.herokuapp.com');

//Fetch URL Params from URL
const queryString = window.location.search;
const urlParams = new URLSearchParams(queryString);
const username = urlParams.get('username');
const roomname = urlParams.get('roomname');
console.log(username, roomname);

//Display the roomname the user is connected to
roomMessage.innerHTML = `Connected in room ${roomname}`

//Emitting username and roomname of newly joined user to server
socket.emit('joined-user', {
    username: username,
    roomname: roomname
})

//Sending data when user clicks send
send.addEventListener('click', () =>{
    socket.emit('chat', {
        username: username,
        message: message.value,
        roomname: roomname
    })
    message.value = '';
})

//Sending username if the user is typing
message.addEventListener('keypress', () => {
    socket.emit('typing', {username: username, roomname: roomname})
})

//Displaying if new user has joined the room
socket.on('joined-user', (data)=>{
    output.innerHTML += '<p>--> <strong><em>' + data.username + ' </strong>has Joined the Room</em></p>';
})

//Displaying the message sent from user
socket.on('chat', (data) => {
    output.innerHTML += '<p><strong>' + data.username + '</strong>: ' + data.message + '</p>';
    feedback.innerHTML = '';
    document.querySelector('.chat-message').scrollTop = document.querySelector('.chat-message').scrollHeight

})

//Displaying if a user is typing
socket.on('typing', (user) => {
    feedback.innerHTML = '<p><em>' + user + ' is typing...</em></p>';
})

//Displaying online users
socket.on('online-users', (data) =>{
    users.innerHTML = ''
    data.forEach(user => {
        users.innerHTML += `<p>${user}</p>`
    });
})
```
To explain in short what chat.js is doing: When the user writes a message and clicks send, the room name, message, and the name of the user are sent to the server. It is also receiving messages from the server about other user's messages and current online users, and displaying them to the HTML page.

### Server side

For handling Socket on the server side, create a file **socket.js** (inside the utils folder). This will be responsible for receiving user messages, room names, and user names. Then the messages will then be sent to the respective rooms, depending on the room name.

```
const {getUsers, users} = require('./getUsers');

//Socket connection
function socket(io) {
    io.on('connection', (socket) => {

        socket.on('joined-user', (data) =>{
            //Storing users connected in a room in memory
            var user = {};
            user[socket.id] = data.username;
            if(users[data.roomname]){
                users[data.roomname].push(user);
            }
            else{
                users[data.roomname] = [user];
            }
            
            //Joining the Socket Room
            socket.join(data.roomname);
    
            //Emitting New Username to Clients
            io.to(data.roomname).emit('joined-user', {username: data.username});
    
            //Send online users array
            io.to(data.roomname).emit('online-users', getUsers(users[data.roomname]))
        })
    
        //Emitting messages to Clients
        socket.on('chat', (data) =>{
            io.to(data.roomname).emit('chat', {username: data.username, message: data.message});
        })
    
        //Broadcasting the user who is typing
        socket.on('typing', (data) => {
            socket.broadcast.to(data.roomname).emit('typing', data.username)
        })
    
        //Remove user from memory when they disconnect
        socket.on('disconnecting', ()=>{
            var rooms = Object.keys(socket.rooms);
            var socketId = rooms[0];
            var roomname = rooms[1];
            users[roomname].forEach((user, index) => {
                if(user[socketId]){
                    users[roomname].splice(index, 1)
                }
            });
    
            //Send online users array
            io.to(roomname).emit('online-users', getUsers(users[roomname]))
        })
    })
}

module.exports = socket;
```
**Displaying currently online users**

You might have noticed const {getUsers, users} = require('./getUsers'); inside socket.js.

users is an object which stores the users currently online in memory. getUsers is a function for storing users WRT their room names in users object whenever a new user connects.

Create a file called getUsers.js(inside the utils folder). Add the following code to it.

```
//Store connected Users
var users = {}

//Funtion to get users online in a room
function getUsers(arr){
    onlineUsers = []
    arr.forEach((onlineUser) => {
        onlineUsers.push(Object.values(onlineUser)[0])
    })
    return onlineUsers
}

module.exports = {getUsers, users};
```

## Run the App
```
node app.js
```

We have now successfully built a real-time chat application and have a fair understanding of how messages are exchanged from one user to another.

**Some features that you can try to add:**

    - Set up a login system and have the ability to have a friends list.
    - Connect it to a database, to save all the past messages.
    - Add About and Profile sections.
    - Try to implement features similar to WhatsApp.
