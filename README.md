# 🍔 FoodShop POS System
A High-Performance, Offline-First Point of Sale system specifically designed for small food shops and restaurants.

## ✨ Key Features
- **🚀 Ultra-Fast POS**: Designed for rapid order processing.
- **📶 Offline-First (PWA)**: Works perfectly without an internet connection using Dexie.js (IndexedDB).
- **📂 Kitchen Inventory**: Track raw materials (Rice, Flour, Meat, etc.) with low-stock alerts.
- **👨‍🍳 Recipe Management**: Automatically deducts raw materials from kitchen stock when a dish is sold.
- **💸 Expense Tracking**: Manage daily shop expenses with dynamic categories.
- **📊 Real-time Dashboard**: Visual statistics of daily revenue, orders, and "Cash in Hand".
- **💳 Multi-Payment Support**: Tracks both Cash and Online Transfer payments separately.
- **🔐 User Access Control**: Simple PIN-based security for Owner vs Staff modes.
- **📠 Thermal Printing**: CSS-optimized for 80mm/58mm thermal printers.
- **☁️ Data Portability**: Local backup and restore via JSON files.

## 🛠️ Technology Stack
- **Frontend**: HTML5, Vanilla JavaScript (ES6+), Lucide Icons.
- **Styling**: Tailwind CSS (via CDN).
- **Database**: Dexie.js (IndexedDB wrapper).
- **Architecture**: Progressive Web App (PWA) with Service Worker for offline support.

## 📦 How to Run Locally
1. Clone this repository or download the ZIP.
2. Open `index.html` in any modern web browser (Chrome, Edge, Safari).
3. (Optional) Run via a local server (like Live Server extension in VS Code) to fully enable PWA features.

## 🔐 Default Access
- **Admin PIN**: `159357`

---
*Built with ❤️ for rapid food business management.*
