#  Weather Analytics Dashboard

### Overview  
The **Weather Analytics Dashboard** is a modern web app that lets users explore and analyze weather patterns for different cities. It pulls in **live weather data**, **past records**, and **forecast trends** to give a complete picture — from what’s happening right now to how things have been changing over time.

The dashboard blends **real-time updates**, **high-performance caching**, and **interactive charts**, allowing users to track **temperature, wind, and rainfall** seamlessly without waiting on slow API calls.

---

##  Key Features

###  Dashboard  
View current weather for multiple cities at once.

Each city card displays:
- Current temperature  
- Condition icon (sun, rain, etc.)  
- Humidity and wind speed  
- Ability to **pin favorite cities** (persisted using localStorage)

---

###  Search & Favorites  
- Search for cities using **WeatherAPI’s autocomplete**.  
- Add or remove favorites instantly.  
- Favorites are **saved locally**, so they persist after reloads.

---

###  Detailed City Analytics  
Click on any city to open its detailed analytics view:
- Current conditions (temperature, “feels like,” humidity, wind, pressure, visibility)  
- Sunrise and sunset times  
- **7-day forecast**  
- **24-hour temperature & rain probability chart**  
- **Historical temperature and wind speed charts**

Fully **responsive** layout that adapts to mobile, tablet, and desktop.

---

###  Interactive Charts (Built with Recharts)
- **Historical Temperature Chart:** daily min/max trends for the past week  
- **7-Day Wind Speed Chart:** historical maximum wind speeds  
- **Hourly Forecast:** temperature and rain probability hour by hour  
- Includes **tooltips**, **resizing**, and instant **Celsius ↔ Fahrenheit** conversion

---

###  Settings  
- Toggle between Celsius (°C) and Fahrenheit (°F) anytime.  
- The unit change updates every component and chart **instantly**.

---

###  Data Caching & Auto-Refresh  
- Backend **caches weather data using Redis** to drastically reduce API load and optimize data retrieval performance.  
- Built-in **rate limiting** prevents overuse and keeps the API stable.

---

##  Tech Stack

###  Frontend  
- React (Functional Components + Hooks)  
- Redux Toolkit (state management)  
- Recharts (data visualization)  
- TailwindCSS (responsive UI)  
- Vite (build tool)

###  Backend  
- Node.js + Express  
- WeatherAPI (live + historical data)  
- Redis (high-performance caching)  
- Express Rate Limit (API protection)

### DevOps & Infrastructure
- **Docker** & **Docker Compose** (containerization and orchestration)

---

##  System Architecture

The **frontend** communicates with a lightweight **Express backend** that handles API calls to WeatherAPI.  
To ensure high speed and reliability, the backend caches responses temporarily in a **Redis** store.  
The client uses **Redux** for centralized state and **Recharts** for all visualizations — keeping everything smooth, reactive, and scalable. All services (frontend, backend, and caching) are containerized using Docker for seamless deployment.

## Getting Started

You can run the entire application stack easily using Docker Compose.

### Prerequisites
- [Docker](https://www.docker.com/get-started) and Docker Compose installed on your machine.
- A WeatherAPI key.

### Setup
1. Clone the repository.
2. Navigate to the `server` directory and create a `.env` file with your environment variables (e.g., `PORT=4000`, your WeatherAPI key).
3. From the root directory, run the following command to build and start the containers:

```bash
docker-compose up --build -d
```
## Accessing the App
Frontend: http://localhost:4173
Backend API: http://localhost:4000
Redis: Running internally on port 6379

