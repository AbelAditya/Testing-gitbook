# REST API Documentation for Text2Video Platform

## Introduction

The Text2Video platform provides a REST API for interacting with the platform programmatically. The API uses HTTP requests with JSON payloads for communication.

## API Endpoints

### User Management

* `POST /users/register`: Register a new user.
* `POST /users/login`: Log in to the platform.
* `PUT /users/profile`: Update user profile information.
* `DELETE /users/profile`: Delete the current user's account.

### Academic Material Upload

* `POST /materials/upload`: Upload a new academic material.
* `GET /materials/{materialId}`: Retrieve the details of a specific academic material.
* `PUT /materials/{materialId}`: Update a specific academic material.
* `DELETE /materials/{materialId}`: Delete a specific academic material.

### Text Prompt Entry

* `POST /prompts`: Create a new text prompt.
* `GET /prompts/{promptId}`: Retrieve the details of a specific text prompt.
* `PUT /prompts/{promptId}`: Update a specific text prompt.
* `DELETE /prompts/{promptId}`: Delete a specific text prompt.

### Video Generation

* `POST /videos`: Generate a new video based on an academic material and text prompt.
* `GET /videos/{videoId}`: Retrieve the details of a specific video.
* `DELETE /videos/{videoId}`: Delete a specific video.

## Error Handling

The API uses HTTP status codes to indicate the success or failure of a request. The following status codes are used:

* `200 OK`: The request was successful.
* `201 Created`: A new resource was created.
* `204 No Content`: The request was successful, but there is no content to return.
* `400 Bad Request`: The request was invalid or missing required parameters.
* `401 Unauthorized`: The user is not authenticated.
* `403 Forbidden`: The user is not authorized to access the requested resource.
* `404 Not Found`: The requested resource was not found.
* `500 Internal Server Error`: An unexpected error occurred on the server.

## Security

The API uses JSON Web Tokens (JWT) for authentication and authorization. The `Authorization` header should be included in all API requests, with the format `Bearer {token}`.

## Rate Limiting

The API may impose rate limits on the number of requests that can be made within a given time period. If a request is rate limited, the API will return a `429 Too Many Requests` status code.