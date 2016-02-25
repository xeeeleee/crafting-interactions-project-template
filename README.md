# The Crafting UX Web Project Template

## Introduction  

The goal of this project is to give you a template to publish on the web. The template will also give you a glimpse into how contemporary web projects are structured.

Once everything is setup the premise is simple.

1. put your html, css, javascript, images etc. into the `public` folder  
2. push your changes to a github repo  
3. github pushes to a webserver and the site is updated

---

## Prereqs 

* Fork this repository into your github account. 
* Create an account at [heroku.com](https://www.heroku.com/) if you don't have one.  
* If you don't have a code editor download **[SublimeText](http://www.sublimetext.com/3)** or **[Atom](https://atom.io/)** or **[Brackets](http://brackets.io/)**. All 3 have the basic code edtior capabilities we want but there may be features in one that you prefer.  
* Install [nodejs](https://nodejs.org/en/). You can download either the LTS or the Stable version. LTS means _Long Term Support_ and is preferred by big enterprise organizations. The Stable release has newer features (that you prob won't need).  
* If you don't want to mess with `git` on the command line you can use an app to manage your repos. [**Github Desktop**](https://desktop.github.com/) is made by Github and [**Git Tower**](https://www.git-tower.com/) is another good alternative.  
*  ...but we are going to mess with the command line a little bit. If you're on OSX you've got **Terminal** inside your **Applications/Utilities** folder. 

> Before doing the last step in the prereqs, open **Terminal** and type `which node` and hit Enter. If you see a folder path output, you've installed node and you're good to go. When you use the `which` command you're asking the system if it knows what command you're talking about. If the command returns a folder the system can find the command and you're good to go. If the command does nothing, it has no idea what you're talking about and you need to reinstall. 

![Typing which node](/screenshots/which-node.png?raw=true "Which Node")  

* The final step is to copy paste this line into your **Terminal** window. `npm install -g bower node-static`

> See if that worked by typing `which bower` and see if you've got a folder path. 

> **Done!** This is a one-time setup and now you've got everyting you need to work with your project. Onwards.

---

## What's included in this project
```
├── README.md
├── app.js
├── bower.json
├── package.json
├── public
|   ├── css
|   ├── index.html
|   └── js
└── screenshots
```

### Breaking it down by file & folder  

**README.md** is what you're reading right now. [README files](https://en.wikipedia.org/wiki/README) are like a project's owner's manual. They typically cover project structure, installation steps, contribution guidelines etc. The `.md` extension is for [markdown](http://markdowntutorial.com/) in case you're curious.

**[app.js](app.js)** is a [node](https://nodejs.org/en/) app that runs on the server. This app is bare-bones. It's 15 lines of code that starts a web-server and serves files out of the `public` folder. If all you want to do is make a static website and push it to the web you don't need anything more complicated than this.  

**[bower.json](bower.json)** is a config file for the `bower` utility you installed in the prereqs. [Bower](http://bower.io/) is a [package manager](https://en.wikipedia.org/wiki/Package_manager) for front-end projects. The bower site says it best: _"Web sites are made of lots of things — frameworks, libraries, assets, and utilities. Bower manages all these things for you."_

**[package.json](package.json)** is a config file for the `npm` package manager. Bower is for front-end packages  and npm is for server-side packages.  

**public/** is the folder where you want to put everything that's part of your website. If your site is `my-site.herokuapp.com` and you have `public/image/cat.png` in your public folder, a user can see your image at `my-site.herokuapp.com/image/cat.png`. Got it?  

**screenshots** you can ignore this. It's where I put the screenshots I reference in this README.

---

## Running the project locally

> Running a project locally means starting a server on your computer and _serving_ the website to yourself so you can see what you're doing during development.

### Installing project dependencies and starting the server  

**0. Change Directories in the Terminal.** We need to point the Terminal at your project. To do this type `cd ` and then drag-drop your entire project folder (not just the public folder) into the Terminal and you'll see the path to your project auto-populate in the window. Hit enter.

**1. Install your project's dependencies.** I'll talk more about dependencies in a bit but for now know that this project depends on some 3rd party libraries to work and we need to have our package managers install them before we can do anything. Run `npm install` from the **Terminal**. 

When the installation is complete you'll have two new folders in your project: `/node_modules` and `public/bower_components`.

**2. Starting the server and previewing your site locally**
Run `npm start` from the **Terminal**. Test it by visiting [http://localhost:3000](http://localhost:3000).

**3. Making changes**  
Edit any file in `public` and refresh the page to see the updates.

---

## Getting the project on the web  

> Next you're going to create an app on [heroku](https://www.heroku.com/) and connect your github repo to it so your website gets updated when you push new code.

### Connecting your app to heroku
1. Create a new app at [https://dashboard.heroku.com/apps](https://dashboard.heroku.com/apps). Your app url will be `your-project-name.herokuapp.com`.
2. Go to your app's **Deploy** tab and connect the app to your GitHub repo.
![Connect Heroku to Github](/screenshots/heroku-connect.png?raw=true "Connect Heroku") 

4. Enable automatic Github deploys from the 'master' branch. Now, everytime you push new updates to `master`, heroku will pick-up the change and deploy the updates to your website. 
![Deploy from Github](/screenshots/heroku-deploy.png?raw=true "Deploy from Github")

---

## Advanced Topics  

### Working with the package managers. 
If you open either [bower.json](bower.json) or [package.json](package.json) you'll see a `dependencies` list. Here's what bower's looks like:
```
"dependencies": {
  "jquery": "~2.2.1",
  "bootstrap": "~3.3.6"
}
```  
#### Searching for packages  
You can [search on the bower website](http://bower.io/search/) to find packages that might be helpful for your project. 

#### Installing a bower package  
Let's install [font awesome](https://fortawesome.github.io/Font-Awesome/).  

`bower install --save fontawesome`

Once that installs you'll have `public/bower_components/fontawesome` in your project.

### Reading the heroku logs to make sure everything is running okay.

> The heroku server that runs your app has a running log that you can tap into to see the status of your site. 

1. Install the [heroku toolbelt](https://toolbelt.heroku.com/)  
2. From the **Terminal** run `heroku logs --app your-heroku-app-name --tail`  
3. Try pushing an update to github and watch the logs update.
