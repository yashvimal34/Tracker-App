# Expense Tracker

A full-stack web application for tracking personal expenses and income with an intuitive dashboard, comprehensive analytics, and user-friendly interface.

## 🚀 Features

### Core Functionality
- **Expense & Income Tracking**: Add, edit, and delete transactions
- **Transaction Management**: Categorize and filter transactions by type, category, and date
- **Dashboard Analytics**: 
  - Total income and expense overview
  - Monthly spending trends with bar charts
  - Category-wise expense breakdown with pie charts
  - Biggest transaction highlights
- **User Authentication**: Secure registration, login, and password reset functionality
- **Profile Management**: Update user profile and profile image
- **Settings**: 
  - Dark mode toggle
  - Email notification preferences

### Technical Features
- **Responsive Design**: Works seamlessly on desktop and mobile devices
- **Real-time Updates**: Instant UI updates after transactions
- **Data Visualization**: Interactive charts using Recharts
- **Form Validation**: Client and server-side validation
- **Toast Notifications**: User-friendly feedback for all actions
- **Loading States**: Linear progress indicators for better UX

## 🛠️ Tech Stack

### Frontend
- **React 19** - UI library
- **Vite** - Build tool and dev server
- **React Router DOM** - Client-side routing
- **Tailwind CSS** - Utility-first CSS framework
- **Recharts** - Chart library for data visualization
- **Axios** - HTTP client
- **React Hook Form** - Form management
- **Yup** - Schema validation
- **React Toastify** - Toast notifications
- **Lucide React** - Icon library

### Backend
- **Node.js** - Runtime environment
- **Express.js** - Web framework
- **MongoDB** - Database
- **Mongoose** - MongoDB object modeling
- **JWT** - Authentication tokens
- **Bcrypt** - Password hashing
- **Express Validator** - Request validation
- **CORS** - Cross-origin resource sharing

## 📁 Project Structure

```
expense_tracker/
├── expense_tracker_client/     # Frontend React application
│   ├── src/
│   │   ├── api/                # API client configuration
│   │   ├── components/         # Reusable React components
│   │   │   ├── AddIncomeForm.jsx
│   │   │   ├── Filters.jsx
│   │   │   ├── Layout.jsx
│   │   │   ├── LoginForm.jsx
│   │   │   ├── TransactionForm.jsx
│   │   │   └── ...
│   │   ├── context/            # React Context providers
│   │   │   ├── AuthContext.jsx
│   │   │   ├── ThemeContext.jsx
│   │   │   └── LoaderContext.jsx
│   │   ├── hooks/              # Custom React hooks
│   │   ├── pages/              # Page components
│   │   │   ├── Dashboard.jsx
│   │   │   ├── TransactionsPage.jsx
│   │   │   ├── ProfilePage.jsx
│   │   │   └── ...
│   │   ├── App.jsx             # Main app component
│   │   └── main.jsx            # Entry point
│   ├── public/                 # Static assets
│   └── package.json
│
└── expense_tracker_server/      # Backend Express API
    ├── config/                 # Configuration files
    ├── controllers/            # Route controllers
    │   ├── authController.js
    │   ├── expenseController.js
    │   ├── incomeController.js
    │   ├── transactionController.js
    │   └── ...
    ├── middleware/             # Custom middleware
    │   ├── authMiddleware.js
    │   └── validationMiddleware.js
    ├── models/                 # Mongoose models
    │   ├── User.js
    │   ├── Transaction.js
    │   ├── Expense.js
    │   └── Income.js
    ├── routes/                 # API routes
    │   ├── authRoutes.js
    │   ├── expenseRoutes.js
    │   ├── transactionRoutes.js
    │   └── ...
    ├── server.js               # Server entry point
    └── package.json
```

## 🚦 Getting Started

### Prerequisites

