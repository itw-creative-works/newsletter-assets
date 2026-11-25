# Why raw SQL belongs in your agent workflow

_Type-safe queries, declarative schemas, and fewer invisible database edges._

There’s a bigger shift happening in backend tooling than most teams are noticing: agents are starting to write and reason about real infrastructure, not just app code. The hard part is making that safe without sanding off the parts of SQL that actually matter.

---

## Stop treating the database like a black box

![A senior engineer reviewing a plain-text database schema file on a laptop, with table diagrams, SQL snippets, and code review annotations in a clean technical illustration style.](https://cdn.itwcreativeworks.com/newsletters/proxifly/content/-P7IrLRA51Se9Nm7gmL8/section-1.png)

Most teams still hide too much behind an ORM, then wonder why migrations drift, constraints go missing, or policies never get revisited. If an agent is helping you ship schema changes, the database needs to be legible in plain text, not buried in generated abstractions. A declarative schema file plus type-aware SQL gives you a better review surface: one place to see tables, indexes, triggers, and access rules together. That matters for production systems where data integrity and operational behavior need to be obvious before the deploy, not after a broken job starts paging you.

[Read the full article →](https://proxifly.dev/blog/how-to-review-tables-indexes-triggers-and-policies-in-one-place)

---

## Let agents work with SQL, not around it

![A robotic assistant editing SQL queries alongside a type checker and query planner visualization, rendered as a crisp modern developer workspace.](https://cdn.itwcreativeworks.com/newsletters/proxifly/content/-P7IrLRA51Se9Nm7gmL8/section-2.png)

Agents are better when they can operate on the same primitives your team already uses. Raw SQL is still the most expressive interface for joins, window functions, constraints, and database-specific features that ORMs tend to smooth over or ignore. The practical move is not to eliminate SQL, but to make it safer with type inference and structured schema definitions so generated queries are checked before they hit production. That gives you the full language of the database while reducing the usual risks of handwritten strings, mismatched columns, and brittle migration scripts.

---

**Sponsored**

---

## Migrations should be explicit, not magical

![A migration checklist beside a database schema file, with highlighted triggers, policies, and permission rules in a utilitarian engineering dashboard scene.](https://cdn.itwcreativeworks.com/newsletters/proxifly/content/-P7IrLRA51Se9Nm7gmL8/section-3.png)

One of the most common failure modes in backend work is assuming the migration tool captured everything. It usually does not. Triggers, policies, permissions, and other database behaviors are easy to lose when schema changes are spread across ad hoc scripts or ORM-specific syntax. A better pattern is to keep the schema declarative and close to the source of truth, so a change to a table and a change to its behavior live in the same reviewable artifact. That makes agent-generated changes easier to audit and much harder to half-apply.

---

## This is a good fit for proxy-heavy systems

![A proxy monitoring dashboard connected to a relational database, showing country flags, job states, retry counts, and queryable logs in a polished technical illustration.](https://cdn.itwcreativeworks.com/newsletters/proxifly/content/-P7IrLRA51Se9Nm7gmL8/section-4.png)

If your product depends on scraping, geo-routing, or automated enrichment, your database often becomes the control plane for what happened, where it happened, and how reliably it worked. That is exactly where typed SQL and explicit schemas pay off. You can model job states, region-specific routing rules, retry histories, and request fingerprints without guessing how an abstraction layer will translate them. And when you are rotating IPs or validating responses across countries, being able to inspect and query the raw data directly is a lot more useful than debugging through a leaky ORM layer. Proxifly exists for the network side of that problem, but the database side still needs to be just as disciplined.

---

Best,  
The Proxifly Team

_Tags: #sql #agents #typescript #databases #developer-tools_

---
_You're receiving this because you subscribed to [Proxifly](https://proxifly.dev)._
