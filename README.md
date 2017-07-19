Hapi Route Configuration
===============

Once you set up a running Hapi server, you are then able to define routes using a method off of the instance of the `Hapi.Server()` called `route`.

```
const Hapi = require('hapi');
const server = new Hapi.Server();

server.route({
	
})
```

---

## Methods

The `route` method from an instance of a Hapi server has the following basic elements: `method`, `path`, `handler`, and `config`

### method
---
The `method` element of the route takes in various valid HTTP methods, or even an array of methods such as `GET`, `POST`, and `DELETE`. This will define the method of HTTP request that you will called upon the `path` element of the server.

```
server.route({
	method: 'GET'
})
```
#### OR
```
server.route({
	method: ['GET', 'POST']
})
```


### path
---
The `path` element of your route provides the location in which the the HTTP method will be called upon. Although the path location is a string, you may also pass in parameters to create a dynamic path using `{}`.

```
server.route({
	method: 'GET',
	path: '/helloWorld'
})
```

Passing in a parameter would look like:

```
server.route({
	method: 'GET',
	path: 'users/{userName}'
})
```


### handler
---
Finally, the `handler` method of your route will be using a function where the logic of your HTTP call is defined.

```
server.route({
	method: 'GET',
	path: '/helloWorld',
	handler: function(request, reply){
		reply('Hello World!')
	}
})
```



### config
---


