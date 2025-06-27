# Database System Principles: Visual Query Plan Analyzer for PostgreSQL

This project is a complete system for **retrieving**, **visualizing**, and **interactively modifying** SQL **Query Execution Plans (QEPs)**. It allows users to explore "what-if" scenarios by altering join methods, scan strategies, and aggregation choices — offering an educational and diagnostic tool for understanding query performance.

> Built using Python, Dash, and PostgreSQL as part of the *Database System Principles* course at NTU Singapore.

---

## 🔍 Project Objectives

- 🔄 Retrieve QEPs from PostgreSQL using raw SQL queries.
- 🌲 Visualize QEPs as hierarchical query trees and interactive graphs.
- ❓ Simulate **what-if** scenarios (e.g., "What if we disabled nested loop joins?").
- 📊 Compare costs between the original QEP and altered AQP (Alternative Query Plan).

---

## 💡 What This Project Demonstrates

- Deep understanding of **PostgreSQL's query planner** and internal execution hints.
- Competence in **query tree parsing**, custom tree rendering, and data visualization.
- Integration of **graph-based models** (`networkx`, `igraph`) with web UIs using **Dash**.
- Ability to modify **server-side planner behavior** programmatically via `SET` commands.

---

## 🚀 How to Run

### 1. Prerequisites

- Python ≥ 3.10  
- PostgreSQL Server (v14–v17)  
- Git LFS (for large file assets)  
- `psycopg2`, `networkx`, `dash`, etc. (see `requirements.txt`)

---

### 2. Installation Steps

```bash
# Clone the repository
git clone https://github.com/yourusername/query-plan-analyzer.git
cd query-plan-analyzer

# Setup Git LFS
git lfs install

# Create and activate virtual environment
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
```

---

### 3. Setup PostgreSQL

- Start your PostgreSQL server.
- Create a new database:

```sql
CREATE DATABASE query_analysis;
```

- Create a `.env` file in the root directory:

```dotenv
DB_NAME=query_analysis
DB_USER=your_username
DB_PASSWORD=your_password
DB_HOST=localhost
DB_PORT=5432
```

- Optionally, populate your database tables via:

```bash
python -m db.populate
```

---

### 4. Run the App

```bash
python -m project
```

---

## 🧪 Example Use Case

1. Input an SQL query  
2. View its full QEP as a tree (with cost, rows, width)  
3. Modify physical operators (e.g., force merge join)  
4. View updated AQP and cost comparison  
5. Export or analyze visualizations

---

## 📁 Key Components

| File             | Description                                     |
|------------------|-------------------------------------------------|
| `interface.py`   | Dash frontend and user interaction logic        |
| `preprocessing.py` | Converts QEP to graph for visualization      |
| `querytree.py`   | Builds custom query trees from raw plans        |
| `whatif.py`      | Runs `SET` command-based what-if configuration  |
| `project.py`     | Main entrypoint to run the entire app           |
| `requirements.txt` | All Python package dependencies              |

---

## 🙋 Contributors

- **Tathagato Mukherjee, Aditya Pugalia, Anushri Iyer, Vardhan Lohia, Teoh Xi Sheng**  
