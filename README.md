<h1 align="center">Emrecan Ay</h1>

<p align="center">
  <a href="https://github.com/emrecanAy">
    <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&size=18&duration=3500&pause=900&color=6E9EFF&center=true&vCenter=true&width=520&lines=Full-stack+developer;CQRS+%C2%B7+DDD+%C2%B7+event-driven+backends;RAG+and+LLM+features+that+stay+grounded" alt="Full-stack developer" />
  </a>
</p>

<p align="center">
  <a href="https://www.linkedin.com/in/emrecan-ay/"><img src="https://img.shields.io/badge/LinkedIn-emrecan--ay-0A66C2?style=flat-square&logo=linkedin&logoColor=white" alt="LinkedIn" /></a>
  <a href="mailto:codemrecan@gmail.com"><img src="https://img.shields.io/badge/Email-codemrecan%40gmail.com-555?style=flat-square&logo=gmail&logoColor=white" alt="Email" /></a>
  <img src="https://img.shields.io/badge/Bursa%2C%20T%C3%BCrkiye-open%20to%20work-2EA043?style=flat-square" alt="Open to work" />
</p>

Most of my work is .NET on the backend — CQRS, DDD, clear boundaries between layers — with Angular, React or React Native on the front. Lately I've been building LLM features where the answer has to be grounded in real data: retrieval, chunking, vector search, and saying "I don't know" when the documents don't cover it.

Open to backend and full-stack roles, on-site or remote.

## Experience

**Glosy Software** · Full Stack Developer  
Enterprise logistics apps and web portals for road, sea and air freight.  
`.NET` `EF Core` `Angular` `Azure` `MSSQL`

**Alphastellar.io** · Backend Developer  
Insurance and custom enterprise software, built on CQRS and Domain-Driven Design.  
`.NET` `CQRS` `DDD` `Clean Architecture` `Azure`

**ikas** · Full Stack Developer  
E-commerce storefronts for online shops.  
`Next.js` `Node.js` `GraphQL` `TypeScript`

## Projects

