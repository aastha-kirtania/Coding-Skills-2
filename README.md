# SMART NAV

A smart navigation web application that visualizes graphs and calculates shortest paths using Dijkstra's algorithm.

## How the Website Works

SMART NAV is an interactive web application for visualizing and navigating graph-based networks. It combines modern web technologies with efficient pathfinding algorithms to provide real-time shortest path calculations.

### Architecture Overview

The application consists of three main components:

1. **Frontend (React + D3.js)**: Interactive graph visualization and user interface
2. **Backend (Express.js)**: REST API server handling graph operations and path calculations
3. **Algorithm Engine (C++/JavaScript)**: Dijkstra's algorithm implementation for shortest path computation

### Core Features

#### Graph Visualization
- **Interactive Graph Display**: Uses D3.js to render nodes (locations) and links (connections) as an interactive SVG visualization
- **Zoom & Pan**: Users can zoom in/out and pan around the graph for better navigation
- **Node Selection**: Click on nodes to select start and end points for navigation
- **Visual Feedback**: Shortest paths are highlighted in the visualization with animated transitions

#### Graph Editing
- **Add Nodes**: Create new locations in the graph with custom names and positions
- **Add Links**: Connect nodes with weighted edges representing distances or costs
- **Dynamic Updates**: Graph changes are immediately reflected in the visualization

#### Pathfinding
- **Dijkstra's Algorithm**: Calculates the shortest path between any two nodes
- **Dual Implementation**:
  - **C++ Backend**: High-performance implementation for optimal speed
  - **JavaScript Fallback**: Pure JavaScript implementation when C++ is unavailable
- **Performance Metrics**: Displays execution time for algorithm runs
- **Path Details**: Shows the complete route with total distance/cost

### Technical Implementation

#### Frontend (React + TypeScript)
- **React Components**: Modular UI built with React hooks and functional components
- **D3.js Integration**: SVG-based graph rendering with force-directed layouts
- **State Management**: Local state handling for graph data, navigation results, and UI interactions
- **Responsive Design**: Tailwind CSS for modern, responsive styling
- **Animations**: Smooth transitions using Framer Motion

#### Backend (Express.js)
- **REST API**: Endpoints for graph operations (`/api/graph`) and navigation (`/api/navigate`)
- **In-Memory Storage**: Graph data stored in server memory (suitable for demo/development)
- **CORS Support**: Cross-origin requests enabled for frontend communication
- **Error Handling**: Graceful fallbacks when C++ compilation fails

#### Algorithm Implementation
- **C++ Dijkstra**: Priority queue-based implementation for optimal performance
- **JavaScript Dijkstra**: Fallback implementation using arrays and loops
- **Graph Representation**: Adjacency list format for efficient neighbor traversal
- **Input/Output**: Structured data exchange between frontend, backend, and algorithm engine

### Data Flow

1. **Graph Loading**: Frontend fetches initial graph data from `/api/graph`
2. **User Interaction**: Users select start/end nodes or modify the graph
3. **Path Calculation**:
   - Frontend sends navigation request to `/api/navigate`
   - Backend prepares graph data for algorithm execution
   - C++ binary processes the data (if available) or falls back to JavaScript
   - Algorithm returns shortest path and distance
4. **Result Display**: Frontend updates visualization and shows path details

### Sample Graph

The application comes pre-loaded with a sample graph representing locations around Vijayawada, India:
- Railway Station Vijayawada
- PVP (Prasad V. Potluri Siddhartha Institute of Technology)
- PVR Cinemas
- Vijayawada Airport
- Bhavani Island
- Mangalgiri
- SRM AP (SRM University Andhra Pradesh)
- Guntur
- Chirala

### Getting Started

1. **Development**: Run `npm run dev` to start the development server
2. **Build**: Use `npm run build` for production builds
3. **C++ Compilation**: The server automatically compiles the C++ Dijkstra implementation if g++ is available

### Technologies Used

- **Frontend**: React, TypeScript, D3.js, Tailwind CSS, Framer Motion
- **Backend**: Express.js, Node.js
- **Algorithms**: Dijkstra's algorithm (C++ and JavaScript implementations)
- **Build Tools**: Vite, TypeScript compiler
- **Development**: TSX for running TypeScript directly
