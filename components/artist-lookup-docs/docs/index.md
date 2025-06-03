# Artist Lookup Service Documentation

Welcome to the Artist Lookup Service! This Service allows you to search for and retrieve metadata about musical artists.

## Base URL

```
https://api.fake-music.com/v1
```

---

## Authentication

All requests must include an API key.

**Header Example:**
```
Authorization: Bearer YOUR_API_KEY
```

---

## Endpoints

### 1. Search Artists

**GET** `/artists/search`

Search for artists by name.

**Query Parameters:**
| Name       | Type   | Description                 |
|------------|--------|-----------------------------|
| `query`    | string | Name or keyword to search   |
| `limit`    | int    | Max number of results (opt) |
| `offset`   | int    | Pagination offset (opt)     |

**Example Request:**
```
GET /artists/search?query=radiohead&limit=5
```

**Example Response:**
```json
{
  "results": [
    {
      "id": "123",
      "name": "Radiohead",
      "genre": "Alternative Rock",
      "year_started": 1985
    }
  ]
}
```

---

### 2. Get Artist Details

**GET** `/artists/{id}`

Retrieve full metadata for a specific artist.

**Path Parameters:**
| Name | Type   | Description          |
|------|--------|----------------------|
| `id` | string | ID of the artist     |

**Example Request:**
```
GET /artists/123
```

**Example Response:**
```json
{
  "id": "123",
  "name": "Radiohead",
  "genre": "Alternative Rock",
  "members": ["Thom Yorke", "Jonny Greenwood", "Ed O'Brien", "Colin Greenwood", "Philip Selway"],
  "year_started": 1985,
  "albums": [
    {
      "title": "OK Computer",
      "year": 1997
    },
    {
      "title": "Kid A",
      "year": 2000
    }
  ]
}
```

---

### 3. List All Genres

**GET** `/genres`

Retrieve a list of all supported music genres.

**Example Request:**
```
GET /genres
```

**Example Response:**
```json
{
  "genres": [
    "Alternative Rock",
    "Pop",
    "Hip-Hop",
    "Jazz",
    "Electronic"
  ]
}
```

---

## Error Codes

| Code | Message              | Description                        |
|------|----------------------|------------------------------------|
| 400  | Bad Request          | Missing or invalid parameters      |
| 401  | Unauthorized         | Missing or invalid API key         |
| 404  | Not Found            | Resource not found                 |
| 500  | Internal Server Error| Something went wrong on our end    |

---

## Contact

For support, please contact: `support@fake-music.com`

---

© 2025 Fake Music Inc.
