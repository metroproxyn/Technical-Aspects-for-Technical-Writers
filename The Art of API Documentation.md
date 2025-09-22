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