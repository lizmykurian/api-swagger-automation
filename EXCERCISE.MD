# Test Plan for Swagger Petstore API

## Project Overview

This test plan outlines the strategy, objectives, scope, and resources for testing the Swagger Petstore API's `/pet` endpoint. The goal is to ensure the API's functionality, reliability, and performance across various scenarios including CRUD operations.

## Objectives

- Validate that all CRUD operations (`POST`, `GET`, `PUT`, `DELETE`) on the `/pet` endpoint work as expected.
- Ensure that the API correctly handles both valid and invalid inputs.
- Verify that the API returns the appropriate HTTP status codes and response data.
- Test the API's behavior under normal and edge cases.

## Scope

### In Scope

- Testing the `/pet` endpoint with the following operations:
  - **POST**: Add a new pet, upload an image, update an existing pet.
  - **GET**: Retrieve pets by status, retrieve a single pet by ID.
  - **PUT**: Update an existing pet.
  - **DELETE**: Delete a pet by ID.
- Validating the correctness of the response data and HTTP status codes.
- Error handling and response verification for edge cases.

### Out of Scope

- Testing other endpoints in the Swagger Petstore API not related to `/pet`.
- Performance, load, and security testing.
- Integration testing with other systems or APIs.

## Test Strategy

### Testing Types

1. **Functional Testing**:
   - Verify the functionality of the CRUD operations.
   - Check the API's behavior with both valid and invalid inputs.

2. **Negative Testing**:
   - Test the API's response to invalid requests, such as missing required fields, incorrect data types, or nonexistent resources.

3. **Boundary Testing**:
   - Validate the API's handling of boundary conditions, such as minimum and maximum values for fields.

### Test Environment

- **API Base URL**: `https://petstore.swagger.io/`
- **Test Tools**:
  - **Programming Language**: JavaScript (Node.js)
  - **Test Framework**: Mocha
  - **Assertion Library**: Chai
- **Test Data**: Defined within the test cases, with various IDs, statuses, and file uploads.

### Test Execution

1. **Preconditions**:
   - Ensure the Swagger Petstore API is running and accessible.
   - Verify that all dependencies (Node.js, npm packages) are installed.

2. **Test Execution Flow**:
   - Run tests using `npm test`.
   - Tests will be executed in the following order:
     1. **POST**: Add pet, upload image, update pet.
     2. **GET**: Retrieve pets by status, retrieve a single pet, handle not found.
     3. **PUT**: Update an existing pet.
     4. **DELETE**: Delete pet, handle not found.

3. **Expected Results**:
   - All CRUD operations should return the expected HTTP status codes and response data.
   - Invalid requests should return appropriate error messages and status codes.

### Test Cases

#### POST Endpoint

- **Add a new pet**: Validate that a pet is successfully added with the correct attributes.
- **Upload an image**: Ensure image upload works with and without additional metadata.
- **Update a pet by ID**: Confirm that a pet's data is correctly updated.

#### GET Endpoint

- **Get pets by status**: Check that pets are retrieved correctly based on their status.
- **Get a single pet by ID**: Verify retrieval of a pet by its ID, including handling of not found cases.

#### PUT Endpoint

- **Update an existing pet**: Ensure the pet's data is correctly updated when a valid request is made.

#### DELETE Endpoint

- **Delete a pet by ID**: Validate that a pet is successfully deleted, and that attempting to delete a nonexistent pet returns a 404 error.

## Roles and Responsibilities

  - Responsible for planning, execution, and reporting of the test activities.
  - Responsible for fixing any bugs found during testing.

## Risks and Mitigations

- **Risk**: The API may return inconsistent data due to changes in the underlying data.
- **Mitigation**: Use controlled test data and reset the environment as needed.
- **Risk**: API downtime during testing.
- **Mitigation**: Schedule tests during known uptime periods, and monitor API status.

## Reporting

- **Test Results**: Console logging for tests on execution
- **Bug Reporting**: Bugs will be reported in the project's issue tracker with detailed steps to reproduce, expected and actual results, and severity.



