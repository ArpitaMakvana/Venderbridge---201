# VendorBridge 🏭

> VendorBridge is a full-stack ERP platform that streamlines the entire vendor procurement lifecycle. It covers everything from creating and publishing Requests for Quotation (RFQs) and collecting vendor quotes, to comparing quotations, raising Purchase Orders, managing approvals, and tracking invoices — all in one place.

---

## 🛠 Tech Stack

| Layer | Technologies |
|---|---|
| **Backend** | Node.js, Express, TypeScript, Prisma ORM, PostgreSQL |
| **Frontend** | React 19, TypeScript, Vite, Tailwind CSS, React Router |

---

## ✨ Features

- 🔐 Role-based access control (Admin, Procurement Officer, Manager, Vendor)
- 🏢 Vendor registration and approval workflow
- 📋 RFQ (Request for Quotation) creation and vendor assignment
- 💬 Quotation submission and comparison
- 📦 Purchase Order creation, approval, and PDF generation
- 🧾 Invoice tracking (Unpaid / Paid / Overdue)
- 📊 Activity logs and analytics dashboard
- 🔑 JWT-based authentication with refresh tokens
- 📧 Email notifications via Nodemailer

---

## 📁 Project Structure

```
VendorBridge/
├── backend/
│   ├── src/
│   │   ├── controllers/
│   │   ├── services/
│   │   ├── repositories/
│   │   ├── routes/
│   │   ├── middleware/
│   │   ├── validators/
│   │   └── utils/
│   ├── prisma/
│   │   └── schema.prisma
│   └── .env
└── frontend/
    └── src/
```

---

## 🚀 Getting Started

### Prerequisites

- Node.js v18+
- PostgreSQL

---

### Backend Setup

```bash
cd backend
npm install
```

Create a `.env` file (or update the existing one):

```env
PORT=5000
DATABASE_URL="postgresql://user:password@localhost:5432/vendorbridge?schema=public"
JWT_SECRET="your_access_secret"
JWT_REFRESH_SECRET="your_refresh_secret"
NODE_ENV="development"

SMTP_HOST="smtp.ethereal.email"
SMTP_PORT=587
SMTP_USER=""
SMTP_PASS=""
SMTP_FROM="noreply@vendorbridge.com"
```

Run migrations and seed the database:

```bash
npx prisma migrate dev
npm run seed
```

Start the development server:

```bash
npm run dev
```

> Backend runs on `http://localhost:5000`

---

### Frontend Setup

```bash
cd frontend
npm install
npm run dev
```

> Frontend runs on `http://localhost:5173`

---

## 📜 Available Scripts

### Backend

| Command | Description |
|---|---|
| `npm run dev` | Start development server |
| `npm run build` | Compile TypeScript |
| `npm start` | Run compiled build |
| `npm run seed` | Seed the database |
| `npm run prisma:studio` | Open Prisma Studio |

### Frontend

| Command | Description |
|---|---|
| `npm run dev` | Start Vite dev server |
| `npm run build` | Build for production |
| `npm run preview` | Preview production build |

---

## 👥 User Roles

| Role | Access |
|---|---|
| **Admin** | Full system access, user management |
| **Procurement Officer** | Create RFQs, manage POs |
| **Manager** | Approve / reject purchase orders |
| **Vendor** | Submit quotations, view assigned RFQs |
