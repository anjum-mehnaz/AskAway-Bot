# AskAway-Bot


High-Impact & Executive
SenseAI: Multi-Agent AI Analytics Engine
Transform raw Power BI metrics & datasets into conversational insights. Powered by a step-skipping multi-agent architecture to automate KPI root-cause analysis and eliminate analyst escalation latency.

[ User Query ] 
      │
      ▼
[ Agent 3 (LLM) ] ── (Receives Column Names & Schema ONLY)
      │
      ▼
[ Generates Code ] ──> e.g., df.groupby('customer_state')['price'].mean()
      │
      ▼
[ Python Executed locally on Laptop ] ──> Runs against 100% of cleaned_sales.csv rows
      │
      ▼
[ Final Result ] ──> Printed instantly to UI with zero token limits!


────────────────────────────────────────────────────────┐
│                      USER QUERY                         │
│       "Give average revenue for customer_state"         │
└────────────────────────────┬────────────────────────────┘
                             │
                             ▼
┌─────────────────────────────────────────────────────────┐
│                   AGENT 3 (Groq LLM)                    │
│    Receives: Schema context ONLY (< 500 tokens)         │
│    Outputs:  `df.groupby('customer_state')['price']...` │
└────────────────────────────┬────────────────────────────┘
                             │
                             ▼
┌─────────────────────────────────────────────────────────┐
│            LOCAL PYTHON ENGINE (`eval()`)               │
│    Runs generated pandas code directly on your laptop  │
│    Processes 100% of rows in cleaned_sales.csv         │
└────────────────────────────┬────────────────────────────┘
                             │
                             ▼
┌─────────────────────────────────────────────────────────┐
│                     STREAMLIT UI                        │
│    Displays exact grouped numbers instantly            │
└─────────────────────────────────────────────────────────┘


2. Agent Responsibilities & Scope Alignment
| Agent Name              | Primary Purpose                           | Core Deliverables / Behavior |
|---|---|---|
| `file_analyzer`         | Dataset & Metadata Profiler               | Inspects schema, column semantics, and sample values. |
| `eda_agent`             | Cleansing & Preprocessing                 | Removes nulls/duplicates, returns exact deleted-row statistics, and produces a 2-sentence summary. |
| `response_generator`    | Intent Router & Conversational Handshake  | Handles greetings, salutations, general help, and collects user feedback. |
| `visual_generator`      | Visual Spec Engine                        | Generates Recharts/Plotly specifications mapped directly to dataset metrics. |
| `dashboard_skimmer`     | Fast KPI Scanner                          | Reads aggregated memory/KPIs to answer high-level metric questions without querying raw data. |
| `sql_generator`         | Deep Data Query Engine                    | Generates dynamic Python/Pandas expressions or SQL to query row-level data. |

3. fwjhebfw
4. 
