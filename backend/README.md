
# Trivia API
Trivia api is a web application that allows people to hold trivia on a regular basis using a webpage to manage the trivia app and play the game.

The app allows one to: 

1) Display questions - both all questions and by category. Questions should show the question, category and difficulty rating by default and can show/hide the answer. 
2) Delete questions.
3) Add questions and require that they include question and answer text.
4) Search for questions based on a text query string.
5) Play the quiz game, randomizing either all questions or within a specific category. 

## Getting Started

### Installing Dependencies

#### Python 3.7

Follow instructions to install the latest version of python for your platform in the [python docs](https://docs.python.org/3/using/unix.html#getting-and-installing-the-latest-version-of-python)

#### Virtual Enviornment

Working within a virtual environment is recommended.

#### PIP Dependencies

navigate to the `/backend` directory and run:

```bash
pip install -r requirements.txt
```

This will install all of the required packages in the `requirements.txt` file.

##### Key Dependencies

- [Flask](http://flask.pocoo.org/)  is a lightweight backend microservices framework. Flask is required to handle requests and responses.

- [SQLAlchemy](https://www.sqlalchemy.org/) is the Python SQL toolkit and ORM we'll use handle the lightweight sqlite database. You'll primarily work in app.py and can reference models.py. 

- [Flask-CORS](https://flask-cors.readthedocs.io/en/latest/#) is the extension we'll use to handle cross origin requests from our frontend server. 

## Database Setup
With Postgres running, restore a database using the trivia.psql file provided. From the backend folder in terminal run:
```bash
psql trivia < trivia.psql
```

## Running the server

From within the `backend` directory

To run the server, execute:

```bash
export FLASK_APP=flaskr
export FLASK_ENV=development
flask run
```


## Testing
To run the tests, run
```
dropdb trivia_test
createdb trivia_test
psql trivia_test < trivia.psql
python test_flaskr.py
```

#### Frontend Dependencies

This project uses NPM to manage software dependencies. from the `frontend` directory run:

```bash
npm install
```

## Running the Frontend in Dev Mode

The frontend app was built using create-react-app. In order to run the app in development mode use ```npm start```. You can change the script in the ```package.json``` file. 

Open [http://localhost:3000](http://localhost:3000) to view it in the browser. The page will reload if you make edits.<br>

```bash
npm start
```

## API Reference

### Getting Started

* Backend Base URL: `http://127.0.0.1:5000/`
* Frontend Base URL: `http://127.0.0.1:3000/`
* Authentication: Authentication or API keys are not used in the project yet.

### Error Handling

Errors are returned in the following json format:

```json
      {
        "success": "False",
        "error": 422,
        "message": "Unprocessable entity",
      }
```

The error codes currently returned are:

* 400 – bad request
* 404 – resource not found
* 422 – unprocessable
* 500 – internal server error


### Endpoints

#### GET /categories

- General: 
  - Returns all the categories.

- Sample:  `curl http://127.0.0.1:5000/categories`

```json
    {
        "categories": {
            "1": "Science", 
            "2": "Art", 
            "3": "Geography", 
            "4": "History", 
            "5": "Entertainment", 
            "6": "Sports"
        }, 
        "success": true
    }
```

#### GET /questions
- General:
  - Returns all questions
  - questions ar### Getting Started

* Backend Base URL: `http://127.0.0.1:5000/`
* Frontend Base URL: `http://127.0.0.1:3000/`
* Authentication: Authentication or API keys are not used in the project yet.

### Error Handling

Errors are returned in the following json format:

```json
      {
        "success": "False",
        "error": 422,
        "message": "Unprocessable entity",
      }
```

The error codes currently returned are:

* 400 – bad request
* 404 – resource not found
* 422 – unprocessable
* 500 – internal server error


### Endpoints

#### GET /categories

- General: 
  - Returns all the categories.

- Sample:  `curl http://127.0.0.1:5000/categories`

```json
    {
        "categories": {
            "1": "Science", 
            "2": "Art", 
            "3": "Geography", 
            "4": "History", 
            "5": "Entertainment", 
            "6": "Sports"
        }, 
        "success": true
    }
```

#### GET /questions
- General:
  - Returns all questions
  - questions are in a paginated.
  - pages could be requested by a query string

- Sample: `curl http://127.0.0.1:5000/questions`<br>

```json
        {
    "categories": {
        "1": "Science",
        "2": "Art",
        "3": "Geography",
        "4": "History",
        "5": "Entertainment",
        "6": "Sports"
    },
    "questions": [
        {
            "answer": "Tom Cruise",
            "category": 5,
            "difficulty": 4,
            "id": 4,
            "question": "What actor did author Anne Rice first denounce, then praise in the role of her beloved Lestat?"
        },
        {
            "answer": "Maya Angelou",
            "category": 4,
            "difficulty": 2,
            "id": 5,
            "question": "Whose autobiography is entitled 'I Know Why the Caged Bird Sings'?"
        },
        {
            "answer": "Edward Scissorhands",
            "category": 5,
            "difficulty": 3,
            "id": 6,
            "question": "What was the title of the 1990 fantasy directed by Tim Burton about a young man with multi-bladed appendages?"
        },
        {
            "answer": "Muhammad Ali",
            "category": 4,
            "difficulty": 1,
            "id": 9,
            "question": "What boxer's original name is Cassius Clay?"
        },
        {
            "answer": "Brazil",
            "category": 6,
            "difficulty": 3,
            "id": 10,
            "question": "Which is the only team to play in every soccer World Cup tournament?"
        },
        {
            "answer": "Uruguay",
            "category": 6,
            "difficulty": 4,
            "id": 11,
            "question": "Which country won the first ever soccer World Cup in 1930?"
        },
        {
            "answer": "George Washington Carver",
            "category": 4,
            "difficulty": 2,
            "id": 12,
            "question": "Who invented Peanut Butter?"
        },
        {
            "answer": "Lake Victoria",
            "category": 3,
            "difficulty": 2,
            "id": 13,
            "question": "What is the largest lake in Africa?"
        },
        {
            "answer": "The Palace of Versailles",
            "category": 3,
            "difficulty": 3,
            "id": 14,
            "question": "In which royal palace would you find the Hall of Mirrors?"
        },
        {
            "answer": "Agra",
            "category": 3,
            "difficulty": 2,
            "id": 15,
            "question": "The Taj Mahal is located in which Indian city?"
        }
    ],
    "success": true,
    "total_questions": 19
}
```

#### DELETE /questions/<int:id\>


- General:
  - Deletes a question by id form the url parameter.

- Sample: `curl http://127.0.0.1:5000/questions/6 -X DELETE`

```json
        {
          "success": "True",
          "message": "Question successfully deleted"
        }
```

#### POST /questions

- General:
  - Creates a new question based on a payload.

- Sample: `curl http://127.0.0.1:5000/questions -X POST -H "Content-Type: application/json" -d '{
            "question": "Frankie Fredericks represented which African country in athletics?",
            "answer": "Namibia",
            "difficulty": 3,
            "category": "6"
        }'`

```json
{
  "message": "Question successfully created!",
  "success": true
}
```

#### POST /questions/search

- General:
  - returns questions that has the search substring

- Sample: `curl http://127.0.0.1:5000/questions/search -X POST -H "Content-Type: application/json" -d '{"searchTerm": "Anne Rice"}'`

```json
{
  "questions": [
    {
      "answer": "Tom Cruise",
      "category": 5,
      "difficulty": 4,
      "id": 4,
      "question": "What actor did author Anne Rice first denounce, then praise in the role of her beloved Lestat?"
    }
  ],
  "success": true,
  "total_questions": 20
}
```

#### GET /categories/<int:id\>/questions

- General:
### Endpoints

#### GET /categories

- General: 
  - Returns all the categories.

- Sample:  `curl http://127.0.0.1:5000/categories`

```json
    {
        "categories": [
      {
        "id": 1,
        "type": "sports"
      },
      {
        "id": 2,
        "type": "Technology"
      },
      {
        "id": 3,
        "type": "Space"
      },
      {
        "id": 7,
        "type": "Art"
      },
      {
        "id": 8,
        "type": "Entertainment"
      },
      {
        "id": 9,
        "type": "Geography"
      },
      {
        "id": 10,
        "type": "History"
      }
    ],
    "success": true
  }
```

#### GET /questions
- General:
  - Returns all questions
  - questions are in a paginated.
  - pages could be requested by a query string

- Sample: `curl http://127.0.0.1:5000/questions`<br>

```json
        {
     "categories": [
    {
      "id": 1,
      "type": "sports"
    },
    {
      "id": 2,
      "type": "Technology"
    },
    {
      "id": 3,
      "type": "Space"
    },
    {
      "id": 7,
      "type": "Art"
    },
    {
      "id": 8,
      "type": "Entertainment"
    },
    {
      "id": 9,
      "type": "Geography"
    },
    {
      "id": 10,
      "type": "History"
    }
  ],
  "current_category": null,
  "questions": [
    {
      "answer": "Six",
      "category": "1",
      "difficulty": 3,
      "id": 1,
      "question": "When Michael Jordan played for the Chicago Bulls, how many NBA Championships did he win?"
    },
    {
      "answer": "Serena",
      "category": "1",
      "difficulty": 3,
      "id": 2,
      "question": "Which Williams sister has won more Grand Slam titles?"
    },
    {
      "answer": "Michael Schumacher",
      "category": "1",
      "difficulty": 3,
      "id": 3,
      "question": "Which racer holds the record for the most Grand Prix wins?"
    },
    {
      "answer": "Hammer throw",
      "category": "1",
      "difficulty": 3,
      "id": 7,
      "question": "Which of these events is NOT part of a decathlon?"
    },
    {
      "answer": "Edmonton Oilers",
      "category": "1",
      "difficulty": 3,
      "id": 8,
      "question": "Which hockey team did Wayne Gretzky play for in the \u201880s?"
    },
    {
      "answer": "1877",
      "category": "1",
      "difficulty": 4,
      "id": 9,
      "question": "In what year was the first ever Wimbledon Championship held?"
    },
    {
      "answer": "11",
      "category": "1",
      "difficulty": 5,
      "id": 10,
      "question": "How many soccer players should each team have on the field at the start of each match?"
    },
    {
      "answer": "HyperText Transfer Protocol",
      "category": "1",
      "difficulty": 2,
      "id": 11,
      "question": "What does \u201cHTTP\u201d stand for?"
    },
    {
      "answer": "kilobyte",
      "category": "1",
      "difficulty": 2,
      "id": 12,
      "question": "What is often seen as the smallest unit of memory?"
    },
    {
      "answer": "Hotmail",
      "category": "1",
      "difficulty": 4,
      "id": 13,
      "question": "Which email service is owned by Microsoft?"
    }
  ],
  "success": true,
  "total_questions": 26

}
```

#### DELETE /questions/<int:id\>


- General:
  - Deletes a question by id form the url parameter.

- Sample: `curl http://127.0.0.1:5000/questions/3 -X DELETE`

```json
        {
          "success": "True",
          "message": "Question successfully deleted"
        }
```

#### POST /questions

- General:
  - Creates a new question based on a payload.

- Sample: `curl http://127.0.0.1:5000/questions -X POST -H "Content-Type: application/json" -d '{
            "question": "Frankie Fredericks represented which African country in athletics?",
            "answer": "Namibia",
            "difficulty": 3,
            "category": "6"
        }'`

```json
{
  "message": "Question successfully created!",
  "success": true
}
```

#### POST /questions/search

- General:
  - returns questions that has the search substring

- Sample: `curl http://127.0.0.1:5000/questions/search -X POST -H "Content-Type: application/json" -d '{"searchTerm": "Anne Rice"}'`

```json
{
  "questions": [
    {
      "answer": "Hotmail",
      "category": "1",
      "difficulty": 4,
      "id": 13,
      "question": "Which email service is owned by Microsoft?"
    }
  ],
  "success": true,
  "total_questions": 27
}
```

#### GET /categories/<int:id\>/questions

- General:
  - Gets questions by category using the id from the url parameter.
- Sample: `curl http://127.0.0.1:5000/categories/1/questions`<br>

```json
{
      "answer": "Six",
      "category": "1",
      "difficulty": 3,
      "id": 1,
      "question": "When Michael Jordan played for the Chicago Bulls, how many NBA Championships did he win?"
    },
    {
      "answer": "Serena",
      "category": "1",
      "difficulty": 3,
      "id": 2,
      "question": "Which Williams sister has won more Grand Slam titles?"
    },
    {
      "answer": "Michael Schumacher",
      "category": "1",
      "difficulty": 3,
      "id": 3,
      "question": "Which racer holds the record for the most Grand Prix wins?"
    },
    {
      "answer": "Hammer throw",
      "category": "1",
      "difficulty": 3,
      "id": 7,
      "question": "Which of these events is NOT part of a decathlon?"
    },
    {
      "answer": "Edmonton Oilers",
      "category": "1",
      "difficulty": 3,
      "id": 8,
      "question": "Which hockey team did Wayne Gretzky play for in the \u201880s?"
    },
    {
      "answer": "1877",
      "category": "1",
      "difficulty": 4,
      "id": 9,
      "question": "In what year was the first ever Wimbledon Championship held?"
    },
    {
      "answer": "11",
      "category": "1",
      "difficulty": 5,
      "id": 10,
      "question": "How many soccer players should each team have on the field at the start of each match?"
    },
    {
      "answer": "HyperText Transfer Protocol",
      "category": "1",
      "difficulty": 2,
      "id": 11,
      "question": "What does \u201cHTTP\u201d stand for?"
    },
    {
      "answer": "kilobyte",
      "category": "1",
      "difficulty": 2,
      "id": 12,
      "question": "What is often seen as the smallest unit of memory?"
    },
    {
      "answer": "Hotmail",
      "category": "1",
      "difficulty": 4,
      "id": 13,
      "question": "Which email service is owned by Microsoft?"
    }

  ],
  "success": true,
  "total_questions": 10
}

```

#### POST /quizzes

- General
  - Takes the category and previous questions in the request.
  - Return random question not in previous questions.

- Sample: `curl http://127.0.0.1:5000/quizzes -X POST -H "Content-Type: application/json" -d '{"previous_questions": [5, 9],
                                            "quiz_category": {"type": "History", "id": "4"}}'`

```json
{
   "question": {
    "answer": "General Motors, Fiat Chrysler Automobiles and Ford Motor Company",
    "category": "4",
    "difficulty": 2,
    "id": 22,
    "question": "Which companies are part of the Big Three?"
  },
  "success": true
}


```

## Testing
To run the tests, run
    dropdb trivia_test
    createdb trivia_test
    psql -U username trivia_test < trivia.psql
    python test_flaskr.py
```
    loader = self.auto_fn(name)
................
----------------------------------------------------------------------
Ran 16 tests in 16.230s

OK
```

## Authors
- Udacity provided the starter files for the project including the frontend
