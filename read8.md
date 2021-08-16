## RESTFULL web API design

![](https://blog.crowdbotics.com/content/images/2020/06/RESTapiFeaturedImage.png)

### What is REST?

***In 2000, Roy Fielding proposed Representational State Transfer (REST) as an architectural approach to designing web services.***


### REST APIs design

REST APIs are designed around resources.


### What is an identifer of a resource?

***A resource has an identifier, which is a URI that uniquely identifies that resource. For example, the URI for a particular customer order might be:***

**HTTP**


* `https://adventure-works.com/orders/1`


### What are the most common HTTP verbs?

***For REST APIs built on HTTP, the uniform interface includes using standard HTTP verbs to perform operations on resources. The most common operations are GET, POST, PUT, PATCH, and DELETE.***


### What should the URIs be based on?


***The HTTP response indicates whether the order was placed successfully or not. When possible, resource URIs should be based on nouns (the resource) and not verbs (the operations on the resource).***

### Give an example of a good URI.


`https://adventure-works.com/orders // Good`



### What does it mean to have a ‘chatty’ web API? Is this a good or a bad thing?

***Therefore, try to avoid `"chatty"` web APIs that expose a large number of small resources. Such an API may require a client application to send multiple requests to find all of the data that it requires.***

### What status code does a successful GET request return?


***A successful GET method typically returns HTTP status `code 200` (OK).***

### What status code does an unsuccessful GET request return?

`HTTP status code 406`


### What status code does a successful POST request return?

***If a POST method creates a new resource, it returns HTTP status `code 201` (Created).***



### What status code does a successful DELETE request return?

***If the delete operation is successful, the web server should respond with HTTP status `code 204` (No Content)***

