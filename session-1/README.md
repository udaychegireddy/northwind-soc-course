# Session 1 — Practical: Triage the Monday morning alerts

**Time:** 20 minutes · **Format:** pairs · **Tool:** Northwind Log Explorer (in your browser)

## Why this matters
- **Case:** at 09:41 on Monday, Northwind's SIEM raised two high-severity alerts. Before anyone can respond, the SOC must know *what* is happening and *where*.
- **Theory:** today you learned which systems produce which logs. Now you use those logs.
- **Later SIEM lab:** searching, filtering and counting by field is exactly what you will do in a real SIEM.

## Files
- `log-explorer/index.html` (or the online Log Explorer link in the main README)
- Dataset: **Session 1 — Monday morning, all sources**

## Steps
1. Open the Log Explorer and choose the dataset **Session 1 — Monday morning**.
2. Search `event.dataset:siem.alert`. Read the two alerts: which laptop and which user?
3. Clear the search. In **Count by field**, choose `event.dataset`. Note how many log sources there are and how many events each produced.
4. Search for the affected laptop, e.g. `host.name:<the laptop>`. Expand events with **+** to see every field.
5. Pin (☆) the events that tell the story of what happened on that laptop, from the earliest suspicious event to the alerts. Do not forget the email gateway: search for the user's name too.
6. Open **Case notebook**, insert the template **Session 1 — Alert triage timeline**, then click **Insert pinned events**. Complete the table and answer the questions.
7. Click **Download as Markdown** and keep the file: you will reuse it in Sessions 2–4.

## Deliverable
`northwind-case-notebook.md` containing your timeline and answers.

## If something does not work
- The online page does not load → open `log-explorer/index.html` from the downloaded ZIP (works offline).
- Your browser blocks downloads → copy the notebook text into any text editor and save it as `.md`.
