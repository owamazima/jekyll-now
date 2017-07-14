---
published: true
---

<span style="color:red"> *An API Endpoint for UTAMU Students Results Query and Access*</span>
### _Introduction_
<div style="text-align: justify"> _In computer programming, an Application Programming Interface (API) is a set of subroutine definitions, protocols, and tools for building application software. In general terms, it is a set of clearly defined methods of communication between various software components. A good API makes it easier to develop a computer program by providing all the building blocks, which are then put together by the programmer. An API may be for a web-based system, operating system, database system, computer hardware or software library. An API specification can take many forms, but often includes specifications for routines, data structures, object classes, variables or remote calls. POSIX, Microsoft Windows API, the C++Standard Template Library and Java APIs are examples of different forms of APIs. Documentation for the API is usually provided to facilitate usage_.</div>

### _A Guide to Designing and Building RESTful Web Service for Students Results Query and Access_
<div style="text-align: justify"> From the point of view of REST, a “real” Web service is a service designed to embrace the “Web” from the ground up. The Web has become the most successful distributed computing platform ever developed, thanks to years of investment and widespread usage. The Web platform includes concepts that you’re probably already familiar with like URIs, HTTP, and common data formats like XML, RSS/ATOM, and JSON. Ultimately, services that embrace these core concepts will immediately derive the valuable benefits they provide.
REST defines an architectural style based on a set of constraints for building things the “Web” way. REST is not tied to any particular technology or platform – it’s simply a way to design things to work like the Web. People often refer to services that follow this philosophy as “RESTful services.” In this blog, i covered  the fundamental REST design principles and considerations show you how to build RESTful services for Students Results Query and Access with Windows Communication Foundation (WCF), the WCF REST Starter Kit, and ADO.NET Data Services. </div>

### _The Web Platform_
<div style="text-align: justify">Before immersing ourselves in the world of REST, we should review the essence of the Web platform as we know it today. We call it the “Web” because the architecture provides a framework for creating and navigating a Web of resources. A resource could be anything. Some resources are simply data like files, images, or videos while others are temporal services that produce dynamic output (e.g., Pluralsight’s upcoming course schedule). Some services even run complex algorithms behind the scenes. You can think of the Web as a resource-oriented architecture for building large-scale distributed systems.</div>

### _Resource-Oriented Architecture_
<div style="text-align: justify">On the Web, every resource is given a unique identifier, also known as a universal resource identifier (URI). The most common type of URI used on the Web today is a uniform resource locator (URL). As an example, the URL – http://www.pluralsight.com/main/ilt/schedule.aspx – identifies and locates Pluralsight’s upcoming training course schedule, a popular resource made available on our site.
Since a given URI uniquely identifies a resource, it can be saved for future use and shared with others. For example, when you find a resource you want to get back to later, you can: try to remember it, write it down on a napkin, save it to disk (as a browser bookmark), or store it in a database of bookmarks on the Web, in which case the bookmark itself becomes a new Web resource. You can also share the resource with others by telling them the URI or emailing it to them so they can easily browse to it themselves. Many companies try hard to create easy-to-remember URIs that can be successfully conveyed via advertising and will hopefully spread via word-of-mouth. In the end, as long as you have the URI, you can enter it into a Web browser and retrieve the resource at some future point in time.
Now, the reason it’s called the “Web” is because resources can contain hyperlinks  to other resources, thereby creating a Web of resources. Hyperlinks make it possible to navigate from one resource to another by using the target resource URI. For example, in HTML you link to another resource through the anchor element. When a browser renders an anchor element, it provides a visual cue showing that you can click on the anchor text to issue a GET request for the target resource URI. Humans-in this case UTAMU students will play an important role in most Web applications because they’re the ones viewing the page, entering data in forms, and clicking links. Humans-(UTAMU Students) are really the client-side engine navigating the Web of resources.
When you retrieve a resource using a Web browser, you’re really retrieving a representation of that resource. This implies that there could be multiple representations of a particular resource. There are many standard and common formats used on the Web today to represent resources that virtually all browsers understand. One of the most common formats is (X)HTML but others are common as well, including JPEG and GIF, WMV and SWF, RSS and ATOM, CSS and JavaScript/JSON to name a few. When a browser receives one of these representations, it does its best to render it for human viewing.</div>

