# Documentation-mftsccs
<h1>How To install mftsccs package for new project</h1>

# How to install mftsccs(package)

mftsccs stands for "mentor friends the symentic concept connection system"

 A package is a way of organizing related pieces of code into a single unit. Packages help manage the complexity of large software projects by providing a hierarchical structure to organize and categorize code. They help in avoiding naming conflicts, improving code reusability, and enhancing maintainability.

###### **Implementation** in javaScript:

In JavaScript, packages are managed using npm (Node Package Manager). A package in this context is a directory containing a `package.json` file, which includes metadata about the package.

#### Command To Initialize:- npm init -y

The command `npm init -y` is used in Node.js and npm (Node Package Manager) to initialize a new Node.js project with default values without prompting the user for information. The `-y` flag stands for "yes" and is used to automatically accept the default values for all configuration options.

Here's what each part of the command does:

- `npm`: This is the Node Package Manager, which is used for managing packages (libraries and dependencies) in Node.js projects.
- `init`: This is a command in npm used to initialize a new `package.json` file for a Node.js project. The `package.json` file contains metadata about the project, such as its name, version, dependencies, scripts, and other configuration details.
- `-y`: This is a shortcut for saying "yes" to all the prompts that would normally appear when running `npm init` without the `-y` flag. It automatically accepts the default values for all configuration options, saving you from manually entering them.

So, when you run `npm init -y`, it creates a `package.json` file in the current directory with default values, and you don't have to interactively provide information for each configuration option. This can be useful when you quickly want to set up a new project with default settings.

###### Package Json file:- 

The `package.json` file is a metadata file commonly used in Node.js projects. It contains essential information about the project, its dependencies, scripts, and other configuration details

`{

   "name":"webApp",

​     "version":"1.0.0",

​      "description":"",

​      "main":"index.js",

​       "scripts":{

​        "test":"echo\"Error: no test specified\"&& exit 1"

},

"keywords":[],

"author":"",

"license":"ISC"

}`

#### Command To Install webpack & webpack-cli :-npm i webpack webpack-cli --save

###### Webpack:- 

  Webpack is a bundler for modules. The main purpose is to bundle JavaScript files for usage in a browser, and it is also capable of transforming, bundling, or packaging just about any resource or asset.

The command `npm i webpack webpack-cli --save` is used to install Webpack and Webpack CLI as dependencies for your Node.js project and save them to the `dependencies` section of your `package.json` file.

Creates node_modules directory:-The `node_modules` directory is a convention used in Node.js projects to store locally installed dependencies. When you install packages using a package manager like npm (Node Package Manager) or Yarn, these packages are typically downloaded and stored in the `node_modules` directory within your project.

Here's what each part of the command does:

- **`npm i`**: This is short for `npm install`. It is the command used to install packages in a Node.js project.
- **`webpack`**: This installs the Webpack package. Webpack is the core module bundler that you'll use to bundle your project's assets.
- **`webpack-cli`**: This installs the Webpack CLI (Command Line Interface), which provides commands for running Webpack from the terminal.
- **`--save`**: This flag is used to add the installed packages to the `dependencies` section of your `package.json` file. However, starting from npm version 5.0.0, dependencies are automatically added to the `dependencies` section without needing the `--save` flag, so it's often optional.

After running this command, your `package.json` file will be updated with the dependencies as following:

`{

 "name": "webpack",
 "version": "1.0.0",
 "description": "",
 "main": "index.js",
 "scripts": {
  "build": "webpack",
  "test": "echo \"Error: no test specified\" && exit 1"
 },
 "keywords": [],
 "author": "",
 "license": "ISC",
 "dependencies": {
  "webpack": "^5.89.0",
  "webpack-cli": "^5.1.4"
 }
}`

* ***Note:- for webpack two folders are important so that we have to create two different folders in root directory.(eg:-dist & scr)***

#### Command To Build:- npm run build

   The `npm run build` command is used in Node.js projects to execute a build script defined in the "scripts" section of the `package.json` file. This command is  used for tasks related to building and preparing a project for production.

Here's how it generally works:

1. Scripts in `package.json`:
   - The `package.json` file can include a section called "scripts" where you define various commands and scripts for your project.

```
json
`{
  "scripts": {
    "build": "webpack"
  }
}`
```

In this example, there is a script named "build" that runs the command "webpack" when executed.

**Running the Build Script:**

- When you run `npm run build` in the terminal, npm looks for the "build" script in the "scripts" section of the `package.json` file and executes the associated command.
- This command is used to build the main. js application for production deployment.

#### Create webpack.config.js file 

​    A webpack configuration file is a JavaScript file. In configuration, this option is used to set the NODE_ENV value during bundling. It can either have a production or development value.



`const path = require('path');

module.exports = env => ({

  entry: './src/index.js',

  mode: 'development/production',

  devtool: 'inline-source-map',

  watch: true,

  output: {

   filename: 'main.js',

   path: path.resolve(__dirname, 'dist'),

  }

});`

#### Command To Install mftsccs:- npm install mftsccs

  After installing mftsccs updated structure will be as follows:

​    `{

 "name": "use-mftsccs",

 "version": "1.0.0",

 "description": "",

 "main": "index.js",

 "scripts": {

  "build": "webpack",

  "test": "echo \"Error: no test specified\" && exit 1"

 },

 "keywords": [],

 "author": "",

 "license": "ISC",

 "dependencies": {

  "mftsccs": "^3.0.6",

  "webpack": "^5.89.0",

  "webpack-cli": "^5.1.4"

 }

}`

