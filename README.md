# 💰 Smart Expense Tracker

A modern, full-stack web application built to help users seamlessly track their budgets and expenses. Designed with a sleek, responsive interface and robust data management to provide real-time financial insights.

![Smart Expense Tracker](public/logo.svg)

## ✨ Features

- **Secure Authentication:** User login and registration powered by [Clerk](https://clerk.com/).
- **Interactive Dashboard:** Visual analytics of budgets and spending using [Recharts](https://recharts.org/).
- **Budget Management:** Create customized budgets with specific limits and emoji identifiers.
- **Expense Tracking:** Add, edit, and delete individual expenses linked directly to your budgets.
- **Modern UI:** Built with [Tailwind CSS](https://tailwindcss.com/) and [Shadcn UI](https://ui.shadcn.com/) for a premium, accessible user experience.
- **Real-time Database:** Server actions cleanly integrated with [Drizzle ORM](https://orm.drizzle.team/) and PostgreSQL.

## 🛠️ Tech Stack

- **Framework:** [Next.js 16](https://nextjs.org/) (App Router, React 19)
- **Styling:** Tailwind CSS, Shadcn UI, Lucide Icons
- **Database:** PostgreSQL (Compatible with NeonDB or local Docker)
- **ORM:** Drizzle ORM
- **Authentication:** Clerk

---

## 🚀 Local Installation & Setup

Follow these steps to run the application locally on your machine.

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/smart-expense-tracker.git
cd smart-expense-tracker
```

### 2. Install Dependencies
```bash
npm install
```

### 3. Setup Environment Variables
Create a `.env.local` file in the root directory and add the following keys. You will need to obtain your Clerk API keys from the Clerk Dashboard, and a Postgres connection string (either from NeonDB or a local instance).

```env
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
CLERK_SECRET_KEY=your_clerk_secret_key

NEXT_PUBLIC_CLERK_SIGN_IN_URL=/sign-in
NEXT_PUBLIC_CLERK_SIGN_IN_FALLBACK_REDIRECT_URL=/
NEXT_PUBLIC_CLERK_SIGN_UP_URL=/sign-up
NEXT_PUBLIC_CLERK_SIGN_UP_FALLBACK_REDIRECT_URL=/

DATABASE_URL=postgresql://user:password@localhost:5432/your_db_name
```

### 4. Setup the Database
You have two options to run the PostgreSQL database:

**Option A: Cloud Database (Recommended)**
Use a free hosted database like [NeonDB](https://neon.tech/). Simply paste your Neon connection string into the `DATABASE_URL` inside `.env.local`.

**Option B: Local Docker Database**
If you have Docker Desktop installed, you can spin up a local PostgreSQL container using the included Compose file:
```bash
docker-compose up -d
```

### 5. Push the Database Schema
Once your database is running and configured in `.env.local`, synchronize the schema structures (Budgets and Expenses tables) using Drizzle:
```bash
npm run db:push
```

### 6. Start the Development Server
```bash
npm run dev
```
Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

---

## 🤝 Contributing
Contributions, issues, and feature requests are welcome! Feel free to check the [issues page](https://github.com/your-username/smart-expense-tracker/issues).

## 📝 License
This project is open-source and available under the MIT License.