### _Fundamental HTTP Concepts_
<div style="text-align: justify">The Web platform also comes with a standard communication protocol – HTTP – for interacting with resources and their representations.  HTTP defines a standard set of methods, status codes, and headers for interacting with resources on the Web. Figure 1 describes the most commonly used HTTP methods, their semantics, and whether they’re defined to be safe and idempotent .
The GET method allows you to retrieve a resource representation, while PUT allows you to create or update a resource with the supplied representation, and DELETE allows you to delete a resource. In short, GET, PUT, and DELETE provide basic CRUD operations (create, retrieve, update, and delete) for the Web. HEAD and OPTIONS, on the other hand, provide the ability to retrieve resource metadata, allowing you to discover out how to interact with resources at run time.
Say we have a resource representing a course description at Pluralsight. You’d issue a GET request to retrieve the course description from a particular URI. If you wanted to update the course description with some changes, you’d issue a PUT request to the same URI supplying the modified course description. If you PUT the course description to a new URI, you’d effectively be creating a new course description resource. And, of course, you’d delete a course description by issuing a DELETE request.</div>

Method | Description |Safe |Idempotent
------------ | -------------
GET | Requests a specific representation of a resource|Yes|Yes
PUT | Create or update a resource with the supplied representation|No|Yes
DELETE | Deletes the specified resource|No|Yes
POST | Submits data to be processed by the identified resource|No|No

### _REST Defined_
<div style="text-align: justify">While REST seems to be growing in popularity these days, it’s a term that seems to mean different things to different people. The official definition for REST is defined in Chapter 5 of Roy Fielding’s PhD dissertation entitled Architectural Styles and the Design of Network-based Software Architectures.
Roy Fielding was one of the authors of the URI and HTTP specifications, which sit at the heart of the Web. Chapter 5 of his dissertation, entitled Representational State Transfer (REST), attempts to codify the architectural style and design constraints that make the Web what it is. REST emphasizes things like separation of concerns and layers, statelessness, and caching, which are common in many distributed architectures because of the benefits they provide. These benefits include interoperability, independent evolution, interception, improved scalability, efficiency, and overall performance.
However, the key design constraint that sets REST apart from other distributed architectural styles is its emphasis on a uniform interface between components. The theory is that generalizing and standardizing the component interface will ultimately simplify the overall system architecture and provide more visibility into the various interactions. REST further defines how to use the uniform interface through additional constraints around how to identify resources, how to manipulate resources through representations, and how to include metadata that make messages self-describing.
When something conforms to these REST design constraints, we commonly refer to it as “RESTful” – a term that I casually use throughout this whitepaper. The Web is indeed RESTful. The Web was built on HTTP’s uniform interface (the methods described in Figure 1) and the focus is on interacting with resources and their representations. Although in theory REST isn’t tied to any specific platform or technology, the Web is the only major platform that fully embodies REST today. So, in practical terms, if you’re going to build something that’s RESTful today, you’ll probably do it on the Web using HTTP.
Uniform Interface
Some argue that generalizing the component interface limits the capabilities of the system, but this is simply not true. There is great power in the simplicity of a uniform interface because of the value it adds at larger scales. The REST model is Turing-complete and can be used to implement complex systems.
A comparison might help explain how this is possible – let’s consider the popular LEGO®  building blocks as an example.   If you’ve played with LEGO® products before, you know there are only a few ways to connect them together, which represents the LEGO® uniform interface. All LEGO® products, regardless of when or where you buy them, can connect with one another through its uniform interface. When new LEGO® products are released, they can be incorporated into existing LEGO® systems and the user doesn’t have to learn anything new. The new components work just like all other LEGO® products.
You might wonder if the limited number of connection possibilities will constrain what you’re able to build with LEGO® products. But if you’ve ever been to LEGOLAND®, you’ll know it doesn’t. You’ll find some incredibly complex objects at LEGOLAND® – including replicas of cars, buildings, even dinosaurs – which were all built from a variety of LEGO® products, connected through the LEGO® uniform interface.
HTTP defines a similar model for the Web. The various methods defined by the HTTP specification (see Figure 1) provide a uniform interface for interacting with resources on the Web. All Web browsers, servers, intermediaries, and custom applications understand this uniform interface and the semantics of each operation. This allows them to connect to one another and exchange information without issues, despite platform and technology differences. And new Web components can be added at any time without causing disruption or requiring changes to the other components already in existence.
The idea of a uniform interface is often hard to accept for many developers, especially those who are used to working with RPC-based component technologies. With RPC, every new component introduces a new interface – a new set of methods – for accessing the component’s functionality. Hence, the component developer is focused on designing and implementing methods, and therefore, new application protocols. It’s been this way for years, and few technologies move away from this trend.
Before clients can take advantage of a new component, they must learn the intricacies of the new interface (application protocol) and the semantics of each operation. Ultimately, as the number of interfaces increases, so does the overall complexity of the system. This complexity can become unwieldy to manage over time and often leads to brittle systems that can’t cope with versioning and change.
A system built around a uniform interface for communication provides stability because it rarely changes and there are only a few methods for everyone to learn. Applications using a uniform interface are free to change at any time while the communication methods connecting them remain stable over time. This is how the Web has always worked, and one of the primary reasons it has worked so well.</div>

