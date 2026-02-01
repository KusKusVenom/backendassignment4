# Blog API - Assignment 4

A secure RESTful API built with Node.js, Express, and MongoDB featuring Role-Based Access Control (RBAC) and a clean MVC architecture.

 Project Overview

This project implements a **Blog Platform** with two related objects:

### Primary Object: **Blog Posts**
- Core entity representing blog articles
- Contains: title, content, author, category, tags, publication status
- Supports full CRUD operations with admin-only access for create, update, and delete

### Secondary Object: **Comments**
- Related entity that belongs to blog posts
- Contains: content, post reference, author, timestamps
- Allows users to engage with blog posts
- Also requires admin privileges for create, update, and delete operations



Security Features

### 1. Password Hashing
- All passwords are hashed using **bcrypt** with salt rounds of 10
- Passwords are never stored in plain text
- Password comparison is done securely during login

### 2. JWT Authentication
- JSON Web Tokens used for stateless authentication
- Tokens are signed with a secret key and expire after 7 days
- Tokens must be included in the Authorization header as `Bearer <token>`

### 3. Role-Based Access Control (RBAC)
- **Public Access**: Anyone can read (GET) posts and comments
- **User Role**: Regular users can register and login
- **Admin Role**: Only admins can create, update, and delete posts/comments



### Prerequisites
- Node.js (v14 or higher)
- MongoDB (local installation or MongoDB Atlas)
- npm or yarn



### Why MVC Pattern?
- **Separation of Concerns**: Each layer has a single responsibility
- **Maintainability**: Easy to locate and update specific functionality
- **Scalability**: Can add new features without affecting existing code
- **Testability**: Individual components can be tested in isolation

### Why JWT over Sessions?
- **Stateless**: No server-side session storage required
- **Scalable**: Works well in distributed/microservices architecture
- **Mobile-Friendly**: Easy to use in mobile applications
- **Performance**: No database lookups for every request

### Why Bcrypt for Password Hashing?
- **Industry Standard**: Widely accepted and battle-tested
- **Adaptive**: Can increase work factor as hardware improves
- **Salting**: Automatically generates unique salts for each password
- **Slow by Design**: Resistant to brute-force attacks

### Why Middleware Pattern?
- **Reusability**: Auth logic used across multiple routes
- **DRY Principle**: Don't repeat authentication code
- **Flexibility**: Easy to add/remove/modify middleware
- **Clean Routes**: Route files remain simple and readable

### Database Relationships
- **Referenced Relationships**: Posts and Comments use ObjectId references
- **Scalability**: Better for large datasets than embedded documents
- **Flexibility**: Can query each collection independently
- **Data Integrity**: Mongoose validation ensures valid references




This project demonstrates:
- Professional project structure and organization
- Secure authentication and authorization
- RESTful API design principles
- Database modeling and relationships
- Error handling and logging
- Environment-based configuration
- Git best practices (.gitignore, .env.example)
