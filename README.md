# Soorjayan's Tech Zone

## Electronics E-Commerce & Shop Management System

> A full-stack, role-based electronics e-commerce and shop-management
> web application developed as an internship/project system. The
> application combines product catalog management, inventory control,
> customer shopping, order processing, delivery operations, supplier
> management, staff permissions, payment-status management,
> authentication, and responsive UI design.

------------------------------------------------------------------------

## 1. Project Overview

**Project Name:** Soorjayan's Tech Zone\
**Project Type:** Full-Stack Web Application / Electronics E-Commerce &
Shop Management System\
**Frontend:** React + Vite\
**Backend:** Node.js + Express\
**Database:** MongoDB + Mongoose\
**Authentication:** JWT + bcryptjs\
**API Communication:** Axios\
**Icons/UI:** Lucide React + custom CSS\
**Development API:** `http://localhost:5000/api`\
**Development Frontend:** `http://localhost:5173`

The project was developed around a product-catalog/shop-management
requirement and has been expanded into a multi-role electronics store
platform.

------------------------------------------------------------------------

## 2. Main Objectives

The system is designed to:

-   Manage an electronics product catalog.
-   Manage categories and brands.
-   Manage inventory and stock movements.
-   Manage suppliers.
-   Manage customers.
-   Manage shop staff and permissions.
-   Manage delivery staff.
-   Allow customers to register and shop online.
-   Provide a shopping cart and checkout flow.
-   Create and manage customer orders.
-   Assign orders to delivery staff.
-   Track order statuses.
-   Track payment statuses and payment history.
-   Provide role-based access control.
-   Provide dashboards and operational summaries.
-   Provide profile management and password management.
-   Provide responsive light/dark user interfaces.

------------------------------------------------------------------------

# 3. User Roles

The current system supports four login roles.

  -----------------------------------------------------------------------
  Role                                Main Responsibilities
  ----------------------------------- -----------------------------------
  **Admin**                           Full system management

  **Staff**                           Restricted operational management
                                      based on permissions

  **Delivery Staff**                  View and manage assigned delivery
                                      orders

  **Customer**                        Browse products, manage cart,
                                      checkout and view own orders
  -----------------------------------------------------------------------

### Supplier

Suppliers are **not login users** in the current design.

Supplier information is managed by the Admin and linked to products.

------------------------------------------------------------------------

# 4. Role-Based Permissions

Staff accounts can receive the following permissions:

-   `productManagement`
-   `inventoryManagement`
-   `orderProcessing`
-   `customerManagement`

This allows the Admin to create staff accounts with controlled access
instead of giving every staff member full administrative privileges.

The backend uses:

-   JWT authentication
-   role authorization
-   permission checking

to protect management endpoints.

------------------------------------------------------------------------

# 5. Technology Stack

## Frontend

-   React 19
-   Vite 7
-   React Router
-   Axios
-   Lucide React
-   CSS
-   Local Storage for client-side UI/account preferences

## Backend

-   Node.js
-   Express 5
-   MongoDB
-   Mongoose
-   JWT
-   bcryptjs
-   dotenv
-   Nodemon

## Development Tools

-   VS Code
-   MongoDB
-   Postman
-   Git / GitHub
-   Browser developer tools

------------------------------------------------------------------------

# 6. System Architecture

``` text
                    ┌─────────────────────────┐
                    │       React Frontend    │
                    │       Vite + React      │
                    └────────────┬────────────┘
                                 │
                              Axios
                                 │
                                 ▼
                    ┌─────────────────────────┐
                    │     Express REST API    │
                    │       Node.js           │
                    └────────────┬────────────┘
                                 │
              ┌──────────────────┼──────────────────┐
              │                  │                  │
              ▼                  ▼                  ▼
        JWT Authentication   Controllers        Middleware
              │                  │          Role + Permission
              │                  │
              └──────────────────┼─────────────────┐
                                 ▼                 │
                         ┌───────────────┐         │
                         │    Mongoose   │◄────────┘
                         └───────┬───────┘
                                 │
                                 ▼
                         ┌───────────────┐
                         │    MongoDB    │
                         └───────────────┘
```

------------------------------------------------------------------------

# 7. Backend Structure

``` text
backend/
├── server.js
├── createAdmin.js
├── package.json
├── package-lock.json
├── .gitignore
├── ADMIN_ORDER_MANAGEMENT.md
├── CATEGORY_BRAND_MANAGEMENT.md
├── INVENTORY_MANAGEMENT.md
├── SUPPLIER_MANAGEMENT.md
├── USER_AND_DELIVERY_MANAGEMENT.md
└── src/
    ├── config/
    │   └── db.js
    ├── controllers/
    │   ├── authController.js
    │   ├── brandController.js
    │   ├── cartController.js
    │   ├── catalogController.js
    │   ├── categoryController.js
    │   ├── customerController.js
    │   ├── dashboardController.js
    │   ├── deliveryController.js
    │   ├── inventoryController.js
    │   ├── orderController.js
    │   ├── paymentController.js
    │   ├── productController.js
    │   ├── profileController.js
    │   ├── staffController.js
    │   └── supplierController.js
    ├── middleware/
    │   └── authMiddleware.js
    ├── models/
    │   ├── Brand.js
    │   ├── Cart.js
    │   ├── Category.js
    │   ├── Order.js
    │   ├── Product.js
    │   ├── StockMovement.js
    │   ├── Supplier.js
    │   └── User.js
    ├── routes/
    │   ├── authRoutes.js
    │   ├── brandRoutes.js
    │   ├── cartRoutes.js
    │   ├── categoryRoutes.js
    │   ├── customerRoutes.js
    │   ├── dashboardRoutes.js
    │   ├── deliveryRoutes.js
    │   ├── inventoryRoutes.js
    │   ├── orderRoutes.js
    │   ├── paymentRoutes.js
    │   ├── productRoutes.js
    │   ├── profileRoutes.js
    │   ├── staffRoutes.js
    │   └── supplierRoutes.js
    └── utils/
        └── auth.js
```

------------------------------------------------------------------------

# 8. Frontend Structure

``` text
frontend/
├── index.html
├── package.json
├── .env.example
├── assets/
├── src/
│   ├── App.jsx
│   ├── index.css
│   ├── assets/
│   ├── components/
│   │   └── common/
│   ├── context/
│   │   └── AuthContext.jsx
│   ├── layouts/
│   │   └── AppLayout.jsx
│   ├── pages/
│   │   ├── Dashboard.jsx
│   │   ├── Profile.jsx
│   │   ├── auth/
│   │   ├── catalog/
│   │   ├── customer/
│   │   ├── customers/
│   │   ├── delivery/
│   │   ├── inventory/
│   │   ├── orders/
│   │   ├── products/
│   │   ├── staff/
│   │   └── suppliers/
│   ├── routes/
│   └── services/
└── ...
```

------------------------------------------------------------------------

# 9. Authentication & Account Management

Implemented:

-   Customer registration
-   Login
-   JWT authentication
-   Role-based login
-   Password hashing using bcryptjs
-   Account active/inactive handling
-   Change password
-   Forgot-password request
-   Password reset using a temporary token
-   Protected routes
-   Automatic handling of unauthorized API responses
-   Profile retrieval
-   Profile update

### Password Reset Note

The current backend generates a secure reset token with a 15-minute
expiration. The API response explicitly indicates that the token should
be connected to an email service for production use.

A production email provider has **not yet been integrated**.

------------------------------------------------------------------------

# 10. Product Catalog Management

The product system supports:

-   Create product
-   View products
-   View product details
-   Update product
-   Delete product
-   Product image URL
-   Product name
-   Brand
-   Category
-   Description
-   Price
-   Discount
-   Stock
-   Warranty
-   Supplier
-   Specifications

Supported specifications include:

-   Processor
-   RAM
-   Storage
-   Display
-   Graphics

### Product Search & Filtering

The backend supports:

-   Search by product name
-   Search by brand
-   Search by category
-   Category filtering
-   Brand filtering
-   Minimum price
-   Maximum price
-   Minimum stock
-   Sorting
-   Pagination

Supported sorting includes:

-   Newest
-   Oldest
-   Price ascending
-   Price descending
-   Name ascending
-   Name descending
-   Stock ascending
-   Stock descending

------------------------------------------------------------------------

# 11. Category Management

Admin can:

-   Create categories
-   List categories
-   Search categories
-   Filter by status
-   View category details
-   View linked product count
-   View category statistics
-   Update categories
-   Activate/deactivate categories
-   Delete categories when no products are linked

