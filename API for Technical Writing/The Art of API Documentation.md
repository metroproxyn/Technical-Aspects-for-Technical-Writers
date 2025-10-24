# The Art of API Documentation

This material assumes that you understand the basics of how APIs work: {JSON}, < XML/>, REST and how to document them.

## What are API?

- Applicaiton Programming Interface
- It defines how two pieces of software talk to each other
- Two most common types of APIs:
  - Web APIs (REST, SOAP, etc.)
  - PLatform APIs (Java, C++, etc.)

## API Documentation

- Software developer audience
- Good documentation
  - Increases developer edoption
  - Decreases support costs
- The developers who created the API are rarely the best people to document it =) Even if they write well, they are too close to the material

## Conceptual vs. Reference Material

API documentation can be divided into 2 parts:

- Conceptual
  - High level
  - Gets developer oriented
  - Gets developer started
  - Helps them with common tasks
- Reference
  - HTTP Requests and Responses
  - Classes, methods, properties, etc.

### Why is Conceptual Material Important?

- Developers need to read something that immediately communicates why they should spend time with an API
- Developers need to be able to get started easily, otherwise they will give up (?)
- Figuring out how to do common tasks can be difficult by just looking at the reference material

#### Writers are important

- Developers aren't great at reference material, but...
- Developers tend to be really bad at conceptual material
  - They naturally focus on "how" and forget "why"
  - They are too close to the API to see the big picture
  - Longer paragraphs tend to be harder for them

### Conceptual Material Consists of ...

Typically:
- Overview
- Getting Started
- Tutorials
- Sample Code

Each of these will be discussed in more details later.

#### Overview

- Explain why to use the API
- Requirements
- Key concepts (for example, for a Learning Management System, explain the roles of student, teacher or administrator)
- Workflow (meaning what is the order of steps taken to do common tasks)
- Architecture diagrams and/or data model

#### Getting Started

- Lead people through a simple task
- Web APIs
  - Registration
  - Get an app key
  - Authorization
  - Doing something simple
- PLatform APIs
  - Downloading the SDK
  - Setting up your IDE
  - Doing something simple

#### Tutorials

- Common Tasks
- Step-by-step
- Screenshots, if they make sense
- Start with basic tasks, move to advanced

#### Sample Code

- Simple and short tasks that actually work
- Developers like to be able to copy and modify them
- Common tasks
- Well-commented
- Sample code is different that production code

## API Overview Material

Overview material is important for the following reasons:

- Developers need to read something that immediately communicates:
  - What can the APi do?
  - What is required to use the API?
  - Is it well-designed?
- They want to quickly figure out: will this solve the problem that they have? If they can't figure out that quickly, they will move on and use something else.
- Once they are ready to learn, a high-level description will orient them.

### Explain "Why", not just "How"

- Most of the documentation will explain how to do something
- The overview must explain why you would use it
  - Descrive key features
  - Provide a few use cases

### Requirements

- Provide a list of what is required
- Get this list from the development team
- For Web APIs
  - This usually isn't included
  - However, for some APIs, you need a separate authentication server
- For Platform APIs:
  - What programming languages are supported?
  - What OS, SDKs, IDEs, etc. are required?

### Key Concepts

- APIs typically have important concepts that should be described
- This usually depends on the "domain" – what does the API do?
- Write a paragraph or two for each concept
- Examples:
  - Learning Management System: Roles, classes, grades, etc.
  - Online Banking: Accounts, transactions, etc.

### Architecture

Explain how the various pieces fit together.

`(Architecture image shoud be here as an example)`

* Explain the major pieces of the API
* Explain how these pieces fit together

### Workflow

- Often, to complete a task, several API calls need to be made
- Workflow described the order of these tasks
- Example: Play a song from a playlist
  - 1. Get a list of all playlists and their IDs. Let the user select a playlist
  - 2. Get the list of songs and their IDs in the playlist using the playlist ID. Let the user select a song.
  - 3. Request the sound file for the song using the song's ID.

### Diagrams

  ![image](img/DiagramExample.jpeg)

- Architecture Diagrams
  - How do various pieces fit together?
- Workflow diagrams
  - What happens when?
- Get diagrams from development team
  - They may need some clean-up

## "Getting Started" section 

Why do you need a Getting Started section? 

- In the early stages, developers are still deciding whether to use the API
- The fact is, learning something new is intimidating
- The Getting Started section can make the API seem much less intimidating and more inviting.

For proper Getting Started, we need the simplest program that demonstrates some feature of the API.

- API experts have a metric on how easy it is to get started with an API TTHW ("Time to Hello World")
  - This is the time it takes for a developer to do a Hello World task from scratch.
- Documentation is an important piece of this
  - There are other pieces, too: like how easy is it for a developer to register and download

### Structure

- Step-by-step instructions
- Lots of screenshots

