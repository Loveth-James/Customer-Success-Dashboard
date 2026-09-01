# Customer-Success-Dashboard
I wanted to answer a simple question a customer success team actually has to answer every week: **which customers need attention right now, and why?** So I built a dashboard to answer it, using a mock SaaS customer dataset and learned Power BI along the way, with Claude as a learning partner to explain concepts and help me catch my own mistakes.

## Key findings
Working through the dashboard surfaced a clear priority list, not just numbers:
- **Highest-priority account:** "NovaFlow Client 32" is tied for the *highest-value* account in the whole book (~£16.5k ACV, Enterprise plan), but has bottom-tier CSAT (5.36) and the lowest product adoption of any high-value account (38.9%) and 50 support tickets on top of that. Losing a top-value account that's quietly disengaged costs far more than losing a low-tier one. This is the account I'd contact first.
- **Support-driven risk:** two other customers stood out for stacking multiple red flags at once. "NovaFlow Client 06" has the highest ticket count in the book (77) alongside near-bottom adoption (35.9%), and "NovaFlow Client 33" combines the second-highest ticket count (68) with one of the lowest CSAT scores (5.29). Both patterns usually mean an onboarding or support failure in progress, not a one-off bad month.
- **Renewals coming up:** three customers are renewing within 60 days, which matters because it sets a deadline on everything above. if an at-risk, high-value account is also renewing soon, that's the one that needs a conversation this week, not next quarter.
- **Where the value concentrates:** Enterprise-plan customers dominate the top of the revenue list, useful for prioritizing which relationships are worth the most proactive investment.

This was mostly sorting and cross-referencing a handful of numbers across related tables. But it's exactly the kind of "who do I call today" judgment call a CS team makes constantly, and building the dashboard forced me to practice making it systematically instead of by gut feel.

## What the dashboard shows
**6 KPI cards:** Total Customers, Total MRR, Total Annual Contract Value, Average Product Adoption, Average CSAT, Total Support Tickets
**Charts:** revenue by customer, customers by plan, customers by industry, product adoption by customer, support tickets by customer, CSAT by customer, and an upcoming renewals table.

## The data
A relational dataset split across 4 related tables — Customers, Subscriptions, monthly Usage, and individual Support tickets, connected through a shared Customer ID. This is closer to what a real CS data setup looks like, where the answer to "how engaged is this customer" isn't sitting in one row; it has to be built from usage patterns over time and ticket history, joined back to who the customer actually is.

## Behind the dashboard (technical notes)
One mistake I found and fixed along the way — I think this matters more than the finished charts, since it's the part where I actually had to understand what the data was telling me rather than trust the first number Power BI showed:

**Sum vs. Average**. A chart was summing 12 months of adoption per customer instead of averaging them, producing numbers like 700+ instead of a sensible percentage.

## Tools
Power BI Desktop, with Claude (Anthropic) as a learning and debugging partner throughout.

## Files in this repo

- `dashboard.pbix` — the Power BI file
- `screenshots/` — dashboard views
