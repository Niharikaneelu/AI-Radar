**AI Radar - Project Charter (Version 1.0)**

Project Name :**AI Radar**

Tagline:**Discover. Understand. Deliver. AI News, Intelligently.**

Created By:** Niharika C**

Status: **Draft**

Created: **3 August 2026**

Last Updated: **4 August 2026**

 
**1. Vision Statement**

To build an AI-powered news intelligence platform that automatically discovers, analyzes, summarizes, categorizes, and distributes trustworthy Artificial Intelligence news through reusable APIs that can power websites, digital signage systems, chatbots, and other applications.

**2. Mission Statement**

Our mission is to reduce information overload by transforming scattered AI news into structured, trustworthy, and accessible knowledge for students, educators, researchers, and organizations.

**3. Problem Statement**

Today, AI news is scattered across numerous websites, blogs, research portals, and government publications. Students, faculty members, researchers, and professionals spend significant time searching for relevant AI news.

**Most websites either:**

•	publish every news article regardless of relevance

•	require manual updates

•	lack intelligent categorization

•	or provide no concise summaries.

Department websites and digital signage systems also rely on manual content updates, making information quickly become outdated. There is currently no lightweight platform dedicated to automatically collecting, filtering, and organizing AI-related news into an easily consumable format.

**4. Proposed Solution**

AI Radar will function as an AI-powered news intelligence engine.

**The platform will:**

•	Collect news from trusted sources.

•	Identify whether the article is genuinely AI-related.

•	Remove duplicate news.

•	Categorize articles.

•	Generate concise AI summaries.

•	Store processed news.

•	Provide APIs for external applications.

Instead of building another news website, AI Radar becomes an intelligent backend service capable of powering multiple frontends.

**5. Objectives**

_Primary Objectives_

✔ Collect AI-related news automatically

✔ Filter irrelevant articles

✔ Categorize articles

✔ Generate concise summaries

✔ Provide APIs

✔ Enable integration with multiple applications

_Secondary Objectives_

✔ Weekly reports

✔ Trending AI topics

✔ Newsletter generation

✔ AI-powered search

**6. Target Users**

_Primary Users_

•	College students

•	Faculty members

•	Researchers

•	Department administrators

_Secondary Users_

•	AI enthusiasts

•	Developers

•	Startups

•	Educational institutions

•	Digital signage systems

**7. Scope**

_Included in Version 1_

✅ News collection

✅ AI relevance detection

✅ AI categorization

✅ AI summarization

✅ MongoDB storage

✅ REST API

✅ Basic documentation

_Not Included in Version 1_

❌ User accounts

❌ Authentication

❌ Recommendation engine

❌ Comments

❌ Likes

❌ Notifications

❌ Mobile application

❌ Advanced analytics

❌ Multi-language support

**8. Functional Requirements**

_The platform shall:_

•	Collect news periodically.

•	Store news.

•	Detect duplicates.

•	Generate summaries.

•	Categorize articles.

•	Expose REST APIs.

•	Support API filtering.

9. Non-functional Requirements

_The system should be:_

•	Modular

•	Scalable

•	Maintainable

•	Fast

•	Reliable

•	Secure

•	Easy to extend

**10. Success Criteria**

_Version 1 will be considered complete when:_

✔ News collection works automatically.

✔ AI correctly filters irrelevant news.

✔ Articles are summarized.

✔ Categories are assigned.

✔ Data is stored.

✔ REST API returns structured JSON.

✔ Another application can successfully consume the API.

**11. Risks**

Risk	Mitigation

News API limitations	Support multiple sources

AI cost	Keep prompts concise and cache results

Duplicate news	Use URL/title similarity checks

Poor categorization	Allow categories to evolve and review edge cases

API downtime	Retry and log failures

**12. Stakeholders**

•	Project Developer(s)

•	Faculty Mentors

•	Department

•	Students

•	Future Contributors

**13. Technology Stack**

Component	Technology

Backend	FastAPI

Database	MongoDB

AI	OpenAI or Gemini

Scheduler	APScheduler

API	REST

Version Control	Git + GitHub

Frontend (later)	React

**14. Deliverables**

•	Working Backend

•	News Database

•	AI Processing Engine

•	REST API

•	Documentation

•	GitHub Repository

**15. Future Roadmap**

_Version 2_

•	Admin Dashboard

•	Trending News

•	Better Search

•	Scheduler Improvements

_Version 3_

•	AI Chat Interface

•	Weekly Reports

•	PDF Generation

•	Email Digest

_Version 4_

•	Multi-language Support

•	Voice Assistant

•	Mobile App

•	Public API

 
**16. Guiding Principles**

This is the section I think will make your project stand out.

1.	Platform First – AI Radar is a platform, not just a website.

2.	Modular Design – Every component should have one clear responsibility.

3.	AI Assists, Humans Verify – AI helps process content, but important decisions should be reviewable.

4.	Source Transparency – Every summary links back to its original source.

5.	Extensibility – New sources and categories should be easy to add.

6.	Documentation Before Complexity – Document major design decisions before implementing large features.
