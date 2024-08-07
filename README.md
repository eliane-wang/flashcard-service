# Flashcard Service
This microservice handles the storage, retrieval, and management of flashcard databases using text files for communication.

## Requesting Data
To request data from the microservice, you need to create a request text file in the 'requests' directory. Each request must follow a specific format depending on the action you want to perform.

### Create a Database
**Request File:** 'create_database.txt'

```
Action: CreateDatabase
DatabaseName: <database_name>
```

**Example:**

```
Action: CreateDatabase
DatabaseName: Biology
```

### Add a Flashcard
**Request File** 'add_flashcard.txt'

```
Action: AddFlashcard
DatabaseName: <database_name>
Question: <question_text>
Answer: <answer_text>
```

**Example:**

```
Action: AddFlashcard
DatabaseName: Biology
Question: What is the powerhouse of the cell?
Answer: Mitochondria
```

### Retrieve Flashcards
**Request File:** 'retrieve_flashcards.txt'

```
Action: RetrieveFlashcards
DatabaseName: <database_name>
```

**Example:**
```
Action: RetrieveFlashcards
DatabaseName: Biology
```

## Receiving Data
The microservice will process the requests and generate response text files in the 'responses' directory. The response file format and content will vary based on the request action.

### Response for Create Database
**Response File:** 'create_database_response.txt'

```
Message: <success_or_error_message>
```

**Example:**

```
Message: Database 'Biology' created successfully.
```

### Response for Add Flashcard
**Response File:** 'add_flashcard_response.txt'

```
Message: <success_or_error_message>
```

**Example:**

```
Message: Flashcard added successfully to 'Biology'.
```

### Response for Retrieve Flashcards
**Response File:** 'retrieve_flashcards_response.txt'

```
{
  "databaseName": "<database_name>",
  "flashcards": [
    {
      "question": "<question_text>",
      "answer": "<answer_text>"
    },
    ...
  ]
}
```

**Example:**

```
{
  "databaseName": "Biology",
  "flashcards": [
    {
      "question": "What is the powerhouse of the cell?",
      "answer": "Mitochondria"
    },
    {
      "question": "What is the basic unit of life?",
      "answer": "Cell"
    }
  ]
}
```

## UML Sequence Diagram
The below diagram illustrates how requesting and receiving data works using text files as the communication pipeline.

![Sequence diagram](https://github.com/user-attachments/assets/74393e96-faee-4529-9685-d3a75e91909c)


