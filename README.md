# Inventory PWA Demo

## Description
This project is a Progressive Web Application (PWA) for managing inventory. It is built using Node.js, Express, and a database backend. The frontend is styled with TailwindCSS and includes React components.

## Installation

1. Clone the repository:
   git clone https://github.com/AlejandroRodriguezCastro/LDAP-DAII-G3.git
   cd inventory


2. Install dependencies:
   npm install


3. Start the application:
   npm start


4. Access the application in your browser at `http://localhost:8080`.

## Database Setup

### MySQL (Current)
The application now uses MySQL as the database. Follow these steps to set it up:

1. Install MySQL server on your machine.
2. Create a database named `inventory_db`:
   ```sql
   CREATE DATABASE inventory_db;
   ```
3. Update the database credentials in `server.js`:
   ```javascript
   const db = mysql.createConnection({
     host: 'localhost',
     user: 'root',
     password: 'yourpassword',
     database: 'inventory_db'
   });
   ```
4. Run the following SQL script to create the `products` table:
   ```sql
   USE inventory_db;
   CREATE TABLE products (
     id INT AUTO_INCREMENT PRIMARY KEY,
     name VARCHAR(255) NOT NULL,
     category VARCHAR(255) NOT NULL,
     quantity INT NOT NULL,
     price DECIMAL(10, 2) NOT NULL,
     description TEXT,
     created_at DATETIME DEFAULT CURRENT_TIMESTAMP,
     updated_at DATETIME DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP
   );
   ```