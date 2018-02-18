# TDD

**T**est
**D**riven
**D**evelopment
- Red: write test first (to fail)
  - write test in steps of what we want to happen, but said things aren't happening yet in the file we are testing
- Green: get it to pass
  - write .js file to pass the test
  - do just enough to get the test to pass, as we don't want to be adding unnecessary things (or junk code)
  -this is often very sloppy
- Gold: then refactor the code
  - in this step, the code does the same thing it did before, but you clean things up, reorganize the code, etc. (make it pretty!)
___

### Setting up testing environment

In order create a testing environment for TDD, we need to set up initial file structure:
- create a new repo and clone it into the Code folder
  ```
  $ git clone 'url'
  ```
    - this will create new directory in Code folder and we need to cd into it


- install node modules, .gitignore file, and mocha & chai libraries
  ```
  $ npm init
  $ $ touch .gitignore
  $ echo >> .gitignore "node_modules"
  $ npm install mocha chai --save-dev
  ```
    - this will create mocha and chai devDependencies that we can see in our package.json file


Build test.js files

Build js files that will be tested

add babel if test is reading ES6

can add eslint as well to proof our syntax
