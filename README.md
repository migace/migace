### Hi, I'm Michał

Full-stack developer in Kraków. Python on the back end (FastAPI, SQLAlchemy, PostgreSQL), React with TypeScript on the front, and LLMs where they earn their place: retrieval, tool calling and agents.

The work I like most is taking a real workflow, from a tutor's week to an HVAC price quote, and turning it into software that holds up.

#### The project to look at first

**[Tutor Calendar](https://github.com/migace/tutor-calendar)** is a booking calendar for independent tutors: weekly lessons, prepaid hours and a monthly statement for the parent. The [live demo](https://tutor.mikrus.dev) needs no account.

What it shows about how I work:

- **A slot cannot be booked twice.** PostgreSQL refuses overlapping bookings with an exclusion constraint, and a test fires 25 simultaneous requests at one slot and expects exactly one to succeed.
- **Money is a ledger.** Prepaid time is only ever added to, a database trigger refuses edits, and e-mail is queued in the same transaction as the booking that caused it.
- **Time is modelled, not formatted.** Recurring rules are wall-clock facts in the tutor's zone, lessons are UTC instants, and property-based tests go looking for the nights when the clocks change.
- **The architecture is enforced by a test.** The build fails if an inner layer imports an outer one.
- **Decisions are written down.** Eleven [decision records](https://github.com/migace/tutor-calendar/tree/main/docs/adr) say what was chosen, what was turned down and why.

#### Building with LLMs

- [agent-ai-v1](https://github.com/migace/agent-ai-v1): an agent written from scratch in TypeScript, with its own reasoning loop, tool calling and persistent memory, and no framework in between.
- [AI-Knowledge-Analyst](https://github.com/migace/AI-Knowledge-Analyst): question answering over local documents with LangChain and FAISS, answering only from what was retrieved and citing the source.
- [hvac-cpq](https://github.com/migace/hvac-cpq): a configure-price-quote proof of concept for HVAC products with an AI product advisor, FastAPI and React.
- [react-trucks-app](https://github.com/migace/react-trucks-app): a fleet dashboard whose assistant answers by calling tools against the fleet's data.

#### Also here

- [hono-redis-case-study](https://github.com/migace/hono-redis-case-study): cache-aside, distributed rate limiting and job state with Hono and Redis.
- [github-repositories-explorer](https://github.com/migace/github-repositories-explorer): a React Native app with offline caching.
