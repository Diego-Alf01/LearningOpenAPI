# OpenAPI
*https://www.openapis.org/* Open API website

## Document structure
    -JSON 
    -YAML
  

## Open API editor
    - swagger api

## Tipe Data
### Open API tipe data
    -integer -> int31
    -integer -> int64
    -number -> Float
    -number -> double
    -string -> byte / binary / date / date-time

## Info Object || Server || External Documentation || Path

```
{
    "openapi" : "3.0.3",
    "info" : {
        "title": "Todo List RestFull API",
        "version": "1",
        "description": "Open APU for todo list RestFull API",
        "contact": {
            "name": "Diego"
        }
    }, 
    "servers": [
        {
            "description": "TodoList RESTFull API Server",
            "url": "https://{environment}.programmerzamannow.com/api/v1",
            "variables": {
                "environment" : {
                    "description": "Server environment",
                    "default": "dev",
                    "enum": [
                        "dev",
                        "prod"
                    ]
                }
            }
        }
    ],
    "externalDocs": {
        "description": "Youtube Tutorial programmerzamannow",
        "url": "https://www.youtube.com/watch?v=o5b6TYSNK5c"
    },
    "paths": {
        "/todolist" :{
            "get" :{

            },
            "post":{

            }
        },
        "/todolist/{todolistId}" :{
            "put":{

            },
            "delete":{
                
            }
        }
    }
}

```

## Operation
    Setiap path di openAPI bisa memiliki > 1 operation || 1 url bisa miliki beberapa HTTP method (GET /POST)

### Detail Object Operation
    -tags [string]
    -summary string
    -description
    -eksternalDocs
    -operationId

### Contoh Kode
```
{
    "openapi" : "3.0.3",
    "info" : {
        "title": "Todo List RestFull API",
        "version": "1",
        "description": "Open APU for todo list RestFull API",
        "contact": {
            "name": "Diego"
        }
    }, 
    "servers": [
        {
            "description": "TodoList RESTFull API Server",
            "url": "https://{environment}.programmerzamannow.com/api/v1",
            "variables": {
                "environment" : {
                    "description": "Server environment",
                    "default": "dev",
                    "enum": [
                        "dev",
                        "prod"
                    ]
                }
            }
        }
    ],
    "externalDocs": {
        "description": "Youtube Tutorial programmerzamannow",
        "url": "https://www.youtube.com/watch?v=o5b6TYSNK5c"
    },
    "paths": {
        "/todolist" :{
            "get" :{
                "summary": "Get all todolist",
                "description": "Get all active todolist by default",
                "responses": {

                }
            },
            "post":{
                "summary": "Create new todolist",
                "description": "Create new todolist to database",
                "responses": {

                }
            }
        },
        "/todolist/{todolistId}" :{
            "put":{
                "summary": "Update existing todolist",
                "description": "Update existing todolist to database",
                "responses": {

                }
            },
            "delete":{
                "summary": "Delete existing todolist",
                "description": "Delete existing todolist from database",
                "responses": {
                    
                }
            }
        }
    }
}

```
## Parameter
    Data yang tidak dikirim melalui request body || Operation bisa memiliki > 1 parameter || OpenAPI mendukung berbagai jenis parameter[Query Paramater, Path Variable, Header, Cookie]

### Parameter Object
    -name (Required) -> string
    -in (Required) -> string -> lokasi paramater [query, path, header, cookie]
    -description -> string
    -required(boolean) -> default FALSE

### Kode Parameter
```
{
  "openapi": "3.0.3",
  "info": {
    "title": "Todo List RestFull API",
    "version": "1",
    "description": "Open API for todo list RestFull API",
    "contact": {
      "name": "Diego"
    }
  },
  "servers": [
    {
      "description": "TodoList RESTFull API Server",
      "url": "https://{environment}.programmerzamannow.com/api/v1",
      "variables": {
        "environment": {
          "description": "Server environment",
          "default": "dev",
          "enum": ["dev", "prod"]
        }
      }
    }
  ],
  "externalDocs": {
    "description": "Youtube Tutorial programmerzamannow",
    "url": "https://www.youtube.com/watch?v=o5b6TYSNK5c"
  },
  "paths": {
    "/todolist": {
      "get": {
        "summary": "Get all todolist",
        "description": "Get all active todolist by default",
        "parameters": [
          {
            "name": "includeDone",
            "in": "query",
            "required": false,
            "description": "Include done todolist in the result",
            "schema": {
              "type": "boolean"
            }
          },
          {
            "name": "name",
            "in": "query",
            "required": false,
            "description": "Filter todolist by name",
            "schema": {
              "type": "string"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "Successful response"
          }
        }
      },
      "post": {
        "summary": "Create new todolist",
        "description": "Create new todolist to database",
        "responses": {
          "201": {
            "description": "Todolist created"
          }
        }
      }
    },
    "/todolist/{todolistId}": {
      "put": {
        "summary": "Update existing todolist",
        "description": "Update existing todolist to database",
        "parameters": [
          {
            "name": "todolistId",
            "in": "path",
            "required": true,
            "description": "ID of the todolist to update",
            "schema": {
              "type": "string"
            }
          }
        ],
        "responses": {
          "200": {
            "description": "Todolist updated"
          }
        }
      },
      "delete": {
        "summary": "Delete existing todolist",
        "description": "Delete existing todolist from database",
        "parameters": [
          {
            "name": "todolistId",
            "in": "path",
            "required": true,
            "description": "ID of the todolist to delete",
            "schema": {
              "type": "string"
            }
          }
        ],
        "responses": {
          "204": {
            "description": "Todolist deleted"
          }
        }
      }
    }
  }
}

```

# last update := SCHEMA 44:07