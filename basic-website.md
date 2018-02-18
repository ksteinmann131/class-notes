# Basic Website

### Create git repository
- create new repository on github.com
- in terminal, in Code folder, clone repo with url
  ```
   $ git clone 'url'
   ```
    - this will create new directory in Code folder, we need to cd into said directory
___

### Create project structure:
- create project directory w/in Code folder (ex. portfolio) in command line (if you cloned git repo, this folder will already exist)
- will create 2 items in portfolio
  1. server.js (touch)
  2. public (directory)
- in public directory, will create 3 files (all touch)
  1. style.css
  2. index.js
  3. index.html
___

### Install node modules, packages to build server, .gitignore file
##### In project directory (portfolio), in command line:


```
$ npm init
```
- press return a bunch of times to get back to prompt
- creates package.json in portfolio folder

```
$ npm install express path --save
```
- installs express and path dependencies
- (needed to create server)

```
$ touch .gitignore
```
- creates .gitignore file that git won't copy when you push

```
$ echo >> .gitignore "node_modules"
```
- puts 'node_modules' into gitignore file so they won't be pushed to github
___

### Create basic html stucture, build server file
#### Open project in Atom (w/ atom .)

##### in HTML file:
- type html, then tab for basic html layout
- name title (ex. < title >I'm a Webpage!</ title>)
- one line under title, type link, then tab
  - should // < link rel= "stylesheet" href="/css/master.css" >
  - need to change '/css/master' to 'style' so that it references our files
- in body, create header (ex. < h1 >Hello World!</ h1 >)
- one line under h1, type spriptsrc, then tab over
  - should // < script src= " " charset= "ntf-8"></ script>
  - need to insert 'index.js' in empty quotes to reference our file

##### in server.js:
```
const express = require('express');
const path = require('path');
const app = express();
app.use('/', express.static(path.join(__dirname, 'public')))
app.listen(3000, () => console.log('it works 3000'))
```
- can test this in the terminal: $ node server.js
- should // it works 3000
___

### Pushing to Github:

- need to add, commit, and push to the master
  ```
  $ git add -A
  $ git commit -m "what commit changes"
  $ git push origin master
  ```
- can now go to github and see all your files there

** Can't find modules? If you clone the repo, you may need to 'npm install' to get back the express module (will look at package.json first and install all dependencies)
___

### Update server.js to port (in Atom):
###### Need to change our local server (3000 to port, though 3000 will still work)

- add port constant under app constant
  ```
  const port = process.env.PORT || 3000;
  ```
- need to change app.listen function
  ```
  app.listen(port, () => console.log('served on ' + port));
  ```

** remember to add, commit, and push this to Github
___

### Deploy to Heroku
###### In terminal, in project directory (portfolio):
- create new empty application on Heroku
  ```
  $ heroku create
  ```
  - // what heroku app name is


- can confirm that a remote named Heroku has been created for your app
  ```
  $ git remote -v
  ```
- deploy app to Heroku using git push to push code from local repo's master branch to Heroku remote
  ```
  $ git push heroku master
  ```
  - then can go to Heroku site and see/open application
  ___
