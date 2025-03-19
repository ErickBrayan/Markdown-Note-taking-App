# Markdown Note-taking App

A simple RESTful API for a note-taking application that allows users to upload Markdown or text files, check grammar, save notes, and render them as HTML.

## Features

- **Check Grammar:** An endpoint to check the grammar of a given Markdown (`.md`) or text (`.txt`) file.
- **Save Notes:** Upload and save Markdown (`.md`) or text (`.txt`) files via an API endpoint.
- **List Notes:** Retrieve a list of all saved notes.
- **Render Markdown as HTML:** Convert uploaded Markdown (`.md`) files into HTML format.

## Technologies Used

- **Java 17**
- **Spring Boot** (Spring Web)
- **CommonMark** (for Markdown parsing and rendering)
- **LanguageTool API** (for grammar checking)

## Installation & Running the Application

### Prerequisites

- Java 17 or later
- Maven installed

### Steps to Run

1. Clone the repository:
   ```sh
   git clone https://github.com/ErickBrayan/Markdown-Note-taking-App.git
   cd markdown-note-taking-app
   ```
2. Build the project using Maven:
   ```sh
   mvn clean install
   ```
3. Run the Spring Boot application:
   ```sh
   mvn spring-boot:run
   ```

The application will start at `http://localhost:8080`.

## API Endpoints

### 1. Check Grammar
**POST** `/check`
- **Request:** Multipart file upload (`.md` or `.txt` file required)
- **Response:**
  ```json
  [
    {
      "position": {
        "from": 1,
        "to": 5
      },
      "message": "Grammar mistake found",
      "suggestedReplacements": ["Suggested correction 1", "Suggested correction 2"]
    }
  ]
  ```

### 2. Save Note
**POST** `/save`
- **Request:** Multipart file upload (`.md` or `.txt` file required)
- **Response:**
  ```json
  {
    "message": "File was save successfully"
  }
  ```

### 3. List Notes
**GET** `/list-file`
- **Response:**
  ```json
  [
    "note1.md",
    "note2.txt"
  ]
  ```

### 4. Convert Markdown to HTML
**POST** `/covert-to-html`
- **Request:** Multipart file upload (`.md` file required)
- **Response:**
  ```html
  <h1>Markdown Title</h1>
  <p>This is some <strong>bold text</strong>.</p>
  ```


https://roadmap.sh/projects/markdown-note-taking-app
