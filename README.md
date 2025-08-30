# Coastal-Alert-System
It is an AI driven Coastal Alert System 

# 🌊 Coastal Alert System – n8n Workflow

This project is an **AI-powered coastal weather and disaster alert system** built using **n8n**.  
It collects **real-time weather data** from OpenWeatherMap, analyzes it with **Google Gemini (PaLM) LLM**, and sends predictions/alerts about **tsunamis, cyclones, and sea level rise** to users via **Telegram** and the connected website.

---

## ⚡ Features
- 🌦️ Fetches real-time weather data (temperature, humidity, wind, pressure, sea level, etc.)
- 🤖 Uses **Google Gemini LLM** for analyzing weather patterns
- 🌊 Predicts **Tsunami, Cyclone probability, and Sea Level rise risks**
- 📩 Sends automated alerts to **Telegram** (and can be extended to websites or dashboards)
- 🛠️ Easily configurable city/region for monitoring

---

## 🗂 Workflow Overview
The workflow consists of the following nodes:

1. **Manual Trigger** – Starts the workflow manually (can be scheduled via Cron).
2. **Edit Fields (City Input)** – Defines the city (default: *Mumbai*).
3. **OpenWeatherMap Node** – Fetches live weather data.
4. **Message a Model (Gemini)** – Structures the weather data into a query for analysis.
5. **Message a Model1 (Gemini)** – Predicts probabilities for:
   - Tsunami
   - Cyclone
   - Sea level rise risk
6. **Telegram Node** – Sends the analysis results to users via Telegram.

---

## 🔧 Setup Instructions

### 1. Prerequisites
- **n8n** installed and running ([Docs](https://docs.n8n.io))
- OpenWeatherMap API Key
- Google Gemini (PaLM API) credentials
- Telegram Bot API Token

### 2. Import the Workflow
1. Open your n8n instance.
2. Import the file: [`Coastal Alert System.json`](./Coastal%20Alert%20System.json).
3. Activate the workflow.

### 3. Configure Credentials
- **OpenWeatherMap API**
  - Create an API key from [OpenWeatherMap](https://home.openweathermap.org/).
  - Add it in n8n under *Credentials → OpenWeatherMap*.
- **Google Gemini (PaLM)**
  - Obtain API credentials.
  - Add under *Credentials → Google Gemini (PaLM)*.
- **Telegram**
  - Create a bot via [BotFather](https://t.me/botfather).
  - Add the bot token in *Credentials → Telegram API*.

### 4. Connect to Website (Optional)
- Expose an **n8n Webhook** or **API endpoint** that your website can call.
- Display predictions and alerts in your website’s UI.
- Use a **Webhook Trigger** node instead of Manual Trigger for automation.

---

## 📊 Example Output
The AI model will return results in the following format:

