# ☕ Nagi Coffee - E-Commerce Platform

A full-stack e-commerce web platform for coffee & beverage retail, built on **ASP.NET MVC 5**, **Entity Framework 6 (Code First)**, and **Microsoft SQL Server**. The application integrates domestic payment gateways (**VNPay**, **MoMo**) and implements modern enterprise software patterns including **Repository Pattern**, **Unit of Work**, and **In-Memory Caching**.

---

## 🌟 Key Features

### 👤 Customer-Facing Portal
- **Product Catalog & Dynamic Discovery:** Browse by category, real-time filtering, responsive layout.
- **Product Customization:** Size variants (Small, Medium, Large) and optional add-ons (Toppings, Cheese foam) with real-time price recalculation.
- **Shopping Cart & Checkout:** Session-managed cart state, multi-item order placement.
- **Online Payment Integration:**
  - **VNPay QR / Bank Card:** Integrated via VNPay Sandbox API (HMAC-SHA512 checksum).
  - **MoMo E-Wallet:** Gateway redirect with automated callback and IPN notification handling.
  - **Cash on Delivery (COD).**
- **Authentication & Authorization:** ASP.NET Identity 2.0 with OWIN Cookie authentication, password hashing (PBKDF2), and role-based access.
- **Blog & News:** Editorial articles with SEO-friendly URL slugs.

### 🛡️ Admin Dashboard (AdminLTE 3)
- **Executive Analytics:** Interactive charts (Google Visualization API) showing monthly revenue trends and payment method distribution.
- **Catalog Management:** Full CRUD operations for Products, Categories, Size Options, and Toppings with image upload processing.
- **Order Processing:** Lifecycle tracking from Pending to Completed, detailed item breakdown.
- **User & Role Management:** Role assignment and account access control.

---

## 🏗️ Architecture & Software Patterns

- **Architecture:** Layered Architecture (MVC - Model, View, Controller) with separate public and admin areas.
- **Design Patterns:**
  - **Repository Pattern:** Decouples business logic from data access operations.
  - **Unit of Work Pattern:** Manages transactions across multiple repositories within a single business transaction.
- **Performance Optimization:** Implemented `System.Runtime.Caching.MemoryCache` for product catalog queries with automated expiration policies.
- **Security:**
  - Anti-forgery tokens (`@Html.AntiForgeryToken()`) against CSRF attacks.
  - Secure checksum verification (SHA256 / SHA512) for payment transactions.
  - Role-based authorization filters (`[Authorize(Roles = "Admin")]`).

---

## 🛠️ Tech Stack

| Component | Technology |
|---|---|
| **Backend Framework** | ASP.NET MVC 5 (.NET Framework 4.7.2 / 4.8) |
| **Language** | C# |
| **ORM / Data Access** | Entity Framework 6 (Code First + Migrations) |
| **Database** | Microsoft SQL Server (LocalDB / Express) |
| **Authentication** | ASP.NET Identity 2.2 + OWIN Cookie Authentication |
| **Payment Gateways** | VNPay Gateway API, MoMo Payment Gateway |
| **Frontend** | HTML5, CSS3, JavaScript, jQuery, Bootstrap, FontAwesome |
| **Admin Template** | AdminLTE 3 Responsive Dashboard |
| **Caching** | MemoryCache |

---

## 🚀 Getting Started

### Prerequisites
- Visual Studio (2019, 2022, or later) with **ASP.NET and web development** workload.
- SQL Server (LocalDB or SQL Server Express).

### Quick Setup

1. **Clone the repository:**
   ```bash
   git clone <your-github-repo-url>
   cd UniCafe
   ```

2. **Open Solution:**
   Open `UniCafe.sln` in Visual Studio.

3. **Restore NuGet Packages:**
   Visual Studio will automatically restore NuGet packages on load, or right-click the Solution and choose **Restore NuGet Packages**.

4. **Database Configuration:**
   Inspect `UniCafe/Web.config` to verify the connection string:
   ```xml
   <connectionStrings>
     <add name="DefaultConnection"
          connectionString="Server=(localdb)\MSSQLLocalDB;Initial Catalog=UniCafe;Integrated Security=True;MultipleActiveResultSets=True;"
          providerName="System.Data.SqlClient" />
   </connectionStrings>
   ```

5. **Run Migrations:**
   Open **Tools ➔ NuGet Package Manager ➔ Package Manager Console** and execute:
   ```powershell
   Update-Database
   ```

6. **Launch:**
   Press `Ctrl + F5` to run the application on IIS Express.

---

## 💼 Author & Contact
- **Developer:** Nagi Luong
- **Email:** vanheo4869@gmail.com
- **Role:** Full-Stack / .NET Developer
- **GitHub:** [https://github.com/Nagi-Luong](https://github.com/Nagi-Luong)
