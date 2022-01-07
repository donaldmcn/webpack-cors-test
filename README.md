This project reproduces an issue with webpack-dev-server 4.5.0 and above where content being served from the \public folder does not work with CORS, because the HTTP OPTIONS requeset returns a 404.

OPTIONS request work with webpack-dev-server 3.11.3.

To see this:

* set the webpack-dev-server version in package.json to ^3.11.3
* copy the content of webpack.config.3.11 into webpack.config.js
* yarn install
* yarn start

Send the following request: OPTIONS http://localhost:9000/logo192.png
The response will be a 200 OK, and the body will contain GET,HEAD

OPTIONS requests will fail with webpack-dev-server 4.5.0 (and above.)

To see this:

* set the webpack-dev-server version in package.json to ^4.5.0
* copy the content of webpack.config.4.5 into webpack.config.js
* yarn install
* yarn start

Send the following request: OPTIONS http://localhost:9000/logo192.png
The response will be a 404.
