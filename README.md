# node-mongo-esm-kit

![contributions welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg?style=flat) ![License: ISC](https://img.shields.io/badge/License-ISC-blue.svg) ![GitHub issues](https://img.shields.io/github/issues/code-collabo/node-mongo-cli?color=red) ![GitHub pull requests](https://img.shields.io/github/issues-pr/code-collabo/node-mongo-esm-kit?color=goldenrod) 

<!--
![GitHub all releases](https://img.shields.io/github/downloads/code-collabo/node-mongo-esm-kit/total?color=green)
-->


The **node-mongo-esm-kit** is the ES Module (esm) boilerplate template, from the 3 boilerplate templates to be generated by the node-mongo-cli, for nodejs and/or mongoDB development. Here is the list of all 3 templates to choose from:
- [ES module template](https://github.com/code-collabo/node-mongo-esm-kit)
- [Commonjs template](https://github.com/code-collabo/node-mongo-cjs-kit)
- Typescript (coming soon)

## Installation
Download the template locally unto your computer through the [node-mongo-cli](https://github.com/code-collabo/node-mongo-cli). The CLI is built to provide better experience, but you can also clone or download it manually. In the case where you are having issues using the CLI, download the template from github. Report issues in [the issues tab of the node-mongo-cli repo](https://github.com/code-collabo/node-mongo-cli/issues).

Change directory (cd) into the root of the downloaded template and install dependencies:
````
npm install
````

Start server and mongoDB connection:
````
npm start
````
**Note:** Incase you see an error message in the terminal, the next sections will guide you on how to set up your mongoDB connection successfully.

## MongoDB connection options
There are two monogoDB connection options already setup for you to choose from:
1. Connection to MongoDB installed on your computer
2. Connection to MongoDB atlas

In the case where the error message "Error in DB connection" is displayed in the terminal when you start the server, you need to either install and get mongoDB running for use locally on your computer or setup mongoDB atlas. Once you have done any of these, the message "Installed MongoDB connection successful!!!" or "MongoDB ATLAS connection successful!!!" should now show up in the terminal. More notes in the sections that explain the mongoDB connection options individually. [Visit this link to install mongoDB](https://docs.mongodb.com/guides/server/install/) on your computer and get mongoDB running if you haven't. [Or choose to use mongoDB atlas](https://docs.atlas.mongodb.com/getting-started/) and connect to your cluster.

## Installed mongoDB option
Create a .env file in the root of the downloaded template. After installing mongoDB, keep mongoDB running in the terminal(s) as shown in the mongoDB doc. Create a database and give it any name of your choice. Go to src/db.js file, you will see that there is a DBNAME environment variable i.e. `process.env.DBNAME` in the mongoDB connection string. You want to store the database name that you created in this variable. Store your database name in the variable inside the .env file you created earlier like so:
````
DBNAME="insert-your-own-db-name-here"
````
You can add other environment variables if you like, but this tutorial is going to stick to this simple setup. Also create a collection. You can use the collection name `demo` from the src/api/models/demo.js file while you follow this tutorial. You can always use a different name later on once you get used to how the template is setup. In the src/app.js file, you will find the import named "mongooseModuleExport" which is what you need. If you ever need to use the mongoDB atlas option, then you will need to comment out mongooseModuleExport and remove comment from "mongooseModuleExportAtlas" so that you can access the db connection set up for atlas instead. Since you have chosen to install mongoDB locally on your computer, use the mongooseModuleExport import. So you don't need to change anything in the src/app.js file. Open up http://localhost:3000 in the browser to see the message `App works` displayed on the screen. Also see http://localhost:3000/demo for items in your demo collection. Count should be zero and items should be an empty array since you have not added anything in the database.

## MongoDB atlas option
Create a .env file in the root of the downloaded template. Create a database (and collection) and connect to your cluster following the mongoDB doc. Go to src/atlas/db.js file, you will see that there are environment variables i.e. `process.env.USERNAME`, `process.env.PASSWORD`, `process.env.CLUSTERNAME`, `process.env.DBNAME` in the mongoDB connection string. You want to store your username, password, cluster name and database name that you created with atlas inside these variables. Store your database name in the variable inside the .env file you created earlier like so:
````
DBNAME="insert-your-own-db-name-here"
USERNAME="insert-your-own-username-here"
PASSWORD="insert-your-own-password-here"
CLUSTERNAME="insert-your-own-clustername-here"
````
Use the collection name `demo` from the src/api/models/demo.js file while you follow this tutorial. You can always use a different name later on once you get used to how the template is setup. In the src/app.js file, you will find the import named "mongooseModuleExportAtlas" which is what you need but is commented out. Comment out "mongooseModuleExport" and remove comment frommongooseModuleExportAtlas so that you can access the db connection set up for atlas instead.
If you ever need to use the installed mongoDB option, then you will need to comment out mongooseModuleExportAtlas and remove comment from mongooseModuleExport so that you can access the db connection setup for the installed mongoDB option. Open up http://localhost:3000 in the browser to see the message "App works" displayed on the screen. Also see http://localhost:3000/demo for items in your demo collection. Count should be zero and items should be an empty array since you have not added anything in the database.

## Interacting with database
You can use postman or any other tool to add data or remove data from the database. To make it easy to test that all is well setup and also to show example usage of the template with a client app in development, you can download the [node-mongo-demo-app](https://github.com/code-collabo/node-mongo-demo-app).

Change directory (cd) into the root of the demo app and install dependencies:
````
npm install
````

Start the app:
````
npm start
````
View the demo app in the browser at http://localhost:4200. Although the app is built with angular, you don't need to have any knowledge of how to write an angular application. Just interact with form supplying name and age (these have been configured in the template's src/api/ folder). Make sure to keep port 3000 still running. You will see your entries in a table under the form. You can also always refresh your browser for http://localhost:3000/demo to see that the changes you made are now returned as json and are in the database. 

## Customizing dev environment

Replace `insert-your-project-name` with your own project name in the src/startMessage.js file. Modify template as you like it.

 
<!--
## Technologies

[<img alt="javascript" height="25px" src="https://www.freepnglogos.com/uploads/javascript/javascript-online-logo-for-website-0.png" />](https://github.com/code-collabo/node-mongo-cli)
[<img alt="node js" height="25px" src="https://nodejs.org/static/images/logos/nodejs-new-pantone-black.svg" />](https://github.com/code-collabo/node-mongo-cli)
[<img alt="mongoDB" height="25px" src="https://webassets.mongodb.com/_com_assets/cms/MongoDB_Logo_FullColorBlack_RGB-4td3yuxzjs.png" />](https://github.com/code-collabo/node-mongo-cli)
-->