**[marquee](https://github.com/emrecanAy/marquee)** — cinema ticketing where a seat is sold exactly once  
A modular monolith with a React front end, built around the moment a premiere opens and everyone clicks the same seat. Redis `SET NX` locks absorb the stampede, PostgreSQL row versions stay the source of truth if a lock is lost, and a virtual waiting room keeps seat selection usable. Payments go through an outbox with idempotency keys, a charge that lands after the hold expired is refunded, and Debezium turns the write-ahead log into an audit trail. One `docker compose up` runs the whole thing.  
`.NET 10` `React 19` `PostgreSQL` `Redis` `Kafka` `Debezium` `Testcontainers`

**[flash-sale](https://github.com/emrecanAy/flash-sale)** — order service for limited-stock drops  
A few units, far more buyers, all at the same second. Stock is reserved with a single conditional `UPDATE`, so there is no read-then-write window to oversell through; rows are locked in a fixed order to avoid deadlocks, retries are idempotent, and unpaid orders give their stock back after 15 minutes. Every race has a test against a real PostgreSQL — 200 concurrent buyers, 10 units, exactly 10 orders.  
`Java 21` `Spring Boot 4` `PostgreSQL` `Flyway` `Spring Modulith` `Testcontainers`

**[tezgah](https://github.com/emrecanAy/tezgah)** — one platform for small businesses, sold module by module  
A hairdresser gets customers, stamp cards and appointments; a café gets a till, the stamp card and stock; a logistics firm gets only fleet tracking. One code base and one database, and each company sees only the modules it was given. The platform admin ticks modules per company at runtime (turning one off closes it with a `403` but keeps its data), and an installation can ship only the modules a customer bought, so the others have no endpoints and no tables. Stamps come only from recorded sales and completed visits, and a staff member can't be double-booked. One `docker compose up` brings up three demo companies.  
`.NET 10` `React 19` `PostgreSQL` `Modular Monolith` `Docker`

**[documind](https://github.com/emrecanAy/documind)** — document assistant that answers from the sources and cites the page  
Ask questions about PDFs, Word files and wikis and get answers with inline citations down to file, page and section, or "not covered" when the documents don't say. Ingestion runs in a background worker on a Postgres job queue (`SKIP LOCKED`, retries, dead-lettering) with live progress over SignalR. Retrieval is hybrid: dense plus BM25 vectors in Qdrant, fused with Reciprocal Rank Fusion, with query rewriting and optional LLM reranking. Workspaces are isolated per tenant on every vector and SQL query, a tool-calling agent mode is bound to its workspace, and a golden-dataset evaluation (hit rate, MRR, LLM-as-a-judge) runs as a CI quality gate. Works with Ollama, OpenAI or Claude.  
`.NET 10` `React 19` `Qdrant` `PostgreSQL` `SignalR` `OpenTelemetry` `Testcontainers`

**[netcore-architecture](https://github.com/emrecanAy/netcore-architecture)**  
An order system built the way I'd build a production service: commands and queries split with MediatR, aggregates that enforce their own rules, domain events dispatched inside a single transaction, and a transactional outbox so emails never go out for a rolled-back order. It also has a RAG help desk — upload documents, they get chunked and embedded in the background, and questions are answered only from the retrieved chunks.  
`.NET 9` `EF Core` `MediatR` `Gemini` `sqlite-vec`

**Simahenk** — hairstyle try-on for barbers  
Analyses face shape, suggests styles, then applies the chosen cut and colour while keeping the person's face untouched.  
`MediaPipe FaceMesh` `BiSeNet` `Gemini` `React`

**AtölyemCepte** — job & payment tracker for small workshops  
Built for industrial workshop owners who still track jobs on paper. Deadline reminders run on Supabase cron jobs and arrive as push notifications.  
`React Native` `Supabase` `OneSignal` `PWA`

**Lingoric** — vocabulary game  
You learn English words by ricocheting shots off the walls, billiards-style.  
`React Native` `Expo`

**Ketebe** — library management system  
Used by the Faculty of Business at Uludağ University: books, members, loans, reports.  
`.NET` `Angular` `MSSQL`

## Stack

<p>
  <img src="https://skillicons.dev/icons?i=cs,dotnet,azure,postgres,redis,rabbitmq,kafka,java,spring&perline=9" alt="Backend stack" /><br/>
  <img src="https://skillicons.dev/icons?i=ts,angular,react,nextjs,nodejs,graphql,supabase,git,githubactions&perline=9" alt="Frontend and tooling" />
</p>

**Backend** — C#, ASP.NET Core, EF Core, MediatR, RabbitMQ, Kafka, Redis, Hangfire · Java, Spring Boot  
**Frontend & mobile** — Angular, React, Next.js, React Native (Expo), TypeScript  
**Data & cloud** — MSSQL, PostgreSQL, Supabase, Docker, Azure, Azure DevOps  
**AI** — OpenAI, Gemini and Claude APIs, embeddings & vector search, MediaPipe, n8n. Claude Code is part of my daily workflow.

<details>
<summary><b>GitHub activity</b></summary>
<br/>

<img src="https://github-readme-stats.vercel.app/api/top-langs/?username=emrecanAy&layout=compact&hide_border=true&bg_color=00000000&title_color=6E9EFF&text_color=8b949e&langs_count=6" alt="Top languages" height="150" />

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/emrecanAy/emrecanAy/output/snake-dark.svg" />
  <img src="https://raw.githubusercontent.com/emrecanAy/emrecanAy/output/snake.svg" alt="Contribution snake" />
</picture>

</details>

---

<p align="center">
  <sub>BSc Management Information Systems, Uludağ University</sub><br/>
  <img src="https://img.shields.io/badge/Graduated-High%20Honors-C9A227?style=flat-square" alt="Graduated with high honors" />
  <img src="https://img.shields.io/badge/GPA-3.55%20%2F%204.00-2EA043?style=flat-square" alt="GPA 3.55 out of 4.00" />
</p>
