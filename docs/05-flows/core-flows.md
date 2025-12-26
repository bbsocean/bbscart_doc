# BBSCART – Core Business Flows

This document describes the primary business flows in the BBSCART platform.

Each flow explains how frontend, backend, and database interact to complete a business action.

---

## Flow 1: User Registration and Login

Actors:
- User
- Frontend
- Backend API
- Database

Steps:
1. User enters registration or login details on frontend
2. Frontend sends request to authentication API
3. Backend validates input and credentials
4. Backend creates or verifies user record in database
5. Backend generates JWT token
6. Token is returned to frontend
7. Frontend stores token securely and grants access

Key APIs:
- POST /api/auth/register
- POST /api/auth/login

---

## Flow 2: Product Browsing

Actors:
- User
- Frontend
- Backend API
- Database

Steps:
1. User browses product listings
2. Frontend requests product data from backend
3. Backend fetches product records from database
4. Backend returns product list to frontend
5. Frontend renders products to user

Key APIs:
- GET /api/products
- GET /api/categories

---

## Flow 3: Order Placement

Actors:
- User
- Frontend
- Backend API
- Database
- Payment Service

Steps:
1. User adds products to cart
2. User initiates checkout
3. Frontend sends order request to backend
4. Backend validates stock and pricing
5. Backend creates order record in database
6. Backend initiates payment process
7. Payment service confirms payment
8. Backend updates order status
9. Frontend displays order confirmation

Key APIs:
- POST /api/orders
- POST /api/payments/initiate
- POST /api/payments/verify

---

## Flow 4: Wallet Transaction

Actors:
- User
- Backend API
- Database

Steps:
1. Backend checks wallet balance
2. Wallet amount is debited or credited
3. Wallet transaction record is created
4. Updated balance is returned

Key APIs:
- GET /api/wallet/balance
- GET /api/wallet/transactions

---

## Flow 5: Order Tracking

Actors:
- User
- Frontend
- Backend API
- Database

Steps:
1. User views order history
2. Frontend requests order details
3. Backend fetches order data
4. Backend returns order status
5. Frontend displays tracking information

Key APIs:
- GET /api/orders/:id
- GET /api/orders/user/:userId

---

## Notes

- All flows are protected by authentication where required
- Backend enforces all business rules
- Frontend never directly modifies data
