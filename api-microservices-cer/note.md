# Managing Packages with Npm

- npm? Node Package Manager
- The Node Package Manager (npm) is a command-line tool used by developers to share and control modules (or packages) of JavaScript code written for use with Node.js.
- When starting a new project, npm generates a package.json file.
- package.json file lists the package dependencies for your project.
- npm saves packages in a folder named node_modules
- These packages can be installed in two ways:

  1. globally in a root node_modules folder, accessible by all projects.
  2. locally within a project's own node_modules folder, accessible only to that project.

- clone boilerplate-npm

## 1. Managing Packages with Npm - How to Use package.json, the Core of Any Node.js Project or npm Package

- The package.json file is the center of any Node.js project or npm package
  https://boilerplate-npm-1.serin0837.repl.co

## 2. add a description to your package.json

- a good package.json file is the description field; where a short, but informative description
  (not passing why??)

## 3. Add Keywords to Your package.json

- The keywords field is where you can describe your project using related keywords.
- as an array of double-quoted strings.

## 4. Add a License to Your package.json

- The license field is where you inform users of what they are allowed to do with your project.

## 5. Add a Version to Your package.json

- This field describes the current version of your project. Here's an example:
  ->https://docs.npmjs.com/about-semantic-versioning (semantic npm)

## 6. Expand Your Project with External Packages from npm

- But how can npm know exactly what your project needs? Meet the dependencies section of your package.json file.
- Note: Moment is a handy library for working with time and dates.
- example: "moment":"12.0.4"

## 7. Manage npm Dependencies By Understanding Semantic Versioning

- Semantic Versioning (SemVer)
- Libraries, frameworks or other tools published on npm should use SemVer in order to clearly communicate what kind of changes projects can expect if they update.
- "package": "MAJOR.MINOR.PATCH"
- PATCHes are bug fixes and MINORs add new features but neither of them break what worked before. Finally, MAJORs add changes that won’t work with earlier versions.

## 8. Use the Tilde-Character to Always Use the Latest Patch Version of a Dependency

- To allow an npm dependency to update to the latest PATCH version, you can prefix the dependency’s version with the tilde (~) character. Here's an example of how to allow updates to any 1.3.x version.
- `"package": "~1.3.8"`

## 9. Use the Caret-Character to Use the Latest Minor Version of a Dependency

- the caret (^) allows npm to install future updates as well. The difference is that the caret will allow both MINOR updates and PATCHes.
- If you were to use the caret (^) as a version prefix instead, npm would be allowed to update to any 2.x.x version.
- `"package": "^1.3.8"`

## 10. Remove a Package from Your Dependencies

- just remove the corresponding key-value pair for that package from your dependencies.

# Basic node and express

- Node.js is a JavaScript runtime that allows developers to write backend (server-side) programs in JavaScript.

- built-in modules
- HTTP: a module that acts as a server
- File System: a module that reads and modifies files
- Path: a module for working with directory and file paths
- Assertion Testing: a module that checks code against prescribed constraints

- Express : while not included with Node.js, is another module often used with it.
  - Express runs between the server created by Node.js and the frontend pages of a web application.
  - Express also handles an application's routing.

## 1. Meet the Node console

## 2. Start a Working Express Server

```js
var express = require("express");
var app = express();
```

- `app.listen(port)` : It tells your server to listen on a given port
- `app.METHOD(PATH, HANDLER)`: METHOD is an http method in lowercase. PATH is a relative path on the server (it can be a string, or even a regular expression). HANDLER is a function that Express calls when the route is matched.
- Handlers take the form `function(req, res) {...}`
  - req is the request object
  - res is the response object
  - example : `function(req, res) {res.send('Response String');}`

example:
`app.get("/",function(req,res){res.send("Hello Express")})`

## 3. Serve an HTML File

- `res.sendFile(path)`:respond to requests with a file
- Behind the scenes, this method will set the appropriate headers to instruct your browser on how to handle the file you want to send, according to its type. Then it will read and send the file.
- This method needs an absolute file path.
- example of absolute file path :`absolutePath = __dirname + relativePath/file.ext`
- example:`app.get("/",function(req,res){res.sendFile(__dirname+"/views/index.html")})`(I can see form )

## 4. Serve Static Assets

- An HTML server usually has one or more directories that are accessible by the user.

- You can place there the static assets needed by your application (stylesheets, scripts, images)

- In Express, you can put in place this functionality using the middleware.`express.static(path)`

- Basically, middleware are functions that intercept route handlers, adding some kind of information.

- A middleware needs to be mounted using the method `app.use(path, middlewareFunction)`

- The first path argument is optional. If you don’t pass it, the middleware will be executed for all requests.

- example: `app.use(express.static(__dirname+"/public"));`
  bring the css stylesheet

## 5. Serve JSON on a Specific Route

this one and api together tomorrow
