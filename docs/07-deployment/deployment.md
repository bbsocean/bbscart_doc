# BBSCART – Deployment Guide

This document explains how the BBSCART platform is deployed across different environments.

---

## Deployment Environments

### Local
- Used for development and testing
- Runs on developer machines
- Uses local or test databases

### Staging
- Used for pre-production testing
- Mirrors production configuration
- Used for QA and validation

### Production
- Live environment
- Serves real users
- Handles real transactions

---

## High-Level Deployment Flow

1. Code changes are committed to the repository
2. Build process generates production artifacts
3. Environment variables are configured
4. Backend service is started or restarted
5. Frontend build is deployed
6. System health is verified

---

## Backend Deployment

- Backend runs as a Node.js service
- Environment variables are loaded at runtime
- Process manager (example: PM2) keeps service alive

---

## Frontend Deployment

- Frontend is built into static assets
- Assets are served via web server or CDN
- Backend API endpoint is configured per environment

---

## Configuration Management

- Secrets are stored in environment variables
- No secrets are committed to the repository
- Separate configs per environment

---

## Rollback Strategy

- Previous stable build must be preserved
- Rollback is done by redeploying last stable version
- Database changes must be backward compatible

---

## Deployment Safety Rules

- Never deploy directly to production from local
- Always test in staging before production
- Monitor logs and health after deployment
