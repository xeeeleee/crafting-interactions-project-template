# The Crafting UX Web Project Template

## Introduction  

The goal of this project is to give you a template to publish on the web. The template will also give you a glimpse into how contemporary web projects are structured.

Once everything is setup the premise is simple. 
1. put your html, css, javascript, images etc. into the `public` folder
2. push your changes to a github repo
3. github pushes to a webserver and the site is updated

## Prereqs 

* If you don't have a code editor download [SublimeText](http://www.sublimetext.com/3) or [Atom](https://atom.io/) or [Brackets](http://brackets.io/). All 3 have the basic code edtior capabilities we want but there may be features in one that you prefer.  
* Install [nodejs](https://nodejs.org/en/). You can download either the LTS or the Stable version. LTS means _Long Term Support_ and is preferred by big enterprise organizations. The Stable release has newer features (that you prob won't need).  
* If you don't want to mess with `git` on the command line you can use an app to manage your repos. [Github Desktop](https://desktop.github.com/) is made by Github and [Git Tower](https://www.git-tower.com/) is another good alternative.  
*  ...but we are going to mess with the command line a little bit. If you're on OSX you've got **Terminal** inside your **Applications/Utilities** folder. 

## What's included  
Everything you need to 

### Developing your website locally
1. Install your project's dependencies.

2. Start your server with `npm start`. Test it by visiting [http://localhost:3000](http://localhost:3000).

### Connecting your app to heroku
1. Create an account at [heroku.com](https://www.heroku.com/)
2. Create a new app at [https://dashboard.heroku.com/apps](https://dashboard.heroku.com/apps). Your app url will be `your-project-name.herokuapp.com`.
3. Go to your app's **Deploy** tab and connect the app to your GitHub repo on Heroku.
4. Enable automatic deploys from GitHub from the 'master' branch. Now, everytime you push new updates to `master`, heroku will pick-up the change and deploy the updates to your website.

#### Reading the app logs
The server that runs your app has a log you can tap into to see the status of your site. 