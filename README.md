
# MyApp 

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 9.1.0 and it lists the basic steps to install , build and deploy Angular app in Gitlab 
The app can be accessed in https://saidev1990.gitlab.io/my-angular-app-devops/

## Set up and install 

Run the below command to switch to root user for installing Angular CLI

`sudo su`

Install Angular CLI (latest release) with the below command 

`npm install -g @angular/cli`

Check the version of Angular cli using the below command 

`ng --version`

Initialise git repo 

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.

## Development server with port 

Run `ng serve` for a dev server at a particular port. Navigate to `http://localhost:8080/`. The app will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

## Changes in angular.json

Specify in angular.json to push the artifacts to public directory using output path otherwise gitlab won't work

 ` "outputPath": "public",` 

## Changes in package.json

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory. Use the `--prod` flag for a production build.
Use `base-href` for defining a reference URL for the Angular app . 

`"buildProd": "ng build --base-href=/my-angular-app-devops/"`

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via [Protractor](http://www.protractortest.org/).

## Creating npm scripts 

npm scripts can be created and placed in scripts section package.json 

    "ng": "ng",
    "start": "ng serve",
    "build": "ng build",
    "test": "ng test",
    "lint": "ng lint",
    "e2e": "ng e2e",
    "buildProd": "ng build --base-href=/my-angular-app-devops/"

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI README](https://github.com/angular/angular-cli/blob/master/README.md).

## gitlab ci commands and screenshots 

### images 

Share the required image to run the app . For ex : The Angular app needs Node JS Runtime version of 12.0 

`image: node:12.0`

### page cache paths 

This is the caching for our node_modules directory so we don’t have to build it every time we do a deploy.

`pages:`
  `cache:`
    `paths:`
      `- node_modules/`

### npm scripts 

This lists the npm commands that's required to run the Angular app 

  `script:`
    `- npm install -g @angular/cli@9.1.0`
    `- npm install`
    `- npm run buildProd`

### Path of artifacts 

This lists the path of artifacts in which it is deployed . Note : public directory is preferred when deploying in gitlab 

 `artifacts:`
    `paths:`
      `- public`

### List branches 

This lists the branches that can be deployed apart from Master . For ex: I have listed a pages branches that can be deployed while running CI apart from Master 

 `only:`
    `- master`
    `- pages`
    
    
### Screenshot for checking path of Angular app to access 




### Screenshot for viewing the Angular app
    





