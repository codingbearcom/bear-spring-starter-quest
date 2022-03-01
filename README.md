# Bear Spring Starter Quest

## Prerequisites

- Java dev environment (JDK + IDE)
- Docker and Docker compose


## Quest 1

Implement simple todo REST API with following endpoints

### Endpoint for listing todos (v1)

Response (200):

```json
[
  {
    "id": 1,
    "task": "Do shopping",
    "done": false
  }, {
    "id": 2,
    "task": "Morning jogging",
    "done": true
  }
]
```

### Endpoint for creating new todo (v1)

Request body:

```json
{
  "task": "Water flowers"
}
```

Response (201):

```json
{
  "id": 3,
  "task": "Water flowers",
  "done": false
}
```

### Endpoint for updating existing todo (v1)

- allows changing `task` and `done` fields (`id` is immutable)

Request body:

```json
{
  "done": true
}
```


Response (200):

```json
{
  "id": 3,
  "task": "Water flowers",
  "done": true
}
```

**When done save send your work at this point as commit.**


## Quest 2

Add Flyway into the project and make sure everything works correctly, namely:
- same schema is created via Flyway,
- existing data gets gracefully migrated.

**When done save send your work at this point as commit.**


## Quest 3

Let's extend our Todo app **while being backward compatible**
(i.e. all endpoints made in quest 1 should stay as are).

## Endpoint for listing todos (v2)

Response (200):

```json
[
  {
    "id": 1,
    "task": "Do shopping",
    "created": "2022-02-28T11:27:42Z",
    "done": null
  }, {
    "id": 2,
    "task": "Morning jogging",
    "created": "2022-02-28T13:08:42Z",
    "done": "2022-03-01T07:27:42Z"
  }
]
```

## Endpoint for creating new todo (v2)

(old endpoint with new logic)

Request body:

```json
{
  "task": "Water flowers"
}
```

Response (201):

```json
{
  "id": 3,
  "task": "Water flowers",
  "created": "2022-03-01T15:08:42Z",
  "done": null
}
```

### Endpoint for updating existing todo (v2)

- allows changing `task` and `done` fields (`id` is immutable)

Request body:

```json
{
  "done": true
}
```


Response (200):

```json
{
  "id": 3,
  "task": "Water flowers",
  "created": "2022-03-01T15:08:42Z",
  "done": "2022-03-01T17:58:42Z"
}
```


**When done save send your work at this point as commit.**
