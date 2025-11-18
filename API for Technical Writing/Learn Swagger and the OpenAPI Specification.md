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

## YAML

We will tlak about how YAML is used with the Open API Specification, then what YAML is, and go over the basic rules of YAML.

### Open API Specification

- The Open API Specification (OAS) uses structured data (JSON/XML) for its definition files
- You can use one of two structured data formats: YAML or JSON
- For this learning material, we will primarly use YAML

### What is YAML?

- YAML is an acronym which stands for "YAML Ain't Markup Language" or "Yet Another Markup Language." The former is meant to underscore that the language is intended for data rather than documents.
- Used for data, not content
- Compared to JSON and XML, it minimizes characters
- It's most often used for configuration files, rather than files pssed over web, like JSON

### Key/value pairs

- Key value pairs are indicated by a colon followed by a space
  - For example, two key pairs: `date: 2025-11-10, firstName: Aleks`
  - One for date, and one for first name

### Levels

- Levels are indicated by white space indenting
  - Cannot be a tab indent. You should only use spaces

### Types

- Types are determinted from context
- Example: 
  `part_no: A4786` – string
  `description: Photoresistor` – string
  `price: 1.47` – float
  `quantity: 4` – integer

### Quotes

- In general, you don't need quotes around string
- Expection: something that will be interpreted as a number or boolean
- Quotes can be either single ' or double "

### Lists

- Use a dash (-) to indicate a list item
- You don't need to declare the list

### Multi-line strings

- Because there are no quotation marks on strings, you need special characters for multiple strings
- "|" means preserve lines and spaces
- ">" means fold lines
- There are variations: | -, | +, etc.

![image](/img/YAMLMultiLineStrings.jpeg)

### Comments

- Comments are denoted with the #
- Everything after # is ignored

### Schemas

- Although not officialy part of YAML, OAS uses references for schemas
  - Used for request and response bodies
- Will go into more detail in a latter lesson
- Use `$ref` to indicate a reference
- Typically put the schema in a `definitions` section

![images](/img/YAMLSchemaExample.jpeg)


## Open API Specification Basics

> Notes about OAS 3 and the Swagger editor

This learning material describes OAS 2. A newer version, OAS 3, is now available, and many companies are using it. At some point the author intend to update the course for OAS 3, but it might not happen for a while.

This article describes the differences between the two. You may want to look at this once you have completed the course. https://blog.restcase.com/6-most-significant-changes-in-oas-3-0/

