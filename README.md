# InkFlow

A modern full-stack blogging platform built with **React, Hono, Prisma, PostgreSQL, Cloudflare Workers, and TypeScript**. InkFlow provides secure authentication, blog creation and management, and a scalable serverless backend.

## Features

- User authentication (Sign Up / Sign In)
- JWT-based authorization
- Create blogs
- Update existing blogs
- View all published blogs
- Read individual blog posts
- Shared type-safe validation using Zod
- Serverless backend deployed on Cloudflare Workers
- PostgreSQL database powered by Prisma Accelerate

---

## Tech Stack

### Frontend

- React
- TypeScript
- Vite
- Tailwind CSS
- Axios
- React Router

### Backend

- Hono
- TypeScript
- Prisma ORM
- Prisma Accelerate
- Cloudflare Workers
- JWT Authentication
- Zod

### Database

- PostgreSQL
- Prisma Postgres

---

## Project Structure

```
InkFlow
│
├── frontend/          # React + Vite frontend
├── backend/           # Hono API (Cloudflare Workers)
├── common/            # Shared Zod validation schemas
│
├── package.json       # Workspace configuration
└── README.md
```

---

## Architecture

```
                React Frontend
                     │
                     ▼
              Cloudflare Workers
                 (Hono API)
                     │
                     ▼
              Prisma Accelerate
                     │
                     ▼
             PostgreSQL Database
```

---

## Authentication Flow

```
User
  │
  ▼
Sign Up / Sign In
  │
  ▼
Backend validates input using Zod
  │
  ▼
User stored in PostgreSQL
  │
  ▼
JWT generated
  │
  ▼
JWT stored in Local Storage
  │
  ▼
Authenticated API Requests
```

---

## Local Setup

### Clone Repository

```bash
git clone https://github.com/<your-username>/inkflow.git
cd inkflow
```

### Install Dependencies

```bash
npm install
```

---

## Environment Variables

### Backend

Create a `.env` file inside `backend`.

```env
DATABASE_URL=your_prisma_postgres_url
JWT_SECRET=your_secret_key
```

---

### Frontend

```env
VITE_BACKEND_URL=https://your-worker.workers.dev
```

---

## Run Locally

### Backend

```bash
cd backend
npm run dev
```

### Frontend

```bash
cd frontend
npm run dev
```

---

## Deployment

### Backend

- Cloudflare Workers
- Wrangler
- Prisma Accelerate
- Prisma Postgres

Deploy using

```bash
npm run deploy
```

---

### Frontend

Deploy on Vercel.

Set the environment variable

```env
VITE_BACKEND_URL=https://your-worker.workers.dev
```

---

## API Endpoints

### Authentication

```
POST /api/v1/user/signup
POST /api/v1/user/signin
```

### Blogs

```
POST   /api/v1/blog
PUT    /api/v1/blog
GET    /api/v1/blog/bulk
GET    /api/v1/blog/:id
```

---

## Security

- JWT Authentication
- Request validation using Zod
- Shared validation schemas between frontend and backend
- Type-safe API contracts
- Prisma ORM prevents SQL injection

---

## Future Improvements

- Rich text editor
- Comments
- Likes
- Image uploads
- User profiles
- Search functionality
- Draft support
- Markdown editor
- Pagination
- Dark mode

---

## Tech Highlights

- Full TypeScript codebase
- Serverless architecture
- Shared validation package
- Monorepo using npm Workspaces
- Type-safe APIs
- Prisma ORM with Accelerate
- Cloudflare Edge deployment

---

## Author

**Anish Dusad**

---

## License

This project is licensed under the MIT License.