---
title: Database & Backend Systems Helper
theme: jekyll-theme-minimal
---

# Mike G.
## Database & Backend Systems Helper

Most technical problems that cost a business real time and money trace back to the same root causes: a system that wasn't designed for how the business grew, a process that was automated incorrectly (or not at all), or legacy code nobody wants to touch. I focus on diagnosing what's actually broken, then building a fix that holds up.

**What I do:**
- Troubleshooting slow, failing, or unreliable systems
- Automating manual, error-prone business processes
- Database performance and schema fixes
- Rescuing or rewriting slow/failing batch jobs and ETL pipelines
- Legacy system modernization (PHP, C#, Python, SQL, Docker, Linux)
- Data migrations and system integrations

---

## Case Studies

### Rescuing an Overnight ETL Job from a Legacy Monolith

**Problem:** A nightly ETL process, written in single-threaded PHP inside a legacy monolith, was falling outside its required overnight processing window as the user base grew — putting downstream reporting and operations at risk.

**What I Found:** The job's PHP implementation had no concurrency, no batching, and no error handling or retry logic. It processed records one at a time, made blocking database calls in sequence, and was tightly coupled to an inefficient, bloated monolith — leaving no room to scale or tune performance.

**What I Did:** I rewrote the entire ETL process as a standalone C# microservice running in Docker, fully decoupled from the legacy monolith. The new service used C#'s concurrency features to parallelize data lookups and calculations, and batched database writes instead of processing row-by-row. This also opened up straightforward options for future performance tuning.

**Tech Stack:** PHP (legacy system), C# for the rewritten service, RabbitMQ for messaging, Docker and Linux for deployment, and SQL for data storage.

**Result:** Throughput improved 5-10x depending on allocated server resources. The job now completes well within its overnight window, with hours to spare.

---

### Automating Digital Content Fulfillment for an EdTech Platform

**Problem:** An EdTech company sold digital content in curated bundles that had grown into an exponential number of variations. Enabling each piece of content in a customer's account was done manually by the support team — slow and error-prone even in normal conditions, and made worse by the fact that most orders landed in a short summer purchasing window, when school districts place their orders. The manual workload consumed so much staff time that it directly cut into the team's ability to handle customer questions.

**What I Did:** I designed and built an automated ERP integration and workflow that handled digital content fulfillment end-to-end, removing the manual enablement process entirely. I also built a web interface and a Qlik integration on top of it, giving both the customer service team and company management real-time visibility into order fulfillment status.

**Tech Stack:** PHP, SQL, RabbitMQ for message queuing between systems, Sage ERP integration, and Docker for deployment.

**Result:** Staff time on fulfillment dropped by roughly 90%, and fulfillment errors were reduced by more than 99% — freeing the support team to focus on customers during their busiest season.

---

### Untangling a Town's Property Tax Assessments

**Problem:** Property tax assessments are supposed to follow a consistent methodology, but it's often unclear whether they actually do. I wanted to find out whether valuations were being calculated fairly and consistently across properties.

**What I Found:** Pulling together public assessment records and real estate data, I found no clear, consistent standard for how the taxable rate per square foot was being applied — similar properties were landing on meaningfully different valuations with no obvious justification. The assessment process itself showed signs of inconsistency rather than a clean, defensible formula.

**What I Did:** I built a data pipeline that combines public town assessment records with scraped real estate listing data, cleans and joins them into a unified dataset, and analyzes the relationship between property characteristics and assessed value. The tool surfaces properties that are outliers relative to comparable homes, and highlights where the underlying valuation logic breaks down.

**Tech Stack:** Python, PostgreSQL for data storage, Docker, geopy for geocoding, and Matplotlib/Seaborn for report visualizations. I used the Anthropic's toolset to speed up development throughout.

**Status:** This is an active project. My near-term goal is to use the findings to challenge my own property's assessment, then publish the analysis for the town more broadly - giving homeowners a data-backed way to question their own valuations.

---

## Let's Talk

If you've got a slow database, a broken process, or a system nobody wants to touch — I'd like to hear about it.

**[Contact Me](mailto:mglass2@gmail.com)** · **[LinkedIn](https://www.linkedin.com/in/mglass2/)**