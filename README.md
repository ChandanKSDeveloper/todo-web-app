### **Project Overview: Todo Management Web Application**

#### **Core Functionality**
1. **User Authentication**
   - Registration with password hashing
   - Login/logout with session management
   - Password security using PBKDF2 hashing

2. **Todo Operations**
   - Create todo items with due dates
   - (Implied) CRUD operations for task management
   - User-specific todo items (each user sees their own tasks)

3. **API Endpoints**
   - `POST /api/auth/register` - User registration
   - `POST /api/auth/login` - User login
   - `GET /api/auth/logout` - Session termination
   - `POST /api/todos` - Create new todo items

#### **Technical Stack**
- **Backend**: Java Servlets
- **Data Handling**: 
  - GSON for JSON serialization
  - Custom TypeAdapter for LocalDate
- **Database**: 
  - MySQL (JDBC)
  - DAO pattern for data access
- **Security**:
  - Password hashing
  - Session-based authentication

#### **Key Components**
1. **Authentication Controller** (`AuthController`)
   - Handles user sessions
   - Prevents multiple logins
   - Validates credentials

2. **Todo Controller** 
   - Manages todo operations
   - Enforces user ownership
   - Handles date serialization

3. **Utility Classes**
   - `PasswordUtil`: Secure password handling
   - `TimeUtils`: Date conversions

#### **Data Flow**
1. **Frontend** → **JSON API** → **Servlet** → **DAO** → **Database**
2. All responses in JSON format

#### **Notable Features**
- **REST-like API** design
- **Proper separation** of concerns (controllers, DAOs, utils)
- **Secure practices** for authentication
- **Type-safe date handling** with Java 8 Time API