The backend also updates product category references when a category
name is changed.

Delete protection prevents deletion while products still use the
category.

------------------------------------------------------------------------

# 12. Brand Management

Admin can:

-   Create brands
-   List brands
-   Search brands
-   Filter by status
-   View brand details
-   View linked product count
-   View statistics
-   Update brands
-   Activate/deactivate brands
-   Delete brands when no products are linked

When a brand name is changed, linked product records are updated.

Delete protection prevents deletion while products still use the brand.

------------------------------------------------------------------------

# 13. Supplier Management

Suppliers are managed by Admin.

Supported operations:

-   Create supplier
-   List suppliers
-   Search suppliers
-   Filter by status
-   View supplier details
-   View supplied product count
-   Update supplier
-   Activate/deactivate supplier
-   Delete supplier
-   Supplier statistics

Supplier information includes:

-   Name
-   Company
-   Contact person
-   Phone
-   Email
-   Address
-   Supplied categories
-   Status

### Supplier Login

There is intentionally **no Supplier login** in the current system.

------------------------------------------------------------------------

# 14. Inventory Management

Inventory management is one of the completed core modules.

Supported operations:

-   View inventory
-   Search inventory
-   View low-stock products
-   View out-of-stock products
-   View inventory statistics
-   View stock movements
-   Add stock
-   Reduce stock
-   Adjust stock
-   View product stock history

### Low-Stock Rule

The current inventory threshold is:

``` text
5 units
```

A product is considered low stock when:

``` text
stock > 0 AND stock <= 5
```

A product with:

``` text
stock = 0
```

is treated as out of stock.

### Stock Movement Types

-   RESTOCK
-   SALE
-   ADJUSTMENT
-   CANCELLATION

The system records:

-   Stock before
-   Stock after
-   Quantity
-   Direction
-   Product
-   User who performed the action
-   Reference
-   Note
-   Timestamp

------------------------------------------------------------------------

# 15. Customer Shopping

Customers can:

-   Register
-   Login
-   Browse products
-   Search products
-   Filter products
-   Sort products
-   View product details
-   Add products to cart
-   Increase quantity
-   Decrease quantity
-   Remove products
-   Clear cart
-   View cart totals
-   Checkout
-   Select payment method
-   Create orders
-   View order history
-   View individual orders
-   Cancel eligible orders
-   Manage profile

------------------------------------------------------------------------

# 16. Shopping Cart

The cart supports:

-   Add item
-   Update quantity
-   Remove item
-   Clear cart
-   Calculate subtotal
-   Calculate total item count
-   Validate available stock

The current frontend quantity controls are connected to:

``` text
PUT /api/cart/:productId
```

so the `+` and `−` controls update the corresponding backend cart item.

------------------------------------------------------------------------

# 17. Checkout & Orders

Customers can create an order from their cart.

Checkout collects:

-   Customer name
-   Phone
-   Address
-   Payment method

Supported payment methods:

-   COD
-   BANK_TRANSFER

### Delivery Fee

Current backend rule:

``` text
Subtotal >= Rs. 100,000 → Free delivery
Subtotal < Rs. 100,000 → Rs. 500 delivery fee
```

When an order is created:

1.  Cart is validated.
2.  Product stock is checked.
3.  Stock is reduced.
4.  SALE stock movements are recorded.
5.  Order is created.
6.  Payment status starts as `PENDING`.
7.  Order status starts as `PLACED`.
8.  Cart is cleared.

The order creation uses a MongoDB transaction/session.

------------------------------------------------------------------------

# 18. Order Status Workflow

The system supports:

``` text
PLACED
   ↓
CONFIRMED
   ↓
PROCESSING
   ↓
SHIPPED
   ↓
OUT_FOR_DELIVERY
   ↓
DELIVERED
```

Cancellation is also supported for eligible orders.

The backend prevents invalid changes from:

-   `DELIVERED`
-   `CANCELLED`

to another status.

------------------------------------------------------------------------

# 19. Order Cancellation & Stock Restoration

Customers can cancel their own orders when the order is:

-   PLACED
-   CONFIRMED

Admin can also cancel eligible orders.

When an order is cancelled:

-   Product stock is restored.
-   A `CANCELLATION` stock movement is recorded.
-   Order status becomes `CANCELLED`.

