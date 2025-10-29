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

A[Homepage]:::high --> B(Executive Summary)
A --> C(Problem Statement)
A --> D(Our Solution)
A --> E(Market & Business)
A --> F(System & Data Design)
A --> G(Team & Contact)

D --> D1(Centralized Management Hub)
D --> D2(Intelligent Procurement Module)
D --> D3(Essential Delivery Oversight)

E --> E1(Market Analysis)
E --> E2(Competitive Analysis)
E --> E3(Business Model)
E --> E4(Product Roadmap)

F --> F1(Data Model & ERD)
F --> F2(MVP vs Full Product)
F --> F3(ETL & Database)

G --> G1(Team Members)
G --> G2(Contact / GitHub Links)

%% 顏色定義（實作優先順序）
classDef high fill:#ff9999,color:#000;
classDef medium fill:#fff799,color:#000;
classDef low fill:#a7c7e7,color:#000;

%% 高優先：MVP 相關頁面
class A,D,D1,D2,D3,F,F1,F3 high;

%% 中優先：說明與商業內容
class B,C,E,E1,E2,E3,E4,F2 medium;

%% 低優先：團隊資訊與聯絡方式
class G,G1,G2 low;
