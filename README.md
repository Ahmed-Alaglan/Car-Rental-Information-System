# Car Rental Information System

Abdulhamid Alaboud · Ahmed Alaglan  
Department of Computer Science  
Jazan University, Saudi Arabia

## Overview
This project is a comprehensive Java enterprise web application for managing car rental operations, developed as part of the Enterprise Application Development curriculum. The system integrates vehicle registration, real-time fleet tracking, availability management, and data persistence to provide a seamless digital rental experience. Built with Java Servlets, JSP, and Microsoft Access database, it demonstrates practical implementation of the Model-View-Controller (MVC) architecture in enterprise-grade applications.

## Key Features
- **Dynamic Vehicle Registration**: Add new cars with complete details including plate number, model, rental rate, and availability status through interactive forms
- **Real-time Fleet Dashboard**: Display all registered vehicles in a structured table format with instant availability updates
- **Database Integration**: Secure data storage using Microsoft Access with JDBC connectivity through UCanAccess driver
- **MVC Architecture**: Clear separation between presentation layer (JSP), business logic (Servlets), and data model (JavaBeans)
- **User-friendly Interface**: Clean, responsive design with intuitive navigation and comprehensive form validation
- **Error Handling**: Robust exception management for database operations and user input validation

## Technical Architecture
| Component | Technology | Purpose |
|-----------|------------|---------|
| **Frontend** | JSP, HTML5, CSS3 | Dynamic page rendering, user interface, responsive styling |
| **Backend** | Java Servlets | HTTP request handling, business logic, controller operations |
| **Database** | Microsoft Access (.accdb) | Persistent data storage for vehicle information |
| **Connectivity** | JDBC (UCanAccess Driver) | Java-to-Microsoft Access database communication |
| **Server** | Apache Tomcat 9.0.95 | Java web application deployment, Servlet/JSP container |
| **Development** | Java JDK 22 | Backend programming, object-oriented design, exception handling |
| **Data Model** | JavaBeans (POJO) | Object representation of database entities |

## System Modules
| Module | Core Functionality | Key Technologies |
|--------|-------------------|------------------|
| **Home Interface** | Central navigation hub with access to all system features | JSP, HTML, CSS, JavaScript |
| **Vehicle Registration** | Form-based car data entry with validation and database persistence | Servlets, JDBC, HTML Forms, Prepared Statements |
| **Fleet Management** | Dynamic display of all registered vehicles with real-time status | JSP, Servlets, ResultSet, JSTL/EL Expressions |
| **Database Operations** | Complete CRUD operations for vehicle records with transaction safety | JDBC, SQL, Parameterized Queries, Connection Pooling |

## Repository Structure
```
Car-Rental-Information-System/
├── CarRental-System.zip           # Complete Eclipse project archive
├── CarRental.accdb                # Empty database template (structure only)
├── README.md                      # Project documentation (this file)
├── LICENSE                        # MIT License file
└── .gitignore                     # Git exclusion rules for Java projects
```

### Project Structure (within ZIP):
```
CarRentalSystem/
├── src/
│   └── com/mycompany/miniproject/
│       ├── CarControllerServlet.java    # Handles car registration (POST)
│       ├── ViewCarsServlet.java         # Retrieves and displays cars (GET)
│       └── car.java                     # Data model class (JavaBean)
├── WebContent/
│   ├── WEB-INF/
│   │   ├── lib/                         # Dependency JAR files
│   │   │   ├── ucanaccess-5.0.1.jar
│   │   │   ├── commons-lang3-3.8.1.jar
│   │   │   ├── commons-logging-1.2.jar
│   │   │   ├── hsqldb-2.5.0.jar
│   │   │   └── jackcess-3.0.1.jar
│   │   └── web.xml                      # Deployment descriptor
│   ├── css/
│   │   └── style.css                    # Styling definitions
│   ├── Home.jsp                         # Main navigation page
│   ├── addcar.jsp                       # Vehicle registration form
│   ├── success.jsp                      # Operation confirmation page
│   └── ViewCars.jsp                     # Fleet display table
├── .classpath                          # Eclipse classpath configuration
├── .project                            # Eclipse project configuration
└── CarRental.accdb                     # Database file (can be external)
```

## Quick Setup & Installation

### Prerequisites Installation
1. **Java Development Kit**: Download and install Java JDK 22 or higher
2. **Application Server**: Install Apache Tomcat 9.0.95 or compatible version
3. **Development Environment**: Set up Eclipse IDE for Enterprise Java Developers
4. **Database System**: Microsoft Access or compatible runtime (for .accdb files)

