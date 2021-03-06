

## Purpose

1. Rapidly search device names and model numbers
2. It also helps in finding out current MCP device testing status
3. You can export the out come in PDF, excel or csv files


## Developer instruction

 Clone this repository

```
$ git clone git@github.com:HarishRam/MCPDashboard.git
$ npm install
```
 Configure dev cert in the application to run locally

```
In the following file update the code snippet : public->javascript->datafeature.js

var cert = fs.readFileSync(process.env.CERT);

and

Replace "strictSSL : true" to use "cert: cert, key: cert, passphrase: process.env.PHRASE, securityOptions: 'SSL_OP_NO_SSLv3'"

In the command line :

$ export CERT=<path of your self signed pem file>
$ export PHRASE=<your cert phrase>
```

## To start server
```
$ npm start
```

Default port=1344, to change
```
export PORT=<your port number>

$ npm start
```
This is will generate error logs (i.e err.log) and output logs (i.e out.log)

Now you can access MCP Dashboard application through [http://localhost:1344/jira](http://localhost:1344/jira)


## To stop the server

```
$ npm stop

```

## Cache for 12hours

On first user request the response will be stored in cache, so until 12hours every response will be from cache.
To clear the cache [http://localhost:1344/clearCache]

