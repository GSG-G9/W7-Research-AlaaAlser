# Session-management in Express

## What is a "Session" ?
The session is a server-side storage  (unlike cookies which a clint side) of information  that is desired to persist throughout the user's interaction with the web site or web application.

Because Express requests are independent and each request don't know what was the previous request for the same user.
Users cannot be identified unless using some kind of mechanism that makes it possible.
That’s what sessions are.

Instead of storing large and constantly changing information via cookies in the user's browser, only a unique identifier is stored on the client side (called a "session id"). This session id is passed to the web server every time the browser makes an HTTP request. The web application pairs this session id with it's internal database and retrieves the stored variables for use by the requested page.

## What are the different ways of managing sessions in express?

There are two way to manage cookies in express
1. Cookie-session
2. Express-session

## **Cookie-session module** :
* This is npm module  stores the session data on the client within a cookie.

## **Express-session module** :
* Express-session stores only a session ID on the client within a cookie and stores the session data on the server, it supports different session stores (like files, DB, cache and whatnot). 


## An example of how to set up a session :

Install express-session npm
```
$ npm install express-session
```

---
Required
```
var session = require('express-session')
```
### example 

```
app.set('trust proxy', 1) // trust first proxy
app.use(session({
  secret: 'name',
  resave: false,
  saveUninitialized: true,
  cookie: { secure: true }
}))