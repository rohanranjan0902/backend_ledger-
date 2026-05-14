# Backend Ledger API

A robust backend service for managing accounts, users, and ledger transactions. Built with Node.js, Express, and MongoDB.

## Tech Stack

- **Node.js** & **Express.js** for the server framework.
- **MongoDB** & **Mongoose** for data storage and modeling.
- **JWT** (JSON Web Tokens) & **cookie-parser** for authentication.
- **bcryptjs** for secure password hashing.
- **nodemailer** for email services.

## Getting Started

### Prerequisites

- Node.js (v14 or higher)
- MongoDB Cluster or Local MongoDB Server

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/rohanranjan0902/backend_ledger-.git
   cd backend_ledger-
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Create a `.env` file in the root directory and add the following environment variables:
   ```env
   MONGO_URI=your_mongodb_connection_string
   # Add any other required environment variables (e.g. JWT_SECRET) here
   ```

4. Start the development server:
   ```bash
   npm run dev
   ```
   *The server will start on port 3000.*

## API Endpoints

### Authentication `/api/auth`
- `POST /register` - Register a new user.
- `POST /login` - Login user and issue a JWT cookie.
- `POST /logout` - Logout user and clear the authentication cookie.

### Accounts `/api/accounts` (Protected Routes)
- `POST /` - Create a new account for the logged-in user.
- `GET /` - Retrieve all accounts belonging to the logged-in user.
- `GET /balance/:accountId` - Get the current balance for a specific account.

### Transactions `/api/transactions` (Protected Routes)
- `POST /` - Create a new transaction (e.g., transfer between accounts).
- `POST /system/initial-funds` - System route to grant initial funds (requires system auth).

## Project Structure

- `src/controllers` - Route handlers for incoming requests.
- `src/models` - Mongoose schemas (User, Account, Transaction, Ledger, BlackList).
- `src/routes` - Express route definitions.
- `src/middleware` - Authentication and validation middleware.
- `src/services` - External services like email (Nodemailer).
- `src/config` - Database connection and configuration.

## License

ISC