### _RESTful Services_
<div style="text-align: justify">In this section, I started from a traditional RPC-based service and redesign it to become a RESTful service.  To accomplish this, first I extracted the resources that make up the existing service. Then I designed a URI scheme for identifying the resources and decide which HTTP methods they’ll support. And finally, I designed the resource representations that will be supported by each method.</div>

### _Moving from Verbs to Nouns_
<div style="text-align: justify">The first step in designing a RESTful service is to identify the resources the service will expose. From inspecting the operations in Figure 3, it looks like there are just a few resources in play:
*Users
*Bookmarks
However, we need to get a little more specific than this since we’ll need the ability to operate on individual bookmarks as well as different collections of bookmarks. After analyzing the current functionality, it’s apparent we’ll need the ability to address the following types of resources:
*An individual user account
*A specific user’s public profile
*An individual bookmark
*A user’s collection of private bookmarks
*A user’s collection of public bookmarks
*The collection of all public bookmarks
You can think of these things as the “nouns” that make up the service. The original service design outlined in Figure 3 focused on “verbs” and not the underlying nouns. This is where RESTful design takes a radical turn. With REST, you focus first on the nouns first (e.g., the resources) because you’ll rely on a standard set of verbs (the uniform interface) to operate on them within the service.

### _Designing the URI Templates_
<div style="text-align: justify">Now that we’ve identified the fundamental resources that make up our service, our next task is to define identifiers for them. Since we plan to host this service on the “Web,” we’ll rely on the Web’s URI syntax for identifying these resources. 
To keep things simple for consumers, we’ll use the service’s base address to identify the list of all public bookmarks. So if our service were hosted at http://contoso.com/bookmarkservice, we’d browse to that address to retrieve the list of all public bookmarks. Since the list of all public bookmarks can get quite large, we should probably also provide a way to filter the collection of bookmarks somehow. We can accomplish this by building additional scoping information into the URI design. For example, we can use the following query string to identify all public bookmarks marked with a particular tag:
?tag={tag}
In this case, the “tag” is providing additional scoping information that consumers can use to reduce the identified collection’s size. The syntax I’m using here is referred to as URI template syntax. 
Anything within curly braces represents a variable, like tag in this case. Everything else in the URI (not enclosed within curly braces) is considered a static part of the URI. Later, when we implement the service, you’ll see how to map these URI variables to method parameters in our WCF code.
The URI template in this case is relative to the service’s base URI. So you can identify all public bookmarks marked with the “rest” tag using http://contoso.com/bookmarkservice?tag=rest.
We can further filter the list of public bookmarks by username. In this case, we’ll use the username as part of the path to filter the collection by user before applying the tag scoping information:
{username}?tag={tag}
For example, you can identify all of skonnard’s bookmarks marked with “wcf” using http://contoso.com/bookmarkservice/skonnard?tag=wcf. And you can access all of onion’s bookmarks marked with “silverlight” using http://contoso.com/bookmarkservice/onion?tag=silverlight.
Next, let’s think about how to identify a particular user. Since we’ve already used a variable in the first path segment (for identifying a user’s public bookmarks), we’ll need to specify a literal string in that first segment to change the meaning of what comes next. For example, we can say that all URIs starting with “users” will identify a specific user. We’ll use the following templates to identify the user resources:
/users/{username}
/users/{username}/profile
And we can identify a user’s complete list of bookmarks by adding “bookmarks” instead:
/users/{username}/bookmarks
Plus, like before, we can filter bookmarks by using “tag” scoping information:
/users/{username}/bookmarks?tag={tag}
When it comes to identifying individual bookmarks, we have to make a decision about how to do that. If we assign each bookmark a unique Id, we could potentially use a simpler URI template for identifying individual bookmarks based on the Id. However, since bookmarks really belong to a specific user, it might make sense to make individual bookmark identifiers relative to a particular user as shown here:
/users/{username}/bookmarks/{id}
</div>

