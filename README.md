# Indoor Navigation System
This project is an indoor navigation application built with Python (Flask) and a web frontend. It calculates and visualizes the shortest paths between rooms across multiple floors, handling staircases and corridors using graph algorithms.

## Features
- Multi-Floor Navigation: Seamlessly finds paths across different levels (Ground, 1st, 2nd floors).
- Interactive Search: Search for rooms by name or type.
- Path Visualization: Generates visual maps showing the route, including floor changes via staircases.
- Emergency Exits: specific functionality to find the nearest emergency exit.

## Prerequisites
- Python 3.8+
- pip (Python package manager)

## Installation
1.  Clone the repository:
    git clone <repository_url>
    cd INDOOR_NAV
    
2.  Install dependencies:
    It is recommended to use a virtual environment.
    python3 -m venv venv
    source venv/bin/activate  # On Windows use `venv\Scripts\activate`
    pip install -r requirements.txt
    
## Usage
1.  Run the application:
    python app.py
    
2.  Access the web interface:
    Open your web browser and navigate to:
    http://127.0.0.1:5000

3.  Find a path:
    - Enter a "Start" location (e.g., a room number or name).
    - Enter an "End" location (or type "Exit" for the nearest emergency exit).
    - Click "Get Path" to view the route.

## Project Structure
- app.py: The main Flask server handling logic, graph construction, and pathfinding.
- geojsons/: Contains GeoJSON files representing the floor plans.
- template/: Contains the index.html frontend file.

## Tech Stack
- Backend: Flask, NetworkX (Graph algorithms), GeoPandas (Spatial data), Shapely (Geometry).
- Visualization: Matplotlib (Plotting paths on maps).
- Frontend: HTML/JS (User interface).

## API Endpoints
- GET /: Serves the frontend application.
- POST /get_path: Calculates the path between two points.
- JSON Body: {"start": "Room A", "end": "Room B"}
- GET /get_rooms: Returns a list of available room types.
- GET /debug_rooms: Returns debugging information about loaded rooms.