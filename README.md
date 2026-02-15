# Symposium Project

This repository contains two interconnected applications that form the **Symposium** ecosystem:

1.  **Symposium Interface (`New_sym`)**: The user-facing chat application where operatives interact with the system.
2.  **Symposium Overwatch (`Admin_Panel`)**: The administrative dashboard for monitoring system status, financial statistics, and controlling user access.

## Project Structure

```
j:/Symposium/1/
├── New_sym/          # User-facing Chat Application
│   ├── app/          # Next.js App Router
│   ├── components/   # UI Components
│   └── ...
└── Admin_Panel/      # Admin Dashboard
    ├── app/          # Next.js App Router
    ├── components/   # UI Components (Vault, HUD)
    └── ...
```

## Features

### Symposium Interface (`New_sym`)
-   **Chat Interface**: Real-time interaction with the system.
-   **Wallet System**: visual representation of user funds.
-   **Security Check**: Automatically blocks access if the Admin Panel toggles "ACCESS: DENIED".
-   **Auto-Logout**: Users are logged out immediately if access is revoked.

### Symposium Overwatch (`Admin_Panel`)
-   **Dashboard**: A futuristic, hacker-themed HUD interface.
-   **System Control**: Toggle User Access (GRANTED/DENIED) globally.
-   **Financial Oversight**: Real-time display of "Global Economy" (Total Network Wealth).
-   **Security Monitoring**: Visual "Threat Level" indicators and simulated breach events.
-   **Classified Intel (Hidden Features)**:
    -   **[ DECRYPT_LEADERBOARD ]**: View top 10 richest operatives.
    -   **[ REVEAL_LEGEND ]**: View the highest single transaction, including the prompt used and the system's response.

## Setup & Installation

### Prerequisites
-   Node.js (v18+ recommended)
-   PostgreSQL Database

### Database Setup
Ensure your PostgreSQL database is running and has the following tables:
-   `participants` (unique_id, team_name, wallet_balance)
-   `messages` (id, unique_id, user_message, llm_message, money_awarded)
-   `admin_control` (allow_signin boolean)
-   `bank_balance` (total_balance)

### Environment Variables
Both projects require a `.env.local` file in their respective root directories with the following keys:

```env
DB_USER=your_db_user
DB_PASSWORD=your_db_password
DB_NAME=your_db_name
DB_HOST=localhost
DB_PORT=5432
```

### Running the Applications

**1. Start the User App (`New_sym`):**
```bash
cd New_sym
npm install
npm run dev
# Runs on http://localhost:3000 (default)
```

**2. Start the Admin Panel (`Admin_Panel`):**
```bash
cd Admin_Panel
npm install
npm run dev
# Runs on http://localhost:3001 (or another port if 3000 is busy)
```
*Note: Next.js will automatically try to find an open port if 3000 is taken.*

## Technology Stack
-   **Framework**: Next.js 14+ (App Router)
-   **Styling**: Tailwind CSS
-   **3D Graphics**: React Three Fiber / Drei (for the Vault)
-   **Database**: PostgreSQL (`pg` library)
-   **Icons**: Lucide React