- **Node.js** (v14 or higher)
- **MongoDB** (local installation or MongoDB Atlas account)
- **npm** or **yarn** (package manager

### Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd expense_tracker
   ```

2. **Install backend dependencies**
   ```bash
   cd expense_tracker_server
   npm install
   ```

3. **Install frontend dependencies**
   ```bash
   cd ../expense_tracker_client
   npm install
   ```

4. **Environment Setup**

   Create a `.env` file in the `expense_tracker_server` directory:
   ```env
   MONGO_URI=your_mongodb_connection_string
   JWT_SECRET=your_jwt_secret_key
   PORT=5000
   ```

   Example MongoDB connection string:
   - Local: `mongodb://localhost:27017/expense_tracker`
   - Atlas: `mongodb+srv://username:password@cluster.mongodb.net/expense_tracker`

5. **Run the application**

   **Terminal 1 - Start the backend server:**
   ```bash
   cd expense_tracker_server
   npm run dev    # Development mode with nodemon
   # or
   npm start      # Production mode
   ```

   **Terminal 2 - Start the frontend development server:**
   ```bash
   cd expense_tracker_client
   npm run dev
   ```

6. **Access the application**
   - Frontend: `http://localhost:5173` (Vite default port)
   - Backend API: `http://localhost:5000`

## 📝 Available Scripts

### Frontend (`expense_tracker_client`)
- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run preview` - Preview production build
- `npm run lint` - Run ESLint

### Backend (`expense_tracker_server`)
- `npm start` - Start production server
- `npm run dev` - Start development server with nodemon
- `npm run seed` - Seed database with sample data

## 🔌 API Endpoints

### Authentication
- `POST /api/auth/register` - Register new user
- `POST /api/auth/login` - User login
- `POST /api/auth/forgot-password` - Request password reset
- `POST /api/auth/reset-password/:token` - Reset password

### Transactions
- `GET /api/transactions` - Get all transactions (with filters)
- `POST /api/transactions` - Create new transaction
- `PUT /api/transactions/:id` - Update transaction
- `DELETE /api/transactions/:id` - Delete transaction

### Expenses
- `GET /api/expenses` - Get all expenses
- `POST /api/expenses` - Create expense
- `PUT /api/expenses/:id` - Update expense
- `DELETE /api/expenses/:id` - Delete expense

### Income
- `GET /api/incomes` - Get all income entries
- `POST /api/incomes` - Create income entry
- `PUT /api/incomes/:id` - Update income entry
- `DELETE /api/incomes/:id` - Delete income entry

### Profile
- `GET /api/profile` - Get user profile
- `PUT /api/profile` - Update user profile

### Settings
- `GET /api/settings` - Get user settings
- `PUT /api/settings` - Update user settings

## 🔐 Authentication

The application uses JWT (JSON Web Tokens) for authentication. Protected routes require a valid token in the request header:

```
Authorization: Bearer <token>
```

## 🎨 Features in Detail

### Dashboard
- **Financial Overview**: Total income, total expenses, and net balance
- **Monthly Trends**: Bar chart showing income vs expenses over months
- **Category Analysis**: Pie chart displaying expense distribution by category
- **Transaction Highlights**: Biggest transaction and highest spending category

### Transaction Management
- Add transactions with title, amount, category, type, and date
- Filter transactions by:
  - Type (income/expense)
  - Category
  - Date range
- Edit and delete existing transactions

### User Settings
- Toggle dark mode
- Enable/disable email notifications
- Update profile information
- Change password

## 🗄️ Database Schema

### User Model
- `name` (String, required)
- `email` (String, required, unique)
- `password` (String, required, hashed)
- `profileImage` (String)
- `darkMode` (Boolean, default: false)
- `emailNotifications` (Boolean, default: true)
- `resetPasswordToken` (String)
- `resetPasswordExpire` (Date)
- `timestamps` (createdAt, updatedAt)

### Transaction Model
- `title` (String, required)
- `amount` (Number, required)
- `category` (String, required)
- `type` (String, enum: ["income", "expense"])
- `date` (Date, default: Date.now)
- `user` (ObjectId, ref: User, required)

## 🚀 Deployment

### Frontend Deployment (Vercel/Netlify)
1. Build the frontend: `cd expense_tracker_client && npm run build`
2. Deploy the `dist` folder to your hosting service
3. Set environment variables if needed

### Backend Deployment (Heroku/Railway/Render)
1. Set environment variables in your hosting platform:
   - `MONGO_URI`
   - `JWT_SECRET`
   - `PORT` (usually auto-set by hosting)
2. Deploy the `expense_tracker_server` directory
3. Update frontend API base URL to point to deployed backend

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 👤 Author

Created with ❤️ for personal finance management

---

**Note**: Make sure to keep your `.env` file secure and never commit it to version control. Add `.env` to your `.gitignore` file.

