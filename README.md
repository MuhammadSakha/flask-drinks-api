# Flask Drinks API

A simple REST API for managing drinks, built with Flask and Flask-SQLAlchemy (SQLite). This project was built as a learning exercise for building APIs.

## Features

- List all drinks
- Get a single drink by ID
- Add a new drink
- Delete a drink

## Tech Stack

- Python 3
- Flask
- Flask-SQLAlchemy
- SQLite

## Installation

```bash
# Clone the repository
git clone https://github.com/USERNAME/flask-drinks-api.git
cd flask-drinks-api

# Create and activate a virtual environment
python3 -m venv .venv
source .venv/bin/activate

# Install dependencies
pip install -r requirements.txt
```

## Create the Database

Run this once to create the tables:

```bash
flask --app application shell
>>> from application import db
>>> db.create_all()
>>> exit()
```

## Run the Server

```bash
flask --app application run --debug
```

The server runs at `http://127.0.0.1:5000`.

## Endpoints

| Method | Endpoint       | Description          |
|--------|----------------|----------------------|
| GET    | `/`            | Health check         |
| GET    | `/drinks`      | Get all drinks       |
| GET    | `/drinks/<id>` | Get a single drink   |
| POST   | `/drinks`      | Add a new drink      |
| DELETE | `/drinks/<id>` | Delete a drink       |

## Example Requests

**POST /drinks**

Header: `Content-Type: application/json`

```json
{
  "name": "Iced Tea",
  "description": "Sweet iced tea"
}
```

Response:

```json
{ "id": 1 }
```

**GET /drinks**

```json
{
  "drinks": [
    { "name": "Iced Tea", "description": "Sweet iced tea" }
  ]
}
```

**GET /drinks/1**

```json
{
  "name": "Iced Tea",
  "description": "Sweet iced tea"
}
```

**DELETE /drinks/1**

```json
{ "message": "yeet!" }
```

## Testing with Postman

1. Start the server.
2. Create a new request and enter the URL, for example `http://127.0.0.1:5000/drinks`.
3. For POST requests, open the **Body** tab, choose **raw**, and set the format to **JSON**.
4. Click **Send**.