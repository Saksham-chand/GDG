🚀 Intelligent Data Dictionary Agent

An AI-powered platform that automatically generates a complete data dictionary from databases, analyzes data quality, visualizes schema relationships, and allows users to query data using natural language instead of SQL.
Built for GDG Hackfest, this tool transforms raw database schemas into AI-enhanced documentation, insights, and interactive exploration.

✨ Features

📊 Automatic Schema Extraction

Detects tables, columns, data types, and primary keys
Works with relational databases like SQLite
Easily extendable to PostgreSQL, Snowflake, SQL Server

🧩 ER Diagram Generation

Automatically detects table relationships
Generates interactive ER diagrams
Helps users understand database structure visually

📈 Data Quality Profiling

Automatically analyzes:
✔ Row counts
✔ Column completeness
✔ Null values
✔ Primary key health
✔ Duplicate records

🤖 AI-Powered Documentation

Using Google Gemini AI, the system generates:
Business-friendly table summaries
Data usage recommendations
Automatic documentation

💬 Natural Language Data Exploration

Ask questions like:
What tables exist?
How are orders related to customers?
Show top 5 products by sales
Total number of orders

The system automatically:

1️⃣ Converts the question into SQL
2️⃣ Executes the query
3️⃣ Displays results

🧠 Natural Language → SQL Generator

Example:
User Query
Show total orders
Generated SQL
SELECT COUNT(*) FROM orders;
Result
count
99441

No SQL knowledge required.

🏗 System Architecture
User Query
     │
     ▼
Streamlit Web Interface
     │
     ▼
Gemini AI Engine
     │
     ▼
SQL Generator
     │
     ▼
Database Execution
     │
     ▼
Results + Visualization
🔄 Data Processing Pipeline
Database
   │
   ▼
Metadata Extraction
   │
   ▼
Data Quality Profiling
   │
   ▼
AI Summary Generation
   │
   ▼
Artifacts Storage (JSON + Markdown)
   │
   ▼
Interactive Chat + SQL Interface
📁 Project Structure
project/
│
├── frontend/
│   └── app.py              # Streamlit UI
│
├── artifacts/
│   ├── metadata.json       # Extracted schema
│   ├── profiles.json       # Data quality metrics
│   └── summaries.json      # AI-generated documentation
│
├── metadata_extractor.py   # Schema extraction
├── profiler.py             # Data quality profiling
├── ai_engine.py            # Gemini AI + SQL generator
├── pipeline.py             # Full pipeline execution
├── storage.py              # JSON utilities
├── config.py               # Configuration settings
│
├── requirements.txt
└── README.md
⚙️ Installation
1️⃣ Clone the Repository
git clone https://github.com/YOUR_USERNAME/intelligent-data-dictionary-agent.git
cd intelligent-data-dictionary-agent
2️⃣ Create Virtual Environment
python -m venv venv
source venv/bin/activate

Windows:

venv\Scripts\activate
3️⃣ Install Dependencies
pip install -r requirements.txt
4️⃣ Set Gemini API Key

Linux / Mac:

export GEMINI_API_KEY="YOUR_API_KEY"

Windows:

set GEMINI_API_KEY=YOUR_API_KEY
▶ Running the Project
Step 1: Run Data Pipeline
This generates metadata, profiles, and AI summaries.
python pipeline.py

Step 2: Start the Application
streamlit run frontend/app.py
Open in browser:
http://localhost:8501
🧪 Example Queries

Try asking:

What tables exist?
Show relationships between tables
Total number of orders
Most frequent product
Average payment value
Orders per city
🛠 Tech Stack
Technology	Purpose
Python	Core backend
Streamlit	Web interface
Gemini AI	Natural language processing
Pandas	Data profiling
NetworkX	Graph structure
PyVis	ER diagram visualization
SQLite	Database engine
🚀 Future Improvements

Multi-database connectors (PostgreSQL, Snowflake, SQL Server)

Data lineage visualization
Query result charts
AI-powered query optimization
Schema change detection

📌 Use Cases

This platform helps:
Data analysts explore unfamiliar databases quickly
Business users query data without SQL knowledge
Data engineers generate automated documentation
Organizations maintain up-to-date data catalogs

🏆 Hackathon Project

Built for GDG Hackfest to demonstrate how AI can simplify data discovery and database documentation.

📄 License
MIT License

⭐ Support

If you found this project useful, please consider starring the repository.
