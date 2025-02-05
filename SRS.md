# Software Requirements Specification (SRS)

## Introduction

This SRS document describes the requirements for a text2video platform for students and teachers. The platform will allow users to upload academic material in various formats and generate videos based on free-text prompts.

## System Features

### User Management

* Users can create and manage their accounts
* Users can log in and log out of the platform

### Academic Material Upload

* Users can upload academic material in the following formats: PDF, PPT, Word DOCX, and TXT
* The platform will include an omni uploader that can handle these file types and extract the relevant information for the video generation process

### Textual Prompts

* Users can enter free-text prompts to guide the content of the generated videos
* The platform will include guardrails on the content being generated to ensure that it is appropriate and relevant for academic learning

### Video Generation

* The platform will generate videos based on the uploaded academic material and textual prompts
* Users can customize the type of visuals or animations used in the videos

## Technical Requirements

* The platform will be hosted on a secure and scalable server infrastructure
* The platform will use modern web technologies, such as HTML, CSS, and JavaScript, to ensure cross-platform compatibility and a responsive design
* The platform will include robust error handling and validation to ensure the integrity of the uploaded academic material and generated videos

## Potential Challenges

* Ensuring the accuracy and relevance of the generated videos based on the free-text prompts
* Handling the various file formats and extracting the relevant information for the video generation process
* Implementing effective guardrails on the content being generated to ensure that it is appropriate for academic learning

- link to API DOCS [./API.md]