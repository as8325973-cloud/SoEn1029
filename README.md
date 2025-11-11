# SoEn1029
軟工課程Version Control, HTML, and CSS


## Assignment #4 – FlowBuilder Website Plan

FlowBuilder 是一個專門為中小型總包商設計的雲端智慧採購平台，目標是解決建築工程中材料採購流程分散、效率低落與風險高的問題。  
系統將傳統透過 email、Excel、電話來回的 RFQ / 報價流程，集中到同一個平台中，並利用 **AI-Assisted RFQ 引擎** 依據工種與歷史績效推薦合適供應商，協助專案準時、在預算內完成。  
下列網站架構是依照 Assignment #1～#3（Business Proposal、Data Model、ETL）文件的章節整理而成，作為之後實作網站的藍圖。

---

### 1. Website Organization (Mermaid Diagram)

```mermaid
graph TD

A[Sign In]:::high --> B(Dashboard)
B --> C(Projects)
C --> C1(Project Detail)
C1 --> D(Create RFQ)
D --> E(AI Supplier Suggestions)
E --> F(Distribute RFQ)
F --> G(Supplier Portal - Token Link)
G --> H(Submit Quote Items)
H --> I(Quote Comparison)
I --> J(Award Quote)
J --> K(Generate PO)
K --> L(PO Status Tracker)

%% Phase 2 / Enhancements
B --> M(Suppliers Directory)
B --> N(Material Catalog)
B --> O(Company & Users - RBAC)
B --> P(Notifications & Emails)
B --> Q(Reports & Analytics)
B --> R(Help Center)
B --> S(API Docs)

%% Priority color classes
classDef high fill:#ff9999,color:#000;
classDef medium fill:#fff799,color:#000;
classDef low fill:#a7c7e7,color:#000;

%% High priority: MVP user flows
class A,B,C,C1,D,E,F,G,H,I,J,K,L high;

%% Medium priority: operational features
class M,N,O,P,Q medium;

%% Low priority: docs & support
class R,S low;
```

---

# FlowBuilder Website Page Map & Tech Overview

## 1) Project Overview

**FlowBuilder** is a smart‑procurement SaaS for construction that replaces fragmented, manual workflows with a centralized, intelligent hub so general contractors can make faster, more cost‑effective decisions. Its core differentiator is an **AI‑assisted RFQ engine** that analyzes project requirements and recommends suppliers based on trade specialty and historical performance.

The platform’s value proposition spans three pillars: a **Centralized Management Hub** (company/users, projects, unified supplier & material databases), an **Intelligent Procurement Module** (AI‑assisted RFQ, quote comparison, one‑click PO), and **Essential Delivery Oversight** (PO status tracking and notifications).

For the **MVP**, FlowBuilder delivers a complete end‑to‑end procurement workflow using one primary persona (Construction Admin), with **pre‑defined suppliers/materials** to reduce setup complexity, while keeping the AI recommendation engine in scope.

---

## 2) Page Map

### Flowchart

```mermaid
graph TD

%% Phase 1 / MVP
A[Sign In]:::high --> B(Dashboard)
B --> C(Projects)

C --> C1(Project Detail)
C --> C2(Manage RFQ)
C --> C3(Manage Quote)

C2 --> C21(Create RFQ)
C2 --> C22(Distribute RFQ)

C3 --> C31(Submit Quote)
C3 --> C32(Compare Quote)
C3 --> C33(Generate PO)

C --> D(PO Tracker)


%% Phase 2 / Enhancements
B --> M(Suppliers Directory)
B --> N(Material Catalog)
B --> O(Company & Users Management)


%% Priority color classes
classDef high fill:#ff9999,color:#000;
classDef medium fill:#fff799,color:#000;
classDef low fill:#a7c7e7,color:#000;

%% High priority: MVP user flows
class A,B,C,D,C1,C2,C3,C21,C31,C32,C33 high;

%% Medium priority: operational features
class M,N,O,C22 medium;
```

### Additional Explanation

- **Create RFQ** embeds **AI Supplier Suggestions** inline (similar to “Get suggestions”), then persists chosen suppliers. Distribution sends the full RFQ package simultaneously to selected suppliers.
- **Submit Quote** is the supplier's submission step results from distribution. Incoming quotes feed a **side‑by‑side comparison** view.
- **Generate PO** converts an awarded quote into a formal **Purchase Order** with one click, carrying line items and totals forward.
- **PO Tracker** manages a simple workflow (Ordered → Confirmed → Shipped → Delivered) and notifies stakeholders on status changes.
- **Phase 2** introduces the **Suppliers Directory** and **Material Catalog** (company‑owned), plus **Company & Users Management** with RBAC—these power richer operations and multi‑tenant scale.

---

## 3) Tech Stack

- Frontend: **HTMX** + **TailwindCSS**
- Backend: **Express (TypeScript)**
- Database: **PostgreSQL**

---

## 4) Team Member

- M11405103 張梓榆 (CEO)
- M11402802 I Putu Krisna Erlangga (CTO)
- M11405507 陳宇任 (CFO)


