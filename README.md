<div align="center">

# WASSIM AHABCHANE

### SOFTWARE ENGINEER · PRODUCT BUILDER

`TypeScript` · `Next.js` · `PostgreSQL` · `Node.js` · `Drizzle`

<br/>

<a href="https://github.com/wassim7254?tab=repositories">
<img src="https://img.shields.io/badge/WORK-171717?style=flat-square&logo=github&logoColor=white&labelColor=0A0A0A"/>
</a>
<a href="https://www.linkedin.com/in/wassim-ahabchane">
<img src="https://img.shields.io/badge/LINKEDIN-171717?style=flat-square&logo=linkedin&logoColor=white&labelColor=0A0A0A"/>
</a>
<a href="mailto:wwassim.wassim2009@gmail.com">
<img src="https://img.shields.io/badge/EMAIL-171717?style=flat-square&logo=gmail&logoColor=white&labelColor=0A0A0A"/>
</a>

</div>

<br/>

---

<div align="center">

```text
┌──────────────────────────────────────────────────────────────────────────┐
│                                                                          │
│  WASSIM / SOFTWARE ENGINEERING                                          │
│                                                                          │
│  I build products where the interface is only one part of the system.   │
│                                                                          │
│  product → domain → API → database → infrastructure                     │
│                                                                          │
└──────────────────────────────────────────────────────────────────────────┘
```

</div>

<br/>

## CURRENT BUILD

### DBER

**A unified transactional engine for marketplace products.**

DBER is the system I'm currently using to go deeper into the parts of software
that become important when a prototype has to behave like a real product:

- transactional workflows
- PostgreSQL as the source of truth
- explicit state machines
- concurrency control
- idempotent mutations
- auditability
- recoverable background work
- deterministic business rules

<br/>

<div align="center">

```text
                         DBER
                          │
          ┌───────────────┼───────────────┐
          │               │               │
          ▼               ▼               ▼
       SOUQ            KHIDMA           KRAYA
    group buying    professional       rentals
                     services
          │               │               │
          └───────────────┼───────────────┘
                          │
                          ▼
                  TRANSACTION CORE
                          │
             ┌────────────┼────────────┐
             │            │            │
             ▼            ▼            ▼
         POSTGRES      OUTBOX       AUDIT
             │
             ▼
       SOURCE OF TRUTH
```

</div>

<br/>

> **The goal isn't to make the demo look production-ready.  
> The goal is to understand what production-ready actually requires.**

---

## HOW I BUILD

<table>
<tr>
<td width="50%" valign="top">

### 01 — MODEL

Before writing endpoints, define the business facts.

Entities.  
Relationships.  
States.  
Invariants.  
Failure conditions.

</td>

<td width="50%" valign="top">

### 02 — CONSTRAIN

If something must never happen, decide who guarantees it.

Application validation where useful.

Database constraints where necessary.

</td>
</tr>

<tr>
<td width="50%" valign="top">

### 03 — TRANSACT

Multi-record business facts belong together.

Locks.  
Atomic updates.  
Isolation.  
Rollback.

</td>

<td width="50%" valign="top">

### 04 — RECOVER

Assume requests repeat.

Assume workers crash.

Assume external systems retry.

Design accordingly.

</td>
</tr>
</table>

---

## THE ENGINEERING LOOP

<div align="center">

```text
        ┌─────────────┐
        │    IDEA     │
        └──────┬──────┘
               │
               ▼
        ┌─────────────┐
        │    MODEL    │
        └──────┬──────┘
               │
               ▼
        ┌─────────────┐
        │  INVARIANTS │
        └──────┬──────┘
               │
               ▼
        ┌─────────────┐
        │ TRANSACTION │
        └──────┬──────┘
               │
               ▼
        ┌─────────────┐
        │   FAILURE   │
        └──────┬──────┘
               │
               ▼
        ┌─────────────┐
        │   RECOVERY  │
        └──────┬──────┘
               │
               ▼
        ┌─────────────┐
        │   PRODUCT   │
        └─────────────┘
```

</div>

---

## THE STACK

<div align="center">

<img src="https://skillicons.dev/icons?i=ts,js,react,nextjs,nodejs,postgres,docker,git,github,tailwind&theme=light" />