------------------------------------------------------------------------

# 20. Delivery Staff Management

Admin can:

-   Create delivery staff
-   List delivery staff
-   Search delivery staff
-   Filter active/inactive staff
-   View delivery staff details
-   Update delivery staff
-   Activate/deactivate delivery staff
-   Delete delivery staff

Deletion is protected when the delivery staff member still has active
assigned orders.

------------------------------------------------------------------------

# 21. Delivery Assignment

Admin can assign an active delivery staff member to an order.

The system:

-   Validates the delivery staff account.
-   Prevents assignment to cancelled orders.
-   Prevents assignment to delivered orders.
-   Stores the assigned delivery staff ID.
-   Changes suitable orders to `OUT_FOR_DELIVERY`.

Delivery staff can access their own assigned orders.

They cannot access or update orders that are not assigned to them.

------------------------------------------------------------------------

# 22. Payment Management

Payment management supports:

-   Payment status update
-   Payment history
-   Payment statistics
-   Payment-method breakdown

Payment statuses:

``` text
PENDING
PAID
FAILED
```

Each payment status update can include a note and the user who performed
the update.

### Current Payment Scope

The project currently implements payment-status management rather than a
live external payment gateway.

------------------------------------------------------------------------

# 23. Customer Management

Admin and appropriately-permissioned staff can:

-   List customers
-   Search customers
-   Filter active/inactive customers
-   View customer details
-   View customer order count
-   View customer orders
-   Update customer information
-   Activate/deactivate customers

Admin can also view customer statistics.

------------------------------------------------------------------------

# 24. Staff Management

Admin can:

-   Create staff
-   List staff
-   Search staff
-   View staff
-   Update staff
-   Change staff status
-   Delete staff
-   Assign operational permissions

Staff permissions include:

``` text
Product Management
Inventory Management
Order Processing
Customer Management
```

------------------------------------------------------------------------

# 25. Admin Dashboard

The backend dashboard provides:

-   Total products
-   Total customers
-   Total orders
-   Total revenue
-   Pending orders
-   Delivered orders
-   Low-stock products
-   Out-of-stock products
-   Active suppliers
-   Active staff
-   Inventory value
-   Inventory units
-   Orders by status
-   Sales by month
-   Top-selling products
-   Category distribution
-   Brand distribution

The frontend dashboard presents these values through cards and
operational sections.

------------------------------------------------------------------------

# 26. Role-Specific Dashboards

The frontend has role-aware dashboard experiences.

### Admin

Includes business-management information such as:

-   Store overview
-   Product management
-   Inventory
-   Orders
-   Customers
-   Suppliers
-   Staff
-   Delivery staff
-   Dashboard statistics
-   Recent orders
-   Low-stock/attention areas

### Staff

Dashboard content is based on assigned permissions and operational
responsibilities.

### Delivery Staff

Includes:

-   Assigned delivery orders
-   Delivery progress
-   Delivery-related checklist/summary

### Customer

Includes:

-   My orders
-   Orders in progress
-   Delivered orders
-   Order value
-   Quick shopping actions
-   My cart
-   My profile
-   Recent orders

The current customer dashboard's **Recent Orders** section is
display-only. Individual rows are not navigation buttons. A **See all**
action is used to open the full My Orders page.

------------------------------------------------------------------------

# 27. Profile Management

All four user roles have profile functionality.

Users can edit:

-   Name
-   Phone
-   Address

The profile editing behavior is:

``` text
Edit profile
     ↓
Fields become editable
     ↓
Save profile
     ↓
API update
     ↓
Fields become read-only
     ↓
Button returns to Edit profile
```

After a successful save, the authenticated user information is updated
in shared frontend state/local storage so the account name shown in the
sidebar and top header updates immediately.

------------------------------------------------------------------------

# 28. Profile Pictures

The UI supports profile pictures for:

-   Admin
-   Staff
-   Delivery Staff
-   Customer

The current implementation stores profile-picture data client-side using
browser local storage.

Profile pictures are displayed in:

-   Sidebar
-   Top header
-   Profile area

No backend image-storage service has been integrated yet.

------------------------------------------------------------------------

# 29. Frontend UI/UX Improvements Completed

A significant amount of work has been completed on the interface.

### Login Interface

Implemented:

