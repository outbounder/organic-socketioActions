# organel | 

The Organelle is responsible for mounting Web Socket Message Handlers to the socketio wrapped by WebSocketServer organelle or any other implementation providing the same interface.

* `mount`: String

  *optional* value to be used for prefixing all routes. Useful for mounting all actions found to specific root url

* `cwd`: Object

  * optional * , Object containing key:value pairs, where all values will be prefixed with `process.cwd()` and set with their coressponding keys directly to the DNA of the organelle.

* `actions`: String

  provided full path to directory containing `actions` defined within javascript files with the following source code definition:

        module.exports = function(config) {
          return {
            "*": function(data, callback, socket) {},
            "GET": function(data, callback, socket) {},
            "POST": function(data, callback, socket) {},
            "PUT": function(data, callback, socket) {},
            "DELETE": function(data, callback, socket) {},
            "OPTIONS": function(data, callback, socket) {},
          }
        }

* `log`: false

  will print any found action routes to the stdout

# incoming | WebSocketServer

* data - WebSocketServer instance