### _Applying the Uniform HTTP Interface_
<div style="text-align: justify">For the publicly accessible bookmark collections and the public user profile resource, we’ll only support GET requests. You can think of these as read-only resources. We’ll return a 200 (“OK”) when the requests are successful. If the URI doesn’t identify a known user, we’ll return 404 (“Not Found”).
The remaining resources will allow creating and modifying resources so you can think of them as read/write resources. For example, we’ll support GET, PUT, and DELETE on user account resources to replace the equivalent operations in the RPC version. We’ll use PUT to create new user accounts, GET to retrieve them, PUT (again) to update them, and DELETE to delete them.
We can use PUT to create new user accounts because the client is the one picking the username that forms the new resource’s URI. If the client is successful, the service will return a 201 (“Created”) response. If the client attempts to use an existing username, the service will return a 401 (“Unauthorized”) response. When issuing the PUT request to create a user account, the client will provide a user account representation in the HTTP request body containing the user’s information.
Once created, a user can retrieve her account resource by issuing a GET request to her account URI.  She can issue a PUT request to update her account resource by supplying an updated user account representation. She can also issue a DELETE request (with no representation) to delete her account. When these operations are successful, the service returns a 200 (“OK”) response. If the client attempts to update or delete a non-existent account, the service will return a 404 (“Not Found”) response.
For individual bookmark resources, we’ll support GET, POST, PUT, and DELETE requests. If a particular bookmark is marked as private, only the owner can retrieve it, but if it’s public, anyone can retrieve it. When a user creates a new bookmark, the service is responsible for assigning it a unique bookmark Id. Hence, the client won’t know the Id to use in the URI ahead of time. So, instead of using a PUT request, we’ll have users POST bookmarks to the user’s bookmark collection resource.  The handler for the POST request will create the new bookmark, assign it an Id, and return a 201 (“Created”) to the client, specifying the URI of the new bookmark resource in the Location header.
This explains when to use POST or PUT for creating new resources. The answer ultimately lies in who is responsible for determining the new resource’s URI. If the client is in charge, the client can use PUT to the new URI (like we did for user accounts) and the service can return a response code of 201 (“Created”). However, if the service is in charge of generating the new URI, the client should POST the new resource to a factory URI like we’ve done for bookmarks. Then, the service can return a response code of 201 (“Created”) along with the URI of the new resource in the response “Location” header.
Once clients know the bookmark ID’s, they can issue PUT and DELETE requests to individual bookmark URIs to update and delete bookmarks. If successful, the service will return a 200 (“OK”). If the client uses a URI that doesn’t exist, the service will return a 404 (“Not Found”) response.
Figure 5 summarizes the final design of our RESTful interface for bookmark resources, showing which HTTP methods we’ll support with each resource. We’ve been able to completely replace the functionality found in the original RPC service through HTTP’s uniform interface.</div>