-   Full-screen login
-   Technology-device background
-   Tech Zone branding
-   Role selection
-   Email input
-   Password input
-   Password visibility toggle
-   Forgot password link
-   Customer registration link
-   Dark/light theme
-   Responsive design
-   Blue gradient sign-in button
-   Technology-themed visual panel
-   Copyright footer

The **Smart Store Management** badge has been positioned to align with
the main headline.

The sign-in panel was also reduced in size for a more compact layout.

------------------------------------------------------------------------

# 30. Registration Interface

Implemented:

-   Customer registration form
-   Same Tech Zone logo as the main application
-   Light mode
-   Dark mode
-   Theme toggle
-   Dark-mode input visibility
-   Responsive registration layout
-   Password input
-   Customer details
-   Link back to login

The original `TZ` placeholder branding was replaced with the actual Tech
Zone logo.

------------------------------------------------------------------------

# 31. Forgot Password Interface

Implemented:

-   Forgot password page
-   Same Tech Zone logo
-   Email input
-   Reset request
-   Back to sign-in
-   Light/dark mode
-   Theme toggle
-   Improved dark-mode contrast
-   Visible form controls
-   Password-reset messaging

The backend reset-token flow is already implemented, while production
email delivery remains a future integration.

------------------------------------------------------------------------

# 32. Dark Mode

Dark mode has been progressively improved across the application.

Areas specifically refined include:

-   Dashboard
-   Statistics cards
-   Product filters
-   Product details
-   Product specifications
-   Modals
-   Inventory
-   Cart
-   Registration
-   Forgot password
-   Login
-   Decorative dashboard circles/orbs
-   Buttons
-   Form inputs
-   Dropdowns
-   Order areas

The goal is to avoid white/low-contrast blocks and keep text and
controls readable on dark surfaces.

The theme is persisted in browser storage.

------------------------------------------------------------------------

# 33. Light Mode

Light mode remains supported throughout the application.

The interface uses:

-   White cards
-   Light blue backgrounds
-   Blue primary actions
-   Dark readable text
-   Light borders
-   Blue navigation theme

------------------------------------------------------------------------

# 34. Display Zoom

The application includes a display zoom control in the authenticated
header.

Current requested behavior:

``` text
25%
 ↓
30%
 ↓
40%
 ↓
50%
 ↓
...
 ↓
200%
```

-   `+` increases by 10%.
-   `−` decreases by 10%.
-   Minimum: 25%.
-   Maximum: 200%.
-   The selected zoom value is persisted.

------------------------------------------------------------------------

# 35. Product Image Improvements

Product images have been improved so that supplied images are displayed
using:

``` css
object-fit: contain;
object-position: center;
```

This prevents products from being unnecessarily cropped.

The product details image area was also reduced and balanced for a
cleaner layout.

------------------------------------------------------------------------

# 36. Responsive Design

The frontend contains responsive layouts for:

-   Desktop
-   Tablet
-   Mobile

Responsive behavior includes:

-   Collapsible sidebar
-   Mobile navigation
-   Responsive product grids
-   Responsive forms
-   Responsive dashboard cards
-   Responsive cart layout
-   Responsive checkout layout
-   Responsive product details
-   Responsive authentication pages

------------------------------------------------------------------------

# 37. Navigation & Protected Routes

The React application currently includes routes for:

``` text
/
 /login
 /register
 /forgot-password
 /dashboard
 /products
 /products/:id
 /categories
 /brands
 /inventory
 /suppliers
 /customers
 /staff
 /delivery-staff
 /orders
 /my-orders
 /cart
 /checkout
 /profile
```

Protected routes require authentication.

Role-specific routes restrict access according to the logged-in user's
role.

------------------------------------------------------------------------

# 38. REST API Summary

## Authentication

``` text
POST   /api/auth/register
POST   /api/auth/login
POST   /api/auth/forgot-password
POST   /api/auth/reset-password
PATCH  /api/auth/change-password
```

## Products

``` text
GET    /api/products
GET    /api/products/:id
POST   /api/products
PUT    /api/products/:id
DELETE /api/products/:id
```

## Cart

``` text
GET    /api/cart
POST   /api/cart
PUT    /api/cart/:productId
DELETE /api/cart/:productId
DELETE /api/cart
```

## Orders

