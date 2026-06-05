# Automated CRM & Order Invoicing Engine via n8n ⚙️📦

An enterprise-grade, event-driven backend automation engine built on self-hosted n8n. This system coordinates data workflows to replace manual spreadsheet reviews with real-time operational alerts, dynamically routing customer records based on their order lifecycles.

### 🧩 Architectural Highlights & Conditional Branching
The system demonstrates advanced conditional branching design patterns to handle single-lane alerts and parallel dual-channel operations simultaneously:

* **Single-Path Routing (Targeted Action):** 
  * `Pending` status isolates the payload to trigger a single email alert directly to customer service.
  * `Processing` status maps to a standalone Slack node, dropping real-time updates into internal operation channels.
* **Multi-Path Routing (Parallel Execution):** 
  * Critical events (`Cancelled` or `Shipped`) trigger dynamic, multi-path parallel logic. The workflow automatically forks the payload to **both** email and Slack nodes simultaneously, instantly syncing support logs while alerting finance and logistics channels.

### 🚀 Stack & Capabilities
* **Core Runtime:** Self-hosted n8n infrastructure deployed on a cloud server.
* **Inbound Sync:** Dynamic extraction of customer records and data filtering from a Google Sheets CRM.
* **ChatOps & Communication:** Integrated Slack Webhook/API App nodes utilizing a precise bot permission matrix alongside automated SMTP notification gateways.
