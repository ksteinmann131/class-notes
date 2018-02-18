# devstart

Devstart will continuously update server when we make changes so that all we have to do is refresh the page to see the changed live...

#### In terminall, in root project folder (portfolio):
```
$ npm install nodemon --save-dev
```
- this creates nodemon in devDependencies in package.json file

```
$ ./node_modules/nodemon/bin/nodemon.js server.js
```
- this runs the server in your terminal

#### In atom, in package.json files

- in "scripts", making sure to add a comma after the last script, type:
  ```
  "devstart": "./node_modules/nodemon/bin/nodemon.js server.js"
  ```

- can now type  in terminal to run the server
```
$ npm run devstart
```
  - this essentially links the keyword "devstart" to nodemon and points the file we want to run (./node_modules/nodemon/bin/nodemon.js server.js)

___

# eslint

ESLint is like spell/grammar checks for code

Add rules to our eslint file that it checks for when we are writing other code files in root directory

- We have already installed eslint in atom packages, so that is there forever, but we do need to install eslint node_modules for every project:

  ```
  $ npm install eslint eslint-plugin-import --save-dev
  ```
  - this will create "eslint" and "eslint-plugin-import" devDependencies in package.json folder


- Need to create .eslintrc file in root directory that will contain all of our rules. In terminal:

  ```
  $ touch .eslintrc
  ```
  - copy and paste in all rules that we want to be included (copy from file we created for MT Code School)
___

# babel
Babel is a transpiler that compiles ES6 into ES5 so that .js files can be used with node_modules as node currently isn't updated with ES6

### Setup:
- in terminal, install babel packages in root directory
```
$ npm install babel-cli babel-preset-es2015 babel-preset-stage-2 babel-register --save-dev
```
  - this will create devDependencies that we can see in package.json file


- in package.json file, needs to add "script" to link to Babel
  - for testing:
  ```
  "test": "mocha --compilers js:babel-core/register ./test/*test.js"
  ```
  - for server:
  ```
  "start": "./node_modules/nodemon/bin/nodemon.js src/server.js --exec babel-node,
  "build": "./node_modules/babel-cli/bin/babel.js src -d dist"
  ```
    - for both projects, we are indicating what node package/s that we are using, then pinting to babel and what files we are transpiling


- like we did for eslint, we need to add .babelrc file to root directory
```
$ touch .babelrc
```
  - w/in file, need to indicate what presets we are using
  ```
  {
  "presets":["es2015"]
  }
  ```
- should now be able to run scripts in command line and it will transpile files into ES5

** see restful-api(bears) and totallyNotStolenReview projects
___

# webpack

### Webpack takes individual files and turns them into one line of JS
- do this because individual files load slowly and page will load files faster if its just loading one file (so we combine them all with webpack)
  - compresses everything, is completely illegible, but retains all functionality and loads very faster
    - essentially is taking things closer to the metal (taking it closer to binary so the computer can read it faster)


### Basic setup:
- In terminal, in root directory:
```
$ npm install webpack --save
$ ./node_modules/webpack/bin/webpack.js
```

- In atom, in package.json, need to add another "script" (don't forget to add comma to end of previous script):
```
"build": "./node_modules/webpack/bin/webpack.js"
```

- when we run `$ npm run build` in command line, should // no configuations file found....
```
$ touch webpack.config.js
```
  - creates configuation file in root project directory


- grab code from webpack site and paste into webpack.config.js
```
module.exports = {
    entry: './app.js',
    outpost: {
      filename: 'bundle.js'
    }
};
```
  - at this point, it still won't work because we don't have an app.js file


- need to create src and dist folders
  - src folder goes w/in root directory
    - move index.js file ino this folder
  - dist folder goes w/in public folder
    - this folder remains empty


- need to edit code w/in webpack.config.js file to point to correct pathways (link index.js file to webpack)
```
module.exports = {
    entry: './src/index.js',
    outpost: {
      filename: './public/dist/bundle.js'
    }
};
```
  - this will create bundle.js file when we run it



- now we can run it in the terminal
```
$ npm run build
```
  - // should get green output in terminal
  - have to run this every time we make a change


- if we look at our page and inspect the console (should have console.log somewhere), it is still not working
  - we need to link the new file to the html file, in bottom of the < body >
  ```
  <script src="./dist/bundle.js" charset="utf-8"></script>
  ```
  - now this should work when we inspect the console on the site


- need to add our dist folder (and all files within it including bundle.js) into the .gitignore files
```
public/dist/*
```

- w/in our src folder, we can more .js files, but they will need to be exported to the index.js file, as that is what is linked to webpack. Example:
  - index.js file
  ```
  import bar from './bar';
  import foo from './foo';
  foo();
  bar();
  console.log("js works")
  ```
  - foo.js file
  ```
  export default function foo() {
  console.log("foo");
  }
  ```
  - bar.js file
  ```
  export default function bar() {
  console.log("bar");
  }
  ```
    - can see that foo.js and bar.js are being imported into the index.js file
    - when we inspect this in the site's console, we should see `foo`, `bar`, and `js works` logged


** see portfolio2 example
___

# mongo
___

# bootstrap
___

# jquery

Can add JQuery library to project to manipulate the DOM with methods build into the library...


#### Use CDN to add:

- google jquery CDN
- copy google CDN that is found on W3Schools website (usually 2nd or 3rd link down in google search)
- add text to < script > tag in < head > of html file (index.html)

- basic syntax uses $(selector).action()
  - $: defines/accesses jquery library
  - (selector): queries or finds HTML elements
  - .action(): is function call that performs action on elements
    - ex:  $(this).hide() //hides the current elements

###### Ajax library ??
```
$(document).ready()
```
- this makes sure the document has loaded before performing jquery methods


** will not be using JQuery much as we will be working more with React
___
