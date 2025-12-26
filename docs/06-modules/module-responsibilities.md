# BBSCART – Module Responsibilities

This document defines the responsibility boundaries of major modules in the BBSCART platform.

Each module must follow single-responsibility principles.

---

## Auth Module

Responsibilities:
- User authentication
- Token generation and validation
- Role and permission checks

Must NOT:
- Handle business logic unrelated to auth
- Access non-auth domain data directly

---

## User Module

Responsibilities:
- User profile management
- Address and preference handling
- User status management

Must NOT:
- Handle payment or order logic

---

## Product Module

Responsibilities:
- Product catalog management
- Category and inventory visibility
- Product pricing data exposure

Must NOT:
- Handle orders or payments

---

## Order Module

Responsibilities:
- Order creation and lifecycle
- Order status transitions
- Order history retrieval

Must NOT:
- Process payments directly
- Modify product catalog

---

## Wallet Module

Responsibilities:
- Wallet balance tracking
- Credit and debit operations
- Transaction history

Must NOT:
- Initiate external payments
- Modify order lifecycle directly

---

## Payment Module

Responsibilities:
- Payment initiation
- Payment verification
- Payment status reporting

Must NOT:
- Store sensitive payment data
- Modify wallet balances directly

---

## Notification Module

Responsibilities:
- Send email and SMS notifications
- Event-based notification triggers

Must NOT:
- Contain business decision logic

---

## General Rules

- Modules communicate through service layers
- Cross-module access must be explicit
- Shared utilities must remain stateless