``` text
POST   /api/orders
GET    /api/orders
GET    /api/orders/my-orders
GET    /api/orders/my-orders/:id
GET    /api/orders/:id
GET    /api/orders/stats
PUT    /api/orders/:id/status
PUT    /api/orders/:id/cancel
PATCH  /api/orders/:id/assign-delivery
```

## Inventory

``` text
GET    /api/inventory
GET    /api/inventory/low-stock
GET    /api/inventory/out-of-stock
GET    /api/inventory/stats
GET    /api/inventory/movements
PUT    /api/inventory/:productId/add-stock
PUT    /api/inventory/:productId/reduce-stock
PUT    /api/inventory/:productId/adjust-stock
GET    /api/inventory/:productId/history
```

## Categories

``` text
GET    /api/categories
GET    /api/categories/:id
GET    /api/categories/stats
POST   /api/categories
PUT    /api/categories/:id
PATCH  /api/categories/:id/status
DELETE /api/categories/:id
```

## Brands

``` text
GET    /api/brands
GET    /api/brands/:id
GET    /api/brands/stats
POST   /api/brands
PUT    /api/brands/:id
PATCH  /api/brands/:id/status
DELETE /api/brands/:id
```

## Suppliers

``` text
GET    /api/suppliers
GET    /api/suppliers/:id
GET    /api/suppliers/stats
POST   /api/suppliers
PUT    /api/suppliers/:id
PATCH  /api/suppliers/:id/status
DELETE /api/suppliers/:id
```

## Customers

``` text
GET    /api/customers
GET    /api/customers/:id
GET    /api/customers/stats
PUT    /api/customers/:id
PATCH  /api/customers/:id/status
```

## Staff

``` text
POST   /api/staff
GET    /api/staff
GET    /api/staff/:id
PUT    /api/staff/:id
PATCH  /api/staff/:id/status
DELETE /api/staff/:id
```

## Delivery Staff

``` text
POST   /api/delivery-staff
GET    /api/delivery-staff
GET    /api/delivery-staff/:id
GET    /api/delivery-staff/my-orders
PUT    /api/delivery-staff/:id
PATCH  /api/delivery-staff/:id/status
DELETE /api/delivery-staff/:id
```

## Payments

``` text
PATCH  /api/payments/:id/payment-status
GET    /api/payments/:id/history
GET    /api/payments/stats
```

## Profile

``` text
GET    /api/profile
PUT    /api/profile
PATCH  /api/profile/password
```

## Dashboard

``` text
GET    /api/dashboard
```

------------------------------------------------------------------------

# 39. Database Collections

The current MongoDB/Mongoose models are:

``` text
User
Product
Category
Brand
Supplier
Cart
Order
StockMovement
```

### User

Stores:

-   Name
-   Email
-   Password hash
-   Phone
-   Address
-   Role
-   Status
-   Permissions
-   Password-reset token information

### Product

Stores:

-   Name
-   Brand
-   Category
-   Description
-   Price
-   Discount
-   Stock
-   Image
-   Specifications
-   Warranty
-   Supplier
-   Status

### Order

Stores:

-   Customer
-   Items
-   Shipping address
-   Payment method
-   Payment status
-   Payment history
-   Order status
-   Assigned delivery staff
-   Subtotal
-   Delivery fee
-   Total amount

------------------------------------------------------------------------

# 40. Security Features

Implemented security-related mechanisms include:

-   Password hashing
-   JWT authentication
-   Protected API routes
-   Role authorization
-   Permission authorization
-   Active/inactive account checking
-   Ownership checks for customer orders
-   Delivery-assignment checks
-   Password reset token hashing
-   Password reset expiration
-   Input validation through Mongoose schemas
-   Unauthorized-response handling in Axios

The frontend stores the JWT in browser local storage for the current
internship/demo implementation.

------------------------------------------------------------------------

# 41. Testing & Development Progress

During development, the backend functionality has been tested
progressively using Postman and application flows.

Areas verified during development include:

### Product

-   Product CRUD
-   Search
-   Filtering
-   Sorting
-   Pagination
-   Product details
-   Validation
-   Role-based update/delete behavior

### Cart

-   Get cart
-   Add item
-   Update quantity
-   Remove item
-   Clear cart
-   Cart totals
-   Product information in cart
-   Cart clearing after order

### Authentication

-   Customer registration
-   Login
-   JWT authentication
-   Role handling
-   Password-related flows

