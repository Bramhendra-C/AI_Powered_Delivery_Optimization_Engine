# ⚡ Blinkit Order Optimizer 🛵

A proof-of-concept system for instant-delivery services combining **geospatial calculations** and **graph algorithms** to find the fastest delivery route.

---

## 🚀 Status & Badges

![Python](https://img.shields.io/badge/Python-3.x-blue.svg)
![FastAPI](https://img.shields.io/badge/Backend-FastAPI-green.svg)
![Frontend](https://img.shields.io/badge/Frontend-TailwindCSS-blueviolet.svg)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)
![Status](https://img.shields.io/badge/Status-Prototype-orange.svg)

---

## ✨ Key Features

- **🧩 FastAPI Backend:**  
  High-performance API endpoint (`/optimize_route`) for handling route calculations.

- **🌍 Geospatial Modeling:**  
  Uses the **Haversine formula** to accurately calculate great-circle distances between any two Earth coordinates.

- **🧠 Optimization Algorithm:**  
  Implements the **Greedy Nearest Neighbor Heuristic** — an efficient solution for approximating the Traveling Salesman Problem (TSP).

- **⏱️ Real-time ETA:**  
  Calculates **Estimated Time of Arrival (ETA)** based on realistic travel speeds (default: 30 km/h).

- **💻 Sleek Frontend:**  
  Fully responsive **HTML + Tailwind CSS** interface for inputting coordinates and visualizing optimized routes.

- **🔁 Resilient Networking:**  
  Built-in **Exponential Backoff Retry** mechanism ensures stable communication between frontend and backend.

---

## 🛠️ Tech Stack

| Component           | Technology                            | Role |
|---------------------|----------------------------------------|------|
| **Backend Framework** | Python 3.x, FastAPI                    | High-performance API for optimization logic |
| **Logic Core**        | Python, Math Library                  | Haversine distance + Nearest Neighbor algorithm |
| **API Server**        | Uvicorn                              | ASGI server to run FastAPI |
| **Frontend**          | HTML5, Tailwind CSS                   | Responsive UI and visualization |
| **Interoperability**  | JavaScript, Fetch API, CORS           | Frontend-backend communication |

---

## 📐 Optimization Logic Explained

The core optimization challenge is based on the **Traveling Salesman Problem (TSP)** — finding the shortest possible route visiting all destinations once and returning to the depot.

### ⚙️ Steps:

1. **Distance Calculation:**  
   Uses the **Haversine formula** (in `optimizer_api.py`) to compute distances between store and customers in kilometers.

2. **Time Estimation:**  
   Converts distances into travel times using a fixed average speed (default: 30 km/h).

3. **Routing Strategy:**  
   The `nearest_neighbor_optimization` function:
   - Starts at the depot.
   - Repeatedly chooses the **nearest unvisited** customer.
   - Continues until all drop-offs are complete.

### ⚖️ Trade-offs
- The **Nearest Neighbor heuristic** is **fast and scalable**, ideal for dense zones.
- However, it’s **not guaranteed optimal**.  
  For absolute shortest routes, consider advanced algorithms like **Dijkstra’s**, **Simulated Annealing**, or **Brute Force** (for very small datasets).

---

## 🚀 Getting Started

### 🧩 Prerequisites
- Python **3.8+** installed on your system.

---

### 🧠 Step 1: Set up and Run the Backend

1. **Install required libraries:**
   ```bash
   pip install fastapi uvicorn pydantic python-multipart starlette-cors
2.Save backend code:
  Save the Python file as optimizer_api.py.

3.Start the FastAPI server:
  uvicorn optimizer_api:app --reload
  The server will start on: http://127.0.0.1:8000

  
🌐 Step 2: Run the Frontend

Save frontend file:
Save the HTML code as optimizer_frontend.html.

Open in browser:
Simply double-click the file or open it in your browser.
💡 Usage Guide

Ensure the FastAPI server is running.

Open the frontend HTML file.

Click "Calculate Fastest Route" to start optimization.

View the step-by-step route and Total Distance + ETA in the results panel.

✅ You can also input your own coordinates (latitude, longitude pairs per line) to test different areas.
📈 Future Enhancements
Feature	Description
🚚 VRPTW (Vehicle Routing Problem with Time Windows)	Add delivery time window constraints per customer.
📦 Capacity Constraints	Incorporate vehicle weight/volume limits, enabling multi-trip planning.
🗺️ Live Traffic Integration	Replace static Haversine distances with real-world Maps Directions API (e.g., Google Maps, OpenRouteService).
📜 License

This project is released under the MIT License
.

🧠 Author

Bramhendra C

---

Would you like me to make this **README include GitHub-style code blocks for both backend and frontend setup** (with example snippets of the API route and frontend fetch call)?  
That makes it look more complete for recruiters or project showcases.