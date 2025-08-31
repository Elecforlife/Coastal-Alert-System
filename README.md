# Natural Calamity Prediction System

A **real-time web dashboard** that visualizes **natural calamity predictions** (floods, earthquakes, wildfires) on an **interactive map**, fetches data from **Supabase**, and displays detailed prediction panels and charts. The system leverages **n8n workflows**, **AI agents**, and **Supabase Edge Functions** to automate prediction data processing and storage.

---

## 🌟 Features

- **Interactive Map**
  - Shows disaster locations with **severity-based color markers**:
    - Green = Low  
    - Yellow = Medium  
    - Red = High
  - Zoom, pan, and click markers for detailed information.

- **Prediction Panel / Sidebar**
  - Displays type of calamity, severity, location, confidence percentage, and timestamp.
  - Expandable and sortable table for easy monitoring.

- **Charts & Data Visualization**
  - Bar/pie charts showing disaster type frequency and severity distribution.
  - Real-time updates from Supabase database.

- **Real-Time Updates**
  - Workflow runs every **minute** (using n8n) to fetch data from external APIs.
  - AI agent processes data and sends predictions to Supabase Edge Function.

- **Dark Mode**
  - Default dark theme with optional toggle for light mode.

- **Notifications**
  - Popups for high-severity events to alert users instantly.

---

## 🏗 System Architecture

The system follows this workflow:

1. **Scheduled Trigger (n8n)**  
   - Runs every minute to fetch data from weather, seismic, or disaster APIs.

2. **AI Agent Node (n8n)**  
   - Processes incoming data.
   - Generates predictions for type, severity, location, and confidence.

3. **HTTP Request Node**  
   - Sends processed prediction data to **Supabase Edge Function**.

4. **Supabase Edge Function**  
   - Receives data and stores it in Supabase PostgreSQL tables.
   - Optional: triggers alerts for high-severity predictions.

5. **Frontend Dashboard**  
   - Fetches data from Supabase and displays on **interactive map, prediction panels, and charts**.

**Diagram:**
![Final ](https://github.com/user-attachments/assets/b60e2652-e306-4177-add2-1934c630c38b)


---

## 🛠 Technology Stack

- **Frontend:** React.js, Tailwind CSS, Next.js (optional)  
- **Map:** Leaflet.js / Mapbox GL JS  
- **Charts:** Chart.js / ApexCharts  
- **Backend / Database:** Supabase (PostgreSQL + Edge Functions)  
- **Automation:** n8n workflow for scheduled data processing  
- **AI / Prediction:** LLM (Gemini or chosen model) for analyzing data

---

## 🚀 Installation & Setup

1. **Clone the repository**
```bash
git clone https://github.com/your-username/natural-calamity-prediction.git
cd natural-calamity-prediction

npm install