The good example of this practice is the [Saleforce API Getting Started](https://resources.docs.salesforce.com/latest/latest/en-us/sfdc/pdf/api_rest.pdf) guide or [Stripe API Get Started](https://docs.stripe.com/get-started) guide.

### Web API Getting Started

Here is what you want in a getting started section for Web API:

- Registration
- Getting an app key
- Making one or two HTTP requests that return a response
- Typically not something that requires complex authorisation (like three-legged OAuth). Try to avoid this

### Platform API Getting Started

- Downloading the SDK
- Setting up your IDE
- Creating an app that does a simple task
  - Often you provide code that they can copy-and-paste

## Tutorials

Reference material shows developers the details, but it can be hard to figure out what to do. Tutorials, on the other hand, lead them through common tasks. This gretaly reduces support costs.

### Subject Matter

- Cover common tasks
- Examples:
  - Learning Management System: Adding a student to a course
  - Online Banking: Getting account information
  - Photo sharing: Uploading an image
- Work with the Project Manager to determine what these tasks area is

### Structure

- Same structure as Getting Started
  - Getting Started *is* a tutorial!
- Step-by-step instructions
- Sample HTTP requests or code they can copy and paste
- As many screenshots as you can, but only if they really show something

### Screenshots

- Web APIs
  - Not that many screenshots needed – often, none
  - Only if the tutorial involves doing something with the developer portal

- Platform APIs
  - Again, not many screenshots
  - Show if you need to do something with the IDE
  - Show if the tutorial does something visual

### How many do you need

- Depends on the complexity of the API
- For most APIs, 3 to 5 is sufficient
  - Developers should be able to figure it out on their own after that
- Some API are so complex, you need a lot more than that

### Conclusion

- Tutorials reduce support costs
- Tutorials cover common tasks, which the project manager should help you with
- Write step-by-step instructions
- Screenshots if you can, but there usually will not be many
- Typically 3 to 5 tutorials is sufficient, but more if the API is very complex

## Sample Code

This section gives you guidelines for writing good sample code and talks about how to apply them.

### The importance of sample code

- Developers really want it
  - Surveys have shown it
  - Survey: Search "sdk bridge documentation survey"
- May developers learn bets by example
- They can copy, paste and modify
  - Much faster that doing it from scratch

### Guidelines

- Prioritise the languages in which your API users code
- Relevant information should be grouped together
- Clarity is more important than efficiency

**Note:** Good production code is *not* the same as good smaple code.

### Web APIs vs. Platform APis

- Web APIs
  - Can ba called from nearly any language
  - Often sample code is not included: only sample requests and responses
  - Need to choose which languages to have code for
  - Typically fairly simple samples

- Platform APIs
  - In the language of the SDK
  - Can be simple or complex

### Web APIs: Choosing languages

- Reach out to project manager or developer and ask what languages they use
- Do as many languages as you have budget for, but prioritise on the one that is most used
- Sometimes, content systems allow you to have tabs for each language
  - Example: stripe.com

### Illustrating workflow

- Think about what your API does and how the sample code could demonstrate common tasks
- Often sample code illustrates a series of API calls
  - Web API example: results from one HTTP call are used for paramneters in a second HTTP call
  - Platform API example: Call to inialise the SDK followed by calls to take actions, followed by a call to shut down the SDK

### Hard-coded values

- Never use hard-coded value sin production code
  - Strings, integersm hexadecimal values, etc.
- At the same time, you *should* use them in sample code
- "Group relevant information together" means using hard-coded values in sample code
  - Otherwise, developers must scroll to the top to see the value
  - Lose train of thought
- Exception: App keys and access tokens, since they will not be what the developer uses

### Comments

- Comments are good for both production and sample code
- In sample code, they are critical
- Every class, function, or method should have at least one comment line explaining what it is or what it does
- Use comments anywhere that the code is not obvious, especially if you need to document a work-around
- In general, have a line of comments at least every 5 to 10 lines of code

### Meaningful names

- For both production and sample code, variable, class, and member names should be clear
- In sample code, you should take this idea farther than in production code
- Remember: clarity is more important that efficiency
- Long, unwieldy names are fine: they add clarity
- Never use menaingless names like "foo" or one-letter variable names

### Object-oriented programming

- Object-oriented programming is a way of organising code
- It is very desirable for production code, but not for sample code
- The reason is OOP distributes information between inherited classes
  - Does not group relevant information together, which is one of our guidelines
- If you use Object-oriented programming in your sample code, this means the developer have to hunt for information, and potentially lose trail of thought

### Conclusion

- Developers really like sample code because they can copy and modify it
- Three guidelines: prioritise languages, group information, clarity over efficiency
- Web APIs will require prioritising languages
- Sample code should illustrate workflow of common tasks
- Use hard-coded values
- Use plenty of comments: one line for every 5-10 lines of code
- Use meaningful names: long in fine
- Don't use object-oriented programming

Source: Gruenbaum sample code

## Tools for Calling REST APIs

Tools are useful for trying out REST requests. No programming required. Making requests with tools will give you a better feel for how the REST API works. 
The biggest advantage is that you can try out requests and answer questions without having to ask the development team. 
- For example, is a parameter required? Try making a request without it and see what happens.

### GUI Tools

- GUI – Graphical User Interface
- Advantages:
  - Visual tool is easy to use
  - Formats responses nicely
  - Keeps track of history
- Available for many operating systems and browsers
- Usually free
- For example, Postman (TBD: provide with the example)

### Command-line Tools

- Type a command into a console or terminal
- Get the results back in the console or terminal
- Easy to include in documentation, so the developers can easily use them
- cURL:
  - The only one that people really use
  - Often called "curl"
  - Comes as part of Mac OS
  - Requires some set-up for Windows

### Conclusion

- Tools let you try out REST requests to see how they work
- No programming required
- GUI tools give you a nice visual interface
- cURL is a command-line tool that is easy to document

How can tools help?

GUI tools

Command-line-tools (cURL)

(TBD)

What the course covers:

*Introduction
API Conceptual Material
Getting Started
Tutorials
Sample Code*

Tools for REST APIs
Hands-on Exercises for Tools
Finding a First Project
Review

Web-based and command-line tools for REST APIs

Outline