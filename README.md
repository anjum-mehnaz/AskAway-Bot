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