Also: in the videos from the [mentioned Udemy course](https://www.udemy.com/course/learn-swagger-and-the-open-api-specification/learn/lecture/8677186#overview), the Swagger editor URL is listed as https://editor2.swagger.io/. That has changed, and it is now https://editor.swagger.io/


### Open API Specification File

- Choose an example and build a file
- Company: example.com
- Service for uploading and sharing photos
- API base URL (example): 
  - https://api.example.com/photo

![images](/img/Swagger_API_Example.jpeg)

### Adding a Request

Let's define requests for getting photo albums.
Requests will have:

- URL endpoint
- HTTP Method
- Path parameters
- Query parameters
- Also (covered later):
  - Request Body
  - Responses

### Example with query parameters

`GET https://api.example.com/photo/album?start=2025-17-26&end=2025-10-12`

```yaml
# Endpoints
paths:
  # Photo album
  /album:
    # Get one or more albums
    get:
      # Query parameters
      parameters:
        # Starting date
        - name: start
          in: query
          required: false
          type: string

        # Ending date
         - name: end
           in: query
           required: false
           type: string
```

![images](/img/Swagger_Example_PathParameter.jpeg)

### Data types

The data type can have several values:

- boolean
- integer
- number
- string
- array

### Custom headers

- Custom headers are threated as parameters
- Standard headers (authorization, content format) are handled elsewhere

```yaml
# Customer level
- name: Access-level
  in: header
  required: false
  type: string
```

! Documentation is added using the **description** key

### Swagger Editor

Swagger provides an editor for OPen API specification files: 

-  https://editor.swagger.io/

## Schemas

This section will talk about what a schema is and how to use references in an OpenAPI specification file.

### Request and Response Bodies

- Certain kinds of requests have extra data
  - POST, PUT, etc.
- Extra data called the request body
- Typically data is formatted in JSON (or sometimes XML)
- Nearly all responses return a response body
- Also typically formatted in JSON

### What is a schema?

- The schema indicates the structure of the data
- OAS schema object is based off the JSON Schema Specification
  - http://json-schema.org/
- The main thing that the schema defines are:
  - The keys in key/value pairs
  - Type of data in the values
- Can contains many levels

### $ref

- $ref is a special OAS key that indicates that the value is a reference to a structure somewhere else in the YAML file

For example:

![images](/img/ref.jpeg)

### Request Body

- Under **parameters**:
- **name** just for reference (not shown in docs)
- **in** – set to body
- **required** – typically set to true
- **schema**:
  - Add a level
  - Key of $ref
  - Value of the reference path, in quotes

![images](/img/ExampleRequestBody.jpeg)

### Schema section
- Create a key called **definitions** at the end of the file
- Add a level and give it the name from the **$ref** value
- Add a **properties** key
- For each top level element in the JSON, add a key of its name.
- Add a **type** key that says what type of data it is
- Add other keys for other data (more later)

![images](/img/ExampleSchema.jpg)

### Schema objects

- You can add other objects sa vakues
- Simply use a **type** of **object**
- Then add a new level with **properties**:
- And continue just like you did before

### Schema objects with $ref

- As you can imagine, this can add a lot of identation
- So you can use $ref from within your definition

### Schema array

- You can also add arrays
- Simply use a **type** of **array**
- Then add a key of **items**
- And define the **type** and any other properties

### Schema array with $ref

- For a more complex type, use $ref for the array items

### Required

- In requests, you can specify that certainb elements are required or optional
- Use the **required** key for this
  - Contains a list of all properties that are required

### Response Body
- Under **response:**, under the response code
- **schema:**
  - Add a level
  - Key of $ref
  - Value of the reference path, in quotes
- If the response is an array instead of an object, then add:
  - type: array
- **Note:** you can have different schemas for different response codes

### allOf

- In the prvious example, album and newAlbum had a lot of duplication
- Can use the **allOf** key to combine several objects into one:

![images](/img/allOf.jpeg)

### Headers and Examples

- Responses can also have custom headers
- You can include example bodies in OAS files
- Refer to the Open API Specification on how these work

### Form Data

- Sometimes the request body uses form data instead of JSON
- For form data, each parameter is a property
- **in** key has value **formData**

```yaml
parameters:
  - name: firstFileName
    in: formData
    required: true
    type: string
```

## Open API Specification Continued

This section will cover security, error conditions, content types (JSON, JPEG, etc.) and operation IDs.

### Security

- Security means what kind of authentication or authorization is required
- Authentication: the user has correct username and password
- Authorization: the user has access to this API and data

#### Security types

OAS handles 4 security types:

- **None**
  - Used for getting publically available information
- **API key**
  - Indicates that the app has permission to use the API
- **Basic Authentication**
  - Username and password is included in a header (not secured)
- **OAuth**
  - Complex issuance of temporary token

#### How security is indicated

- **Each operation has a security key**
  - Contains an array of security definition objects
  - Often just one element in the array
- **Security Definitions**
  - The file contains a **securityDefinitions** key
  - Typically at the end
  - Contains security objects
- **Security object**
  - Contains information needed for that type of security

### API key

- **Add security key to each operation**
  - Use dash to indicate an array
  - Create name for definition and use empty brackets, since no data is needed
- **Add security definition**
  - Add definition for that name in securityDefinition section
  - **type: apiKey**
  - **name:** name of the header or query parameter to be used
  - **in: query** or **header**

#### API key example

- Put a security key in the **get** section and **securityDefinitions** at the end of the file

```yaml

security:
  - api_key: [ ]
```

and

```yaml

securityDefinitions:
  api_key:
    type: apiKey
    name: application-key
    in: header
```

Also token can be used in the "name" parameter.

### Basic authentication

- Add security key to an operation
  - Use dash to indicate an array
  - Create name for definition and use empty bracket, since no data is needed
- Add security definition
  - Add definition for that name in securityDefinition section
  - **type:basic**

#### Basic authentication example

- Put a security key in the get section and securityDefinition at the end of the file
  
```yaml

security:
  - basic_auth: [ ]
```

At the bottom of the file is

```yaml

securityDefinition:
  basic_auth:
    type: basic
```
### OAuth

- Add security key to request, like before
  - However, now you add scopes in the array
- Add security definition
    - Add definition for that name in security Definition section
    - **type: oauth2**
    - **authorizationUrl:** URL where credentials are entered
    - **tokenUrl:** URL for the token
    - **flow:** OAuth 2 flow (**implicit**, **password**, **application** or **accessCode**.)
    - **scopes:** list of scopes with descriptions

#### OAuth example

- Put a security key in the **get** section and **securityDefinition** at the end of the file

```yaml

securityDefinition:
  - oauth_example:
    - write: albums
```

```yaml

- securityDefinitions:
    oauth_example:
      type: oauth2
      authorizationUrl: http://example.com/authenticate
      flow: implicit
      scopes:
        write:albums: modify albums in your account
        read:albums: read your albums
```

### Errors

- Errors are simply different response codes
- Often APIs return a special structure with errors
- Example 401 (Unauthorized) code returned:
  - *{"errorCode": 13, "message": "Username not found"}*
- Should include schema for every potential status code

#### Error Example

```yaml
responses:
  # Response code
  200:
    description: Successful response
  401:
    description: Unauthorized
    schema:
      $ref: '#/definitions/error'
```

### Content Types

- Content types indicate the format of the data in the request and response bodies
- This is done through the **Content-Type** header
- You can specify this for:
  - The whole API
  - Individual operations
- Use the **consumes** and **produces** keys
  - **consumes** for requests, **produces** for responses
  - Use the **Content-Type** value (for example, **application/json**)

#### Example Content-Type

```yaml
# URL data
host: api.example.com
basePath: /photo
schemes:
  - https

consumes:
  - application/json
produces:
  - application/json
```

### Operation ID

- Although it doesn't show up in the documentation, you can optionally add an operation ID to each request
- Some tools will use this

```yaml
paths:
  # Photo albums
  /album:
    # Get one or more albums
    get:
      operationId: getAlbums
      
      # Query parameters
      parameters:
        #Starting date
        - name: start
```

## Autogenerated Documentation

We will talk about what autogenerated documentation is, how it looks and how to add description tags.

- Tools (including Swagger) take OAS files and generate HTML documentation to put on the web
- If the OAS file is kept up to date, then the documentation is likely to be more accurate than if you wrote the docs manually
- Autogenerated documentation allows you to try out requests from within the documentation

### Description key

- Use the **description** key to add documentation
- Add description key to:
  - API info
  - Operations (get, post, etc.)
  - Parameters
  - Responses
  - Schema definitions

*** 

Creating Documentation

Using Swagger

Using JSON

Alternatives to Swagger and Open API Specification