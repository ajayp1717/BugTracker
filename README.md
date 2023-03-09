
[![NPM version](https://img.shields.io/badge/npm-6.13.6-brightgreen.svg)](https://www.npmjs.com/)
[![Node version](https://img.shields.io/badge/node-12.14.0-brightgreen.svg)](https://nodejs.org/)
[![Express version](https://img.shields.io/badge/express-~4.17.1-brightgreen.svg)](https://expressjs.com/)
[![React version](https://img.shields.io/badge/react-^16.12.0-brightgreen.svg)](https://reactjs.org/)
[![Mongo version](https://img.shields.io/badge/mongoDB-4.2.2-brightgreen.svg)](https://www.mongodb.com/try/download/enterprise)


After populating all enviroment variables, your resultant file will look something like this
```
# node application environment development,testing,staging,production
NODE_ENV=development

# mongodb database url
MONGODB_URI=mongodb://localhost:27017/tipoff
# mongodb database url to be used when running tests
MONGODB_URI_TEST=mongodb://localhost:27017/test-tipoff

# port number at which app will listen
# this is not required when deploying on heroku. the app will default to process.env.PORT for heroku
TIPOFF_API_PORT=5000

# secret key used to sign and validate auth token
JWT_SECRET_KEY=mysecretkey

#SendGrid API key to notify of new tips via email
NOTIFIER_API_KEY_SENDGRID=mysendgridapikey
#SendGrid From email to use when sending out email notifications
NOTIFIER_FROM_EMAIL_SENDGRID=no-reply@myapp.com
```
### Start Server
```
npm start
```


### Install and Run the UI to View Tips
1. In a new terminal tab or window, go to the Tipoff directory
2. drill down into **react-app** directory
```
cd react-app
```
3. Install the react application dependencies
```
npm install
```


Find the following line in tipoff/react-app/package.json
```json
"proxy":  "http://localhost:5000"
```
and change it to
```json
"proxy":  "http://localhost:<your_new_api_port>"
```
5. Start the react-app
Within the react-app directory, run 
```
npm start
```
You can now navigate to Tipoff UI at http://localhost:3000 or your own react-app port
