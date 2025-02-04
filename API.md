**API Documentation for Text2Video Platform**

**1. Introduction**

The Text2Video platform provides a RESTful API for uploading academic material, submitting text prompts, and generating videos. The API uses JSON as the default data format and supports standard HTTP methods, such as GET, POST, PUT, and DELETE.

**2. API Endpoints**

2.1. **File Upload**

* `POST /api/upload`: Uploads a file in PDF, PPT, DOCX, or TXT format and returns a unique identifier for the uploaded file.

2.2. **Text Prompts**

* `POST /api/prompts`: Submits a free-text prompt and associates it with a previously uploaded file. Returns a unique identifier for the prompt and the associated file.

2.3. **Video Generation**

* `POST /api/generate`: Generates a video based on a previously submitted prompt and returns a unique identifier for the generated video.
* `GET /api/generate/{videoId}`: Retrieves a previously generated video by its unique identifier.

**3. API Request and Response Formats**

All API requests and responses use JSON as the default data format. Here are some example request and response formats for each endpoint:

3.1. **File Upload**

Request:
```json
{
  "file": {
    "name": "example.pdf",
    "type": "application/pdf",
    "size": 123456,
    "data": "JVBERi0xLjQKJcOkw7zDtsOfCjIgMCBvYmoKPDwvTGVuZ3RoIDMgMCBSPj4Kc3RyZWFtCkJUCjAgMCBUZAovRjEgMTIgVGYKKC4uLlR4dC4uLikKRVQKZW5kc3RyZWFtCmVuZG9iagoKMyAwIG9iagozOTAKZW5kb2JqCg=="
  }
}
```
Response:
```json
{
  "fileId": "12345678-abcd-1234-abcd-1234567890ab"
}
```
3.2. **Text Prompts**

Request:
```json
{
  "prompt": {
    "text": "Explain the concept of gravity",
    "fileId": "12345678-abcd-1234-abcd-1234567890ab"
  }
}
```
Response:
```json
{
  "promptId": "87654321-abcd-1234-abcd-1234567890ab",
  "fileId": "12345678-abcd-1234-abcd-1234567890ab"
}
```
3.3. **Video Generation**

Request:
```json
{
  "video": {
    "promptId": "87654321-abcd-1234-abcd-1234567890ab"
  }
}
```
Response:
```json
{
  "videoId": "45678901-abcd-1234-abcd-1234567890ab"
}
```
4. **Error Handling**

The API uses standard HTTP status codes to indicate success or failure. Here are some common error codes and their meanings:

* 400 Bad Request: The API request was invalid or contained invalid data.
* 401 Unauthorized: The API request required authentication but failed to provide valid credentials.
* 404 Not Found: The requested resource was not found.
* 500 Internal Server Error: The API encountered an unexpected error.

Please let me know if you have any further questions or clarifications regarding the API documentation.