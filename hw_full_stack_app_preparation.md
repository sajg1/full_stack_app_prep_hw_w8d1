# Homework: Full Stack Games Hub App

### Learning Objectives

- Understand the relationship between client, server and database
- Be able to navigate a codebase that you haven't written

## Brief

Your boss has asked to you look over the codebase of a full-stack JavaScript application. The front-end is written in JavaScript using Vue, the back-end uses an Express server and a MongoDB database. Your task is to make yourself familiar with the codebase.

The application includes a README.md with instructions on running the application.

![Overview of the tech stack and tooling with commands](images/tech_stack_with_commands.png)

*Overview of the tech stack and tooling with commands*

## MVP

### Task

Draw a diagram showing the dataflow through the application starting with a form submission, ending with the re-rendering of the page. This will involve a multi-direction data-flow with the client posting data to the server and the server sending data back to the client with the response. Detail the client, server and database in the diagram and include the names of the files involved in the process.

### Questions

1. What is responsible for defining the routes of the `games` resource?
    Answer - create_router.js holds modular code that can then be used by server.js to assign specific
    
2. What do you notice about the folder structure?  Whats the client responsible for? Whats the server responsible for?
Answer - Client and Server are separated into different folders. The Client is responsible for the front end output to the user, displaying the form to be filled in and the data about each game in a card within a grid. It is also responsible for sending the request to the baseURL (localhost:3000/api/games). The Server is responsible for the backend functionality, listening out for requests from the client. It then interperits the rest-ful route being requested and  updates the database accordingly.

3. What are the the responsibilities of server.js?
Answer - server. js main responsibility is to respond to requests.

4. What are the responsibilities of the `gamesRouter`?
    Answer - to deal with the requests and update the database accordingly.
    
5. What process does the the client (front-end) use to communicate with the server?
    Answer - an http fetch request.

6. What optional second argument does the `fetch` method take? And what is it used for in this application? Hint: See [Using Fetch](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch) on the MDN docs
    Answer - The second argument is an init object that contains settings. In this case we use method to assign the restful route we wish to use and the body property which converts the current elements into json strings.
    
7. Which of the games API routes does the front-end application consume (i.e. make requests to)?
    Answer: 'POST' and 'DELETE'
    
8. What are we using the [MongoDB Driver](http://mongodb.github.io/node-mongodb-native/) for?
    Answer for callback and promise-based interaction with MongoDB.

## Extension

Why do we need to use [`ObjectId`](https://mongodb.github.io/node-mongodb-native/api-bson-generated/objectid.html) from the MongoDB driver?

Add to your diagram the dataflow for removing a game.