### _Security Considerations_
<div style="text-align: justify">Our service requires the ability to authenticate users so we can authorize the resources and methods they’re allowed to access. For example, only authenticated users can access their own user account resources and operate on them. And only authenticated users can create new bookmarks and operate on them. If an unauthenticated user attempts to do so – or a user attempts to operate on another user’s resources – the service needs to return a 401 (“Unauthorized”) response and deny access.
So we need to figure out how we’ll identify users in order to authenticate them. HTTP comes with some built-in authentication mechanisms, the most popular of which is basic access authentication. This is one of the most popular authentication schemes used on the Web today because it’s so easy and widely supported, but it’s also one of the most unsecure, because passwords are sent across the wire in a simple-to-decode plain text format.  One way around this is to require SSL (HTTPS) for all HTTP traffic that will be using basic authentication, thereby encrypting the pipe carrying the passwords.
Another approach is to use digest authentication, another authentication scheme built into HTTP. Digest authentication prevents eavesdropping by never sending the password across the wire. Instead, the authentication algorithm relies on sending hash values computed from the password and other values known only by the client and server. This makes it possible for the server to recompute the hash found in an incoming message to validate that client has possession of the password.
Here’s how it works. When a client attempts to access a protected resource, the server returns a 401 (“Unauthorized”) response to the client along with a “WWW-Authenticate” header indicating that it requires digest authentication along with some supporting data. Once the client receives this, it can generate an “Authorization” header containing the computed hash value and send an identical request back to the server including the new header. Assuming the client generates a valid “Authorization” header, the server will allow access to the resource. Digest authentication is better than basic but it’s still subject to offline dictionary and brute force attacks (unless you enforce a really strong password policy), and it’s not as widely supported by Web browsers and servers.
Another approach is to avoid both basic and digest authentication and implement a custom authentication scheme around the “Authorization” header. Many of these schemes use a custom Hash Message Authentication Code (HMAC) approach, where the server provides the client with a user id and a secret key through some out-of-band technique (e.g., the service sends the client an e-mail containing the user id and secret key). The client will use the supplied secret key to sign all requests.
For this approach to work, the service must define an algorithm for the client to follow when signing the requests. For example, it must outline how to canonicalize the message and which parts should be included in the HMAC signature along with the secret key. This is important because the client and service must follow the same algorithm for this to work. Once the client has generated the HMAC hash, it can include it in the “Authorization” header along with the user id:
Authorization: skonnard:uCMfSzkjue+HSDygYB5aEg==
When the service receives this request, it will read the “Authorization” header and split out the user id and hash value. It can find the secret for the supplied user id and perform the same HMAC algorithm on the message. If the computed hash matches the one in the message, we know the client has possession of the shared secret and is a valid user. We also know that no one has tampered with whatever parts of the message were used to compute the HMAC hash (and that could be the entire message). In order to mitigate replay attacks, we can include a timestamp in the message and include it in the hash algorithm. Then the service can reject out-of-date messages or recently seen timestamp values.
The HMAC approach is superior to both basic and digest authentication, especially if the generated secrets are sufficiently long and random, because it doesn’t subject the password to dictionary or brute force attacks. As a result, this technique is quote common in today’s public facing RESTful services.
For the service we’re designing, we could pick any of these techniques to authenticate users. We’ll assume an HMAC approach for our service, and that each user will be assigned a secret key through an out-of-band e-mail after creating a new user account. And for all of the non-public resources, we’ll look for a valid HMAC hash in the “Authorization” header and return a 401 (“Unauthorized”) when necessary.
Now that we have a way for users to prove who they are, we’ll need logic to authorize their requests, in other words, to decide what they are allowed to do. For example, any authenticated or anonymous user may retrieve any public bookmark, while private bookmarks may only be retrieved by the authenticated user who owns them. We’ll see how to implementation this authorization logic later in the paper.
Designing the Resource Representations
Now we need to decide how we’re going to represent the resources exposed by our service. There are many different data formats commonly used to represent resources on the Web including plain text, form-encoding, HTML, XML, and JSON, not to mention the variety of different media formats used to represent images, videos, and the like. XML is probably the most popular choice for RESTful services, although JSON has been growing in popularity thanks to the Web 2.0/Ajax movement.
XML is easier to consume in most programming languages (e.g., .NET) so it’s often the default format. However, for browser-based scenarios (which abound), the JavaScript Object Notation (JSON) is actually easier to consume because it’s a JavaScript native format. For the service we’re designing, we’ll support both XML and JSON to accommodate both client scenarios equally well.
An important thing to think about while designing resource representations is how to define the relationships between different resources. Doing so will allow consumers to navigate the “Web” of resources exposed by your service, and even discover how to use navigate service by actually using it.
Let’s begin by designing the XML representation for a user account. When creating a new user account, we need the user to supply only a name and e-mail address (remember, the username is represented in the URI). The following is the XML format we’ll use for creating new user accounts:
<User>
   <Email>aaron@pluralsight.com</Email>
   <Name>Aaron Skonnard</Name>
