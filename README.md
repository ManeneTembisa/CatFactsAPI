API Testing for Catfact Ninja
Overview
This document outlines the approach to testing the Catfact Ninja API, detailing the aspects to be tested, the rationale behind these tests, and the methodologies employed. Additionally, it includes three example tests implemented using Postman, along with a description of the setup process.

What to Test
Endpoint Functionality: Verify that each API endpoint returns the expected responses for valid requests.

Input Validation: Ensure the API correctly handles invalid or unexpected inputs.

Performance: Assess the response times to ensure they meet acceptable thresholds.

Security: Confirm that the API is protected against common vulnerabilities and unauthorized access.

Data Integrity: Validate that the data returned by the API is accurate and consistent.

Why Test These Aspects
Endpoint Functionality: To confirm that the API operates as intended and provides the correct data.

Input Validation: To prevent potential errors or security issues arising from improper input handling.

Performance: To ensure a good user experience by maintaining quick response times.

Security: To protect the API and its data from unauthorized access and potential exploits.

Data Integrity: To maintain user trust by providing reliable and accurate information.

How to Test
Functional Testing: Use tools like Postman to send requests to each endpoint with both valid and invalid inputs, verifying that the responses are as expected.

Performance Testing: Utilize load testing tools to simulate multiple concurrent requests and measure response times.

Security Testing: Conduct tests for common vulnerabilities such as SQL injection, cross-site scripting (XSS), and ensure that data is transmitted securely.

Data Validation: Cross-reference the data returned by the API with authoritative sources to verify its accuracy.

Example Tests Using Postman
1. Retrieve a Random Cat Fact
Objective: Verify that the /fact endpoint returns a random cat fact.

Request:

Method: GET

URL: https://catfact.ninja/fact

Assertions:

Status code is 200 OK.

Response body contains a fact field with a non-empty string.

Response body contains a length field that matches the length of the fact string.

2. Retrieve a List of Cat Breeds with Pagination
Objective: Test the /breeds endpoint's ability to return a paginated list of cat breeds.

Request:

Method: GET

URL: https://catfact.ninja/breeds

Query Parameters:

limit: 5

page: 1

Assertions:

Status code is 200 OK.

Response body contains a data array with a maximum of 5 items.

Each item in the data array includes the fields: breed, country, origin, coat, and pattern.

3. Handle Invalid Endpoint Gracefully
Objective: Ensure the API returns an appropriate error for an invalid endpoint.

Request:

Method: GET

URL: https://catfact.ninja/nonexistent

Assertions:

Status code is 404 Not Found.

Response body contains an error message indicating the endpoint does not exist.

Process of Setting Up the Tests
Collection Creation: Created a new Postman collection named "Catfact Ninja API Tests" to organize the test requests.

Request Addition: Added individual requests for each endpoint to the collection, specifying the method, URL, and any required parameters.

Assertion Scripting: Utilized Postman's test scripting feature to write JavaScript assertions that validate the response status codes, body content, and structure.

Environment Configuration: Set up environment variables in Postman for dynamic data handling and to facilitate testing across different environments.

Execution and Iteration: Ran the tests, reviewed the results, and refined the tests as necessary to ensure comprehensive coverage and accuracy.

Additional Files
The exported Postman collection and any other necessary files are attached to this repository. To import and use the collection:

Download the Catfact_Ninja_API_Tests.postman_collection.json file from this repository.

Open Postman and navigate to the "Collections" tab.

Click on the "Import" button and select the downloaded JSON file.

The collection will be imported and ready for use.

By following this structured approach, we can ensure the Catfact Ninja API is thoroughly tested for functionality, performance, security, and data integrity.
