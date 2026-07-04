# Hypermarket Management System
> A lightweight, modular enterprise desktop application built in Java Swing. It features a complete role-based workflow tailored for Administrators, Inventory Managers, Sellers, and Marketing staff, utilizing a flat-file persistence layer.

![Java](https://img.shields.io/badge/java-%23ED8B00.svg?style=for-the-badge&logo=openjdk&logoColor=white)
![Desktop Application](https://img.shields.io/badge/Application-Desktop-blue?style=for-the-badge)
![Architecture](https://img.shields.io/badge/Design-Modular_Managers-green?style=for-the-badge)
![License](https://img.shields.io/badge/license-GPL--3.0-blue.svg?style=for-the-badge)


## Table of Contents
* [About The Project](#-about-the-project)
* [System Architecture](#-system-architecture)
* [Key Features](#-key-features)
* [File Persistence Format](#-file-persistence-format)
* [Getting Started](#-getting-started)
* [Contributors](#-contributors)


## About The Project
This system addresses retail workflow operational demands by transforming day-to-day hypermarket management into an automated standalone desktop engine. It replaces heavy database dependencies with an optimized, lightweight flat-file parser, providing instant deployment and highly granular modularity.


## 📐 System Architecture
The application adheres to a strict **Modular Manager Paradigm**, segregating operational logic into independent enterprise managers that interact seamlessly with dynamic Swing components:

src/
├─ models/          — Domain Entities (Product, Order, User, Offer)
├─ managers/        — Business & Core Logic Subsystems
└─ view/            — Graphical UI Components (Swing panels & dialogs) 
Core Logic Modules:
* **AdminManager:** Oversees user authentication, privileges bounds, and dynamic employee lifecycle tracking.
* **InventoryManager:** Governs warehouse stock tracking, threshold limits, and automated warning sequences.
* **SalesManager:** Validates transaction queues, handles point-of-sale computations, and processes automatic stock deductions.
* **MarketingManager:** Coordinates ongoing campaigns, system offers, and promotional event sequences.
* **IdGenerator:** Ensures collision-free runtime unique identifiers across all entity types.

* ## Key Features
* **Role-Based Authentication:** Dynamic UI updates and view permissions depending on whether the authenticated actor is an Admin, Seller, Inventory, or Marketing staff member.
* **Robust Inventory Monitoring:** Complete lifecycle management with dynamic minimum-stock flags and automated product expiration tracking.
* **Order Validation & Processing:** Real-time stock availability verification, safe deductions, and automated transaction records compilation.
* **Zero-Dependency Persistence:** All system configurations and records load from and serialize directly into plain text arrays (`data/*.txt`).
* **Native Java GUI:** Built entirely upon clean Java Swing layouts utilizing modular frame switching mechanisms.

* ## File Persistence Format
Data records reside within the local application directory root inside the `data/` branch:
* `users.txt` — Stores secure personnel login keys and access level mappings.
* `products.txt` — Maintains live inventory structures, price targets, and tracking matrices.
* `orders.txt` — Houses detailed archives of historical transactional records.
* `offers.txt` — Holds promotional definitions and ongoing system discount codes.

* ## Getting Started

### Prerequisites
* **Java Development Kit (JDK 8 or Higher)** configured correctly inside your environment variable paths.
* A standard GNU environment with `make` capabilities installed (Optional, for running with Makefile).

### Installation & Run Procedures
**Clone the repository:**
   ```sh
   git clone [https://github.com/your-username/hypermarket-mgtm.git](https://github.com/your-username/hypermarket-mgtm.git)
   cd hypermarket-mgtm

make       # Compiles source files into target class builds
make run   # Spins up the graphic desktop system interface
