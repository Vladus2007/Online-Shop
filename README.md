# 🛍️ OnlineShop - ASP.NET Core MVC E-Commerce Platform

![ASP.NET Core](https://img.shields.io/badge/ASP.NET_Core-6.0-purple.svg)
![EF Core](https://img.shields.io/badge/EF_Core-6.0-blue.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)
![Build](https://img.shields.io/badge/build-passing-brightgreen.svg)

A fully-featured e-commerce platform built with ASP.NET Core MVC, featuring user authentication, shopping cart functionality, product management, and order processing.

## ✨ Features

### 🛒 Shopping Experience
- **Product Catalog** with categories and search functionality
- **Shopping Cart** with session management
- **User Authentication** with role-based authorization
- **Order Processing** with inventory management

### 👨‍💼 Admin Panel
- **Product Management** (CRUD operations)
- **Image Upload** for products
- **Inventory Control** with stock tracking
- **Category & Manufacturer Management**

### 🔐 Security
- **Password Hashing** with SHA256
- **Cookie-based Authentication**
- **Role-based Authorization** (Admin/User)
- **Secure Session Management**

## 🏗️ Architecture

```
OnlineShop/
├── Controllers/
│   ├── AccountController.cs     # User authentication & registration
│   ├── CartController.cs        # Shopping cart operations
│   ├── HomeController.cs        # Main pages & product browsing
│   └── ShopManagerController.cs # Admin product management
├── Models/                      # Data models & ViewModels
├── Views/                       # Razor views
└── Helpers/                     # Utility classes
```

## 🚀 Getting Started

### Prerequisites
- .NET 6.0 SDK
- SQL Server (LocalDB or Express)
- Visual Studio 2022 or VS Code

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/your-username/OnlineShop.git
cd OnlineShop
```

2. **Configure the database**
- Update connection string in `appsettings.json`
- Run migrations: `dotnet ef database update`

3. **Run the application**
```bash
dotnet run
```
or
```bash
dotnet watch run
```

4. **Access the application**
- Open `https://localhost:7000` in your browser
- Admin login: Use an account with "admin" role
- User registration: Create new account through registration page

## 📖 API Controllers Overview

### AccountController (`AccountController.cs`)
Handles user authentication and registration.

**Key Methods:**
- `Register()` - User registration with password hashing
- `Login()` - User authentication
- `Logout()` - Session termination
- `Authenticate()` - Claims-based identity creation

### CartController (`CartController.cs`)
Manages shopping cart operations.

**Key Methods:**
- `Index()` - Display cart contents
- `Add()` - Add product to cart
- `Delete()` - Remove product from cart
- `Order()` - Process order and update inventory

### HomeController (`HomeController.cs`)
Handles main pages and product browsing.

**Key Methods:**
- `Index()` - Home page with products
- `Category()` - Products by category
- `Search()` - Product search functionality
- `Product()` - Individual product details

### ShopManagerController (`ShopManagerController.cs`)
Admin panel for product management.

**Key Methods:**
- `Create()`/`Edit()`/`Delete()` - Product CRUD operations
- `Images()` - Product image management
- `AddImage()`/`DeleteImage()` - Image handling

## 🗃️ Database Models

### Core Entities:
- **Buyer** - User accounts with roles
- **Product** - Items with categories and manufacturers
- **Order** - Purchase records
- **Category** - Product categories
- **Manufacturer** - Product brands
- **Image** - Product images

## 🔧 Configuration

### appsettings.json
```json
{
  "ConnectionStrings": {
    "DefaultConnection": "Server=(localdb)\\mssqllocaldb;Database=OnlineShop;Trusted_Connection=True;"
  },
  "Logging": {
    "LogLevel": {
      "Default": "Information",
      "Microsoft.AspNetCore": "Warning"
    }
  }
}
```

### Authentication Setup
```csharp
services.AddAuthentication(CookieAuthenticationDefaults.AuthenticationScheme)
    .AddCookie(options => {
        options.LoginPath = "/Account/Login";
        options.AccessDeniedPath = "/Account/AccessDenied";
    });
```

## 🎨 Frontend Features

- **Responsive Design** - Mobile-friendly layout
- **Product Images** - Multiple images per product
- **Shopping Cart** - Real-time cart updates
- **Search & Filter** - Find products easily
- **Admin Interface** - Clean management dashboard

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. Fork the project
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add AmazingFeature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Development Guidelines
- Follow ASP.NET Core best practices
- Use meaningful commit messages
- Test all functionality before submitting
- Update documentation as needed


## 🛡️ Security Features

- **Password Hashing**: SHA256 with salt
- **XSS Protection**: Input validation and encoding
- **CSRF Protection**: Anti-forgery tokens
- **SQL Injection Prevention**: Parameterized queries
- **Session Security**: Secure cookie settings

## 📊 Performance Optimizations

- **EF Core Tracking**: No-tracking queries where appropriate
- **Eager Loading**: Includes related data efficiently
- **Session Management**: Optimized cart storage
- **Image Handling**: Efficient file uploads

## 🔮 Future Enhancements

- [ ] Payment gateway integration
- [ ] Email notifications
- [ ] Product reviews and ratings
- [ ] Wishlist functionality
- [ ] Advanced search filters
- [ ] Order tracking
- [ ] Multi-language support
- [ ] REST API endpoints

## 📞 Support

For support, please open an issue on GitHub or contact the development team.

## 🙏 Acknowledgments

- ASP.NET Core team for the excellent framework
- Entity Framework Core for data access
- Bootstrap for frontend components
- Contributors and testers

---

<div align="center">

**Happy Shopping!** 🛍️

*Built with ❤️ using ASP.NET Core MVC*

</div>
