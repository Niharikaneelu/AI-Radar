# AI Radar

# 04_Database_Design.md

**Version:** 1.0

**Status:** Draft

**Database:** MongoDB

**Last Updated:** 4 August 2026

# Table of Contents

1. Database Overview
2. Database Design Principles
3. Collections
4. Article Schema
5. Source Schema
6. Category Schema
7. Indexes
8. Relationships
9. Data Validation
10. Future Collections


# 1. Database Overview

AI Radar uses MongoDB because news articles naturally fit a document-based structure.

Each news article is stored as a single document with its metadata, AI-generated information, and source details.


# 2. Database Design Principles

The database is designed to be:

- Flexible
- Scalable
- Easy to extend
- Optimized for searching
- Optimized for API responses

# 3. Collections

Version 1 uses the following collections:

```

articles

sources

categories

system_logs

```


# 4. Article Collection

Each document represents one processed AI news article.

Example structure

```json
{
  "_id": "ObjectId",

  "title": "Karnataka approves AI Centre of Excellence",

  "summary": "The Karnataka government approved a ₹12 crore Centre of Excellence at IIIT Raichur to promote AI research and innovation.",

  "content": "Original cleaned article text",

  "url": "https://example.com/article",

  "image_url": "https://...",

  "published_at": "2026-08-04T09:00:00Z",

  "collected_at": "2026-08-04T09:15:10Z",

  "source": {
      "name": "The Hindu",
      "domain": "thehindu.com"
  },

  "category": "Education",

  "keywords": [
      "AI",
      "Education",
      "Research",
      "IIIT"
  ],

  "language": "en",

  "ai_score": 0.97,

  "status": "published",

  "reading_time": 3,

  "hash": "sha256_hash",

  "created_at": "...",

  "updated_at": "..."
}
```


# Field Description

| Field | Description |
|--------|-------------|
| title | Article title |
| summary | AI generated summary |
| content | Clean article text |
| url | Original article URL |
| image_url | Thumbnail image |
| published_at | Original publication date |
| collected_at | Collection timestamp |
| source | Source information |
| category | Assigned category |
| keywords | AI generated keywords |
| language | Article language |
| ai_score | AI confidence score |
| status | Processing status |
| reading_time | Estimated reading time |
| hash | Duplicate detection |
| created_at | Database creation time |
| updated_at | Last modification |

# 5. Source Collection

Stores trusted news providers.

Example

```json
{
    "_id": "...",

    "name": "The Hindu",

    "website": "https://thehindu.com",

    "type": "News",

    "enabled": true,

    "rss": true,

    "country": "India"
}
```

# 6. Category Collection

```json
{
    "_id": "...",

    "name": "Healthcare",

    "description": "Artificial Intelligence in Healthcare"
}
```

# Default Categories

- Healthcare
- Agriculture
- Education
- Government
- Research
- Finance
- Industry
- Robotics
- Cybersecurity
- Environment
- Others

# 7. System Logs

Stores processing logs.

Example

```json
{
    "timestamp":"...",

    "module":"collector",

    "level":"INFO",

    "message":"Collected 15 articles."
}
```

# 8. Indexes

Version 1 indexes

| Collection | Index |
|------------|-------|
| articles | url |
| articles | published_at |
| articles | category |
| articles | source.name |
| articles | created_at |
| articles | hash |

# 9. Relationships

```

Sources

│

├──────────────┐

│

▼

Articles

│

▼

Categories

```

Although MongoDB is document-oriented, logical relationships exist between collections.


# 10. Data Validation Rules

Every article must have

- title
- url
- summary
- category
- source
- publication date

No article should be stored without these fields.


# 11. Duplicate Detection

Duplicates are identified using

- URL
- SHA-256 hash
- Normalized title

If any duplicate exists

↓

Ignore insertion.


# 12. Status Values

Possible status values

- collected
- processing
- published
- rejected
- failed

# 13. Future Collections

Version 2

```

users

bookmarks

analytics

notifications

```

Version 3

```

research_papers

github_projects

ai_tools

weekly_reports

```

# Database Summary

The database is optimized for storing AI-processed news articles while remaining flexible for future expansion.

The schema prioritizes searchability, extensibility, duplicate prevention, and API efficiency.
