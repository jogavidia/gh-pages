# How to use the gh-pages npm module to deploy

Learn how to use the gh-pages npm module to easily deploy any front-end app or website to Github pages. We will deploy a static site.

## Getting Started

### Creating the project's files via Terminal

* Create a root folder with a subfolder called "build", or whatever you want to call, with your projects files within. 
    
### Steps

#### In the Terminal

1. To access the root folder run:

``` $ cd <rootFolderName> ```


2. To create a package.json file run:

``` $ npm init ```
or ``` $ npm init -y ``` if you don't want to anwser any question.

3. To install gh-pages package run:

``` $ npm i gh-pages ```

You will see gh-pages inside "dependencies" in your package.jason file:
    - Below the "license" line add: "home": "https://username.github.io/repository-name"
    - Then, inside "scripts" create: "deploy": "gh-pages -d build" where "build" is the directory name we want to deploy.

Your package.json file should look something like this:
  ```
  {
  "name": "test",
  "version": "1.0.0",
  "description": "This is a test of gh-pages",
  "main": "index.js",
  "scripts": {
    "deploy": "gh-pages -d build"
  },
  "keywords": [],
  "author": "joga",
  "license": "MIT",
  "home": "https://username.github.io/respositoryname",
  "dependencies": {
    "gh-pages": "^2.2.0"
  }
}
  
  ```

4. Create .gitignore file in the root folder, inside .gitignore type "node_modules" so the node_module folder will be ignored when you push to the repository.


5. Run the following command to initialize the git repository:

``` $ git init ``` It creates a hidden folder.

6. To add everything to a staging area run:

``` $ git add . ```

7. To do your initial commit run:

``` $ git commit -m "your comment here" ```

8. To add remote repository run:

``` git remote add origin https://github.com/username/repository-name.git ```

  If you have your SSH set up run: 

``` $ git remote add origin git@github.com:username/repository-name.git ```

9. To do the initial push to the Master branch run:
``` $ git push -u origin master  ```

10. The last thing you need to do is to deploy to the gh-pages branch, so run the following command:

``` $ npm run deploy  ``` Run this command everytime you want to push new changes to your gh-pages branch.

* [ Click to see a sample of website uploaded through gh-pages](https://jogavidia.github.io/gh-pages/)
