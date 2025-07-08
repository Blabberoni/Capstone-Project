# 🎯 Capstone Project: Real-Time Dynamic Parking Price Optimization

> Dynamic pricing engine for urban parking lots using real-time data streaming, demand drivers & competitive pricing — built with Python (Pandas) and Pathway applications. Includes real-time Data Visualization using Bokeh plots and Panel.

---

## 📌 **Tech Stack**
| Layer | Tools / Libraries |
|-----:|------------------:|
| Streaming data processing | [Pathway](https://pathway.com/) |
| Data manipulation | pandas, numpy |
| Visualization | Bokeh, Panel |
| Notebook & orchestration | Google Colab / Jupyter |
| Storage (CSV simulation) | pandas, local CSV files |

---

## 📊 **Architecture Overview**

**Goal:**  
- Ingest real-time parking data stream
- Compute demand dynamically based on occupancy, queue, traffic, special days & vehicle types
- Compute **real competitor price** using *latitude & longitude*
- Adjust price competitively
- Visualize daily price trend live

---

### 🧩 **Architecture flow:**

```mermaid
flowchart TD
    A[Parking CSV with lat/lon] --> B[Precompute nearby lots]
    B --> C[Pathway streaming]
    C --> D[Tumbling window per lot]
    D --> E[Self-join competitor avg price]
    E --> F[Competitive price]
    F --> G[Live Bokeh+Panel plot]
