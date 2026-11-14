# CSUN Restaurant Campus Navigator

## Project Overview

The CSUN Restaurant Campus Navigator is a Minimum Viable Product (MVP) designed to help California State University, Northridge (CSUN) students, staff, and visitors find the best dining options on campus. Because there is currently no efficient way to know accessibility and traffic conditions, this tool aims to find the restaurant that is closest in both time and distance.

## Problem Statement

Users on the CSUN campus often want to grab a meal but struggle to determine which dining location is the most accessible. There is no centralized system that accounts for walking distance and campus traffic. Our goal is to build a tool that services the needs of users who want to dine at a restaurant where accessibility and traffic flow are considered.

## Proposed Methods & Algorithms


We will model the CSUN campus as a weighted graph:

- **Vertices (Nodes):** Restaurants, food outlets, and starting user locations.
- **Edges:** Walkable pathways connecting locations.
- **Weights:** Distance in miles (and potentially traffic/congestion data).

To calculate the shortest route, we will implement and compare two classic algorithms:

1. **Dijkstra's Algorithm:** Because all walkable pathway weights (distances) are non-negative, Dijkstra's will efficiently find the shortest path using a binary min-heap.
2. **Bellman-Ford Algorithm:** We will run this in comparison to Dijkstra's to analyze the differences in performance. Bellman-Ford relaxes all edges repeatedly until the shortest path is found.

**Goals for Implementation:**

- Analyze and compare the runtime analysis of both algorithms.
- Ensure both algorithms produce identical shortest paths.
- Apply concepts from graph theory, shortest paths, and heaps.

## Data Sources

- **OpenStreetMap:** An open-source platform maintained by volunteers. We will use this to retrieve exact location coordinates for restaurants and walkable paths. Data can be downloaded as an `.xml` file or accessed via HTTP requests.
- **TomTom Traffic Flow API:** Used to retrieve real-time congestion information to factor into route accessibility.

## Evaluation Plan

- **Scope:** We will focus exclusively on restaurants inside the CSUN campus itself.
- **Challenges Addressed:** CSUN is ever-changing, has high foot traffic, and features multi-story buildings.
- **Focus Areas:** We will prioritize mapping areas where traffic is heavily dense and volatile.
- **Integration:** We will utilize both OpenStreetMap and TomTom's Traffic Flow API to consider the best shortest path based on edge weight (distance) and traffic congestion from desired locations.

## Project Status

**Phase 1: Planning & Data Acquisition** (Current)

- Defining the graph architecture.
- Sourcing data from OpenStreetMap and TomTom.
