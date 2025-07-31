
---

# 🧱 Full-Stack Monorepo UI Template

A **production-ready monorepo template** for full-stack web applications using **Next.js**, **Express**, **Prisma**, **Firebase Auth**, and **Tailwind/ShadCN UI**. Built for speed, maintainability, and real-world use cases — from dashboards to editors and SaaS tools.

---

## ✨ Highlights

* ⚡ Modern monorepo setup with [Turborepo](https://turbo.build/repo)
* 🧑‍🚀 Firebase Authentication with Google Sign-In
* 🎨 Prebuilt dark/light theme toggle
* 💬 Realtime WebSocket-ready backend
* 🧠 Modular editor-ready frontend (e.g. Block-based, Markdown, etc.)
* ☁️ Optional AWS S3 file upload integration
* 🧩 Reusable UI components (ShadCN + TailwindCSS)
* 🔒 Token-based protected APIs
* 📱 Fully responsive layout

---

## 🧱 Tech Stack

| Layer         | Tech Stack                                              |
| ------------- | ------------------------------------------------------- |
| **Frontend**  | Next.js 14+ (App Router), TailwindCSS, ShadCN UI        |
| **Backend**   | Node.js + Express (REST APIs, WebSocket support)        |
| **Database**  | PostgreSQL + Prisma ORM                                 |
| **Auth**      | Firebase Auth (Client SDK + Admin SDK)                  |
| **Storage**   | AWS S3 (optional for file uploads)                      |
| **Dev Tools** | Turborepo, ESLint, Prettier, Husky, Turbo Cache, dotenv |

---

## 📁 Monorepo Structure

```
fullstack-ui-template/
├── apps/
│   ├── web/         # Frontend app (Next.js)
│   └── server/      # Backend service (Express + Prisma + Firebase)
├── packages/
│   └── db/          # Shared Prisma schema and generated client
├── turbo.json       # Turborepo config
├── package.json     # Root dependencies and workspace config
└── README.md
```

---

## 🚀 Getting Started

### 1. Clone the Template

```bash
git clone https://github.com/naiyar2000/reusable_ui_template.git
cd reusable_ui_template
```

---

### 2. Install Dependencies

```bash
npm install
```

> Uses npm workspaces with Turborepo.

---

### 3. Setup Environment Variables

Create `.env` files in the following directories:

#### `packages/db/.env`

```env
DATABASE_URL="postgresql://user:password@localhost:5432/dbname"
```

#### `apps/server/.env`

```env
DATABASE_URL="..."
PORT=4000

FIREBASE_PROJECT_ID=...
FIREBASE_CLIENT_EMAIL=...
FIREBASE_PRIVATE_KEY="..."

CLIENT_URL=http://localhost:3000
```

#### `apps/web/.env`

```env
NEXT_PUBLIC_FIREBASE_API_KEY=...
NEXT_PUBLIC_FIREBASE_AUTH_DOMAIN=...
NEXT_PUBLIC_FIREBASE_PROJECT_ID=...
NEXT_PUBLIC_BACKEND_URL=http://localhost:4000
```

---

### 4. Initialize Database

```bash
npx prisma generate --schema=packages/db/prisma/schema.prisma
npx prisma db push --schema=packages/db/prisma/schema.prisma
```

---

### 5. Run the Project

```bash
npm run dev           # Starts both frontend and backend
npm run dev:web       # Starts frontend only
npm run dev:server    # Starts backend only
```

---

## 🧩 UI Components Included

* **Responsive Layout** (with sidebar, navbar, page containers)
* **Theme Toggle** (Dark/Light with system preference)
* **Reusable Form + Dialog Components**
* **Editor Area Placeholder** (can plug in any text editor)
* **Notification System** (Toast provider)
* **API Utility Layer** (with token handling)

---

## 🧪 Dev Utilities

| Command              | Description                 |
| -------------------- | --------------------------- |
| `npm run dev`        | Run all apps concurrently   |
| `npm run dev:web`    | Start frontend (Next.js)    |
| `npm run dev:server` | Start backend (Express API) |
| `npx prisma db push` | Push schema to DB           |
| `turbo run lint`     | Lint all packages/apps      |

---

## 🧩 Use Cases

This template is ideal for:

* 🚀 SaaS apps and admin dashboards
* 🧠 Note-taking or content-editing tools
* 📊 Internal tools with auth and database
* 📁 File manager or storage solutions
* ✨ Any CRUD-based app with rich UI

---

## 🧰 Extendability

You can add:

* More apps (e.g., `admin/`, `docs/`)
* More packages (e.g., `ui/`, `utils/`, `hooks/`)
* Additional auth providers (e.g., GitHub, email/password)
* Background workers (e.g., queue consumers, CRON tasks)
* CI/CD & Docker support

---

## 📄 License

MIT © \[naiyar2000]

---

Let me know if you'd like a version of this README pre-filled with:

* Docker setup
* Firebase config stubs
* GitHub Actions CI template

Or would you like me to generate a `template.config.json` or CLI script to quickly scaffold your next project based on this structure?
