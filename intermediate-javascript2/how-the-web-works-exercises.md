# { HOW THE WEB WORKS EXERCISESS. }

## How The Web Works Exercise
Answer the following questions. Write out your answers in atext or markdown file.

1. What is HTTP?
### ans: The Hyper Text Transfer Protocol is a client-server protocol which allows the client to get data from the server or set data on the server.

2. What is a URL?
### ans: A Uniform Resource Locator (also called web address) is a reference to a web resource that specifies its location on a computer network and a mechanism for retrieving it.

3. What is TCP?
### ans: The Transmission Control Protocol provides reliable, ordered, and error-checked delivery of a stream of data between applications running on hosts communicating via an IP network.

4. What is IP?
### ans: The Internet Protocol (IP) is the protocol that governs how data is sent across a network from one computer to another.

5. What is DNS?
### ans: Domain Name System is a server that takes a domain as input and returns an IP address as output

6. What is idempotent?
### ans: Idempotent refers to an operation that can be repeated many times on a set of data and the state of the set of data will not change.

7. What is a query string?
### ans: A query string is simply a collection of parameters, which are a list of key and value pairs.

8. What is a path or route?
### ans: A path may relate to a file that the web server has in its hard drive or an abstract resource that the web server is able to create, read update or delete.

9. List four HTTP Verbs and their use cases.
### ans:
### 1. GET: for getting data from server
### 2. POST: for creating data on the server
### 3. PUT: for modifying existing data on the server
### 4. DELETE: for deleting data from the server

10. What is a client?
### ans: This an and user device (e.g. phone, computer) that is used to request for resources on the internet.

11. What is a server?
### ans: This a device (mostly computers) where resources are stored and shared upon request from client.
12. What is an HTTP request?
### ans: HTTP request are communications on the internet issued by a clients (or servers) to other servers.

13. What is an HTTP response?
### ans: HTTP response are communications on the internet issued by servers to the originator of any request.

14. What is an HTTP header? Give a couple examples of request and response headers you have seen.
### ans: HTTP header is simply more information about a particular HTTP request or response.
### Example of HTTP request headers: accept-encoding, accept-language, user-agent
### Example of HTTP response headers: Content-Type, Transfer-Encoding, X-Xss-Protection

15. What is REST?
### ans: Representaional State Transfer is an architectural style for an application program interface (API) that uses HTTP requests to access and use data. Some of the constraints governing it include:
### 1. It must be stateless.
### 2. It should be designed to encourage the storage of cacheable data
### 3. This interface should provide an unchanging, standardized means of communicating between the client and the server.

16. What is JSON?
### ans: JavaScript Object Notation is a lightweight format for storing and transporting data commonly used when sending data from server to web page

17. What happens when you type in "Hello World" in google.com and press enter?
### ans: 
### 1. The browser will still first the get the ip address from the domain name (in this case google.com) with the help of a domain name server, then make a connection.
### 2. The browser will then make an HTTP GET request that contains the query string of "Hello World" as well as other parameters in the path
### 3. The google.com server receives the GET request and generates the appropriate HTML page.
### 4. The HTML page is sent back to me via a HTTP response message, which contains a status code and a response body (the html page to be rendered) and a the DOM is created
### 5. As the DOM is being created, other resources (css, script, images) needed for page load the page will also be requested for.

18. What does it mean when we say the web is "stateless"?
### ans: It means the web does not record of previous interactions and each interaction request has to be handled based entirely on the information that comes with it. 
19. What is curl?
### ans: curl  is  a tool to transfer data from or to a server, using one of the supported protocols. The command is designed to work without user interaction.


20. Make a GET request to the icanhazdadjoke API with curl to find all jokes involving the word "pirate." (your answer should be the curl command required).
### ans: curl -H "User-Agent: https://github.com/mojeedkusimo" -H "Accept: application/json" https://icanhazdadjoke.com/search?term=pirate
### ans:
```
{
    curl -H "User-Agent: https://github.com/mojeedkusimo" -H "Accept: application/json" https://icanhazdadjoke.com/search?term=pirate
}
```