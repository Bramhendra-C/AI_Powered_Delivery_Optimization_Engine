AI Powered Delivery Optimization Engine

AI Powered Delivery Optimization Engine is a proof-of-concept system for instant-delivery services that combines geospatial calculations and graph algorithms to compute fast delivery routes. It includes a FastAPI backend for route optimization and a responsive frontend to visualize the results.

Live Demo:
https://bramhendra-c.github.io/AI_Powered_Delivery_Optimization_Engine/
 
GitHub

Table of Contents

Key Features

Tech Stack

Core Concepts

Installation

Usage

API Endpoints

Frontend

Project Structure

Future Enhancements

License

Author

Key Features

FastAPI Backend for optimized delivery route computation. 
GitHub

Geospatial Modeling using the Haversine formula for accurate distance measurement. 
GitHub

Routing Optimization via a Nearest Neighbor heuristic for scalable route approximations. 
GitHub

Responsive Frontend UI built with HTML and Tailwind CSS for interactive route input and visualization. 
GitHub

Live Demo Integration over GitHub Pages. 
GitHub

Tech Stack
Component	Technology
Backend API	Python, FastAPI
ASGI Server	Uvicorn
Frontend UI	HTML5, Tailwind CSS, JS
Optimization Logic	Python Math Library
Deployment	GitHub Pages (Frontend)
Core Concepts

This system solves a variant of the Traveling Salesman Problem (TSP) to visit customer locations efficiently starting from a store/depot.

Distance Calculation: Calculates great-circle distances using the Haversine formula. 
GitHub

Nearest Neighbor Heuristic: At each step, the algorithm selects the nearest unvisited point, building a quick and scalable route. 
GitHub

ETA & Distance Estimation: Translates distances into estimated delivery time using a configurable average speed. 
GitHub

Installation
Prerequisites

Python 3.8+

pip (Python package installer)

Backend Setup (Local)

Clone the repository:

git clone https://github.com/Bramhendra-C/AI_Powered_Delivery_Optimization_Engine.git
cd AI_Powered_Delivery_Optimization_Engine


Install dependencies:

pip install -r requirements.txt


Run the FastAPI server:

uvicorn optimizer_api:app --reload


The API will be available at:
http://127.0.0.1:8000 
GitHub

Usage
Backend
Test the Base Endpoint
curl http://127.0.0.1:8000


Expected response:

{ "message": "Blinkit Order Optimizer API is running." }

Optimize Route

Use the /optimize_route POST endpoint to submit coordinates and receive an optimized route:

Example:

curl -X POST http://127.0.0.1:8000/optimize_route \
  -H "Content-Type: application/json" \
  -d '{"start": [lat, lng], "stops": [[lat, lng], ...]}'

Frontend

Open the optimizer_frontend.html file in a browser or host it on a static server. The frontend interacts with the backend API to display route results dynamically using JavaScript and Tailwind CSS. 
GitHub

Tip: Ensure the API_URL in the script matches your running backend.

Project Structure
AI_Powered_Delivery_Optimization_Engine/
├── optimizer_api.py             # FastAPI backend code
├── optimizer_frontend.html      # Frontend UI file
├── requirements.txt             # Python dependencies
├── render.yaml                  # (optional) deployment config
├── README.md                   # Project README
└── assets/                     # UI assets (screenshots, images)


GitHub

Future Enhancements

Exact Optimization Algorithms (Branch & Bound, Genetic Algorithms).

Time Windows / Constraints Support (VRPTW).

Multiple Vehicles & Depots Optimization.

Integration with Real Road Networks & Traffic APIs (e.g., Google Maps, OSRM). 
GitHub

License

This project is released under the MIT License. 
GitHub

Author

Bramhendra C
GitHub: https://github.com/Bramhendra-C
 
GitHub
