# BBSCART – Database Collections

This document describes the primary MongoDB collections used in the BBSCART platform.

---

## Database Overview

BBSCART uses MongoDB as its primary data store.

Design principles:
- Each collection represents a clear business entity
- Documents are structured for fast read operations
- Relationships are handled using references where required
- Indexes are used for frequently queried fields

---

## Core Collections

### 1. users

Purpose:
- Store user identity and authentication data

Key fields:
- _id
- name
- email
- phone
- passwordHash
- role
- isActive
- createdAt

Relationships:
- Referenced by orders
- Referenced by wallet transactions

Indexes:
- email (unique)
- phone (unique)

---

### 2. products

Purpose:
- Store product catalog data

Key fields:
- _id
- name
- sku
- category
- price
- stock
- status
- createdAt

Relationships:
- Referenced by orders

Indexes:
- sku (unique)
- category

---

### 3. orders

Purpose:
- Store customer order records and lifecycle state

Key fields:
- _id
- orderNumber
- userId
- items
- totalAmount
- paymentStatus
- orderStatus
- createdAt

Relationships:
- References users
- References products

Indexes:
- orderNumber (unique)
- userId
- orderStatus

---

### 4. walletTransactions

Purpose:
- Track wallet credits and debits

Key fields:
- _id
- userId
- amount
- transactionType
- referenceId
- createdAt

Relationships:
- References users
- References orders

Indexes:
- userId
- transactionType

---

## Supporting Collections (High Level)

Examples:
- categories
- reviews
- addresses
- notifications
- auditLogs

Each supporting collection follows the same principles:
- Clear ownership
- Minimal duplication
- Indexed access paths

---

## Data Integrity Rules

- Backend enforces schema validation
- Business rules applied before writes
- No direct client access to database
- Soft deletes preferred over hard deletes where applicable

---

## Migration and Changes

- Any schema change must be documented here
- Backward compatibility should be maintained
- Index changes must be reviewed for performance impact
