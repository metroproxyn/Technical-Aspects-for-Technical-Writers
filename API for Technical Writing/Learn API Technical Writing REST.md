# Learn API Technical Writing: REST

**REST** – **RE**presentational **S**tate **T**ransfer

REST is a category of Web APIs

**Requests and Responses**

![image](img/WebAPIs.png)

**Authentication and Authorisation**

* Client device must prove identity to the server.
* Authentication
  * Username and password
* Authorization
  * Use token
  * Authority to make a request
* OAuth: one of the most common authorisation platforms*


## Introduction – What is REST?

* **RE**presentational **S**tate **T**ransfer
* It is a type of web API
* REST has several features
* Design pattern, not a protocol*

Design pattern vs protocol

A protocol is a pattern you need to fit exactly. For example, USD: size of plug, number of pins etc. 
A design pattern is a set of guidelines. For exampe, a house design that can be modernist, victoria, etc.

<mark> Rest is a Design Pattern </mark>

* Guidelines to follow, but they are not strict.
* Some APIs follow guidelines more closely than others.
* Because it is a design pattern, many people call APIs that use REST as "RESTful APIs".

**History**

* Previous web API styles required a lot of information being passed back and forth.
* REST proposed by [Roy Fielding](https://en.wikipedia.org/wiki/Roy_Fielding). It is simpler and more flexible.
* REST in its pure form is highly flexible, but not always easy to use.
* Most RESTful APIs do not follow the pure design pattern.

### Requests and Responses

![image](img/REST-Requests-and-Responses.png)

### HTTP

Like all web APIs, REST uses HTTP (HyperText Transfer Protocol) to send messages.

* An HTTP address is a URL, just like for web pages.
* HTTP has different "verbs" it can use: GET, POST, DELETE, etc.
* Secure HTTP (https) is also an option.

### Resources defined in the URL

* A resource is a piece of data that represents something
* If you are making a request about users, then the URL should have the word "users" in it.
* For example, the URL to return all users might be: http:/api.example.com/users
* The URL can contain IDs to narrow information
* For example, the URL to return information about user with ID 12345 might be: http:/api.example.com/users/12345

### Formats

One of the REST features is that it is completely independent of the format. The data sent and returned can be of any format. JSON is the most common; XML is also widely used. Can be media types, like images, sound files, etc.

### Stateless

REST is stateless. In this case, "stateless" means that the server does not keep track of the state of the device. For example, pagination with "Load more" button in the web pages and browser keeps track and do all the math.

### SOAP comparison

SOAP is the **S**imple **O**bject **A**ccess **P**rotocol. 
* Previously the most common web API. 
* Not actually all that simple.
* XML only.
* Protocol instead of a design pattern. Thus, the design had to follow strict standards.

### Review

* REST is a type of web API
* It is a design pattern, not a protocol
* It has requests and responses
* Resourced are defined in the URL
* It uses HTTP to send messages
* It can use any data format
* It does not keep track of the device's state


## Requests

A simple HTTP request looks like:

```json

POST http://api.example.com/user?source=ios&device=iphone

Accept: application/json
Content-type: application/json

{
  "name": "Aleks Mashanski",
  "email": "maszanski@yahoo.com"
}

```

### The Anatomy of the Request

* POST – method
* URL – http://api.example.com/user
* Query parameters – ?source=ios&device=iphone
* Headers – in our case, Accept and Content-type. There are standard headers to use for HTTP requests
* Body – in the {}. Only have a body for POST and PUT

#### Method

Method is the action that you are taking.

Examples

* **GET:** Return data from the server
* **POST:** Create a new resource on the server
* **DELETE:** Delete a resource from the server
* **PUT** Modifies an existing resource object

#### URL

URL stands for Uniform Resource Locator. Comes with the server information.

#### Query parameters

* Usually contains information on how the data should be returned
* Key/value pairs
* You can sometimes see these in browser address bars
* Example: 
  * http://api.example.com/user?sort-name&dir=ascend
  * Query parameters used to say: "Return sorted by name in ascending order."

## Resources

A resource represents a data concept. For example:
* Learning Management System (LMS).
  * Teatcher, student, course, assignment
* Flight Reservation System
  * Airline, passenger, flight, ticket
* Restaurant Review System
  * Restaurant, user, review, menu
  
### Resources and URLs

In REST, the resource is defined in the URL. THis means URL contains singular nouns. For example:
* http://api.example.com/restaurants
* http://api.example.com/courses/39314
* http://api.example.com/airlines/984289/flight

#### Speifying one or more resources

* Resource objects that exist have an ID
* Use IDs in the URL to specify a particular resource object
* If no ID – To get data on all restaurants:
  * GET http://api.example.com/restaurants
* To get data the restaurant with ID = 93839
  * GET http://api.example.com/restaurants/93839

### Endpoints

An endpoint means the URL for a resource
Examples:
* http://api.example.com/restaurants
* http://api.example.com/courses/{course-id} – *endpoint*
* http://api.example.com/airlines/{airline-id}/flight

### Resources can contain resources

* You can have a hierarchy of resources
* For example, airlines have flights that are specific to them
* To get all flights for the airline with ID = 53239:
  * GET http://api.example.com/airlines/53239/flight
* To get data on the flight 457 for that airline:
  * http://api.example.com/airlines/53239/flight/457

### Review

* A resources represents a data concept
* Resources are specified in the URL
* Use IDs to specify one particular resource object
* Resources can be containe din other resources


## HTTP methods

* As part of the HYperText Transfer Protocol, there are different types of requests:
  * If you type an address into a browser, that is a GET
  * If you fill out a form in a browser, that is a POST
  * There are actually several more

### What can you do with a resource? (CRUD)

* **C**reate – POST
* **R**etrieve – GET
* **U**pdate – PUT
* **D**elete – DELETE

#### GET

* Retrieves data
* Has no body
* Use IDs in the URL to specify a particular object
* To get data on all restaurants:
  * `GET http://http://api.example.com/restaurants`
* To get data the restaurant with ID = 93473:
  * `GET http://http://api.example.com/restaurants/93473`

#### POST

* Create a new resource object
* Data for creating object is in the body
* To create a new restaurant object:
  * `POST http://http://api.example.com/restaurants` 

```json
{
  ...data for new object
}
```

#### PUT

* Modifies an existing resource object
* Data for updating the object is in the body
* Use IDs in the URL to specify a particular object
* To modify a restaurant object with ID = 93473:
  * `PUT http://http://api.example.com/restaurants/93473`

```json
{
  ...data for updated object
}
```

#### DELETE
* Deletes an object
* Has no body
* Use IDs in the URL to specify a particular object
* To modify a restaurant object with ID = 93473:
  * `DELETE http://http://api.example.com/restaurants/93473`
  
> **Important Note:** Not all requests fit this model! 

* Sometimes a request does not have to do with a resource 
* For example:
  * Request turns on an appliance
  * Request sends an email message

## Query parameters

This topic is about query parameters and how to document them. You will know what are query parameters, see the examples of how they used and learn how to document them.

- Query parameters contain additional data that you can send to the server.
- Typically used to modify or filter the data that is returned
- You see these in browser fairly often

Although for the purposes of documentation it is better to think of query parameters and URLs as different.

### Sometimes considered part of the URL

- If URL has a question mark in it
  - Query parameters are after the question mark
- Key and value separated by equals sign
- Key/value pairs separated by ampersand

For instance,
`http://api.example.com/users?limit=10&offset=5`

### Example: Pagination

- What if you GET could return a lot of data?
- Break it up into several pieces through pagination
- First ask for first 10 items, then next 10, etc.
- Use query parameters to say what number to start at and how many
- Example: First 10
  `GET http://api.example.com/users?limit=10&offset=0`
- Example: Next 10
  `GET http://api.example.com/users?limit=10&offset=10`

### Example: Filter

- Query parameters are also used for filtering data, so you only receive the items you want
- Example: Only return restaurants whose type is "pizza"
  `GET http://api.example.com/restaurant?type=pizza`

### Example: Format

- Query parameters are also used to specify the data format
  - Note: this technique has fallen out of favor. Instead, usually the header is used to specify format.
- Example: Use XML
  - `GET http://api.example.com/restaurant?format=xml`

#### Specifying the format

Here are three ways that the data format can be specified:

- Header
  - Will be explained in the topic below. This is considered the best way to do it *(TBD: link)*
- Query parameter
  `GET http://api.example.com/restaurant?format=json`
- Suffix (not used much anymore)
  `GET http://api.example.com/restaurant.json`

### Example: Authorization

- Sometimes query parameters are used for authorizaiton
- For example, a key like "token" or "APIkey"
  - `GET http://api.example.com/restaurant?token=35f373e23723c`
- More common is to use headers for this information
  - Explained in the Authentication and Authorisation topic *(TBD: link)*

### Documenting Query Parameters

- Because they are key/value pairs, it is very similar to documenting JSON or XML. Refer to the Learn API Technical Writing JSON and XML topic for additional information.  *(TBD: link)*
- Create a table with these columns:
  - Parameter
  - Description
  - Type
  - Required
  - Notes

### Query Parameters Types

- Unlike JSON, all values are technically strings
- So for type, you may want to be more specific:
  - Integer
  - Date
  - URL
- If the values are limited to a set, put that in the notes.

### U.S. Weather Example

- date
  - The date of the forecast, in format YYYY-MM-DD. Optional. Default is today's date
- days
  - The number of days. Required.
- zip. 
  - The zip code (postal code) that says where the forecast is for. Required.
- language
  - The language for the returned data. Two-letter language code. Optional. Default is "en". Valid values are "en", "es", and "fr".

**Query Parameters:**

| Parameter | Description | Type | Required | Notes |
| :--- | :--- | :--- | :--- | :--- |
| date | The first day of the forecast | date | Optional | Format is YYYY-MM-DD. Default is today's date. |
| days | The number of days of forecast to return | integer | Required | |
| zip | The zip code for the location of the forecast | integer | Required | |
| language | The language of the returned data | string | Optional | Two-letter language format. Default is en. Valid values: en, es, fr |

### Conclusion

- Query parameters carry extra data
- Typically they modify the data you get back
- Key/value pairs
- To document, create a table with columns:
  - Parameter, Description, Type, Required, Notes
- Type can be more specific than string, such as date, URL, etc.

## Headers

The following material covers:

- What HTTP headers are
- Usage of headers to specify formats
- Usage of headers for authorization
- How to document headers

Headers are part of HTTP. They have key/value pairs. Usually, the key is a standard HTTP header key, but not always. Headers are used for things like browser cookies. 
In REST, headers most often used for:
- Specifying format
- Authorization

### Formats

- HTTP defines special headers to specify data formats
- You can actually use a different format when sending vs. receiving data

### Format of data you send

- This refers to the data for the POST or PUT body
- Header key
  - Content-Type
- Header value
  - application/json for JSON
  - application/xml for XML
  - Can also use this for media, like image/jpeg

For example,
`Content-Type: application/json`

### Format of data you receive

- This refers to the data in the response
- Header key
  - Accept
- Header value
  - application/json for JSON
  - application/xml for XML
  - Can also use this for media, like image/jpeg

For example,
`Accept: application/json`

### More complex formats

- Some APIs have the formats not only specify JSON or XML, but also the format of the resource.
  - In other words, the JSON or XML for each resource is considered a different format
- The following format is an example of a header value with a format for a product resource and a version number 1

`application/json;vnd.example.product.json+v1`

### Documenting Headers

- Headers will be similar for all API requests
  - GET and DELETE will not need Content-Type headers
  - Unless you have a different format type for each resource
- Create a table with these columns:
  - Header name
  - Description
  - Values

### Sample Header Documentation

| Header Name | Description | Required | Values |
| :--- | :--- | :--- | :--- |
| Bearer | Access token | Required | See Authorization section |
| Content-Type | Format of request data | Optional | application/json, application/xml. Default is application/json. |
| Accept | Format of response data | Optional | application/json, application/xml. Default is application/json. |

### Conclusion

- Headers are a standard part of HTTP
- Typicallu used to specify format and for authorization
- Format can be specific for resource
- Common header names:
  - Content-Type, Accept, Bearer
- To document, create a table with columns:
  - Header name, description, values

## Authentication and Authorization

The goal is to give you a basic information about the subject, so that you are in a better position to document it.

### Why is security important?

- Only registered developers should have access
  - Can affect revenue
  - Limits access (e.g., the number of requests per month)
  - Allows companied to collect important data on how APIs is used
- User informaiton should remain private
  - User data can be sensitive
  - No different than browser access

### Authentication vs. Authorization

- Authentication
  - A user provides valid username and password
  - This typically results in the return of an access token
- Authorization
  - When you make an API request, you send the server an access token
  - This token determines what API requests you can make

### App keys

- Also known as "API keys"
- For each app that a developer creates, they register that app in the company's developer portal
- The developer portal then gives them an "App Key", which is typically a string of numbers and characters
- This key is sent to the server in exchange for an access token so that each API reques is associated with the registered app

### OAuth

- There are many ways to handle security
- OAuth is a popular open protocol
  - Very flexible
  - Very complex
- Details at http://oauth.net/
- Most APIs use OAuth 2.0

#### Valet key

- OAuth uses a concept like a valet key
- Different API users have different privileges
  - For example: admin, teatcher, student
- Each API user has an access token
  - The token tells the server what the API user has access to
  - For example, a student cannot create a course
  - Note: tokens are temporary

#### One-legged vs. Three-legged

- OAuth has several ways to handle authorization
- Most common for REST are referred to as one-legged and three-legged
- One-legged:
  - Used when no sensitive user data involved. For example, in Linkedin, every user can see public profiles.
  - Send API key => return access token; Send API request with access token => return API response
- Three-legged:
  - Used when need to protect user data. For example, Linkedin connections. 
  - Significantly more complex than one-legged
  - Three pathways of data are involved: Client device, Authentication server and API server
    - Authentication server is different from API server; Could be even a different company
- Some API don't have users, so always use one-legged

#### Grant Types

- There are different flows of information, depending on how authorization is granted
- These are called "grant types"
- Two most common:
  - Authorization code: Used with server-side applications
  - Implicit: Used with mobile apps and web applications

### Headers

- Access tokens are most commonly put in a header

### How to document authentication and authorization

- Need a section on Authorization
  - Describe step-by-step how the process works to get an access token
    - The URL of the authentication server
    - How to get the access token from the server's redirect URL
  - Then describe how to pass the tken to server
  - Tokens often expire after a fixed amount of time. Describe how to get a new token if this happens.

- How to use token:
  - Include token information in the appropriate table
  - Header or query parameter
  - Might want this table for each API request

### Conclusion

- Authentication is getting valid username and password
- Authorization is telling server that user has access
- App keya are obtained bu developer on the developer portal
- OAuth is a popular, complex, open standard
- One-legged OAuth for no user data
- Three-legged OAuth for protected user data
- Grant types: Authorization code and Implicit
- Document with an Authorization section

## Request body and responses

Structured data is organized in terms of objects and lists that contain other objects and lists.

### Structured data

- Request body
  - POST and PUT only
- Response body
  - All methofs, usually
  - Sometimes DELETE does not return a response body
- Usually JSON or XML

#### Documenting structured data

- Create a table that lists:
  - Element, Destination, Type and Notes
  - For requests, also add Required

### URLs in Responses

- Sometimes there are URLs in the responses
- These are URLs to other resources
- Example request:
  - http://api.example.com/restaurant
- This returns all restaurants
  - That could be a huge amount of data
  - So only return limited data plus links to more data

#### If no response body

- Just say it, instead of the table:
  - No response body in returned.

### Objects section

- Sometimes many API requests return the same type of data
- In this case, response information and sample responses are redundant
- Create an Objects section of the docs which contain responses body tables
  - Examples: restaurant, menu, address, etc.
- Link to the Object section from the request section

### Errors

- Errors are returned by one of two ways
  - HTTP status codes
  - Elements in the response body
- HTTP status codes are part of the HTTP protocol
  - A status code is always returned with the response
  - They were designed for web pages, but have been repurposed for APIs
  - They contain some information
  - But you will want to document them more completely

### HTTP Status Codes

- They have a code and a description
- Examples:
  - 200 – OK: Successful GET, PUT or DELETE
  - 201 – Created: Successful POST
  - 401 – Unauthorized: Bad access token
  - 404 – Not found: Bad URL

#### Documenting HTTP Status Codes

- Create a table with Code, Description, and Notes
- Often one per API, but can be one per request

| Code | Description | Notes |
| :--- | :--- | :--- |
| 200 | OK | API request was successful |
| 401 | Unauthorized | Access token is not valid |
| 415 | Unsupported media type | Only JSON and XML are supported formats |

### Errors in Response Bodies

- Document like other response elements
- Create a similar table as HTTP status codes

```json
{
  "errorCode": 15,
  "errorMessage": "Class size limit reached"
}
```

### Conclusion

- Structured data can be found in the request and response bodies
- How to document is covered in JSON/XML class
- URLs in the response point to another resource objects 
- You may want an Object section
- Errors are returned using HTTP status codes
  - Document with a table
- Errors can also be returned with response elements
  - Document like other elements, but add an error table

## API Reference Documentation

## Tools