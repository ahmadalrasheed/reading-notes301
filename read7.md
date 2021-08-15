## Explain REST
![](https://i1.wp.com/www.burning-glass.com/wp-content/uploads/coding_400x267-1.jpg?fit=400%2C267&ssl=1)
### Who is Roy Fielding?

***Some guy. He's smart. He helped write the first web servers, that sent documents across the internet… and then he did a ton of research explaining why the web works the way it does. His name is on the specification for the protocol that is used to get pages from servers to your browser.***

### Why don’t the techniques that we use today work well when we need to be able to talk to all of the machines in the world?

***Machines don't have a universal noun - that's why they suck. Every programming language, database, or other kind of system has a different way of talking about nouns. That's why the URL is so important. It let's all of these systems tell each other about each other's nouns.***

### What is the HTTP protocol that Fielding and his friends created?
***The protocol I mentioned, that he helped write, HTTP, it's capable of all sorts of neat stuff that people ignore for some reason, That first part tells the browser what protocol to use. That stuff you type in there is one of the most important breakthroughs in the history of computing.it is capable of describing the location of something anywhere in the world from anywhere in the world. It's the foundation of the web. You can think of it like GPS coordinates for knowledge and information.***
### What does a GET do?
***So anyway, HTTP—this protocol Fielding and his friends created—is all about applying verbs to nouns. For instance, when you go to a web page, the browser does an HTTP GET on the URL you typed in and back comes a web page.***

***Web pages usually have images, right? Those are separate resources. The web page just specifies the URLs to the images and the browser goes and does more GETs using the HTTP protocol on them until all the resources are obtained and the web page is displayed. But the important thing here is that very different kinds of nouns can be treated the same. Whether the noun is an image, text, video, an mp3, a slideshow, whatever. I can GET all of those things the same way given a URL.***

### What does a POST do?

***If one system needs to add something to another system, it would use an HTTP verb of POST.***

### What does PUT do?
***If a system wants to replace something in another system, it uses an HTTP verb of PUT***

### What does PATCH do?

***to do a partial update, it uses an HTTP verb of PATCH.***


