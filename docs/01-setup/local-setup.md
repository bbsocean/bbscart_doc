# BBSCART – Local Setup Guide

This document explains how to set up and run the BBSCART project in a local development environment.

---

## Prerequisites

Before starting, ensure the following tools are installed:

### System Requirements
- Windows / macOS / Linux
- Minimum 8 GB RAM recommended

### Software Requirements
- Node.js (LTS version)
- npm or yarn
- MongoDB (local or cloud)
- Git
- VS Code (recommended)

---

## Project Structure

High-level folders:
- backend/   → API server
- frontend/  → Web application
- docs/      → Technical documentation

---

## Backend Setup

1. Navigate to backend folder
2. Install dependencies
3. Configure environment variables
4. Start backend server

Example steps:
- npm install
- npm start

Environment variables are loaded from `.env` files.

---

## Frontend Setup

1. Navigate to frontend folder
2. Install dependencies
3. Start development server

Example steps:
- npm install
- npm start

Frontend communicates with backend via REST APIs.

---

## Database Setup

- MongoDB must be running before backend starts
- Can be local MongoDB or MongoDB Atlas
- Connection string is provided via environment variable

---

## Common Setup Issues

### Port already in use
- Stop the process using the port
- Or change the port in configuration

### Environment variables not loading
- Check file name and location
- Restart the server after changes

### Database connection failed
- Verify MongoDB is running
- Check connection string format

---

## Verification Checklist

- Backend server starts without errors
- Frontend loads in browser
- API requests return valid responses
- Database connection is successful
