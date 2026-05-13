<div align="center">

```
 ____  _     _                     __   __          _
/ ___|| |__ (_)_   ____ _ _ __ _   \ \ / /_ _  __| | __ ___   __
\___ \| '_ \| \ \ / / _` | '_ ` _ \  \ V / _` |/ _` |/ _` \ \ / /
 ___) | | | | |\ V / (_| | | | | | |  | | (_| | (_| | (_| |\ V /
|____/|_| |_|_| \_/ \__,_|_| |_| |_|  |_|\__,_|\__,_|\__,_| \_/
```

[![Typing SVG](https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=20&duration=3000&pause=800&color=39D353&center=true&vCenter=true&multiline=true&width=700&height=80&lines=Shivam+Yadav+%7C+Backend+Engineer;Building+scalable+event-driven+systems)](https://git.io/typing-svg)

<img src="https://komarev.com/ghpvc/?username=Shivam-1827&style=for-the-badge&color=39d353&labelColor=0d1117&label=PROFILE+VIEWS" alt="Profile Views"/>

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/shivam-yadav-18278652s/)
[![LeetCode](https://img.shields.io/badge/LeetCode-FFA116?style=for-the-badge&logo=leetcode&logoColor=black)](https://leetcode.com/u/Shivam_1827/)
[![Codeforces](https://img.shields.io/badge/Codeforces-1F8ACB?style=for-the-badge&logo=codeforces&logoColor=white)](https://codeforces.com/profile/shivam_1886_)
[![GeeksForGeeks](https://img.shields.io/badge/GeeksforGeeks-2F8D46?style=for-the-badge&logo=geeksforgeeks&logoColor=white)](https://www.geeksforgeeks.org/profile/shiva1znhc)
[![Gmail](https://img.shields.io/badge/Gmail-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:shivam018860@gmail.com)

</div>

---

## `$ whoami`

```go
package main

type Engineer struct {
	Name        string
	Role        string
	Location    string
	Speciality  []string
	CurrentWork string
	OpenTo      string
}

func main() {
	me := Engineer{
		Name:     "Shivam Yadav",
		Role:     "Backend Engineer Intern → Systems & Distributed Infrastructure",
		Location: "Mumbai / Pune, Maharashtra 🇮🇳",
		Speciality: []string{
			"Distributed Systems",
			"Low-Latency Architecture",
			"Event-Driven Microservices",
			"Concurrent & Parallel Systems",
		},
		CurrentWork: "Building AI-powered platforms @ Raja Software Labs, Pune",
		OpenTo:      "Full-time Backend / Systems / Platform Engineering roles",
	}
	_ = me
}
```

---

## `$ ls -la experience/`

### 🟢 Software Developer Intern — [Raja Software Labs](https://rajasoftwarelabs.com) `Jan 2026 – Present · Pune`
> `React · Node.js · Docker · Ollama · PostgreSQL · Redis`

- Built an **AI-powered coding assessment platform** — cut average manual evaluation time from **~12 min → ~4 min** per candidate
- Automated test case generation (30+ cases per problem) — previously required manual authoring per submission

---

### 🔵 Software Engineer (Backend) — StayAccom `Aug 2025 – Dec 2025 · Remote`
> `Node.js · Docker · Redis · MongoDB · Elasticsearch · AWS`

- Engineered **distributed backend** for hotel booking: integrated pricing engine, booking orchestration, and payment workflows
- Built search pipeline on Elasticsearch + Redis cache layer — reduced p95 query latency from **~800ms → ~440ms**
- Designed notification + data-sync automation pipeline; platform sustained **99.9% availability** during load tests

---

### 🟠 Software Developer Intern — Symphony Fintech Solutions `May 2025 – Jul 2025 · Mumbai`
> `C++ · C# · RabbitMQ`

- Built **C++ TCP server** using non-blocking I/O (`epoll`) — sustained low-latency request handling under **10,000+ concurrent connections**
- Integrated RabbitMQ message queue + heartbeat monitoring for connection liveness detection

---

## `$ ls -la projects/`

> All repos include architecture diagrams, benchmarks, and docker-compose. Click to explore.

---

<details>
<summary><b>⚡ <a href="https://github.com/Shivam-1827/SchedulrX">SchedulrX</a> — Distributed CPU Scheduling Platform · 2026</b></summary>

<br>

> `Go (Gin) · C++17 · Redis · PostgreSQL · Prometheus · Docker`

**What it does:** Distributed platform for benchmarking and visualizing CPU scheduling algorithms in real environments — not simulation.

**Architecture highlights:**
- Scheduler core in C++17 with **SMP work-stealing** — idle cores pull tasks from busy cores' queues
- **Adaptive burst prediction** adjusts time quantum dynamically based on rolling task history
- Go API layer (Gin) exposes scheduling decisions and metrics via REST
- Prometheus + Grafana dashboard for real-time per-core utilization

**Benchmarks (local, 8-core, Docker):**

| Algorithm | Throughput | Avg Latency | Context Switches |
|---|---|---|---|
| Work-Stealing (SMP) | ~10,200 tasks/sec | 0.8ms | Low |
| Round Robin | ~6,800 tasks/sec | 1.4ms | High |
| FCFS | ~5,100 tasks/sec | 2.1ms | Lowest |

</details>

---

<details>
<summary><b>💳 <a href="https://github.com/Shivam-1827/payment-engine">Payment Engine</a> — Fault-Tolerant Distributed Payments · 2026</b></summary>

<br>

> `Go (Chi) · C++ (librdkafka) · Kafka · PostgreSQL · Redis · Docker`

**What it does:** An event-driven payment processing system built around correctness — idempotent handlers, transactional event publishing, and an ACID-compliant ledger.

**Architecture highlights:**
- Kafka partitioned by `account_id` — ordered processing per account, parallel across accounts
- **Idempotency keys** in Redis (TTL 24h) — duplicate requests short-circuit before DB write
- Strongly consistent **double-entry ledger** in PostgreSQL
- Dead-letter queue with exponential backoff retry for failed events
- **Distributed lock** via Redis prevents double-spend under concurrent requests

**Design patterns applied:**
`Idempotent Processing` · `Outbox Pattern` · `Event Sourcing` · `Retry + Dead-Letter Queue` · `Distributed Locking`

</details>

---

<details>
<summary><b>🔍 <a href="https://github.com/Shivam-1827/worksy">Worksy</a> — Multimodal RAG Platform · 2025</b></summary>

<br>

> `Node.js · PostgreSQL · Pinecone · Traefik · RabbitMQ · Redis · Docker · WebSocket`

**What it does:** A workplace knowledge platform — uploads trigger asynchronous ingestion jobs for transcription, embedding, and semantic retrieval in real time.

**Architecture highlights:**
- **RabbitMQ** buffers ingestion load spikes via backpressure — no dropped requests under burst traffic
- **Pinecone** vector store for semantic search; Redis caches hot query embeddings
- WebSocket layer pushes indexing progress and search results to clients in real time
- **Traefik** reverse proxy handles routing across microservices

**Results (internal test corpus, ~500 docs):**
- Reduced zero-result queries from ~22% → ~11% after query-expansion step
- P95 search latency: **210ms** (cold), **48ms** (cache hit)

</details>

---

## `$ cat system-design-highlights.md`

> Patterns applied across projects — not just listed, but shipped.

| Pattern | Where Applied |
|---|---|
| **Work-Stealing (SMP)** | SchedulrX — idle cores pull from busy queues |
| **Idempotent Processing** | Payment Engine — idempotency keys + Kafka offset commits |
| **Outbox Pattern** | Payment Engine — transactional event publishing |
| **Retry + Dead-Letter Queue** | Payment Engine — exponential backoff for failed events |
| **Cache-Aside** | StayAccom — Redis layer over Elasticsearch |
| **Backpressure via Queue** | Worksy — RabbitMQ buffers ingestion load spikes |
| **Distributed Locking** | Payment Engine — Redis lock prevents double-spend |
| **Adaptive Burst Prediction** | SchedulrX — dynamic time quantum per task history |
| **Non-blocking I/O (epoll)** | Symphony Fintech — 10k+ connections on single server |
| **Event Sourcing (partial)** | Payment Engine — ledger as append-only event log |

---

## `$ cat tech-stack.json`

```json
{
  "languages":   ["Go", "C++17", "C", "JavaScript"],
  "frameworks":  ["Node.js", "Gin", "Chi", "Boost.Asio", "GraphQL", "gRPC"],
  "messaging":   ["Kafka", "RabbitMQ", "Pub/Sub", "WebSockets"],
  "databases":   ["PostgreSQL", "Redis", "MongoDB", "Elasticsearch", "Pinecone"],
  "infra":       ["Docker", "AWS", "Linux", "CI/CD", "Prometheus", "Traefik"],
  "concepts":    [
    "Distributed Systems", "Concurrency", "Multithreading",
    "Event-Driven Architecture", "Fault Tolerance", "Idempotency",
    "TCP/IP Networking", "Low-Level Design", "Backpressure", "Work-Stealing"
  ]
}
```

<div align="center">

![Go](https://img.shields.io/badge/Go-00ADD8?style=for-the-badge&logo=go&logoColor=white)
![C++](https://img.shields.io/badge/C%2B%2B-00599C?style=for-the-badge&logo=c%2B%2B&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Kafka](https://img.shields.io/badge/Apache_Kafka-231F20?style=for-the-badge&logo=apachekafka&logoColor=white)
![RabbitMQ](https://img.shields.io/badge/RabbitMQ-FF6600?style=for-the-badge&logo=rabbitmq&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-232F3E?style=for-the-badge&logo=amazonaws&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)
![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=for-the-badge&logo=prometheus&logoColor=white)

</div>

---

## `$ cat github-stats.md`

<div align="center">

[<img height="180em" src="https://github-readme-stats.vercel.app/api?username=Shivam-1827&show_icons=true&theme=github_dark&hide_border=true&bg_color=0d1117&title_color=39d353&icon_color=39d353&text_color=e6edf3&ring_color=39d353&count_private=true" alt="Shivam Yadav's GitHub Stats"/>](https://github-readme-stats.vercel.app/api?username=Shivam-1827)

<img height="180em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=Shivam-1827&layout=compact&theme=github_dark&hide_border=true&bg_color=0d1117&title_color=39d353&text_color=e6edf3&langs_count=8" alt="Top Languages"/>

</div>

<div align="center">

[![GitHub Streak](https://streak-stats.demolab.com?user=Shivam-1827&theme=github-dark-blue&hide_border=true&background=0d1117&stroke=39d353&ring=39d353&fire=f78166&currStreakLabel=39d353&sideLabels=e6edf3&dates=8b949e)](https://git.io/streak-stats)

</div>

---

## `$ cat competitive.log`

<div align="center">

| 🏅 Platform | 📊 Rating / Rank |
|:---:|:---:|
| 🟡 LeetCode | **1700+** Rating |
| 🔵 Codeforces | **Pupil** (Rated) |
| 🟢 GeeksForGeeks | Active |
| 🏆 TCS CodeVita Season 12 | **Rank #492** Nationally |
| 🥈 College Contests | **2nd / 3rd place** |

**1,500+ problems** solved across all platforms

</div>

---

## `$ cat education.txt`

- 🎓 **B.Tech — Computer Science & Engineering** · `8.42 CGPA`
  Shri Guru Gobind Singhji Institute of Engineering and Technology, Nanded · `2022–2026`

- 📚 **Higher Secondary — Science** · `90%`
  Bhavans College, Mumbai · `2020–2022`

---

<div align="center">

```
╔══════════════════════════════════════════════════════════╗
║  Shivam Yadav — Open to Backend / Systems / Platform     ║
║  📧  shivam018860@gmail.com                              ║
║  📍  Mumbai / Pune, Maharashtra                          ║
╚══════════════════════════════════════════════════════════╝
```

*"Make it work. Make it right. Make it fast."*

⭐ **If a project was useful or interesting, a star goes a long way!**

</div>