### Orders

-   Order creation
-   Order listing
-   Search
-   Status filtering
-   Payment filtering
-   Pagination
-   Order details
-   Status updates
-   Order statistics
-   Cancellation
-   Stock restoration
-   Delivery assignment

### Inventory

-   Inventory list
-   Low stock
-   Out of stock
-   Statistics
-   Add stock
-   Reduce stock
-   Adjust stock
-   Stock history
-   Sale movements
-   Cancellation movements

### Suppliers

-   Create
-   List
-   Search
-   Status filtering
-   Details
-   Statistics
-   Update
-   Activate/deactivate
-   Delete protection

### Categories

-   Create
-   List
-   Search
-   Status filtering
-   Details
-   Statistics
-   Update
-   Activate/deactivate
-   Reactivation
-   Delete protection

### Brands

-   Create
-   List
-   Search
-   Status filtering
-   Details
-   Statistics
-   Update
-   Activate/deactivate
-   Reactivation
-   Delete protection

### Delivery

-   Delivery staff creation
-   Listing
-   Assignment
-   Assigned-order retrieval
-   Status updates
-   Active/inactive handling
-   Protection against deleting staff with active assignments

------------------------------------------------------------------------

# 42. Important Development Fixes Completed

Several integration problems were identified and corrected during
development.

### Backend route mounting

The backend was updated to mount:

``` text
/api/customers
/api/staff
/api/delivery-staff
/api/payments
/api/profile
/api/dashboard
```

### CORS

Local development CORS support was added for common Vite/React
development origins.

### Health endpoint

Added:

``` text
GET /api/health
```

### Delivery assignment

Added order-to-delivery-staff assignment support.

### Frontend delivery-staff loading

Corrected frontend handling of the backend response structure so active
delivery staff appear in the assignment control.

### Cart update

Corrected the frontend cart update request to match:

``` text
PUT /api/cart/:productId
```

instead of sending the product ID only in the request body.

### Dashboard data handling

Frontend dashboard handling was aligned with the backend `data.summary`
structure.

------------------------------------------------------------------------

# 43. Current UI Branding

The application uses the **Soorjayan's Tech Zone / Tech Zone** branding
across:

-   Login
-   Registration
-   Forgot password
-   Sidebar
-   Header
-   Profile
-   Authenticated pages

The technology-themed logo is used instead of the earlier placeholder
`TZ` branding.

The login interface also uses technology-device artwork.

------------------------------------------------------------------------

# 44. Current Project Status

### Completed Core Modules

-   [x] React frontend
-   [x] Express backend
-   [x] MongoDB/Mongoose integration
-   [x] JWT authentication
-   [x] Customer registration/login
-   [x] Role-based access
-   [x] Staff permissions
-   [x] Product management
-   [x] Category management
-   [x] Brand management
-   [x] Supplier management
-   [x] Inventory management
-   [x] Stock movement tracking
-   [x] Customer management
-   [x] Staff management
-   [x] Delivery staff management
-   [x] Delivery assignment
-   [x] Customer cart
-   [x] Checkout
-   [x] Order management
-   [x] Order cancellation
-   [x] Payment status management
-   [x] Payment history
-   [x] Dashboards
-   [x] Profile management
-   [x] Password change
-   [x] Forgot/reset password backend flow
-   [x] Responsive UI
-   [x] Dark/light mode
-   [x] Profile pictures
-   [x] Display zoom
-   [x] Modernized authentication UI
-   [x] Product image containment
-   [x] Customer recent-orders UI refinement

------------------------------------------------------------------------

# 45. Remaining / Future Improvements

The core system is substantially implemented, but the following
improvements can still be considered.

## High Priority

-   [ ] Complete full end-to-end regression testing after the latest
    frontend changes.
-   [ ] Production deployment.
-   [ ] Production environment configuration.
-   [ ] Connect forgot-password reset to an email service.
-   [ ] Add production-grade error logging.
-   [ ] Add stronger production security configuration.
-   [ ] Verify all role/permission combinations through final testing.

## Medium Priority

-   [ ] Real online payment gateway.
-   [ ] Product reviews and ratings.
-   [ ] Wishlist/favorites.
-   [ ] Notifications.
-   [ ] Advanced order-tracking timeline.
-   [ ] CSV/PDF export.
-   [ ] More advanced sales analytics.
-   [ ] Server-side image storage/upload.
-   [ ] Cloud image hosting.

