# 🤖 Enterprise Intelligence Data Agent (Production Architecture)

A decentralized, local analytics microservice architecture designed to parse enterprise sales, cross-channel performance metrics, social sentiment, and customer service data. It merges local algorithmic execution using Pandas matrix math and text keyword scanning with automated record hygiene loops and structured LLM synthesis to generate highly visual, responsive HTML executive reports.

All components are dynamically aligned with the project's data schema requirements, enforcing strict uppercase data dimensions and utilizing local SQLite processing layers.

## About

Local multi-channel marketing intelligence agent built with Streamlit, LangChain, Groq LLM, and Pandas/SQLite. Programmatically parses transactional sales logs, correlates social influencer metrics, detects manufacturing defects, and dispatches automated HTML executive reports via SMTP.

### ⭐ Show Your Support

If you like the UI design, microservice architecture, or automated multi-channel analytics behind **Enterprise Intelligence Data Agent**, please consider giving this repository a **Star ⭐** on GitHub! It helps showcase this work and motivates future builds.
---
![Desktop Screenshot](assets/desktop-screenshot.png)

---

## 📊 System Architecture & Process Flow

The system separates raw database querying and heavy mathematical calculations from text synthesis, ensuring zero SQL-injection vulnerabilities, sandboxed HTML frontend rendering, and stable runtime execution.

### 1. Data Ingestion & System Interaction Funnel
```mermaid
graph TD
    User([Dashboard Interaction / Prompt]) --> Streamlit[app.py Frontend UI]
    Streamlit --> Engine[engine/agent.py Core Pipeline]
    
    subgraph Data Extraction Layer
        Engine -->|Programmatic Loop| SQLite[(data/mock_data.db)]
        SQLite -->|Uppercase Rows Matrix| Pandas[Pandas DataFrame Math Engine]
    end

    subgraph Analytical Processing
        Pandas -->|Pearson R Calculation| Calc[Cross-Channel Performance Correlation]
        Pandas -->|Text Keyword Scan| Anom[Service Case Anomaly Detector]
        Pandas -->|Record Cleanse Sweep| Hygiene[Automated System Record Hygiene Engine]
    end

    subgraph Report Synthesis & Automation
        Calc & Anom & Hygiene -->|Context Matrices| LLM[Groq Layer Engine]
        LLM -->|Formatted Executive Summary| Orchestrator{Query Classifier}
        Orchestrator -->|Rich HTML Sandboxed Preview| Streamlit
        Orchestrator -->|Forced Port 465 SSL Trigger| SMTP[Secure Outbound Corporate Gateway]
        SMTP -->|Automated Broadcast| Inbox[Concerned Stakeholder's Email Inbox]
    end
```

### 2. Database Schema Mappings
Enforced across the application to ensure flawless joins, cross-channel calculation lookups, and system telemetry delivery tracking:

```mermaid
erDiagram
    products {
        INTEGER PRODUCT_ID PK
        TEXT PRODUCT_NAME
        TEXT CATEGORY
    }
    sales {
        TEXT DATE
        TEXT REGION
        INTEGER PRODUCT_ID FK
        INTEGER UNITS_SOLD
        REAL SALES_AMOUNT
    }
    performance_metrics {
        TEXT DATE
        TEXT CATEGORY
        TEXT CHANNEL_NAME
        INTEGER IMPRESSIONS
        INTEGER ENGAGEMENTS
    }
    social_sentiment {
        TEXT DATE
        TEXT CATEGORY
        TEXT PLATFORM
        TEXT INFLUENCER
        INTEGER MENTIONS
    }
    service_cases {
        TEXT id PK
        TEXT title
        TEXT product
        TEXT transcript
        TEXT date
    }
    system_users {
        INTEGER USER_ID PK
        TEXT EMAIL
        TEXT FIRST_NAME
        TEXT JOIN_DATE
        TEXT STATUS
    }
    system_event_logs {
        INTEGER EVENT_ID PK
        TEXT TIMESTAMP
        TEXT CHANNEL_NAME
        INTEGER USER_ID FK
        TEXT EVENT_TYPE
        TEXT REFERENCE_URL
    }

    sales }o--|| products : "joins via PRODUCT_ID"
    social_sentiment }o--|| performance_metrics : "correlates via CATEGORY"
    system_event_logs }o--|| system_users : "tracks via USER_ID"
```

---

## 🚀 Quick Start & Installation

