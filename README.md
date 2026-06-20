# Issa Compass — Data Visualization Hackathon

**Issa Compass** is a software company making living anywhere in the world as easy as ordering online — starting with visas. [More about us](https://www.issacompass.com/about)

You'll be working under **[Aaron Yip](https://www.linkedin.com/in/aaron-builds)** — 20 years in Silicon Valley across games, self-driving cars, and consumer tech (Apple industry advisor, Google App of the Year). Startup builder. Guest lecturer at Stanford and Chulalongkorn.

---

## The Brief

Issa's team runs 100K+ client conversations — visa consultations, document reviews, status updates. That data lives in Postgres. Right now, getting anything meaningful out of it means writing SQL or waiting for a report.

**Build the thing that replaces that.** A natural-language interface where any team member — ops, sales, leadership — can ask a business question and get back the right chart, table, or diagnosis. No SQL. No waiting.

This project is representative of the work at Issa. You'll be building real product, on real data, for real users inside the company, from day 0. What you see here gives you a sense of what the job actually looks like, so we hope you have fun!

---

## Access

Read-only Postgres on Neon with synthetic conversation data.

```
postgresql://readonly_dashboard:[PASSWORD]@ep-old-sunset-aowtz4h6-pooler.c-2.ap-southeast-1.aws.neon.tech/neondb?sslmode=require&channel_binding=require
```

Password provided separately — store it in an env var, not in your repo.

Start by exploring the schema:

```sql
SELECT table_name FROM information_schema.tables WHERE table_schema = 'public';
```

Understanding the data model well before building will save you hours.

---

## What It Needs to Handle

Two categories of prompts — and both matter.

### Direct queries

The user knows what they want. The tool should fetch it and render it correctly.

```
Show me new client conversations started each month this year
```
```
Compare average response time by team member over the last 90 days
```
```
Conversation volume in Q1 vs Q2 broken down by channel
```
```
Clients who haven't had any contact in over 30 days
```
```
Who closed the most conversations last month?
```
```
How has client satisfaction trended week over week this quarter?
```

### Business-level investigation

The user knows something is wrong but doesn't know where to look. The tool needs to decompose the question, run the right sub-queries, and come back with a diagnosis.

```
Why did our revenue go down in March?
```
```
Why are we getting fewer new clients this month?
```
```
Which clients are at risk of churning?
```
```
Is the team keeping up with demand?
```
```
What's been our best month this year and why?
```
```
Are there any unusual patterns in conversations lately?
```

For these, the interesting part is how the tool reasons about *which* signals to pull and how it synthesizes them into something actionable. That's where most candidates fall short.

---

## Evaluation

Speed, product quality, and _"Did you build something we haven't seen from any other candidate before?"_

Less than 2–3% of candidates who complete this get an offer. They build something that makes the other submissions look like prototypes. The delta is your technical and product judgment: knowing what to cut, what to polish, and where to do something unexpected.

Ask yourself: would someone at Issa actually open this instead of asking their analyst? Is there a moment in the demo where the response genuinely surprises and wows you?

That's what we're looking for.

---

## Submission

- Hosted, working demo (not localhost)
- Repo link with a clean README explaining your (1) process, (2) architecture decisions, and (3) time it took you to complete
- A short Loom or screen recording walking through your best prompts, especially the business-level ones
- Share the above to recruiting.team@issacompass.com and aaron@issacompass.com please

Good luck and have fun!
