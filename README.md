# foodfast



-- Users table to store user information
CREATE TABLE Users (
    UserID INT PRIMARY KEY,
    FirstName VARCHAR(50),
    LastName VARCHAR(50),
    Email VARCHAR(100) UNIQUE,
    Phone VARCHAR(15),
    Password VARCHAR(255) 
);

-- Restaurants table to store restaurant information
CREATE TABLE Restaurants (
    RestaurantID INT PRIMARY KEY,
    Name VARCHAR(100),
    Address VARCHAR(255),
    CuisineType VARCHAR(50),
    Rating DECIMAL(3, 2)
);

-- MenuItems table to store restaurant menu items
CREATE TABLE MenuItems (
    MenuItemID INT PRIMARY KEY,
    RestaurantID INT,
    Name VARCHAR(100),
    Description TEXT,
    Price DECIMAL(5, 2)
);

-- Orders table to store customer orders
CREATE TABLE Orders (
    OrderID INT PRIMARY KEY,
    UserID INT,
    RestaurantID INT,
    OrderDate TIMESTAMP,
    TotalAmount DECIMAL(8, 2),
    Status VARCHAR(20)
);

-- OrderItems table to store items within each order
CREATE TABLE OrderItems (
    OrderItemID INT PRIMARY KEY,
    OrderID INT,
    MenuItemID INT,
    Quantity INT,
    Subtotal DECIMAL(8, 2)
);

-- DeliveryDrivers table to store information about delivery drivers
CREATE TABLE DeliveryDrivers (
    DriverID INT PRIMARY KEY,
    FirstName VARCHAR(50),
    LastName VARCHAR(50),
    VehicleType VARCHAR(50),
    AvailabilityStatus VARCHAR(20)
);

-- DeliveryAssignments table to assign orders to delivery drivers
CREATE TABLE DeliveryAssignments (
    AssignmentID INT PRIMARY KEY,
    OrderID INT,
    DriverID INT,
    AssignmentTime TIMESTAMP,
    Status VARCHAR(20)
);

-- Payments table to store payment information
CREATE TABLE Payments (
    PaymentID INT PRIMARY KEY,
    OrderID INT,
    PaymentAmount DECIMAL(8, 2),
    PaymentDate TIMESTAMP,
    PaymentStatus VARCHAR(20)
);

-- Reviews table to store restaurant reviews
CREATE TABLE Reviews (
    ReviewID INT PRIMARY KEY,
    UserID INT,
    RestaurantID INT,
    Rating DECIMAL(3, 2),
    Comment TEXT,
    ReviewDate TIMESTAMP
);

