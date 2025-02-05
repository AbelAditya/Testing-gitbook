# API Documentation

## Introduction

This API documentation describes the required REST API for a text2video platform for students and teachers. The API will allow users to upload academic material, enter textual prompts, and generate videos based on these inputs.

## Endpoints

### User Management

#### `POST /users`

* Description: Create a new user account
* Request Body:
```json
{
  "username": "string",
  "email": "string",
  "password": "string"
}
```
* Response:
```json
{
  "id": "integer",
  "username": "string",
  "email": "string"
}
```

#### `POST /users/login`

* Description: Log in to an existing user account
* Request Body:
```json
{
  "email": "string",
  "password": "string"
}
```
* Response:
```json
{
  "id": "integer",
  "username": "string",
  "email": "string",
  "token": "string"
}
```

#### `DELETE /users/logout`

* Description: Log out of the current user session
* Response: None

### Academic Material Upload

#### `POST /materials`

* Description: Upload new academic material
* Request Headers:
```json
{
  "Authorization": "Bearer <token>"
}
```
* Request Body:
```json
{
  "title": "string",
  "file": "file"
}
```
* Response:
```json
{
  "id": "integer",
  "title": "string",
  "file_type": "string",
  "created_at": "datetime",
  "updated_at": "datetime"
}
```

#### `GET /materials`

* Description: Retrieve a list of academic material
* Request Headers:
```json
{
  "Authorization": "Bearer <token>"
}
```
* Response:
```json
[
  {
    "id": "integer",
    "title": "string",
    "file_type": "string",
    "created_at": "datetime",
    "updated_at": "datetime"
  }
]
```

#### `GET /materials/{id}`

* Description: Retrieve the details of a specific academic material
* Request Headers:
```json
{
  "Authorization": "Bearer <token>"
}
```
* Response:
```json
{
  "id": "integer",
  "title": "string",
  "file_type": "string",
  "file_url": "string",
  "created_at": "datetime",
  "updated_at": "datetime"
}
```

#### `PUT /materials/{id}`

* Description: Update the details of a specific academic material
* Request Headers:
```json
{
  "Authorization": "Bearer <token>"
}
```
* Request Body:
```json
{
  "title": "string"
}
```
* Response:
```json
{
  "id": "integer",
  "title": "string",
  "file_type": "string",
  "file_url": "string",
  "created_at": "datetime",
  "updated_at": "datetime"
}
```

#### `DELETE /materials/{id}`

* Description: Delete a specific academic material
* Request Headers:
```json
{
  "Authorization": "Bearer <token>"
}
```
* Response: None

### Textual Prompts

#### `POST /prompts`

* Description: Create a new textual prompt
* Request Headers:
```json
{
  "Authorization": "Bearer <token>"
}
```
* Request Body:
```json
{
  "text": "string"
}
```
* Response:
```json
{
  "id": "integer",
  "text": "string",
  "created_at": "datetime",
  "updated_at": "datetime"
}
```

#### `GET /prompts`

* Description: Retrieve a list of textual prompts
* Request Headers:
```json
{
  "Authorization": "Bearer <token>"
}
```
* Response:
```json
[
  {
    "id": "integer",
    "text": "string",
    "created_at": "datetime",
    "updated_at": "datetime"
  }
]
```

#### `GET /prompts/{id}`

* Description: Retrieve the details of a specific textual prompt
* Request Headers:
```json
{
  "Authorization": "Bearer <token>"
}
```
* Response:
```json
{
  "id": "integer",
  "text": "string",
  "created_at": "datetime",
  "updated_at": "datetime"
}
```

#### `PUT /prompts/{id}`

* Description: Update the details of a specific textual prompt
* Request Headers:
```json
{
  "Authorization": "Bearer <token>"
}
```
* Request Body:
```json
{
  "text": "string"
}
```
* Response:
```json
{
  "id": "integer",
  "text": "string",
  "created_at": "datetime",
  "updated_at": "datetime"
}
```

#### `DELETE /prompts/{id}`

* Description: Delete a specific textual prompt
* Request Headers:
```json
{
  "Authorization": "Bearer <token>"
}
```
* Response: None

### Video Generation

#### `POST /videos`

* Description: Generate a new video based on academic material and textual prompt
* Request Headers:
```json
{
  "Authorization": "Bearer <token>"
}
```
* Request Body:
```json
{
  "material_id": "integer",
  "prompt_id": "integer"
}
```
* Response:
```json
{
  "id": "integer",
  "material_id": "integer",
  "prompt_id": "integer",
  "status": "string",
  "url": "string",
  "created_at": "datetime",
  "updated_at": "datetime"
}
```

#### `GET /videos`

* Description: Retrieve a list of generated videos
* Request Headers:
```json
{
  "Authorization": "Bearer <token>"
}
```
* Response:
```json
[
  {
    "id": "integer",
    "material_id": "integer",
    "prompt_id": "integer",
    "status": "string",
    "url": "string",
    "created_at": "datetime",
    "updated_at": "datetime"
  }
]
```

#### `GET /videos/{id}`

* Description: Retrieve the details of a specific generated video
* Request Headers:
```json
{
  "Authorization": "Bearer <token>"
}
```
* Response:
```json
{
  "id": "integer",
  "material_id": "integer",
  "prompt_id": "integer",
  "status": "string",
  "url": "string",
  "created_at": "datetime",
  "updated_at": "datetime"
}
```

## Error Handling

* The API will return a `400 Bad Request` status code for invalid requests, such as missing or incorrect parameters
* The API will return a `401 Unauthorized` status code for requests that require authentication but do not include a valid token
* The API will return a `403 Forbidden` status code for requests that are forbidden due to insufficient permissions
* The API will return a `404 Not Found` status code for resources that cannot be found
* The API will return a `500 Internal Server Error` status code for unexpected errors or exceptions