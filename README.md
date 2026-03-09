Intelligent Data Dictionary Agent

An AI-powered platform that automatically generates a complete data dictionary from enterprise databases, analyzes data quality, visualizes schema relationships, and allows users to query databases using natural language instead of SQL.

The system extracts database metadata, builds ER diagrams, profiles data quality, generates business-friendly documentation using AI, and enables conversational exploration of datasets.

Features
Automatic Schema Extraction

Detects tables, columns, data types, and primary keys

Works with relational databases like SQLite (extendable to PostgreSQL, Snowflake, etc.)

ER Diagram Generation

Automatically identifies relationships between tables

Generates interactive ER diagrams to visualize database structure

Data Quality Profiling

Performs automated quality checks including:

Row counts

Column completeness

Null value detection

Primary key health (duplicates and missing values)

AI-Generated Data Documentation

Using Gemini AI, the system generates:

Business-friendly table summaries

Usage recommendations for each dataset

Natural Language Data Exploration

Users can ask questions like:

What tables exist in this database?
How are orders related to customers?
What is the total number of orders?
Top 5 products by sales

The system converts the question into SQL automatically and returns results.

SQL Generator (Natural Language → SQL)

Users can ask data questions without writing SQL. The system:

Converts the prompt into SQL

Executes the query

Displays results in table format

Example:

Prompt

Show total orders

Generated SQL

SELECT COUNT(*) FROM orders;

Output

count
99441
Architecture
User Prompt
     ↓
Streamlit Interface
     ↓
AI Engine (Gemini)
     ↓
SQL Generator
     ↓
Database Execution
     ↓
Results + Visualization

Pipeline Flow:

Database
   ↓
Metadata Extraction
   ↓
Data Profiling
   ↓
AI Summary Generation
   ↓
Artifacts Storage (JSON + Markdown)
   ↓
Interactive Chat & SQL Interface
Project Structure
project/
│
├── frontend/
│   └── app.py              # Streamlit UI
│
├── artifacts/
│   ├── metadata.json
│   ├── profiles.json
│   └── summaries.json
│
├── metadata_extractor.py   # Extract schema + relationships
├── profiler.py             # Data quality analysis
├── ai_engine.py            # Gemini AI + SQL generator
├── pipeline.py             # Full pipeline orchestration
├── storage.py              # JSON artifact utilities
├── config.py               # Project configuration
│
├── requirements.txt
└── README.md
Installation
1. Clone Repository
git clone https://github.com/YOUR_USERNAME/intelligent-data-dictionary-agent.git
cd intelligent-data-dictionary-agent
2. Create Virtual Environment
python -m venv venv
source venv/bin/activate

Windows:

venv\Scripts\activate
3. Install Dependencies
pip install -r requirements.txt
4. Set Gemini API Key
export GEMINI_API_KEY="YOUR_API_KEY"

Windows:

set GEMINI_API_KEY=YOUR_API_KEY
Running the Project
Step 1: Run the Data Pipeline

This generates metadata, profiles, and AI summaries.

python pipeline.py
Step 2: Start the Web Application
streamlit run frontend/app.py

Open in browser:

http://localhost:8501
Example Queries

Users can ask:

What tables exist?
Show relationships between tables
Total number of orders
Most frequent product
Average payment value

The system automatically generates SQL and displays results.

Technologies Used

Python

Streamlit

Gemini AI (Google GenAI)

Pandas

NetworkX

PyVis

SQLite

Use Cases

This platform can help:

Data analysts understand unfamiliar databases quickly

Business users explore data without SQL knowledge

Data engineers generate automated data documentation

Organizations maintain up-to-date data catalogs

Future Improvements

Multi-database connectors (PostgreSQL, Snowflake, SQL Server)

Data lineage visualization

Automated anomaly detection

Query result visualization (charts)

Incremental schema monitoring
