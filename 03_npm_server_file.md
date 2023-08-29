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
