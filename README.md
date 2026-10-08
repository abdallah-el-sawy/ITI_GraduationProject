# 🛒 E-Commerce Marketplace

## 🚀 How to Run the Project

### 1. Prerequisites

Before running the project, make sure you have:

* [.NET SDK](https://dotnet.microsoft.com/download)
* [SQL Server](https://www.microsoft.com/sql-server)
* Visual Studio 2022 or Visual Studio Code
* Git

### 2. Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git
```

Then navigate to the project folder:

```bash
cd YOUR_REPOSITORY
```

### 3. Configure the Database

Open the project and locate the database connection string in:

```text
appsettings.json
```

Update the connection string according to your SQL Server configuration.

Example:

```json
{
  "ConnectionStrings": {
    "DefaultConnection": "Server=YOUR_SERVER;Database=FinalProjectDb;Trusted_Connection=True;TrustServerCertificate=True;"
  }
}
```

### 4. Restore .NET Packages

Run:

```bash
dotnet restore
```

### 5. Apply Database Migrations

Make sure the required Entity Framework Core tools are installed:

```bash
dotnet tool install --global dotnet-ef
```

Then update the database:

```bash
dotnet ef database update
```

### 6. Run the Project

Run the application using:

```bash
dotnet run
```

The terminal will show the local URL where the application is running.

You can also open the project in **Visual Studio** and press:

```text
F5
```

or

```text
Ctrl + F5
```

---

# 📌 Project Overview

A full-stack **E-Commerce Marketplace** graduation project that connects customers and sellers in one platform. Customers can browse and purchase products from different sellers, while sellers can manage their products and orders. Administrators have full control over users, sellers, products, categories, and orders.

---

## ✨ Main Features

### 👤 Customer

Customers can:

* Register and log in
* Browse products
* Search for products
* Filter products by category
* Sort products by price
* View product details
* Add products to the shopping cart
* Increase or decrease product quantities
* Remove products from the cart
* Proceed to checkout
* Place orders
* View order history
* View order details
* Cancel orders when possible
* Add products to their wishlist
* Remove products from their wishlist
* Review purchased products
* Rate products

---

### 🛍️ Products

Each product contains:

* Product Name
* Description
* Price
* Available Quantity
* Category
* Seller
* Product Image

Customers can search, filter, sort, and view detailed information about products.

---

### 🏪 Seller

Sellers can:

* Add new products
* Edit their products
* Delete their products
* View their products
* Update product quantities
* View orders containing their products
* Update order status
* View their sales

> Sellers can only manage products that belong to them.

---

### ✅ Seller Approval

Users can request to become sellers.

Administrators can:

* View seller requests
* Approve seller requests
* Reject seller requests

Only approved sellers are allowed to add products.

---

### 🛒 Shopping Cart

Customers have a shopping cart that allows them to:

* Add products
* Remove products
* Increase quantity
* Decrease quantity
* View the total price
* Proceed to checkout

The system validates product availability and prevents customers from ordering more products than are available.

---

### 📦 Orders

Customers can create orders containing their selected products.

Orders support the following statuses:

* `Pending`
* `Confirmed`
* `Shipped`
* `Delivered`
* `Cancelled`

Customers can view their order history and order details.

Sellers can update the status of orders related to their products.

---

### 🗂️ Categories

Administrators can:

* Add categories
* Edit categories
* Delete categories
* View categories

Every product belongs to a category.

---

### ⭐ Reviews & Ratings

Customers can review products they have purchased.

Each review contains:

* ⭐ Rating
* 💬 Comment

Product pages display customer reviews and the overall product rating.

---

## 🛡️ Administrator

The administrator has full management capabilities.

### Users

* View users
* Activate users
* Suspend users

### Sellers

* Approve seller requests
* Reject seller requests

### Products

* View products
* Remove inappropriate products

### Categories

* Add categories
* Edit categories
* Delete categories

### Orders

* View all orders
* View order details

---

## 📊 Dashboards

### Administrator Dashboard

The administrator dashboard provides an overview of the marketplace:

* 👥 Total Customers
* 🏪 Total Sellers
* 📦 Total Products
* 🛒 Total Orders
* ⏳ Pending Orders

### Seller Dashboard

Sellers have access to statistics related to their business:

* 📦 Their Products
* 🛒 Their Orders
* 💰 Their Sales

---

## 🔐 User Roles & Permissions

| Feature           | Customer |  Seller | Admin |
| ----------------- | :------: | :-----: | :---: |
| Browse Products   |     ✅    |    ✅    |   ✅   |
| Search Products   |     ✅    |    ✅    |   ✅   |
| Add to Cart       |     ✅    |    ❌    |   ❌   |
| Place Orders      |     ✅    |    ❌    |   ❌   |
| Wishlist          |     ✅    |    ❌    |   ❌   |
| Reviews           |     ✅    |    ❌    |   ❌   |
| Add Products      |     ❌    |    ✅    |   ❌   |
| Edit Own Products |     ❌    |    ✅    |   ❌   |
| Manage Orders     |    Own   | Related |  All  |
| Seller Approval   |     ❌    |    ❌    |   ✅   |
| Manage Categories |     ❌    |    ❌    |   ✅   |
| Manage Users      |     ❌    |    ❌    |   ✅   |
| Manage Products   |     ❌    |   Own   |  All  |

---

## 🏗️ Project Structure

```text
E-Commerce Marketplace
│
├── Authentication & Authorization
│
├── Customer
│   ├── Products
│   ├── Search & Filtering
│   ├── Cart
│   ├── Checkout
│   ├── Orders
│   ├── Wishlist
│   └── Reviews
│
├── Seller
│   ├── Product Management
│   ├── Order Management
│   └── Seller Dashboard
│
├── Administrator
│   ├── User Management
│   ├── Seller Approval
│   ├── Product Management
│   ├── Category Management
│   ├── Order Management
│   └── Admin Dashboard
│
└── Database
    ├── Users
    ├── Products
    ├── Categories
    ├── Orders
    ├── Order Items
    ├── Cart
    ├── Wishlist
    └── Reviews
```

---

## 🔒 Security & Authorization

The application implements **role-based access control** to ensure that each user can only access the functionality allowed for their role.

Examples:

* Customers can only manage their own cart and orders.
* Sellers can only manage their own products.
* Sellers can only access orders related to their products.
* Only approved sellers can add products.
* Administrators can manage the entire marketplace.

---

## 🧪 Main User Flow

### Customer Flow

```text
Register/Login
      ↓
Browse Products
      ↓
Search / Filter / Sort
      ↓
View Product
      ↓
Add to Cart
      ↓
Checkout
      ↓
Place Order
      ↓
Track Order
      ↓
Review Product
```

### Seller Flow

```text
Request Seller Role
      ↓
Admin Approval
      ↓
Seller Dashboard
      ↓
Add / Edit Products
      ↓
Receive Orders
      ↓
Update Order Status
      ↓
Track Sales
```

### Admin Flow

```text
Admin Login
      ↓
Dashboard
      ↓
Manage Users
      ↓
Approve Sellers
      ↓
Manage Products
      ↓
Manage Categories
      ↓
View Orders
```

---

## 🎓 Graduation Project

This project was developed as a **Graduation Project** to demonstrate practical experience in building a complete e-commerce marketplace with multiple user roles, authentication, authorization, product management, shopping cart functionality, order management, reviews, and administrative dashboards.

---

## 👨‍💻 Contributors

**Graduation Project Team**

* Add your team members here.

---

## 📄 License

This project was developed for educational and graduation project purposes.
