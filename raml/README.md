# RAML

## Example

```raml
#%RAML 1.0
---
title: Questions
/questions:
  displayName: Resources related to questions in the API.
  get:
    description: List All Questions
    responses:
      200:
        body:
          application/json:
            type: array
            example: |
              [
                {
                  "question": "Favourite programming language?",
                  "published_at": "2014-11-11T08:40:51.620Z",
                  "url": "/questions/1",
                  "choices": [
                    {
                      "choice": "Swift",
                      "url": "/questions/1/choices/1",
                      "votes": 2048
                    }, {
                      "choice": "Python",
                      "url": "/questions/1/choices/2",
                      "votes": 1024
                    }, {
                      "choice": "Objective-C",
                      "url": "/questions/1/choices/3",
                      "votes": 512
                    }, {
                      "choice": "Ruby",
                      "url": "/questions/1/choices/4",
                      "votes": 256
                    }
                  ]
                }
              ]
  post:
    description: Create a New Question
    body:
      application/json:
        type: object
        example: |
          {
            "question": "Favourite programming language?",
            "choices": [
              "Swift",
              "Python",
              "Objective-C",
              "Ruby"
            ]
          }
    responses:
      201:
        headers:
          Location:
            type: string
            example: /questions/1
        body:
          application/json:
            type: object
            example: |
              {
                "question": "Favourite programming language?",
                "published_at": "2014-11-11T08:40:51.620Z",
                "url": "/questions/1",
                "choices": [
                  {
                    "choice": "Swift",
                    "url": "/questions/1/choices/1",
                    "votes": 0
                  }, {
                    "choice": "Python",
                    "url": "/questions/1/choices/2",
                    "votes": 0
                  }, {
                    "choice": "Objective-C",
                    "url": "/questions/1/choices/3",
                    "votes": 0
                  }, {
                    "choice": "Ruby",
                    "url": "/questions/1/choices/4",
                    "votes": 0
                  }
                ]
              }
  /{question_id}:
    uriParameters:
      question_id:
        description: ID of the Question in the form of an integer
        type: integer
    get:
      description: View a Questions Detail
      responses:
        200:
          body:
            application/json:
              type: object
              example: |
                {
                  "question": "Favourite programming language?",
                  "published_at": "2014-11-11T08:40:51.620Z",
                  "url": "/questions/1",
                  "choices": [
                    {
                      "choice": "Swift",
                      "url": "/questions/1/choices/1",
                      "votes": 2048
                    }, {
                      "choice": "Python",
                      "url": "/questions/1/choices/2",
                      "votes": 1024
                    }, {
                      "choice": "Objective-C",
                      "url": "/questions/1/choices/3",
                      "votes": 512
                    }, {
                      "choice": "Ruby",
                      "url": "/questions/1/choices/4",
                      "votes": 256
                    }
                  ]
                }
    delete:
      responses:
        204:
```

## Install

`npm install -g raml2html`

## Command

`raml2html api.raml > api.html`
