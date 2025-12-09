---
title: "Self-Assessment"
date:
weight: 6
chapter: false
pre: " <b> 6. </b> "
---

### Internship Overview

From **September 8 to December 9, 2024**, I interned at **Amazon Web Services (AWS)** and immersed myself in the daily rhythm of a production-grade cloud team. The experience forced me to connect classroom theories with the realities of deploying resilient, secure, and cost-aware workloads.

My primary project was the **Bandup IELTS Learning Platform**, an AI-assisted learning experience that evaluates Writing and Speaking tasks and generates contextual flashcards. I owned several backend and AI integration streams that turned the concept into a working system students could interact with.

---

### Key Achievements

Working on Bandup allowed me to sharpen both technical depth and product thinking:

**Cloud Architecture & AWS Services**
- Sketched and iterated on a serverless blueprint using AWS Lambda, API Gateway, and SQS to decouple workloads
- Hardened networking by carving VPC public/private subnets, NAT Gateways, and Security Groups aligned with AWS Well-Architected guidance
- Provisioned container workloads on Amazon ECS with Fargate to host auxiliary services
- Chose the right data stores—Amazon S3 for documents, DynamoDB for high-scale metadata, and ElastiCache (Redis) for caching test artifacts
- Experimented with Amazon Bedrock (Titan Embeddings) alongside Google Gemini API to bring AI insight closer to end users

**Development & DevOps**
- Implemented Python Lambda functions that grade submissions and trigger flashcard creation
- Built the RAG (Retrieval-Augmented Generation) flow that indexes materials and surfaces contextually relevant snippets
- Wired CI/CD pipelines through GitLab runners and AWS CodePipeline so every change moved predictably from commit to deployment
- Practiced Infrastructure as Code, keeping environments reproducible and reviewable

**AI/ML Integration**
- Used Gemini’s native audio pipeline to process speaking samples at roughly **72%** lower cost than a custom stack
- Embedded lesson chunks with Amazon Titan Text Embeddings V2 to support semantic search and scoring explanations
- Iterated on prompt engineering tactics to align AI scoring outputs with IELTS descriptors

---

### Work Ethics

I held myself accountable for every deliverable by:
- Closing tasks with production-ready quality instead of proof-of-concept shortcuts
- Respecting AWS security guardrails and consistently reviewing cost impact before rolling changes out
- Scheduling proactive syncs with mentors so blockers surfaced early and were resolved quickly
- Capturing architecture decisions, runbooks, and test evidence to reduce knowledge gaps for anyone inheriting my work

---

### Self-Evaluation Criteria

To gauge how much I truly grew, I rated myself on metrics that mattered to the project and team:

| No. | Criteria | Description | Good | Fair | Average |
| --- | -------- | ----------- | ---- | ---- | ------- |
| 1 | **Professional knowledge & skills** | Applying AWS design patterns, selecting the right services, and delivering production-grade code | ✅ | ☐ | ☐ |
| 2 | **Ability to learn** | Picking up new AI services and DevOps tooling quickly enough to unlock project milestones | ✅ | ☐ | ☐ |
| 3 | **Proactiveness** | Investigating design options and AWS docs before escalating for help | ✅ | ☐ | ☐ |
| 4 | **Sense of responsibility** | Owning Lambda features end-to-end, from architecture discussions to deployment checklists | ✅ | ☐ | ☐ |
| 5 | **Discipline** | Staying aligned with sprint ceremonies, coding standards, and daily stand-ups | ☐ | ✅ | ☐ |
| 6 | **Growth mindset** | Treating code reviews and architectural feedback as chances to iterate fast | ✅ | ☐ | ☐ |
| 7 | **Communication** | Explaining trade-offs in docs and demos, while still improving presentation clarity | ☐ | ✅ | ☐ |
| 8 | **Teamwork** | Supporting mentors and peers, sharing test data, and pairing on tricky debugging sessions | ✅ | ☐ | ☐ |
| 9 | **Professional conduct** | Following AWS security expectations, respecting data privacy, and keeping commitments | ✅ | ☐ | ☐ |
| 10 | **Problem-solving skills** | Unblocking Lambda bugs, tracing performance issues, and driving the 72% audio-processing savings | ✅ | ☐ | ☐ |
| 11 | **Contribution to project/team** | Shipping four Lambda services plus documentation, demos, and a repeatable AI pipeline | ✅ | ☐ | ☐ |
| 12 | **Overall** | Holistic view of my readiness to contribute as a junior cloud engineer | ✅ | ☐ | ☐ |

---

### Key Learnings

**Technical Skills Gained**
- Strengthened my mental model for building serverless-first systems on AWS
- Proved out AI/ML integration patterns that translate research ideas into usable product features
- Became confident writing structured, testable Python for Lambda runtimes
- Internalized how RAG pipelines, vector stores, and embeddings interact to serve real queries

**Soft Skills Developed**
- Crafted documentation that balances architectural detail with actionable steps
- Broke down ambiguous issues into root causes and tracked fixes methodically
- Evaluated every feature for cost impact, looking for savings before launch
- Adapted to enterprise collaboration rhythms, tools, and review processes

---

### Areas for Improvement

* **Discipline:** Build firmer routines so even on hectic days I never miss status updates or deadlines
* **Communication:** Practice storytelling for technical demos to make non-technical listeners comfortable
* **Problem-solving:** Adopt lighter-weight runbooks for debugging so future incidents resolve faster
* **Networking:** Invest time connecting with more AWS teams to better understand adjacent services and opportunities

---

### Gratitude

Thank you to the mentors who trusted me with real production responsibilities, the operations team that kept the environment stable while I iterated, and AWS for opening its doors to curious students like me. The lessons from this internship now shape how I plan, build, and communicate every new idea.
