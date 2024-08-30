# Swagger Petstore API Test Suite

This project contains a test suite for the Swagger Petstore API. It uses `chai` for assertions and includes tests for various CRUD operations on the `/pet` endpoint. The tests cover `POST`, `GET`, `PUT`, and `DELETE` methods to ensure the proper functioning of the API.

## Prerequisites

Before running the tests, make sure you have the following installed:

- Node.js
- npm (Node Package Manager)

## Installation

1. Clone the repository:

   git clone https://github.com/yourusername/api-swagger-automation.git
   cd api-swagger-automation/src

2. Install the necessary dependencies:

   npm install

3. Project Structure

 - api.action.js: Contains functions to interact with the Petstore API endpoints.
 - test: Contains the test files for various API operations.

4. Running the Tests

To run the tests, use the following command:

   npx mocha test.js  

# Test Cases

## POST Endpoint Tests

**Upload Image with petId, additionalMetadata, and file**:

Sends a POST request to upload an image with the specified petId, additionalMetadata, and file.
Asserts that the response status is 200 and checks the response data.

**Upload Image without additionalMetadata**:

Sends a POST request to upload an image without the additionalMetadata.
Asserts that the response status is 200 and checks the response data.

**Upload Image without file**:

Attempts to send a POST request without a file.
Expects a 500 Internal Server Error.

**Add a new pet**:

Sends a POST request to add a new pet with the specified data.
Asserts that the response status is 200 and verifies the pet data.

**Update a pet by ID**:

Sends a POST request to update an existing pet by its ID.
Asserts that the response status is 200 and verifies the response message.

## GET Endpoint Tests

**Get pets by status**:

Loops through different statuses (available, pending, sold) and sends a GET request to retrieve pets with each status.
Asserts that the response status is 200 and that the response data is an array.

**Get a single pet by ID**:

Sends a GET request to retrieve a single pet by its ID.
Asserts that the response status is 200 and verifies the pet data.

**Get a pet that does not exist**:

Attempts to retrieve a pet with an ID of 0.
Expects a 404 Not Found error.

## PUT Endpoint Tests**

**Update an existing pet**:

Sends a PUT request to update an existing pet with the provided data.
Asserts that the response status is 200 and verifies the pet data.

## DELETE Endpoint Tests

**Delete an existing pet**:

Sends a DELETE request to remove a pet by its ID.
Asserts that the response status is 200 and verifies the response message.

**Delete a pet that does not exist**:

Attempts to delete a pet with an ID of 0.
Expects a 404 Not Found error.

