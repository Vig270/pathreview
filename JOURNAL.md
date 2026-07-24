# Development Journal

## Week 7 — Issue selection

**Issue link:** https://github.com/ascherj/pathreview/issues/11

**Issue title:** Add support for ingesting a portfolio website URL

**Tier:** [ ] Tier 1  [x] Tier 2  [ ] Tier 3

**Problem summary:**
PathReview currently collects user information from sources like GitHub repositories and resumes, but it does not support personal portfolio websites. This issue adds the ability for users to provide a portfolio URL, allowing the ingestion pipeline to fetch and extract useful content such as biographies and project descriptions. The extracted information should be processed and stored in the vector database alongside existing profile data so it can improve future AI-generated reviews.

**Selection reasoning:**
I selected this Tier 2 issue because it requires understanding multiple parts of the application, including API schemas, ingestion pipelines, and document parsing. This issue aligns with my goal of learning how AI systems collect, process, and use user data in real-world applications. I also see this issue as an opportunity to develop a troubleshooting mindset by handling edge cases such as invalid URLs, missing webpage content, and extraction failures. Understanding how users submit data through APIs and how the backend processes that information connects well with solution engineering responsibilities.


**Branch name:** feature/11-portfolio-url-ingestion

**Setup confirmation:** [x] App runs locally at localhost:5173 

**Setup notes:**
Used Docker Compose to start the required services (PostgreSQL, Redis, and ChromaDB). Resolved a ChromaDB startup issue caused by a NumPy version incompatibility by pinning NumPy to version 1.26.4. After restarting the containers, completed the project setup with `make setup` and verified the application by running `make run` and logging in successfully with the seeded test account.

**Cohort ledger:** [x] Issue added to cohort ledger




## Week 8 — Reproduction & solution planning

**Reproduction commit link:** https://github.com/Vig270/pathreview/commit/7597f54

**Reproduction summary:**
I reproduced the issue by running PathReview locally with Docker Compose and submitting a review request containing a portfolio URL. The application accepts and stores the URL, but the ingestion pipeline currently does not fetch or process portfolio website content.

**PLAN.md link:** https://github.com/Vig270/pathreview/blob/feature/11-portfolio-url-ingestion/PLAN.md

**Walkthrough video (recommended):** Not recorded.

**Blockers or open questions:**
Need to determine the best approach for fetching and parsing different portfolio website structures.