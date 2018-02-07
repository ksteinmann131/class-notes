# Basic Website

### Create project directory:
- create project directory w/in Code folder (ex. portfolio) in command line
- will create 2 items in portfolio
  1. server.js (touch)
  2. public (directory)
- in public directory, will create 3 files (all touch)
  1. style.css
  2. index.js
  3. index.html
___

### In project directory (portfolio), in command line:


- $ npm init
  - press return a bunch of times to get back to prompt
  - creates package.json in portfolio folder


- $ npm install express path --save
  - installs express and path dependencies


- $ touch .gitignore
  - creates .gitignore file that git won't copy when you push


- $ echo >> .gitignore "node_modules"
___

### Open project in Atom (w/ atom .)

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
- const express = require('express');
- const path = require('path');
- const app = express();
- app.use('/', express.static(path.join(__dirname, 'public')))
- app.listen(3000, () => console.log('it works 3000'))
  - can test this in the terminal: $ node server.js
  - should // it works 3000
___

### Need to push to Github:
- create new repository on github website
- copy url, in command line (in portfolio) directory,
  - $ git clone (url)
- then we need to add, commit, and push to the master
  - $ git add -A
  - $ git commit -m "what commit changes"
  - $ git push origin master
- can now go to github and see all your files there

** Can't find modules? If you clone the repo, you may need to 'npm install' to get back the express module (will look at package.json first and install all dependencies)
___

### Need to change server.js to port (in Atom):
** need to change our local server (3000 to port, though 3000 will still work
- add port constant under app constant
  - const port = process.env.PORT || 3000;
- need to change app.listen function
  - app.listen(port, () => console.log('served on ' + port));

** remember to add, commit, and push this to Github
___

### Need to deploy to Heroku
** in terminal, in project directory (portfolio):
- create new empty application on Heroku
  - $ heroku create
  - // what heroku app name is
- can confirm that a remote named Heroku has been created for your app
  - $ git remote -v
- deploy app to Heroku using git push to push code from local repo's master branch to Heroku remote
  - $ git push heroku master
  - then can go to Heroku site and see/open application
  ___
