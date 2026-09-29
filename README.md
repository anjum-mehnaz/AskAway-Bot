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




AskAway Bot (Multi-Agent Conversational Analytics Engine) – LangGraph, LLM, RAG, EDA, Streamlit (Link)                                                                                     
●	Engineered a real-time data workspace in Streamlit enabling dataset ingestion (.csv, .xlsx) with automated schema mapping to generate instant KPI cards, driver insights, and interactive visual dashboard grids.
●	Designed an async 7-agent state graph via LangGraph powered by Groq-hosted LLMs (OpenAI/gpt-oss-120b, gpt-oss-20b), implementing dynamic triage routing to execute code generation, chart rendering, and visual skimming.
●	Built EDA profiling workflows for duplicate removal and missing value imputation, combined with a code-gen agent (sql_generator) that converts user queries into sandboxed, executable Pandas expressions.
●	Integrated a schema-bound Retrieval-Augmented Generation (RAG) framework that injects schema metadata, sample records, and pre-computed dashboard payloads into agent context windows for real-time natural language query answering.
●	Implemented a cyclic Quality Critic evaluation loop in LangGraph to validate aggregation logic, enforce metric non-additivity constraints and eliminate cascading LLM hallucinations.


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
5. <img width="4102" height="6215" alt="image" src="https://github.com/user-attachments/assets/e76151ed-6848-48d0-99d1-4062b522e700" />