### Database Configuration
```sql
-- Microsoft Access SQL Table Definition
CREATE TABLE Car (
    PlateNumber TEXT(20) PRIMARY KEY,
    Model TEXT(50) NOT NULL,
    Rate DOUBLE NOT NULL,
    Available YESNO DEFAULT TRUE
);

-- Optional: Insert sample test data
INSERT INTO Car (PlateNumber, Model, Rate, Available) VALUES
('JAZ-2024', 'Toyota Camry', 45.50, TRUE),
('JAZ-2025', 'Honda Accord', 50.00, TRUE),
('JAZ-2026', 'Hyundai Elantra', 40.25, TRUE),
('JAZ-2027', 'Ford Explorer', 75.00, FALSE),
('JAZ-2028', 'Nissan Altima', 42.75, TRUE);
```

### Project Deployment

#### Method 1: Using Eclipse IDE
1. **Extract** `CarRental-System.zip` to your workspace directory
2. **Open Eclipse** and import as "Existing Projects into Workspace"
3. **Configure Tomcat Server** in Eclipse Server Runtime Environments
4. **Update database path** in servlets if needed (default: project root)
5. **Add Project to Server** and start Tomcat
6. **Access Application** at: `http://localhost:8080/CarRentalSystem/Home.jsp`

#### Method 2: Manual WAR Deployment
1. **Export** project as WAR file from Eclipse
2. **Copy WAR file** to Tomcat's `webapps` directory
3. **Start Tomcat** server
4. **Access Application** at: `http://localhost:8080/CarRentalSystem/`

### Launch Application
1. **Start Apache Tomcat** server from control panel or command line
2. **Ensure database file** (`CarRental.accdb`) is accessible at configured path
3. **Open Web Browser** and navigate to: `http://localhost:8080/CarRentalSystem/Home.jsp`
4. **Test functionality** by adding new vehicles and viewing the fleet

## Development Dependencies
- **Java**: JDK 22 or higher (for modern language features and modules)
- **Server**: Apache Tomcat 9.x (Servlet 4.0, JSP 2.3 compatible)
- **Database**: Microsoft Access 2016+ or compatible .accdb format
- **JDBC Driver**: UCanAccess 5.0.1+ (includes all required dependencies)
- **Browser**: Modern Chrome, Firefox, or Edge with JavaScript enabled
- **IDE**: Eclipse 2023+, IntelliJ IDEA, or NetBeans with Java EE support
- **Build Tool**: Apache Maven (optional, for dependency management)

## Performance & Results
- **Database Operations**: Optimized with Prepared Statements and connection pooling
- **Response Time**: < 500ms for typical database queries on local server
- **Scalability**: Modular MVC design allows easy addition of reservation system, user management, and reporting modules
- **Security**: Parameterized queries prevent SQL injection; input validation on both client and server sides
- **Maintainability**: Clear separation of concerns following MVC pattern; comprehensive error logging
- **Compatibility**: Tested on Windows 10/11 with Java 22, Tomcat 9, and Access 2019

## Methodology
1. **Requirements Analysis**: Identified core rental operations, data entities, and user workflows
2. **Technology Selection**: Evaluated Java EE stack versus alternatives for enterprise application needs
3. **Database Design**: Created normalized schema focusing on vehicle information management
4. **MVC Implementation**: Separated JSP (View), Servlets (Controller), and JavaBeans (Model) layers
5. **Frontend Development**: Designed intuitive interfaces with responsive CSS and client-side validation
6. **Backend Integration**: Connected Servlets with database using JDBC and UCanAccess driver
7. **Testing & Validation**: Performed unit testing, integration testing, and user acceptance testing
8. **Documentation**: Created comprehensive README, code comments, and deployment guides

## Future Enhancements
1. **Reservation System**: Allow customers to book vehicles for specific dates with calendar integration
2. **User Authentication**: Role-based access control for administrators, staff, and customers
3. **Advanced Search & Filtering**: Multi-criteria vehicle search with price range, model year, and features
4. **Reporting Module**: Generate rental reports, financial summaries, and maintenance schedules
5. **Payment Integration**: Secure online payment processing with invoice generation
6. **Mobile Application**: Cross-platform mobile app for on-the-go reservations
7. **Maintenance Tracking**: Vehicle service history, maintenance scheduling, and downtime management
8. **Customer Management**: Customer profiles, rental history, and loyalty programs
9. **GPS Integration**: Real-time vehicle tracking and location services
10. **Multi-language Support**: Internationalization for global rental operations

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 📬 Contact
For technical questions, collaboration opportunities, or feedback:
- **Repository Issues**: [GitHub Issues Page](https://github.com/Ahmed-Alaglan/Car-Rental-Information-System/issues)
- **Academic Inquiries**: Department of Computer Science, Jazan University
