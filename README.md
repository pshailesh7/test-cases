# API Testing Practice Collection for Postman

A comprehensive Postman collection designed for learning and practicing API testing. It includes **35+ requests** organized across 10 folders, covering all major API testing concepts with ready-to-run test scripts.

## Public APIs Used

| API | Base URL | Description |
|-----|----------|-------------|
| JSONPlaceholder | `https://jsonplaceholder.typicode.com` | Fake REST API for testing CRUD operations |
| ReqRes | `https://reqres.in/api` | Hosted REST API for testing auth, pagination, and CRUD |
| httpbin | `https://httpbin.org` | HTTP request/response inspection service |

All APIs are free, public, and require no API keys.

## Getting Started

1. **Import the Collection** -- Open Postman, click **Import**, and select `API_Testing_Practice.postman_collection.json`.
2. **Import the Environment** -- Click **Import** again and select `API_Testing_Practice.postman_environment.json`.
3. **Select the Environment** -- In the top-right corner of Postman, select **API Testing Practice Environment** from the environment dropdown.
4. **Run Requests** -- Open any folder and send individual requests, or use the **Collection Runner** to run all requests in sequence.

## Collection Structure

### 01 - GET Requests
- Get All Posts
- Get Single Post by ID
- Get Posts with Query Parameters
- Get Comments for a Post (nested resources)
- Get All Users (nested object validation)
- Get Users List (paginated with ReqRes)

### 02 - POST Requests
- Create a New Post (JSON body)
- Create User on ReqRes (with variable chaining)
- Register User -- Successful (token storage)
- Login User -- Successful
- POST with Form Data (URL-encoded)

### 03 - PUT & PATCH Requests
- PUT -- Full Update Post
- PATCH -- Partial Update Post
- PUT -- Update User on ReqRes (timestamp validation)

### 04 - DELETE Requests
- Delete a Post (200 response)
- Delete a User on ReqRes (204 No Content)

### 05 - Negative Testing & Error Handling
- Get Non-Existent Resource (404)
- Register Without Password (400)
- Login Without Password (400)
- Invalid HTTP Method (405)
- Delayed Response (timeout testing)

### 06 - Headers & Authentication
- Inspect Request Headers (custom headers, dynamic GUID)
- Basic Authentication
- Bearer Token Authentication

### 07 - Pre-request Scripts & Dynamic Data
- Dynamic Post with Random Data (pre-request script)
- Request with Timestamp & UUID (dynamic variables)

### 08 - Response Validation & Schema Testing
- JSON Schema Validation -- User
- JSON Schema Validation -- Post List
- Validate Response Headers

### 09 - Request Chaining & Workflows
- Step 1: Create a User (stores ID)
- Step 2: Update the User (uses stored ID)
- Step 3: Delete the User (cleans up)

### 10 - Advanced Techniques
- Response Status Code Ranges
- Cookie Handling
- IP and Origin Info
- XML Response Handling
- Gzip Compressed Response
- Multiple Assertions Pattern (comprehensive example)

## Testing Concepts Covered

- **Status code validation** -- Verify 200, 201, 204, 400, 404, 405 responses
- **Response body assertions** -- Validate JSON fields, data types, and values
- **JSON Schema validation** -- Contract testing with `tv4.validate()`
- **Header assertions** -- Validate Content-Type, custom headers, and cache controls
- **Response time checks** -- Assert performance thresholds
- **Query and path parameters** -- Filtering, pagination, and resource lookup
- **Request body formats** -- JSON, form-data, URL-encoded
- **Authentication** -- Basic Auth, Bearer Token, registration/login flows
- **Pre-request scripts** -- Dynamic data generation, timestamps, random values
- **Collection variables** -- Store and reuse data across requests
- **Request chaining** -- Pass data between sequential requests (CRUD workflow)
- **Negative testing** -- Missing fields, invalid methods, non-existent resources
- **Cookie handling** -- Set and validate cookies
- **XML responses** -- Non-JSON response format testing
- **Compression** -- Gzip response handling

## Running with Newman (CLI)

You can also run this collection from the command line using [Newman](https://github.com/postmanlabs/newman):

```bash
# Install Newman
npm install -g newman

# Run the collection
newman run API_Testing_Practice.postman_collection.json \
  -e API_Testing_Practice.postman_environment.json

# Run with HTML report
npm install -g newman-reporter-htmlextra
newman run API_Testing_Practice.postman_collection.json \
  -e API_Testing_Practice.postman_environment.json \
  -r htmlextra
```

## Tips for Practice

1. **Read the descriptions** -- Each request has a description explaining what to practice.
2. **Check the Tests tab** -- Review existing test scripts to learn assertion patterns.
3. **Modify and experiment** -- Change request bodies, parameters, and assertions.
4. **Use the Console** -- Open the Postman Console (Ctrl+Alt+C) to see `console.log()` output.
5. **Run the Collection Runner** -- Execute all requests in order to see the chaining workflow in action.
6. **Add your own tests** -- Extend the collection with your own assertions and edge cases.
