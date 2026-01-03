# DayFlow - HR Management System

A modern HR management system built with Next.js 16, featuring employee management, attendance tracking, leave management, and payroll processing.

## Tech Stack

- **Framework:** Next.js 16 (App Router)
- **Database:** PostgreSQL (Neon)
- **ORM:** Prisma
- **Authentication:** NextAuth.js v5
- **UI:** Tailwind CSS + Radix UI + shadcn/ui
- **Charts:** Recharts

## Features

- 🔐 Role-based authentication (Admin & Employee)
- 👥 Employee management
- 📅 Attendance tracking
- 🏖️ Leave request management
- 💰 Payroll processing
- 📊 Dashboard with analytics charts
- 🌙 Dark/Light theme support
- ⌨️ Command menu (Ctrl/Cmd + K)

---

## 🚀 Setup Guide

For detailed installation and setup instructions, please refer to the **[SETUP.md](SETUP.md)** file.

### Quick Start

```bash
# 1. Clone the repository
git clone https://github.com/your-username/hr_management_sys.git
cd hr_management_sys

# 2. Install dependencies
npm install

# 3. Set up environment variables (see SETUP.md for details)
cp .env.example .env

# 4. Generate Prisma client
npx prisma generate

# 5. Run database migrations
npx prisma migrate deploy

# 6. Seed the database
npx tsx prisma/seed.ts

# 7. Start the development server
npm run dev
```

📖 **[Full Setup Instructions →](SETUP.md)**

---

## 🔑 Default Login Credentials

After seeding the database, you can log in with these accounts:

### Admin Account
| Email | Password |
|-------|----------|
| admin@dayflow.com | admin123 |

### Employee Accounts
| Email | Password |
|-------|----------|
| john@dayflow.com | employee123 |
| jane@dayflow.com | employee123 |

---

## 👤 User Roles

| Role | Access |
|------|--------|
| **Admin** | Full access - manage employees, view all attendance, approve/reject leave requests, process payroll |
| **Employee** | Limited access - view own profile, mark attendance, apply for leave, view own payroll |

---

## 📁 Project Structure

```
├── app/
│   ├── (auth)/          # Login & Register pages
│   ├── (dashboard)/     # Admin & Employee dashboards
│   │   ├── admin/       # Admin pages (employees, attendance, leave, payroll)
│   │   └── employee/    # Employee pages (profile, attendance, leave, payroll)
│   └── api/             # API routes
├── components/          # Reusable UI components
│   ├── ui/              # shadcn/ui components
│   └── charts/          # Recharts components
├── lib/                 # Utilities & Prisma client
│   └── generated/       # Generated Prisma client
├── prisma/              # Database schema & migrations
│   ├── schema.prisma    # Database models
│   ├── seed.ts          # Seed script
│   └── migrations/      # Migration files
└── public/              # Static assets
```

---

## 🛠️ Available Scripts

| Command | Description |
|---------|-------------|
| `npm run dev` | Start development server |
| `npm run build` | Build for production |
| `npm run start` | Start production server |
| `npm run lint` | Run ESLint |
| `npx prisma studio` | Open Prisma Studio (database GUI) |
| `npx prisma migrate dev` | Create new migration |
| `npx prisma migrate deploy` | Apply migrations |
| `npx prisma generate` | Generate Prisma client |

---

## 🐛 Troubleshooting

### Common Issues

**1. Database connection error**
- Verify your `DATABASE_URL` is correct
- Ensure your database is running and accessible
- Check if SSL is required (add `?sslmode=require` for Neon)

**2. Prisma client not found**
- Run `npx prisma generate` to regenerate the client

**3. Migration errors**
- Make sure your database is empty or run `npx prisma migrate reset` (⚠️ this will delete all data)

**4. Authentication issues**
- Ensure `AUTH_SECRET` is set in your `.env` file
- Verify `NEXTAUTH_URL` matches your app URL

---

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

---

## 📄 License

MIT
