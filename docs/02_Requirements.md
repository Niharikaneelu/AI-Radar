**Project:** AI Radar

**Version:** 1.0

**Status:** Draft


# 1. Introduction

## Purpose

This document defines the functional and non-functional requirements for AI Radar.

It serves as the primary reference for development, testing, and future enhancements.

## Project Summary

AI Radar is an AI-powered news intelligence platform that automatically collects AI-related news from trusted sources, processes it using AI, stores structured information, and exposes APIs for external applications.

# 2. Problem Overview

Users currently spend significant time searching multiple websites for AI news.

Problems include:

* Information scattered across many sources
* Duplicate articles
* No automatic categorization
* No concise summaries
* Manual maintenance of department websites
* Difficult to reuse information across applications

# 3. Goals

The system should

* Collect AI news automatically.
* Process articles intelligently.
* Store structured data.
* Serve data through APIs.
* Be reusable by different applications.

# 4. Stakeholders

| Stakeholder        | Role                        |
| ------------------ | --------------------------- |
| Developers         | Build and maintain AI Radar |
| Students           | Consume AI news             |
| Faculty            | Review and use news         |
| Department Website | Displays AI news            |
| Digital Signage    | Displays latest updates     |
| Future Developers  | Extend the platform         |

---

# 5. User Types

## Primary

* Students
* Faculty
* Researchers


## Secondary

* Department websites
* Chatbots
* Mobile apps
* Third-party systems

Notice something?

Some of our "users" are actually **software**.

That means we're building both a product and a platform.


# 6. Functional Requirements

Let's number them.


## FR-001

### Collect News

The system shall collect news from supported sources.

Input:

News source

Output:

Raw article


## FR-002

### Validate News

The system shall reject

* broken links
* empty articles
* duplicate URLs

## FR-003

### AI Relevance Detection

The AI shall determine

Is this article primarily about Artificial Intelligence?

Possible outputs

YES

NO

UNSURE


## FR-004

### AI Categorization

Each article shall belong to one category.

Initial categories

* Healthcare
* Agriculture
* Education
* Research
* Government
* Industry
* Robotics
* Finance
* Environment
* Cybersecurity
* Others

One category only in Version 1.


## FR-005

### AI Summary

Generate

2–3 sentence summary.

## FR-006

### Keyword Extraction

Generate keywords.

Example

```text
Generative AI

LLM

Healthcare

Cancer Detection
```

## FR-007

### Store Article

Store

* title
* summary
* source
* category
* keywords
* date
* URL
* image URL
* timestamp


## FR-008

### REST API

Provide APIs.

Examples

```text
GET /news

GET /news/latest

GET /news/category/{category}

GET /news/search
```

## FR-009

### Scheduler

Automatically run every few hours.

No manual intervention required.


## FR-010

### Logging

Record

* processing errors
* AI failures
* API failures

# 7. Non-Functional Requirements

## Performance

Latest news should be available within one collection cycle after publication.

## Reliability

Failures in one news source should not stop processing of other sources.


## Maintainability

Each module should have one responsibility.


## Scalability

Adding a new news source should require minimal code changes.

## Security

Store API keys securely using environment variables.


## Availability

The API should remain available even when scheduled collection is not running.


# 8. Business Rules

These are extremely important.


## BR-001

Only AI-related news shall be stored.


## BR-002

Every article must have a source.

No anonymous news.

## BR-003

Every summary must preserve the original meaning.

No fabricated facts.

## BR-004

Never modify

* dates
* numbers
* statistics

Only summarize.

## BR-005

Every article shall belong to exactly one category in Version 1.

## BR-006

Every stored article must contain a publication date.


# 9. Assumptions

* News APIs are available.
* AI services are available.
* MongoDB is running.
* Internet connection exists.

# 10. Constraints

Version 1

No authentication.

No frontend dependency.

No mobile application.

No recommendation engine.

No user accounts.

# 11. Success Metrics

We need measurable goals.

| Metric                    | Target                            |
| ------------------------- | --------------------------------- |
| Duplicate articles stored | 0                                 |
| API response time         | <500 ms (excluding AI processing) |
| AI summary length         | 2–3 sentences                     |
| News collection           | Automated                         |
| Categories                | 100% assigned                     |
| Source attribution        | 100%                              |

# 12. Out of Scope

Version 1 will NOT include

* User login
* Notifications
* Newsletter
* AI chatbot
* PDF generation
* Voice assistant
* Recommendation engine
* Sentiment analysis
* Multi-language support

# 13. Open Questions (Parking Lot)

Instead of changing the plan later, we'll keep future ideas here.

Examples:

* Should an article have multiple categories?
* Should we rank news importance?
* Should users be able to approve summaries?
* Should we support multiple AI providers?
* Should research papers be included?

Nothing here blocks Version 1.
