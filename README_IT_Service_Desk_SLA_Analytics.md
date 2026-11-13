# IT Service Desk & SLA Analytics

## Project Overview
This portfolio project analyses **600 synthetic IT service desk incident records** to understand ticket demand, response and resolution performance, workload distribution, open backlog, and resolution Service Level Agreement (SLA) attainment.

The project follows a practical service-operations analytics workflow: inspect the data, validate its quality, calculate operational KPIs, investigate patterns, and translate the findings into questions and dashboard recommendations for service desk stakeholders.

## Business Problem
An IT support team needs a consistent way to monitor incoming incidents and assess whether tickets are being handled within their resolution targets. Without clear reporting, it can be difficult to identify high-volume categories, priority groups with longer resolution times, unassigned work, and areas where SLA performance may need attention.

## Objectives
- Measure total ticket volume and ticket status distribution.
- Monitor first-response and resolution times.
- Calculate resolution SLA attainment for completed tickets.
- Understand ticket volume and performance by category and priority.
- Review workload distribution and identify unassigned tickets.
- Recommend useful KPIs and visuals for an operational dashboard.

## Dataset
File: `data/service_desk_tickets.csv`

The dataset contains 600 illustrative, synthetic incident records with fields including:
- `ticket_id`: unique incident identifier
- `created_at`: date and time the ticket was created
- `category`: incident category
- `priority`: ticket priority (P1–P4)
- `status`: current ticket status
- `assigned_to`: assigned support agent or `Unassigned`
- `response_time_min`: minutes until first response
- `resolution_time_min`: minutes until resolution
- `resolution_sla_min`: target resolution time in minutes
- `resolution_sla_met`: indicator for meeting the resolution target (1 = met, 0 = not met)

**Data note:** The records and service targets are synthetic and intended only for learning and portfolio demonstration. They do not represent a real organisation or production service desk.

## Analysis Workflow
1. Load the CSV and inspect its structure.
2. Check missing values, duplicate ticket IDs, data types, and invalid values.
3. Calculate service desk KPIs, including ticket volume, completed tickets, open backlog, average response time, average resolution time, and SLA attainment.
4. Analyse ticket volume by category, priority, status, and month.
5. Compare response and resolution performance across priority and category.
6. Review agent workload and unassigned tickets.
7. Summarise evidence-based observations and propose dashboard components.

## Key KPIs
| KPI | Definition |
|---|---|
| Tickets created | Count of unique ticket IDs |
| Completed tickets | Tickets with status `Resolved` or `Closed` |
| Open backlog | Tickets with status `In Progress` or `Pending` |
| Average response time | Mean first-response time in minutes |
| Average resolution time | Mean resolution time in minutes for completed tickets |
| Resolution SLA attainment | Completed tickets meeting target ÷ all completed tickets |
| Unassigned tickets | Tickets where `assigned_to` is `Unassigned` |

## Tools & Skills
- Python, Pandas, NumPy
- Matplotlib for charts
- Data cleaning and validation
- Exploratory Data Analysis (EDA)
- KPI definition and operational reporting
- SLA and service-performance analysis
- Business interpretation and dashboard planning

## Repository Structure
```text
it-service-desk-sla-analytics/
├── data/
│   └── service_desk_tickets.csv
├── notebooks/
│   └── IT_Service_Desk_SLA_Analytics.ipynb
├── sql/
│   └── service_desk_analysis.sql
├── python/
│   └── analyze_service_desk.py
├── docs/
│   └── kpi_dictionary.md
├── requirements.txt
└── README.md
```

## How to Run
1. Clone or download this repository.
2. Install the required packages:
   ```bash
   pip install pandas numpy matplotlib
   ```
3. Open `notebooks/IT_Service_Desk_SLA_Analytics.ipynb` in Jupyter Notebook, JupyterLab, or Google Colab.
4. Keep `service_desk_tickets.csv` in the repository's `data/` folder.
5. Run the notebook cells from top to bottom.

The SQL analysis is available separately in `sql/service_desk_analysis.sql`. The Python script in `python/analyze_service_desk.py` provides an additional command-line analysis.

## Suggested Power BI Dashboard
- **Service overview:** total tickets, completed tickets, open backlog, SLA attainment.
- **Performance:** average response/resolution time by priority and category.
- **Demand:** ticket volume by category, priority, and month.
- **Workload:** tickets by assignee and unassigned queue.

## Important
This is a synthetic portfolio case study. Describe it as an independent analytics exercise, not as work completed for a real company. Report numerical findings only after running the notebook against the included dataset.
