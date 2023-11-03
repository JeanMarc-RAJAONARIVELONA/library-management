# library-management

API that manages library.

# Petstore Link

[You can see here the UI in Petsore](https://petstore.swagger.io/?url=https://raw.githubusercontent.com/JeanMarc-RAJAONARIVELONA/library-management/TD1/docs/api.yml)

# This API provides two endpoints:

## Books

### Get all books

- HTTP Method: GET
- Endpoint: /books
- Tags: Books
- Summary: Get all books
- Description: Retrieve a list of all books, which - are ordered by their updated datetime.
- Operation ID: getBooks

#### Query Parameters

- `bookName` (optional): Filter returned books by given name.
- `releaseDateRange` (optional): Filter books by release date range.

#### Responses

- 200: The list of filtered books.
- Content Type: application/json
- Schema: Book

### Create or update a list of books

- HTTP Method: PUT
- Endpoint: /books
- Tags: Books
- Summary: Create or update a list of books
- Operation ID: crupdateBooks

#### Request Body

- Content Type: application/json
- Schema: Array of Book

#### Responses

- 200: The list of created or updated books.
- Content Type: application/json
- Schema: Array of Book

## Authors

### Get all authors

- HTTP Method: GET
- Endpoint: /authors
- Tags: Authors
- Summary: Get all authors
- Description: Retrieve a list of all authors or filter them by name.
- Operation ID: getAuthors

#### Query Parameters

- authorName (optional): Filter authors by name.

#### Responses

- 200: List of authors.
- Content Type: application/json
- Schema: Array of Author

### Create or update a list of authors

- HTTP Method: PUT
- Endpoint: /authors
- Tags: Authors
- Summary: Create or update a list of authors
- Operation ID: crupdateAuthors

#### Request Body

- Content Type: application/json
- Schema: Array of Author

### Delete an author by ID

- HTTP Method: DELETE
- Endpoint: /authors/{authorId}
- Tags: Authors
- Summary: Delete an author by ID
- Operation ID: deleteAuthor

#### Path Parameters

- authorId (required): ID of the author to delete.

#### Responses

- 204: Author deleted successfully

# Data Models

## Book

- Type: Object
- Properties:
  - id: String
  - bookName: String
  - author: String
  - pageNumbers: Integer
  - topic: String
    - Allowed values: ROMANCE, COMEDY, OTHER
  - releaseDate: String (Format: date)

## Author

- Type: Object
- Properties:
  - id: String
  - name: String
  - sex: String
    - Allowed values: M, F
