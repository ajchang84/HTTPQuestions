## HTTP Questions

__URLs__

* Name all of the parts of the url that you can remember.  In your own words describe what they do.

```
1) Protocol
defines the protocol to be used by the browser and other programs in order to interpret requests amongst servers. Usually that's Http:// and Https://

2) Domain 
that's the main address of the server you're requesting from, like the actual address to a building

3) Port 
it's different entry points to the server domain. Default is 80 and 443 for HTTP and HTTPs respectively. They may serve different purposes, like the front entrance of the building can be for guests while the back entrance is for employees.

4) Path 
it's the directory to the destination within the server domain, like going to the second floor, fifth room of a building.

5) Query
these are arguments that can be brought in as additional requests from the server.

6) Anchor Tag
these are specific positions on the resource or document

```

* Name the pieces of the following urls:
	* `https://www.google.com/`
	* `https://workbook.galvanize.com/cohorts/41/learning_experiences/367`
	* `http://locahost:5000/animals/puppies?onlycute=1&size=medium#firstpuppy`
	* `https://en.wikipedia.org/wiki/List_of_HTTP_status_codes#4xx_Client_Error`
	
```
	1) protocol/domain/path	(https://)(www.google.com)(/))
	2) protocol/domain/path (https://)(workbook.galvanize.com)(/cohorts/41/learning_experiences/367)
	3) protocol/domain/port/path/query/anchortag (http://)(locahost)(:5000)(/animals/puppies)(?onlycute=1&size=medium)(#firstpuppy)
	4) protocol/domain/path/anchortag	(https://)(en.wikipedia.org)(/wiki/List_of_HTTP_status_codes)(#4xx_Client_Error)

```	
	
* Can a server use more than 1 port?

```
Oh yeah
```

* Why is https different than http?

```
https is more secured; it will encrypt your requests
```

* How does a server interpret the following url's query paramter.  What data structure does it create on the server?

```
http://locahost:5000/animals?puppies=fido&puppies=max&puppies=moxie
```
```
It will be in an array due to the repeated puppies variable. Something like this:
puppies = [fide, max, moxie]
```

__HTTP Request/Response__

* Name at least 4 http verbs

```
GET POST PUT DELETE
```

* What is each verb useful for in your own words

```
GET: request resources from the server, like a webpage. GET is idempotent, it won't change the state on the server in any way

POST: requests information to be sent to the server and is usually NOT idempotent 

PUT: requests updating existing information on the server

DELETE: requests deletion of resources on the server
```

* What does idempotent mean?

```
it means that the state of the server will not change. this is associated with GET requests.
```

* Name the 5 http status code ranges.  What are they used for in general?

```
1xx: still running
2xx: okay
3xx: okay but redirected
4xx: client error, cannot be found
5xx: error 

These are the responses from the server for computers to interpret what went wrong

```

* If a server returns a http status code of 301 and a location of `https://www.google.com/`, what does the browser do?

```
it automatically redirects to the correct url of https://www.google.com/
```

* For the following HTTP headers, decide if the following header is used for requests, responses or both:
	* Accept `request`
	* Content-type `both`
	* User-agent `request`
	* Set-cookies `response`
	* Cache-control `both`
	* Cookie `request`
* Is the following a http request or response?  How do you know for each?

```
HTTP/1.1 200 OK
Access-Control-Allow-Origin: *
Vary: Accept
Content-Type: text/html; charset=utf-8
Content-Length: 722
ETag: W/"2d2-Wu0We9N5g35FXWY+gOATLA"
Date: Tue, 08 Mar 2016 20:37:11 GMT
Connection: keep-alive

<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <link rel="stylesheet" href="/style.css">
    <title>Student Roster</title>
  </head>
  <body>
    <main>
      <h1>Student Roster</h1>
      
        <section>
          <h3>Daenerys Targaryen</h3>
          <span>Student Id: nys8fbohl</span>
          <h4>Hobby: Motherhood</h4>
          <img src="https://i.imgur.com/KlycRG5.jpg" alt="Daenerys Targaryen" />
        </section>
      
        <section>
          <h3>Tyrion Lannister</h3>
          <span>Student Id: njehukbohe</span>
          <h4>Hobby: Traveling</h4>
          <img src="https://i.imgur.com/fFMusdC.png" alt="Tyrion Lannister" />
        </section>
      
    </main>
  </body>
</html>
```
`^response`

```
DELETE /students/n1vmyrw3x HTTP/1.1
Host: g22-students.herokuapp.com
Accept: application/json
Cache-Control: no-cache
Postman-Token: 0041e3c3-efdb-f0c3-b2f4-2d79f6d0f44b
```
`^request`

__JSON__

* Describe what JSON is.  What is it used for.

```
JSON is the format used to exchange readable data between servers/clients. It is language independent and is in the format of a string that may represent array or objects.
```

* Convert the following map into a javascript object then console log the age.

```
{ "company" : "Github", "age": 7, "categories" : "Services,Internet,Software"}
```

```javascript
var myObj = JSON.parse('{ "company" : "Github", "age": 7, "categories" : "Services,Internet,Software"}');
console.log(myObj.age);
```

* Convert the following to a javascript object.  Console log each company name.

```
{ "Companies":[ { "company": "Github", "age": 7, "categories": "Services,Internet,Software"},
              { "company": "Airbnb", "age": 6, "categories": "Hotels,Travel"},
              { "company": "Square", "age": 7, "categories": "FinTech,Hardware + Software,Finance"},
              { "company": "Dropbox", "age": 11, "categories": "Cloud Data Services,Storage,Web Hosting"}
            ]
}
```

```
var myObj = JSON.parse('{"Companies": [ {"company": "Github", "age": 7, "categories": "Services,Internet,Software"},{ "company": "Airbnb", "age": 6, "categories": "Hotels,Travel"},{ "company": "Square", "age": 7, "categories": "FinTech,Hardware + Software,Finance"},{ "company": "Dropbox", "age": 11, "categories": "Cloud Data Services,Storage,Web Hosting"}]}');

myObj.Companies.forEach(function(c){
    console.log(c.company);
});
```

* The following is javascript.  Convert the object to a string and console log it.

```
var myObj = {
  company: "Galvanize",
  age: 3,
  categories: "Education"
};
```

```
var myObj = {
  company: "Galvanize",
  age: 3,
  categories: "Education"
};

console.log(JSON.stringify(myObj));
```


__MISC__

* Describe what DNS is.

```
Domain Name System are servers that act as a phonebook for domain names to be interpreted into IP addresses.
```
* In the terminal, type `man curl`.  Look at the man page for curl.  What do the following flags do? `-v`, `-X`.  (Hint: to search for a string, type `/` then the text you want, then enter.  To quit the man page, type `q`).

```
-v flag means verbose, making the header data more clear during curl operation
-X flag means request, which specifies that a request method is to be used to communicate with the server, usually followed by a HTTP verb
```

* What is TCP/IP?  How does it interact with HTTP?

```
TCP is Transmission Control Protocol and is responsible for ensuring data will go to and from the server, retransmitting even if it fails. It also breaks large data into smaller chunks.
IP is Internet Protocol and is responsible for making sure that data goes to the correct place through IP addresses.
```
* Does HTTP break the data that is being sent into small packets?  If not, what protocol is responsible for it?

```
No, HTTP is responsible for servers to issue requests with one another. It is TCP that breaks data into small packets.
```

