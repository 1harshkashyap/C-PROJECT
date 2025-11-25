# Parking Management System in C

A comprehensive parking management system implemented in C that handles vehicle parking operations, revenue tracking, and slot management with advanced features like VIP support, dynamic billing, and transaction logging.

## 📋 Table of Contents

* [About](#about)
* [Features](#features)
* [How to Run](#how-to-run)
* [System Architecture](#system-architecture)
* [Usage Guide](#usage-guide)
* [Billing System](#billing-system)
* [Data Structure](#data-structure)
* [Test Cases](#test-cases)
* [Author](#author)

## 🅿️ About

This Parking Management System is a console-based application designed to efficiently manage vehicle parking operations. It provides comprehensive features for handling multiple parking slots, automatic billing calculations, VIP support, discount management, and detailed transaction logging. The system demonstrates advanced C programming concepts including dynamic memory allocation, file I/O, time-based calculations, and structured data management.

## ✨ Features

* **Multi-Type Vehicle Support**: Handle bikes, cars, and trucks with different pricing tiers
* **VIP Parking**: Support for premium VIP slots with double billing rates
* **Dynamic Billing**: Time-based billing calculated per 10-second units
* **Discount System**: Automatic long-stay discounts (10% for stays > 120 seconds) and coupon support
* **Unique Ticketing**: Automated ticket generation with combined random numbers and slot identifiers
* **Visual Parking Map**: ASCII-based grid display showing all slots and their occupancy status
* **Real-Time Status**: Dashboard showing occupancy, VIP usage, and total revenue
* **Transaction Logging**: File-based audit trail for all parking transactions
* **Input Validation**: Comprehensive validation for vehicle types, slot counts, and input ranges
* **Flexible Slot Management**: Support for any number of parking slots (determined at runtime)

## 🚀 How to Run

### Prerequisites

* GCC compiler (or any C compiler)
* Terminal/Command Prompt
* ~5 MB free disk space (for parking logs)

### Compilation

```bash
gcc parking.c -o parking
```

### Execution

```bash
./parking
```

On Windows:

```bash
parking.exe
```

## 🏗️ System Architecture

### Core Components

**1. Data Structure**

```c
typedef struct {
    int slot;
    char vehicleNo[20];
    char ticketID[20];
    char type[10];
    int isVIP;
    time_t entryTime;
    int occupied;
} Parking;
```

**2. Main Functions**

* `isAlreadyParked()` - Duplicate vehicle detection
* `generateTicketID()` - Unique ticket creation
* `logToFile()` - Transaction recording
* `getRate()` - Rate calculation by vehicle type
* `isValidType()` - Input validation
* `showParkingStatus()` - Display system analytics
* `showParkingMap()` - Visual slot representation
* `parkVehicle()` - Vehicle check-in
* `removeVehicle()` - Vehicle check-out with billing
* `main()` - Menu loop and orchestration

## 📖 Usage Guide

### Main Menu

```
1. Park Vehicle
2. Remove Vehicle
3. Display Status
4. Parking Map
5. Exit
```

### Parking a Vehicle

1. Select option 1
2. Enter registration number
3. Choose vehicle type
4. Provide VIP status
5. System assigns slot & generates ticket

### Removing a Vehicle

1. Select option 2
2. Enter ticket ID
3. Bill is calculated
4. Discounts applied
5. Revenue updated
6. Transaction logged

## 💰 Billing System

### Rate Structure

* Bike: ₹2/unit
* Car: ₹3/unit
* Truck: ₹5/unit
* 1 unit = 10 seconds

### Billing Formula

```
units = max(1, duration/10)
rate doubled if VIP
10% discount if duration > 120 sec
10% coupon discount if SAVE10
```

## 📊 Data Structure

* Slot: parking slot number
* vehicleNo: registration number
* ticketID: generated unique ID
* type: bike/car/truck
* isVIP: flag
* entryTime: timestamp
* occupied: status flag
* totalRevenue: global double

## 🧪 Test Cases

(unchanged — functional examples)

## 🔐 Security & Validation

* Buffer overflow protection
* Validity checks
* Duplicate prevention
* Error-handled file operations

## 💡 Concepts Demonstrated

* Dynamic memory
* Structures
* File I/O
* String operations
* Time functions
* Menu-driven logic

## 🐛 Limitations

* Single-threaded
* In-memory data only
* No authentication
* No persistent database

## 🚀 Future Enhancements

* Database integration
* Multi-threading
* Web UI
* Mobile app
* Real-time monitoring
* Advanced reporting

## 👨‍💻 Author

**Harsh Kashyap**

* SAP ID: **590022724**
* Course: B.Tech CSE
* **Batch: 36**
* Institution: UPES Dehradun
* Academic Year: 2025–2026

## 📄 License

Educational use only.

## 📞 Contact

For queries, feel free to reach out.