</User>
However, when a user retrieves his user account resource, the service will supply a different representation containing a little more information, in this case an Id and a link. We’ll provide the Id that links back to this particular user resource and a link to this user’s list of public bookmarks:
<User>
   <Bookmarks>http://contoso.com/bookmarkservice/skonnard</Bookmarks>
   <Email>aaron@pluralsight.com</Email>
   <Id>http://contoso.com/bookmarkservice/skonnard</Id>
   <Name>Aaron Skonnard</Name>
</User>
There may be other pieces of information that make sense only in either the request or response representations. A valid user can update this representation with a new e-mail address or a different name and PUT it back to the same URI to perform an update.
A user’s public profile will provide yet another representation because we probably don’t want to share one user’s e-mail address with another. Here’s what we’ll use for the user profile resource:
<UserProfile>
   <Bookmarks>http://contoso.com/bookmarkservice/skonnard</Bookmarks>
   <Id>http://contoso.com/bookmarkservice/skonnard</Id>
   <Name>Aaron Skonnard</Name>
</UserProfile>
Now let’s turn our attention to bookmark resources. For our example, a bookmark is a pretty simple data set. When a user creates a bookmark, it must provide a title, a URL, some optional tags, and a public/private flag. We’ll support the following representation for creating new bookmarks:
<Bookmark>
   <Public>true</Public>
   <Tags>REST,WCF</Tags>
   <Title>Aaron’s Blog</Title>
   <Url>http://pluralsight.com/aaron</Url>
</Bookmark>
And we’ll use a slightly enhanced representation when returning bookmark resources that includes an Id, additional information about the user who created it, and a last-modified time:
<Bookmark>
   <Id>http://contoso.com/bookmarkservice/users/skonnard/bookmarks/13</Id>
   <LastModified>2008-03-12T00:00:00</LastModified>
   <Public>true</Public>
   <Tags>REST,WCF</Tags>
   <Title>Aaron's Blog</Title>
   <Url>http://pluralsight.com/aaron</Url>
   <User>skonnard</User>
   <UserProfile>http://contoso.com/bookmarkservice/users/skonnard/profile
   </UserProfile>
</Bookmark>
A list of bookmarks will simply be represented by a <Bookmarks> element, containing a list of child <Bookmark> elements as shown here:
<Bookmarks>
   <Bookmark>
      <Id>http://contoso.com/bookmarkservice/users/skonnard/bookmarks/13</Id>
      <LastModified>2008-03-12T00:00:00</LastModified>
      <Public>true</Public>
      <Tags>REST,WCF</Tags>
      <Title>Aaron's Blog</Title>
      <Url>http://pluralsight.com/aaron</Url>
      <User>skonnard</User>
      <UserProfile>http://contoso.com/bookmarkservice/users/skonnard/profile
      </UserProfile>
   </Bookmark>
  <Bookmark>...</Bookmark>
  <Bookmark>...</Bookmark>
</Bookmarks>
These representations make is possible to navigate between different types of resources, and they are simple to consume in any programming framework that includes a simple XML API.</div>



