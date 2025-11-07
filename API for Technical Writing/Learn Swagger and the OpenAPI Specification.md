# Learn Swagger and the OpenAPI Specification

Swagger and the Open API Specification are ways to define an API

## What are APIs?

- **A**pplication **P**rogramming **I**nterface
- It defines how two pieces of software talk to each other
- For this learning material, we are talking about Web APIs

The API definition describes:
- What requests are available
- What the response looks like for each request

### REST

- Swagger and the Open API Specification are designed for REST APIs
- REST is a type of web API
- Stands for **RE**presentational **S**tate **T**ransfer

### Prerequisites

- Understand how REST APIs work
  - Check out my other [REST API](/API%20for%20Technical%20Writing/Learn%20API%20Technical%20Writing%20REST.md) material
- Read JSON
  - Check out my [JSON/XML](/API%20for%20Technical%20Writing/Learn%20API%20Technical%20Writing%20JSON%20and%20XML.md) material
- Simple text editor for YAML files
- Modern browser and internet (I suspect you have it already :D)

### API Definition File

- File describes all the things you can do with an API
- Lists every request you can make
- Tells you how to make that request
- Tells you what the response will look like

#### Why Create an API Definition?

- Lets you design the API before implementing it
- Helps with automated testing
- Automatically create code in several languages
- Can be used to automatically generate documentation
  - Documentation can be interactive

### Swagger

- Historically, Swagger was a specification for how to create an API definition file
- After a new version (Swagger 2.0), the specification became the Open API Specificstion (OAS)
- Swagger is now a collection of tools that use the Open APi Specification
- Many people still refer to OAS as "Swagger"

#### Open API Initiative

- The Open API Initiative (OAI) is an organization created by a consortium of industry experts
- Focused on creating, evolving, and promoting a vendor neutral description format.
- It is in charge of the Open API Specification, but not in charge of any tools that use it

#### Swagger Tools

Swagger provides several tools:
  - Swagger Editor: Helps you write OAS files
  - Swagger CodeGen: Generates code in popular languages for using your API
  - Swagger UI: generates documentation from OAS files
  - SwaggerHub: Hosted platform for designing and documenting APIs

## API Definition File

- API definition file is a file that describes everything you can do with an API
  - Note: "API" means a collection of related requests
- Server locaiton
- How security is handled (i.e., authorization)
- All the available requests in that API
- All the different data you can send in a request
- What data is returned
- What HTTP status codes can be returned

### The Anatomy of a Request

![image](/img/AnatomyoftheAPIRequest.jpeg)

#### URL

- Example request URL: https://api.example.com/v2/user
- Scheme
  - https
- Host
  - api.example.com
- Base path
  - /v2
- Path
  - /user

#### Method

- The HTTP method describes what kind of action to take
- GET, POST, PUT, DELETE, etc.

#### Parameters

- Example:
  - https://api.example.com/v2/user/{user-id}/connections?degrees=2
- Path Parameters
  - {user-id}
- Query Parameters
  - degrees

#### Request Body

- For some methods (POST, PUT, etc.) you can specify a request body, often in JSON
- The body is treated as a parameter
- You specify a schema for the request body

#### Response Body

- In REST, the response body can be anything, but is most often structured data, such as JSON
- The response body is included in a response object
- The response object has a schema to describe the structured data
- You can have a separate response object for each HTTP status code returned

### Security

APIs often use security.

- Security means authentication and authorization
- Can be:
  - None
  - Basic Auth
  - API key
  - OAuth

### Documentation

- Human-readable description of elements
- For generating documentation
- Add a "description" section for:
  - The API
  - Each operation (path and method)
  - Each parameter
  - Each response element

### Getting the information to create an OAS file

- If you asked to create an OAS file, how do you find the information?
- Developers can provide rough documentation
- Developers can provide sample requests and responses:
  - Most common
- You can figure it out from the code
  - Requires strong coding skills
- For exercises, sample requests and responses will be provided (see the attachments folder)


Course overview:

API Definition

YAML

Open API Specification

Creating Documentation

Using Swagger

Using JSON

Alternatives to Swagger and Open API Specification