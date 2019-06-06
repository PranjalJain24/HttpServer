# HttpServer

HTTP(Hypertext Tranfer Protocol capacities as a request–response convention in the client–server processing model. A web program, for instance, might be the client and an application running on a PC facilitating a site might be the server.
HTTP basically has the below functions:
1- Listen for incoming http requests on a specific TCP socket address (IP address and a port number)
2- Handle this request and sends a response back to the user.

Python’s HTTPServer is the classic quick solution for serving the files in a directory via HTTP.
Notice that in Python 2, there was a module named SimpleHTTPServer. This module has been merged into http.server in Python 3.


### Installation
Clone the repository, then install the requirements and start the web server.
Downlaod required packages for HTTP Server using the below command:
#### pip install HTTPServer 

### Usage
To create an http web server in Python you can go by any of the program included. One is done using built-in libraries in python(httpServer_lib) and the other one is including the methods(httpServer_methods).
#### 1.httpServer_lib
We need to create a simple http server that serves a static html web page. Save that file as index.html in the same directory where you are doing to add the python file- httpServer_lib because by default the SimpleHTTPRequestHandler will look for a file named index.html in the current directory.
In order to create a web server in Python 3, you will need to import two modules: http.server and socketserver.
##### Handler = http.server.SimpleHTTPRequestHandler
This is a simple HTTP request handler that serves files from the current directory and any of its subdirectories.
##### socketserver.TCPServer(("", PORT), Handler)
To instantiate a TCP Server, we need two things: The TCP address (IP address and a port number) and The handler.
##### $ python httpServer_lib.py
##### serving at port 8080
By doing that, you now have an HTTP server that is listening on any interface at port 8080 waiting for incoming http requests. Open your browser and type localhost:8080 in the address bar.

#### 2.httpServer_methods
This program responds to GET, HEAD, POST requests.
##### _set_headers():
Sets or appends the value of a specified HTTP response header.
##### do_HEAD():
This method serves the 'HEAD' request type: it sends the headers it would send for the equivalent GET request.
##### do_GET():
Use GET requests to retrieve resource representation/information only – and not to modify it in any way. It should make multiple identical requests and must produce the same result every time until another API (POST or PUT) has changed the state of the resource on the server.
##### do_POST():
Use POST APIs to create new subordinate resources into the collection of resources.
##### do_PUT():
Use PUT APIs primarily to update existing resource (if the resource does not exist then API may decide to create a new resource or not).
##### do_PATCH():
HTTP PATCH requests are to make partial update on a resource. PATCH method is the correct choice for partially updating an existing resource and PUT should only be used if you’re replacing a resource in it's entirety.
##### do_DELETE():
As the name suggests, DELETE APIs are used to delete resources (identified by the Request-URI).
##### $ python httpServer_methods.py [port_number]
Running this command creates an HTTP server that is listening at the given port waiting for incoming http requests.
##### Run in browser http://127.0.0.1:[port_number]/ (Press CTRL+C to quit)

### HTTP - Status Codes
The Status-Code element in a server response, is a 3-digit integer where the first digit of the Status-Code defines the class of response and the last two digits do not have any categorization role. There are 5 values for the first digit:

#### 1xx Informational- It means the request has been received and the process is continuing.
100 Continue    101 Switching Protocols    102 Processing (WebDAV)
#### 2xx Success- It means the action was successfully received, understood, and accepted.
200 OK    201 Created    202 Accepted    203 Non-Authoritative Information    204 No Content    
#### 3xx Redirection- It means further action must be taken in order to complete the request.
300 Multiple Choices    301 Moved Permanently    302 Found    303 See Other    304 Not Modified
#### 4xx Client Error- It means the request contains incorrect syntax or cannot be fulfilled.
400 Bad Request    401 Unauthorized    402 Payment Required    403 Forbidden    404 Not Found    409 Conflict
#### 5xx Server Error- It means the server failed to fulfill an apparently valid request.
500 Internal Server Error    501 Not Implemented    502 Bad Gateway    503 Service Unavailable