------------------------------------------------------------------------

# 46. Current Known Scope Limitations

The following are intentional/current implementation limitations:

### Password Reset Email

The backend generates reset tokens but does not currently send
production emails.

### Payment Gateway

COD and bank-transfer payment methods are represented in the system, but
a live payment gateway is not integrated.

### Profile Images

Profile pictures are currently stored client-side rather than in a
server/cloud storage service.

### Supplier Authentication

Suppliers do not have their own login account in the current design.

### Production Deployment

The project is currently structured for local development and still
requires deployment configuration.

------------------------------------------------------------------------

# 47. Local Setup

## Backend

``` bash
cd backend
npm install
npm run dev
```

or:

``` bash
npm start
```

The backend runs on:

``` text
http://localhost:5000
```

Health check:

``` text
http://localhost:5000/api/health
```

------------------------------------------------------------------------

## Frontend

``` bash
cd frontend
npm install
npm run dev
```

The Vite frontend runs on:

``` text
http://localhost:5173
```

------------------------------------------------------------------------

# 48. Environment Configuration

The backend uses environment variables through `dotenv`.

A local backend `.env` should contain the required MongoDB/JWT/server
configuration used by the project.

The frontend supports:

``` text
VITE_API_URL=http://localhost:5000/api
```

Do **not** commit:

``` text
.env
```

or real secrets to GitHub.

The project distributions intentionally exclude sensitive `.env` files
and `node_modules`.

------------------------------------------------------------------------

# 49. GitHub Project Structure

A recommended repository structure is:

``` text
Soorjayan-Tech-Zone/
│
├── backend/
│
├── frontend/
│
├── README.md
│
└── .gitignore
```

Recommended GitHub documentation can include:

-   Project overview
-   Features
-   Screenshots
-   Technology stack
-   Installation instructions
-   API documentation
-   Role/permission matrix
-   Future improvements

------------------------------------------------------------------------

# 50. Project Presentation Summary

### Short Description

**Soorjayan's Tech Zone is a full-stack electronics e-commerce and
shop-management system that provides role-based product, inventory,
customer, order, supplier, staff, and delivery management, together with
a customer shopping and checkout experience.**

### Technical Description

**The system is developed using React and Vite for the frontend, Node.js
and Express for the REST API, and MongoDB with Mongoose for data
management. JWT authentication, bcrypt password hashing, role-based
authorization, and permission-based staff access are used to secure the
application.**

### Main Functional Areas

``` text
Authentication
      │
      ├── Registration
      ├── Login
      ├── Password Reset
      └── Profile
      │
      ▼
Product Catalog
      │
      ├── Products
      ├── Categories
      ├── Brands
      └── Suppliers
      │
      ▼
Inventory
      │
      ├── Stock
      ├── Low Stock
      ├── Stock Movements
      └── History
      │
      ▼
Shopping
      │
      ├── Cart
      ├── Checkout
      └── Orders
      │
      ▼
Operations
      │
      ├── Customers
      ├── Staff
      ├── Delivery Staff
      ├── Delivery Assignment
      └── Payment Management
      │
      ▼
Analytics
      │
      ├── Dashboard
      ├── Sales
      ├── Orders
      ├── Inventory
      └── Product Performance
```

------------------------------------------------------------------------

# 51. Current Development Milestone

The project has progressed beyond a basic product catalog into a
**multi-role full-stack electronics commerce and shop-management
platform**.

The backend now contains the major business modules and protected REST
APIs, while the frontend contains role-specific pages, shopping
functionality, operational dashboards, responsive layouts, and a
progressively refined visual system.

The latest frontend work has focused on:

-   Consistent Tech Zone branding
-   Dark/light mode
-   Authentication interfaces
-   Product image presentation
-   Dashboard readability
-   Cart functionality
-   Recent-order presentation
-   Display zoom
-   Profile synchronization
-   Responsive UI
-   Dark-mode visibility

------------------------------------------------------------------------

## Author

**Soorjayan Varatharajan**

**Computer Engineering Undergraduate**\
**University of Jaffna**

**Project:** Soorjayan's Tech Zone\
**Domain:** Full-Stack Web Development / E-Commerce / Shop Management