Now different functions in mftsccs can be used by importing them in entry point .js file as follows:

`import { CreateTheConnection, GetComposition, GetCompositionList, GetCompositionWithId, GetTheConcept, MakeTheInstanceConcept, SyncData, init } from "mftsccs";

init("https://devboom.freeschema.com", "https://devai.freeschema.com");`

#### command used to run the Webpack bundler for your project:npx webpack

The npx webpack command is used to run the Webpack bundler for your project. It is a way to execute the locally installed Webpack binary without the need to install it globally.

Here's a breakdown of what happens when you run npx webpack:

##### npx:

npx is a tool that comes with npm (Node Package Manager). It allows you to run binaries from locally installed npm packages.

##### webpack:

This is the command you want to run. It invokes the Webpack bundler.
When you run npx webpack in the terminal, it looks for the webpack binary in the node_modules directory of your project (where Webpack was installed locally) and executes it.

Assuming you have a webpack.config.js file in your project, Webpack will use the configuration specified in that file to bundle your project's assets.

`npx webpack`

If you don't have a webpack.config.js file, Webpack will use default settings and attempt to bundle the src/index.js file into a dist/main.js file by default (assuming these are the default entry and output configurations).

Keep in mind that using npx is recommended for running binaries from locally installed packages, as it avoids potential version conflicts between globally installed and locally installed packages.

Before running npx webpack, make sure you have Webpack and its dependencies installed. If they are not installed yet, you can install them using:

`npm install mftsccs`

After the installation, you should be able to use npx webpack to bundle your project.



# MakeTheInstanceConcept

------

(mftsccs>=3.0.6)

MakeTheInstanceConcept--Makes the new concept in devboom.freeschema.com database



#### Description

------

`MakeTheInstanceConcept(type:string, referent:string, composition:boolean=false, userId: number,
  accessId:number, sessionInformationId: number=999)`

**MakeTheInstanceConcept()** returns  The Concept  with unique **ID**

  

#### Parameters

------

**type**

​        Type of the concept(eg:-The-big-cat)

**referent**

​        value of the concept type(eg:-the-lion,the-tiger etc)

**composition**

​        Is concept's type a composition(eg:- the big cat is a composition so pass **`true`** as an argument for composition or pass **`false`** if the concept is  not a composition) 

**userId**

​        User Id of the concept

**accessId**

​        Access Id of the user

**sessionInformationId**

​        Session Information Id of the user

#### Example

------

    1. `MakeTheInstanceConcept("The-big-cat", "", true, 999, 4, 999);`

​        Above example return the new concept with unique Id which would be a composition of type The-big-cat.

​    2. `MakeTheInstanceConcept("The-big-cat", "the-lion", true, 999, 4, 999);`

​         Above example return the new concept with unique Id which would be a referent with value The-lion.

# createTheConnection

------

(mftsccs>=3.0.6)

createTheConnection--Creates the connection from concept's type  (composition/of the concept) to concept's referent (to the concept)

#### Description

 `createTheConnection(ofTheConceptId:number, ofTheConceptUserId:number, toTheConceptId:number, toTheConceptUserId:number,
   typeId: number, sessionInformationId: number, sessionInformationUserId: number
  )`



**createTheConnection()**  Creates the connection from ofTheConcept(concept's type) to toTheConcept(concept's referent)

#### Parameters

------

**ofTheConceptId**

Id of the concept's type/composition(eg:-The-big-cat)

**ofTheConceptUserId**

user Id of concept's type/composition

**toTheConceptId**

Id of the concept's referent(eg:-the-lion)

**toTheConceptUserId**

user Id of concept's referent

**typeId**

Id of the concept's type

 **sessionInformationId**

Session Information Id of the concept

**sessionInformationUserId**

Session Information Id of the user

#### Example

------

`var typeConcept = MakeTheInstanceConcept("The-big-cat", "", true, 999, 4, 999);
  var referentConcept = MakeTheInstanceConcept("referent", the-lion, false, 999, 4, 999);`

`CreateTheConnection(typeConcept.id, typeConcept.userId, referentConcept.id, referentConcept.userId, typeConcept.id, 999, 999);`

Above example creates the connection from typeConcept to referentConcept.



# GetCompositionWithId

------

(mftsccs>=3.0.6)

GetCompositionWithId--returns final result of the composition with unique Id

#### Description

`GetCompositionWithId(id: number)`

GetCompositionWithId():- returns final result of the composition with unique Id

#### Parameters

**id**

id of concept's type(eg:-typeconcept)

#### Example

GetCompositionWithId(typeConcept.id)

Above example returns id of the composition by taking typeconcept's id as an paramatre

# GetCompositionList

------

(mftsccs>=3.0.6)

GetCompositionList:-returns composition list from server

#### Description

`GetCompositionList(compositionName:string,userId:number,inpage:number=10,page:number=1)`

GetCompositionList():- This is a function that returns composition list from server.

#### Parameters

**compositionName**

Name of the composition.

**userId**

Id of a user.

**inpage**

Number of compositions in a page.

**page** 

Number of Page

#### Example

`GetCompositionList("E-product", 999, 100, 1);`

Above example lists hundred compositions in a page of E-product,
