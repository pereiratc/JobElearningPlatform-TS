# 🎓💼 Yordanka — Job & E-Learning Platform (TypeScript Refactor)

A full-stack monorepo platform combining a **job portal** and an **e-learning platform** into one product — built with the PERN stack and written entirely in **TypeScript**.

> 🔁 **This is a TypeScript refactor** of the original JavaScript project [`jobElearningPortal`](https://github.com/pereiratc/jobElearningPortal). The goal is to rewrite the entire codebase in TypeScript with a cleaner monorepo architecture using Turborepo, improved type safety, and better scalability.
>
> 🚧 **Not all features from the original project have been ported yet.** See the [Feature Parity Checklist](#-feature-parity-checklist-vs-original-js-project) below to track progress and find where you can contribute.

---

## 🔗 Original Project

The original version was built in JavaScript and is available at:

👉 **[pereiratc/jobElearningPortal](https://github.com/pereiratc/jobElearningPortal)** — JS, live at [pereiratc.github.io/jobElearningPortal](https://pereiratc.github.io/jobElearningPortal/)

| | Original (JS) | This Repo (TS) |
|---|---|---|
| Language | JavaScript + some TS | TypeScript 100% |
| Architecture | Monolith (`client/` + `server/`) | Monorepo (Turborepo) |
| ORM | Prisma | Prisma |
| Auth | JWT + Bcrypt ✅ | ❌ Not yet ported |
| Frontend | React + TailwindCSS ✅ | ❌ Not yet created |
| Tests | Jest + Supertest (partial) ✅ | ❌ Not yet ported |
| Uploads | Multer + Cloudinary ✅ | ❌ Not yet ported |

---

## 🧱 Tech Stack

| Layer | Technology |
|---|---|
| Language | TypeScript (100%) |
| Backend | Node.js + Express |
| Database | PostgreSQL |
| ORM | Prisma |
| Frontend | React + TailwindCSS *(not yet ported)* |
| Monorepo | Turborepo |
| Runtime | @swc-node |
| Auth | JWT + Bcrypt *(not yet ported)* |
| Uploads | Multer + Cloudinary *(not yet ported)* |

---

## 📁 Project Structure

```
JobElearningPlatform-TS/
├── apps/
│   └── server/          # Express + Node.js API (TypeScript)
├── packages/            # Shared packages (types, utils, configs)
├── prisma/              # Prisma schema & migrations
├── turbo.json           # Turborepo pipeline config
├── package.json         # Root workspace config
└── .gitignore
```

> ⚠️ `apps/web` (the React frontend) does not exist yet — it needs to be scaffolded as part of this refactor.

---

## 👥 User Roles (from original project — to be ported)

| Role | Description |
|---|---|
| `CANDIDATE` | Applies to jobs and enrolls in courses |
| `RECRUITER` | Creates and manages job listings |
| `TRAINER` | Creates and manages courses |
| `ADMIN` | Administrative management |
| `SUPERADMIN` | Full access (developer level) |

> Users can hold multiple roles via a `RoleAssignment` relationship.

---

## 💳 Plans (from original project — to be ported)

| Plan | Access |
|---|---|
| Free | Apply to jobs |
| Experimental | Create jobs & courses for 7 days |
| Pro | Premium courses + authenticated certificates |
| Empresa | Corporate job & course management |

---

## ✅ What's Built So Far

- ✅ Monorepo architecture with Turborepo
- ✅ Express server scaffolded with TypeScript
- ✅ Prisma ORM connected to PostgreSQL
- ✅ @swc-node for fast TS execution
- ✅ Workspace structure (`apps/`, `packages/`)

---

## 📋 Feature Parity Checklist (vs Original JS Project)

Everything below exists in the original JS repo and **needs to be ported to TypeScript** in this monorepo. Contributions are very welcome!

### 🔒 Authentication & Access Control
- [ ] User registration & login (JWT + Bcrypt)
- [ ] Role-based access: `CANDIDATE`, `RECRUITER`, `TRAINER`, `ADMIN`, `SUPERADMIN`
- [ ] Multi-role support via `RoleAssignment`
- [ ] `auth.middleware` — protect authenticated routes
- [ ] `hasRole.middleware` — route access by role
- [ ] `hasPlan.middleware` — validate access by plan
- [ ] `checkPlanExpiration.middleware` — block actions when plan expires

### 💼 Job Module
- [ ] Create, read, update, delete job listings
- [ ] Job search and filtering
- [ ] Apply to a job (candidate flow)
- [ ] View my applications (candidate)
- [ ] View all applications (admin/recruiter)
- [ ] Prevent duplicate applications

### 🎓 Course & E-Learning Module
- [ ] Create and manage courses (free & premium)
- [ ] Support media types: video, text, quizzes, presentations, GitHub links, YouTube
- [ ] Premium courses with optional preview
- [ ] Course enrollment
- [ ] Progress tracking per lesson
- [ ] 30% platform commission on course sales

### 📄 Resume Module
- [ ] Upload resume (PDF / DOCX)
- [ ] Local storage via Multer
- [ ] Cloud storage via Cloudinary
- [ ] Resume parsing (optional)
- [ ] Skills extraction from resume

### 🏆 Certificates
- [ ] Authenticated certificate generation on course completion (Pro plan)

### 🏢 Company Module
- [ ] Company profile management
- [ ] Corporate plan: manage jobs and courses

### 📊 Dashboard & Admin
- [ ] Admin panel (reports, promotions)
- [ ] Candidate dashboard (applications, enrolled courses, progress)
- [ ] Recruiter dashboard (posted jobs, applicants)
- [ ] Instructor dashboard (courses, enrollments)
- [ ] Statistics & summaries

### 🧪 Tests
- [ ] Port `application.test.js` (apply, duplicate check, view applications)
- [ ] Tests for `Course` module
- [ ] Tests for `Job` module
- [ ] Tests for `Enrollment` module
- [ ] E2E tests for critical flows

### 🗄️ Database (Prisma Schema)
- [ ] `User`, `Role`, `RoleAssignment`
- [ ] `Job`, `Application`
- [ ] `Course`, `Lesson`, `Enrollment`, `Progress`
- [ ] `Resume`, `Skill`
- [ ] `Plan`, `Company`
- [ ] Seed scripts

### 🖥️ Frontend — `apps/web` *(does not exist yet)*
- [ ] Scaffold React + TypeScript app inside `apps/web`
- [ ] Set up TailwindCSS
- [ ] React Router navigation
- [ ] Shared layout components (Navbar, Sidebar, Footer)
- [ ] Job listings, detail, and application pages
- [ ] Course catalog, detail, and video player
- [ ] Student, recruiter, and instructor dashboards
- [ ] Auth pages (login, register, password reset)

### 🛠️ DevOps & Developer Experience
- [ ] Add `.env.example` to `apps/server`
- [ ] Fix `.gitignore` — `node_modules/` is currently tracked by git
- [ ] Add `apps/web` to the Turborepo pipeline
- [ ] GitHub Actions CI (lint, test, build on PR)
- [ ] Docker + `docker-compose.yml` for local PostgreSQL
- [ ] Write a `CONTRIBUTING.md` guide
- [ ] Add a license (MIT recommended)

### 📦 Shared Packages — `packages/`
- [ ] `packages/types` — shared TypeScript interfaces (User, Job, Course, etc.)
- [ ] `packages/ui` — shared React component library
- [ ] `packages/config` — shared ESLint, TypeScript, and Prettier configs

---

## ⚙️ Getting Started

### Prerequisites

- Node.js `>= 18`
- PostgreSQL running locally or via Docker
- npm or pnpm

### Installation

```bash
git clone https://github.com/pereiratc/JobElearningPlatform-TS.git
cd JobElearningPlatform-TS
npm install
```

### Environment Setup

Create a `.env` file inside `apps/server/`:

```env
DATABASE_URL="postgresql://USER:PASSWORD@localhost:5432/yordanka_db"
PORT=3000
JWT_SECRET=your_jwt_secret_here
```

### Database Setup

```bash
npx prisma generate
npx prisma migrate dev
```

### Run

```bash
# All apps via Turborepo
npm run dev
```

---

## 🤝 Contributing

All contributions are welcome! If you want to help port features from the original JS project to TypeScript, pick any unchecked item from the [Feature Parity Checklist](#-feature-parity-checklist-vs-original-js-project) above.

1. Fork the repository
2. Create a branch: `git checkout -b feature/your-feature-name`
3. Commit: `git commit -m 'feat: port X module to TypeScript'`
4. Push: `git push origin feature/your-feature-name`
5. Open a Pull Request

> 💡 Looking at the [original JS project](https://github.com/pereiratc/jobElearningPortal) is a great way to understand the expected behavior of each module before porting it.

---

## 👤 Author

**Ferreira Pereira** — [@pereiratc](https://github.com/pereiratc)

---

📄 License
This project does not have a license yet. Adding one (MIT recommended) is listed in What's Next.