</div>

<br/>

<table>
<tr>
<td width="33%" valign="top">

### PRODUCT

Next.js  
React  
TypeScript  
Tailwind CSS

</td>

<td width="33%" valign="top">

### SYSTEMS

Node.js  
PostgreSQL  
Drizzle ORM  
REST APIs

</td>

<td width="34%" valign="top">

### DELIVERY

Git  
GitHub  
Docker  
CI/CD

</td>
</tr>
</table>

---

## DBER / SYSTEM VIEW

```text
┌─────────────────────────────────────────────────────────────────────────┐
│                              HTTP                                       │
└────────────────────────────────┬────────────────────────────────────────┘
                                 │
                                 ▼
┌─────────────────────────────────────────────────────────────────────────┐
│                         REQUEST CONTEXT                                 │
│                  auth · request_id · idempotency                        │
└────────────────────────────────┬────────────────────────────────────────┘
                                 │
                                 ▼
┌─────────────────────────────────────────────────────────────────────────┐
│                           DOMAIN                                        │
│                  validation · state · invariants                        │
└────────────────────────────────┬────────────────────────────────────────┘
                                 │
                                 ▼
┌─────────────────────────────────────────────────────────────────────────┐
│                         TRANSACTION                                     │
│              lock · mutate · audit · outbox · commit                    │
└────────────────────────────────┬────────────────────────────────────────┘
                                 │
                 ┌───────────────┼────────────────┐
                 ▼               ▼                ▼
             PostgreSQL        Audit           Outbox
                 │                                │
                 │                                ▼
                 │                         Background jobs
                 │
                 ▼
             SOURCE OF
               TRUTH
```

---

## WHAT I'M OPTIMIZING FOR

<table>
<tr>
<td width="50%">

**Correctness over cleverness**

Simple systems are easier to reason about.

</td>

<td width="50%">

**Explicitness over magic**

Important business behavior should be visible.

</td>
</tr>

<tr>
<td>

**Failure-aware design**

The unhappy path is part of the feature.

</td>

<td>

**Useful abstraction**

Abstract because the domain requires it,
not because the code looks repetitive.

</td>
</tr>
</table>

---

## GITHUB ACTIVITY

<div align="center">

<img
src="https://github-readme-activity-graph.vercel.app/graph?username=wassim7254&bg_color=ffffff&color=171717&line=171717&point=555555&area=true&hide_border=true"
width="100%"
alt="GitHub activity"
/>

<br/>

<img
src="https://github-readme-stats.vercel.app/api?username=wassim7254&show_icons=true&hide_border=true&theme=transparent&include_all_commits=true&rank_icon=github"
width="48%"
alt="GitHub statistics"
/>

<img
src="https://github-readme-stats.vercel.app/api/top-langs/?username=wassim7254&layout=compact&hide_border=true&theme=transparent&langs_count=8"
width="41%"
alt="Top languages"
/>

</div>

---

## A FEW THINGS I BELIEVE

> Good software should make the next decision obvious.

> If two requests can race, design for the race.

> If an operation can be retried, make the retry safe.

> If a business rule matters, give it a place where it can be enforced.

> Production engineering starts where the happy path ends.

---

## NOW

```text
LOCATION       MOROCCO
ROLE           SOFTWARE ENGINEER
FOCUS          FULL-STACK / BACKEND SYSTEMS
BUILDING       DBER
LEARNING       TRANSACTIONS · CONCURRENCY · DISTRIBUTED FAILURE
DEFAULT        TYPESCRIPT
DATABASE       POSTGRESQL
```

<br/>

<div align="center">

### BUILDING SOFTWARE THAT CAN BE DEPENDED ON.

<br/>

<a href="https://github.com/wassim7254?tab=repositories">
<img src="https://img.shields.io/badge/EXPLORE_THE_WORK-0A0A0A?style=for-the-badge&logo=github&logoColor=white"/>
</a>

<a href="mailto:wwassim.wassim2009@gmail.com">
<img src="https://img.shields.io/badge/START_A_CONVERSATION-0A0A0A?style=for-the-badge&logo=gmail&logoColor=white"/>
</a>

<br/><br/>

`WASSIM / 2026`

</div>