Follow these sequential steps to configure your environment variables and boot the application container locally.

### 1. Clone & Install Dependencies
Ensure you have Python 3.10+ installed on your local machine.
```bash
git clone https://github.com
cd enterprise-intelligence-data-agent
pip install -r requirements.txt
```

### 2. Configure Streamlit Secrets Configuration Mappings
Create a local secrets project initialization profile configuration file named **`.streamlit/secrets.toml`** directly inside the project root folder:
```bash
mkdir .streamlit
touch .streamlit/secrets.toml
```
Open the `secrets.toml` file and populate it with your active processing parameters:
```toml
# 🔑 Groq Processing Layer Engine Keys
GROQ_API_KEY = "gsk_your_actual_groq_api_token_here"

# ✉️ Secure Outbound Mail Gateway Routing Parameters
SMTP_SERVER = "smtp.gmail.com"
SMTP_PORT = 465
SMTP_USER = "your_authenticated_corporate_email@gmail.com"
SMTP_PASSWORD = "your_16_character_google_app_password"

# 📬 Target Report Inbox Destination Mappings
REPORT_RECIPIENT = "your_personal_receiving_mailbox@domain.com"
```

### 3. Initialize & Seed Database Footprint
Run the setup pipeline to compile directories, construct the upgraded uppercase database layout schemas, and seed live row metrics across the 4 fiscal quarters:
```bash
python setup.py
```

### 4. Boot the Microservice Dashboard Application
Launch your web server dashboard instance locally:
```bash
localhost:8506 run app.py
```

---

## ⚙️ Core Application Interface Workflows

The application dashboard provides four pre-onboarded automated quick-prompt tasks:

*   **📋 Q1: Trend Analysis (Sales Audit):** Compiles the full annual transactional history matrix across all product categories. Automatically sends out a summary report titled `📊 Q1 Executive Operations Audit - 2025 Sales Trends`.
*   **⚠️ Q2: Feedback Auditing (Jacket Quality Risk):** Scans customer service logs for structural defects. Programmatically isolates critical anomalies (such as the *Thermal Expedition Parka* armpit seam tearing failures) and sends out an alert titled `⚠️ Q2 Executive Operations Audit - Product Quality Log`.
*   **📈 Q3: Growth Correlation Run (Performance RPC):** Performs a Pearson Product-Moment Correlation calculation ($R = 0.9652$) between internal system click logs and active social media impressions. Delivers a report titled `📈 Q3 Executive Operations Audit - Channel Correlation Run`.
*   **🛡️ Q4: Record Hygiene (System Integrity Matrix):** Evaluates interaction boundaries and bounce thresholds. It computes live delivery telemetry logs, **automatically switches broken or deactivated user row records to inactive status metrics**, and dispatches a rich-text HTML advisory report titled `📋 Q4 Executive Operations Audit - System User Base Health`.

---
---

## ⚠️ Disclaimer

This **Enterprise Intelligence Data Agent** is provided strictly for educational, research, and technical evaluation. It uses simulated data (`mock_data.db`), and automated AI-generated reports require human oversight before making business or financial decisions. Users must safely manage their own API keys (`GROQ_API_KEY`), respect rate limits, and ensure email reports go only to authorized users.

---

## 🛡️ License, Copyright & Compliance Notices

**All Rights Reserved © 2026 T A Srinivas.**

> **Strict Intellectual Property Notice:** For portfolio viewing and evaluation only. **DO NOT COPY, CLONE, FORK, OR REDISTRIBUTE** this code or documentation. Unauthorized usage will result in a **GitHub DMCA copyright takedown**.

* **Lead Architect & Developer:** [Srinivasta](https://github.com) | **Contact:** [tasrinivass@gmail.com](mailto:tasrinivass@gmail.com)

### 🌐 Let’s Connect

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/srinivas-t-a-557637119/)
[![Kaggle](https://img.shields.io/badge/Kaggle-20BEFF?style=for-the-badge&logo=kaggle&logoColor=white)](https://www.kaggle.com/srinivasta)
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:tasrinivass@gmail.com)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/srinivasta)
[![Website](https://img.shields.io/badge/Website-000000?style=for-the-badge&logo=website&logoColor=white)](https://srinivasta.github.io)

---

💡 *Engineered with **automated analytical pipelines** to bridge the gap between **raw multi-channel enterprise telemetry** and **actionable executive intelligence**.*
