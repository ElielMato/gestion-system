# Gestion System

![Python](https://img.shields.io/badge/Python-3.12+-blue?logo=python)
![Flask](https://img.shields.io/badge/Flask-3.1.0-green?logo=flask)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-Database-blue?logo=postgresql)
![Docker](https://img.shields.io/badge/Docker-Containerized-blue?logo=docker)
![SQLAlchemy](https://img.shields.io/badge/SQLAlchemy-2.0.39-red?logo=sqlalchemy)

A comprehensive and scalable inventory management system built with Flask and PostgreSQL. This application provides complete control over product inventory, stock management, receipts processing, and business operations with clean architecture principles and containerized deployment.

## 🌟 Features

- **Article Management**: Complete CRUD operations for products with detailed information
- **Brand & Category Control**: Organize products by brands and categories
- **Stock Management**: Real-time inventory tracking with batch control
- **Receipt Processing**: Handle purchase and sales receipts with detailed item tracking
- **Notification System**: Alert management for low stock and important events
- **Batch Tracking**: Monitor product batches for expiration and quality control
- **RESTful API**: Well-structured API endpoints for all operations
- **Database Migrations**: Automated database schema management with Flask-Migrate
- **Environment Configurations**: Separate configurations for development, testing, and production
- **Comprehensive Testing**: Full test suite with unit and integration tests

## 🛠️ Tech Stack

| Technology            | Purpose                         | Version |
| --------------------- | ------------------------------- | ------- |
| **Python**            | Backend Programming Language    | 3.12+   |
| **Flask**             | Web Framework                   | 3.1.0   |
| **SQLAlchemy**        | ORM & Database Management       | 2.0.39  |
| **PostgreSQL**        | Primary Database                | Latest  |
| **Flask-SQLAlchemy**  | Flask-SQLAlchemy Integration    | 3.1.1   |
| **Flask-Migrate**     | Database Migration Tool         | 4.1.0   |
| **Marshmallow**       | Serialization/Deserialization   | 3.26.1  |
| **Flask-Marshmallow** | Flask-Marshmallow Integration   | 1.3.0   |
| **Psycopg2**          | PostgreSQL Adapter              | 2.9.10  |
| **Docker**            | Containerization                | Latest  |
| **Python-dotenv**     | Environment Variable Management | 1.0.1   |

## 📁 Project Structure

```
gestion-system/
├── app/
│   ├── __init__.py              # Flask app factory
│   ├── config/                  # Configuration management
│   │   ├── __init__.py
│   │   └── config.py           # Environment configurations
│   ├── controller/             # Request handlers (MVC Controllers)
│   │   ├── __init__.py
│   │   ├── article_controller.py
│   │   ├── brand_controller.py
│   │   ├── category_controller.py
│   │   ├── home_controller.py
│   │   └── notification_controller.py
│   ├── models/                 # Database models (MVC Models)
│   │   ├── __init__.py
│   │   ├── article.py
│   │   ├── batch.py
│   │   ├── brand.py
│   │   ├── category.py
│   │   ├── notification.py
│   │   ├── receipt.py
│   │   ├── receipt_footer.py
│   │   ├── receipt_header.py
│   │   ├── receipt_item.py
│   │   ├── receipt_type.py
│   │   └── stock.py
│   ├── repositories/           # Data access layer
│   │   ├── __init__.py
│   │   ├── base_repositories.py
│   │   ├── article_repositories.py
│   │   ├── batch_repositories.py
│   │   ├── brand_repositories.py
│   │   ├── category_repositories.py
│   │   ├── notification_repositories.py
│   │   ├── receipt_repositories.py
│   │   ├── receipt_type_repositories.py
│   │   └── stock_repositories.py
│   ├── services/               # Business logic layer
│   │   ├── __init__.py
│   │   ├── article_services.py
│   │   ├── batch_services.py
│   │   ├── brand_services.py
│   │   ├── category_services.py
│   │   ├── message_services.py
│   │   ├── notification_services.py
│   │   ├── receipt_services.py
│   │   ├── receipt_type_services.py
│   │   └── stock_services.py
│   ├── mapping/                # Data transformation layer
│   │   ├── __init__.py
│   │   ├── article_mapping.py
│   │   ├── brand_mapping.py
│   │   ├── category_mapping.py
│   │   ├── message_mapping.py
│   │   └── notification_mapping.py
│   ├── dto/                    # Data Transfer Objects
│   │   ├── __init__.py
│   │   ├── receipt_dto.py
│   │   └── receipt_item.py
│   ├── validators/             # Input validation layer
│   │   ├── __init__.py
│   │   └── validator.py
│   └── routes/                 # URL routing
│       ├── __init__.py
│       └── routes.py
├── test/                       # Test suite
│   ├── __init__.py
│   ├── test_app.py
│   ├── test_article.py
│   ├── test_batch.py
│   ├── test_brand.py
│   ├── test_category.py
│   ├── test_db.py
│   ├── test_notification.py
│   ├── test_receipt.py
│   ├── test_receipt_dto.py
│   ├── test_receipt_type.py
│   ├── test_stock.py
│   └── utils/                  # Test utilities
│       ├── __init__.py
│       ├── article_utils.py
│       ├── batch_utils.py
│       ├── brand_utils.py
│       ├── category_utils.py
│       ├── receipt_footer_utils.py
│       ├── receipt_header_utils.py
│       ├── receipt_items_utils.py
│       ├── receipt_type_utils.py
│       ├── receipt_utils.py
│       └── stock_utils.py
├── docs/                       # Documentation & UML diagrams
│   ├── article_domain_sequence_diagram.puml
│   ├── brand_sequence_diagram.puml
│   ├── category_sequence_diagram.puml
│   ├── class_diagram.puml
│   ├── reciept_sequence_diagram.puml
│   ├── reciept_type_sequence_diagram.puml
│   └── stock_sequence_diagram.puml
├── docker/                     # Docker configurations
│   ├── app/
│   │   └── docker-compose.yml
│   └── db/
│       └── docker-compose.yml
├── app.py                      # Application entry point
├── requirements.txt            # Python dependencies
├── boot.ps1                    # Windows startup script
├── installs.ps1               # Installation script
├── Dockerfile                  # Docker container configuration
└── README.md                   # Project documentation
```

## 🚀 Getting Started

### Prerequisites

- **Python** (version 3.12 or higher)
- **PostgreSQL** (or Docker for containerized database)
- **Docker & Docker Compose** (optional, for containerized deployment)
- **pip** package manager

### Installation

1. **Clone the repository**

   ```powershell
   git clone https://github.com/ElielMato/gestion-system.git
   cd gestion-system
   ```

2. **Create a virtual environment**

   ```powershell
   python -m venv venv
   .\venv\Scripts\Activate.ps1
   ```

3. **Install dependencies**

   ```powershell
   pip install -r requirements.txt
   ```

4. **Set up environment variables**

   Create a `.env` file in the root directory:

   ```env
   DEV_DATABASE_URI=postgresql://username:password@localhost/gestion_system_dev
   TEST_DATABASE_URI=postgresql://username:password@localhost/gestion_system_test
   PROD_DATABASE_URI=postgresql://username:password@localhost/gestion_system_prod
   FLASK_CONTEXT=development
   ```

5. **Initialize the database**

   ```powershell
   flask db init
   flask db migrate -m "Initial migration"
   flask db upgrade
   ```

6. **Run the application**

   ```powershell
   python app.py
   ```

7. **Access the application**

   Navigate to `http://localhost:5000` to see the application running.

## 🐳 Docker Deployment

### Using Docker Compose

1. **Build and run with Docker Compose**

   ```powershell
   docker-compose up --build
   ```

2. **Run in detached mode**

   ```powershell
   docker-compose up -d
   ```

3. **Stop the services**

   ```powershell
   docker-compose down
   ```

### Using Dockerfile

```powershell
# Build the image
docker build -t gestion-system .

# Run the container
docker run -p 5000:5000 gestion-system
```

## 🏗️ Development

### Running Tests

```powershell
# Run all tests
python -m unittest discover test/

# Run specific test file
python -m unittest test.test_article

# Run specific test class
python -m unittest test.test_article.ArticleTestCase

# Run with verbose output
python -m unittest discover test/ -v
```

### Database Operations

```powershell
# Create a new migration
flask db migrate -m "Description of changes"

# Apply migrations
flask db upgrade

# Rollback migration
flask db downgrade

# Show migration history
flask db history
```

### Quick Setup Scripts

For Windows users, convenience scripts are provided:

```powershell
# Install dependencies and setup environment
.\installs.ps1

# Quick application startup
.\boot.ps1
```

## 🔧 Architecture & Design Patterns

- **MVC Architecture**: Clear separation of concerns with Models, Views (Controllers), and business logic
- **Repository Pattern**: Abstracted data access layer for better testability and maintainability
- **Service Layer**: Business logic encapsulation separate from controllers
- **DTO Pattern**: Data Transfer Objects for clean data transportation
- **Factory Pattern**: Efficient object creation and configuration management
- **Dependency Injection**: Loose coupling between components
- **SOLID Principles**: Applied throughout the codebase for maintainability and extensibility

## 📝 License

This project is proprietary software developed for Inventory Management System. All rights reserved.

---

<div align="center">

**Built with ❤️ using Python, Flask, and modern software engineering practices**

</div>
