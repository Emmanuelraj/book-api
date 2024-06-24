# Book-Api
Create an API for managing a personal book library. Users can add, update, delete, and retrieve books.


# Creating Rest API

You need to create an express HTTP server in Node.js which will handle the logic of a book list app.
  - Don't use any database, just store all the data in an array to store the book list data (in-memory)
  - Hard book: Try to save responses in files, so that even if u exit the app and run it again, the data remains (similar to databases)
  Each book has a title and a description. The title is a string and the description is a string.
  Each book should also get an unique autogenerated id every time it is created
  The expected API endpoints are defined below,
  1.GET / - Retrieve all book items
    Description: Returns a list of all book items.
    Response: 200 OK with an array of book items in JSON format.
    Example: GET http://localhost:3000/books
  2.GET /books/:id - Retrieve a specific book item by ID
    Description: Returns a specific book item identified by its ID.
    Response: 200 OK with the book item in JSON format if found, or 404 Not Found if not found.
    Example: GET http://localhost:3000/books/123
  3. POST /books - Create a new book item
    Description: Creates a new book item.
    Request Body: JSON object representing the book item.
    Response: 201 Created with the ID of the created book item in JSON format. eg: {id: 1}
    Example: POST http://localhost:3000/books
    Request Body: { "title": "Buy book", "completed": false, description: "I should buy books" }
  4. PUT /books/:id - Update an existing book item by ID
    Description: Updates an existing book item identified by its ID.
    Request Body: JSON object representing the updated book item.
    Response: 200 OK if the book item was found and updated, or 404 Not Found if not found.
    Example: PUT http://localhost:3000/books/123
    Request Body: { "title": "Buy groceries", "completed": true }
  5. DELETE /books/:id - Delete a book item by ID
    Description: Deletes a book item identified by its ID.
    Response: 200 OK if the book item was found and deleted, or 404 Not Found if not found.
    Example: DELETE http://localhost:3000/books/123
    - For any other route not defined in the server return 404
