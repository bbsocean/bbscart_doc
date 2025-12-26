# BBSCART – Troubleshooting Guide

This document lists common issues encountered while developing, running, or deploying BBSCART, along with their fixes.

---

## Backend Issues

### Server not starting

Symptoms:
- Application crashes on start
- Port binding errors

Possible causes:
- Port already in use
- Missing environment variables

Fix:
- Stop the process using the port
- Verify all required environment variables are set
- Restart the backend server

---

### Database connection failed

Symptoms:
- Backend logs show connection timeout or refused

Possible causes:
- MongoDB not running
- Invalid connection string

Fix:
- Ensure MongoDB service is running
- Verify database URI format
- Check network access for cloud databases

---

## Frontend Issues

### API requests failing

Symptoms:
- Network errors in browser console
- 401 or 403 errors

Possible causes:
- Backend server not running
- Invalid or expired authentication token

Fix:
- Start backend server
- Re-login to refresh token
- Verify API base URL configuration

---

### Application not loading

Symptoms:
- Blank page
- Build errors

Possible causes:
- Dependency installation failure
- Build script errors

Fix:
- Reinstall dependencies
- Clear cache and rebuild
- Check console output for errors

---

## Deployment Issues

### Environment variables not applied

Symptoms:
- Application behaves incorrectly after deploy

Possible causes:
- Variables not loaded
- Incorrect environment configuration

Fix:
- Verify environment variable values
- Restart services after configuration changes

---

## General Debugging Tips

- Always check logs first
- Reproduce issues in local or staging environment
- Make one change at a time
- Document new issues and fixes here
