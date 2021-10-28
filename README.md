# Tutorial: Deploying a basic CodeIgniter app on Jekyo

Demo app [here](https://codeigniter-demo.jekyo.app/)

### Prerequisites

Make sure you have [NodeJS](https://nodejs.org/en/download/), [npm](https://docs.npmjs.com/downloading-and-installing-node-js-and-npm) and [git](https://github.com/git-guides/install-git) installed.

If it's your first time using **Jekyo**, you can **install** it by running the following command in your terminal:

`npm install -g jekyo`

### Sign in to Jekyo

You can sign in to Jekyo by running `jekyo user:signin`

```
➜  ~ jekyo user:signin 
Your email?: **************
Your password?: **********
You have successfully signed in!
```
If you don't have a Jekyo account, you can create one in the terminal by running `jekyo user:signup`. 

## 1. Create a basic CodeIgniter app

You can start your CodeIgniter project by using `jekyo create`

Using the **arrows** on your keyboard, select **codeigniter** and press **enter**.  
```
? Select template
  None Creates only the application
  expressjs A basic app skeleton using [Express](https://expressjs.com/)     
  nuxt-js A boilerplate SSR application using [Nuxt.js](https://nuxtjs.org/) 
❯ codeigniter A basic starter app using [CodeIgniter](https://codeigniter.com/)
```
When prompted, enter the desired name for your CodeIgniter app. 

`Application name?: codeigniter-tutorial`

This will create a basic CodeIgniter app in the current directory by cloning this [CodeIgniter starter app](https://github.com/jekyo/codeigniter-getting-started) repository.

```
Cloning source code... OK
Application created!
```

### Deploy the CodeIgniter app on Jekyo

To deploy the app, first navigate to the newly created directory:

`cd codeigniter-tutorial`

Now you can deploy this app to Jekyo by running: 

`jekyo deploy`

After a while, you should see something like this:

```
➜  Fetching source code ... OK
➜  Building application, this might take a while ... OK
➜  Publishing application, this might take a while  ... OK
➜  Deploying application ... OK        
➜  Waiting for application to start ... OK
➜  Visit your app on: https://codeigniter-tutorial.jekyo.app ... OK
```

You can now browse to your CodeIgniter app on https://codeigniter-tutorial.jekyo.app (replace 'codeigniter-tutorial' with your app name)

## 2. Deploying an existing CodeIgniter app

Navigate to your local CodeIgniter app directory

`cd my-codeigniter-app`

### Create a Procfile

In the root directory of your app, create a file named `Procfile` (no extension), and add the following line:

```
web: vendor/bin/heroku-php-apache2 public/
```

This will start the app in production mode using Apache. 

### Commit changes

```
git add Procfile
git commit -m "your commit message"
```
If you are not in a git repository, please run: 

```
git init
git add .
git commit -m "your commit message"
```

### Create an empty Jekyo app:

`jekyo create` 

Select 'none' using the **arrows** on your keyboard and press **enter**. This will create an app using your current directory. 

```
? Select template (Use arrow keys)
❯ None Creates an application from your current directory
```

Name your app: 

`Application name?: my-codeigniter-app`

Run `jekyo link` to link your local app to the remote Jekyo app. Select 'my-codeigniter-app' using the **arrows** on your keyboard and press **enter**.

```
? Select application (Use arrow keys)
❯ my-codeigniter-app
```
### Now you can deploy this app to Jekyo by running: 

`jekyo deploy`

After a while, you should see something like this:

```
➜  Fetching source code ... OK
➜  Building application, this might take a while ... OK
➜  Publishing application, this might take a while  ... OK
➜  Deploying application ... OK        
➜  Waiting for application to start ... OK
➜  Visit your app on: https://my-codeigniter-app.jekyo.app ... OK
```

You can now browse to your CodeIgniter app on https://my-codeigniter-app.jekyo.app (replace 'my-codeigniter-app' with your app name)

## Pushing local changes to Jekyo 

Add the newly modified file(s) to the git index by using [git add](https://www.atlassian.com/git/tutorials/saving-changes)

`git add filename`

Create a [git commit](https://github.com/git-guides/git-commit)

`git commit -m "your commit message"`

Now, simply deploy your app again:

`jekyo deploy`

You will see your changes on your live app after a short while. 