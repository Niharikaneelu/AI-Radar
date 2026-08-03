# AI Radar

# 05_API_Design.md

**Version:** 1.0

**Status:** Draft

**Architecture:** REST API

**Framework:** FastAPI

**Last Updated:** August 2026


# Table of Contents

1. API Overview
2. API Design Principles
3. Base URL
4. Authentication
5. Response Format
6. Error Format
7. Endpoints
8. Status Codes
9. Future APIs


# 1. API Overview

AI Radar exposes REST APIs that allow external applications to access processed AI news.

The APIs are designed to be:

- Fast
- Consistent
- Easy to extend
- Easy to consume
- JSON-based


# 2. API Design Principles

The API follows these principles:

- RESTful architecture
- Consistent naming
- Stateless requests
- Predictable responses
- Versionable

# 3. Base URL

Development

/api/v1

Future

/api/v2


# 4. Authentication

Version 1

No authentication required.

Future versions

- API Keys
- OAuth2
- JWT

# 5. Standard Response

Every successful request returns

```json
{
  "success": true,
  "message": "Request successful",
  "data": []
}
```

Every failed request returns

```json
{
  "success": false,
  "message": "Error description",
  "error": {}
}
```

# 6. Endpoints


## Get Latest News

GET

/api/v1/news/latest

Description

Returns latest AI news.

Parameters

| Parameter | Required | Description |
|------------|----------|-------------|
| limit | No | Number of articles |

Example

GET

/api/v1/news/latest?limit=10


## Get All News

GET

/api/v1/news

Supports

- pagination
- sorting
- filtering

Query Parameters

| Parameter | Description |
|------------|-------------|
| page | Page number |
| limit | Results per page |
| category | Category |
| source | News source |
| keyword | Search keyword |

Example

/api/v1/news?page=1&limit=20

## Get News by Category

GET

/api/v1/news/category/{category}

Example

/api/v1/news/category/Healthcare

## Search News

GET

/api/v1/news/search

Parameters

| Parameter | Required |
|------------|----------|
| q | Yes |

Example

/api/v1/news/search?q=robotics


## Get Single Article

GET

/api/v1/news/{id}

Returns one article.


## Get Categories

GET

/api/v1/categories

Returns available categories.


## Get Sources

GET

/api/v1/sources

Returns supported news providers.


## Trigger Collection

POST

/api/v1/collector/run

Purpose

Manually start collection.

Version 1

Admin use only.


## Get System Status

GET

/api/v1/system/status

Returns

- database status
- scheduler status
- API status


# 7. Example Response

```json
{
  "success": true,

  "message": "News fetched successfully",

  "data": [
    {
      "title": "...",

      "summary": "...",

      "category": "Healthcare",

      "source": "The Hindu",

      "published_at": "...",

      "url": "...",

      "keywords": [
        "AI",
        "Healthcare"
      ]
    }
  ]
}
```


# 8. HTTP Status Codes

| Code | Meaning |
|------|---------|
| 200 | Success |
| 201 | Created |
| 400 | Bad Request |
| 404 | Not Found |
| 422 | Validation Error |
| 500 | Internal Server Error |


# 9. Versioning Strategy

Current

/api/v1

Future

/api/v2

Breaking changes

↓

New version

No breaking changes

↓

Stay in current version


# 10. API Naming Rules

Use

- nouns
- lowercase
- plural resources

Correct

/news

/categories

/sources

Avoid

/getNews

/fetchLatest

/newsList


# 11. Pagination

Version 1

?page=1

&limit=20

Future

Cursor-based pagination


# 12. Filtering

Supported filters

- category
- source
- keyword
- date

Future

- importance
- language

# 13. Sorting

Supported

Newest First

Oldest First

Future

Most Relevant

Most Popular


# 14. API Documentation

FastAPI automatically generates

Swagger UI

/docs

Redoc

/redoc

These become the official interactive API documentation.


# 15. Future APIs

Version 2

POST

/news/bookmark

GET

/trending

GET

/reports

Version 3

POST

/chat

GET

/github

GET

/research

GET

/tools


# API Summary

The API is designed to provide a stable, reusable interface for websites, chatbots, digital signage systems, and future applications.

It follows REST principles and provides consistent JSON responses while remaining easy to extend in future versions.
