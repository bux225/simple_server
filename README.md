This is a simple node.js server.  Here's how it was created from scratch

1. mkdir simple_server
2. cd simple_server
3. npm_init
4. fill out the package.json info
5. npm i http-status-codes -S   installs needed node_modules
6. make a main.js file
7. copy the following code into main.js
*/
const port = 3000,
  http = require( 'http' ),
  httpStatus = require( 'http-status-codes' ),
  app = http.createServer( ( request, response ) => {
    console.log( 'Received an incoming request!' );
    response.writeHead( httpStatus.OK, {
      'Content-Type': 'text/html'
    } );

    let responseMessage = '<h1>Hello, Universe!</h1>';
    response.write( responseMessage );
    response.end();
    console.log( `Sent a response : ${responseMessage}` );
  } );

app.listen( port );
  console.log( `The server has started and is listening on port number: ${port}` );
/*
8. add a .gitignore file in main directory
9. add node_modules/ to .gitignore
10. in terminal, run node main to started
11. open browser to localhost:3000
12. should see "Hello, Universe"
