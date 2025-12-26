# BBSCART – API Index

This document provides an index of all major API endpoints used in the BBSCART platform.

All APIs are exposed by the backend server and consumed by web and mobile clients.

---

## API Design Principles

- REST-based architecture
- JSON request and response format
- Token-based authentication (JWT)
- Role-based access control
- Consistent error responses

---

## Authentication APIs

Purpose:
- User authentication
- Token generation
- Session validation

Examples:
- POST /api/auth/login
- POST /api/auth/register
- POST /api/auth/logout
- GET  /api/auth/profile

---

## User APIs

Purpose:
- User profile management
- Address and preference handling

Examples:
- GET    /api/users/me
- PUT    /api/users/me
- GET    /api/users/:id

---

## Product APIs

Purpose:
- Product catalog access
- Category-based browsing

Examples:
- GET  /api/products
- GET  /api/products/:id
- GET  /api/categories

---

## Order APIs

Purpose:
- Order creation and management
- Order status tracking

Examples:
- POST /api/orders
- GET  /api/orders/:id
- GET  /api/orders/user/:userId

---

## Wallet APIs

Purpose:
- Wallet balance management
- Transaction history

Examples:
- GET  /api/wallet/balance
- GET  /api/wallet/transactions

---

## Payment APIs

Purpose:
- Payment initiation
- Payment status verification

Examples:
- POST /api/payments/initiate
- POST /api/payments/verify

---

## Error Handling

- Standard HTTP status codes are used
- Error responses include:
  - errorCode
  - message
  - optional details

---

## Notes

- Detailed request and response schemas are documented in module-specific files
- API versioning should be introduced when breaking changes occur
