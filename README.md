# Fullstack Portfolio

A modern, full-stack portfolio website with a blog and GitHub-authenticated comment system. Built with Next.js 16, React 19, TypeScript, and PostgreSQL.

## Features

- **Portfolio Home** - Hero section with personal introduction and about me
- **Blog System** - Markdown-powered blog with GitHub Flavored Markdown support
- **Comment System** - GitHub OAuth authenticated comments
- **Dark Mode** - Full light/dark theme support
- **Responsive Design** - Mobile-first layout with Tailwind CSS

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Framework | [Next.js 16](https://nextjs.org) (App Router, React Server Components) |
| Language | [TypeScript](https://www.typescriptlang.org) |
| UI | [React 19](https://react.dev) |
| Styling | [Tailwind CSS 4](https://tailwindcss.com) |
| Components | [shadcn/ui](https://ui.shadcn.com) (New York style) |
| Database | [PostgreSQL](https://www.postgresql.org) |
| ORM | [Prisma 7](https://www.prisma.io) |
| Auth | [Better Auth](https://www.better-auth.com) (GitHub OAuth) |
| Markdown | [react-markdown](https://github.com/remarkjs/react-markdown) + remark-gfm |
| Icons | [Lucide React](https://lucide.dev) |

## Project Structure

```
app/
├── page.tsx                    # Home page
├── layout.tsx                  # Root layout
├── globals.css                 # Global styles & theme
├── api/
│   ├── auth/[...all]/route.ts  # Auth endpoints (Better Auth)
│   └── comments/route.ts       # Comments API
├── blog/
│   ├── page.tsx                # Blog listing
│   └── [slug]/page.tsx         # Blog post detail
└── comments/
    └── page.tsx                # Comments page

components/
├── ui/                         # shadcn/ui components (Button, Card, Avatar, Textarea)
├── auth-button.tsx             # GitHub sign-in/sign-out
├── comment-form.tsx            # Comment submission form
├── comment-list.tsx            # Comment display list
└── markdown-renderer.tsx       # Markdown content renderer

lib/
├── auth.ts                     # Better Auth server config
├── auth-client.ts              # Auth client hooks
├── db.ts                       # Prisma client singleton
└── utils.ts                    # Utility functions

prisma/
├── schema.prisma               # Database schema
└── seed.ts                     # Database seed script
```

## Getting Started

### Prerequisites

- Node.js 18+
- PostgreSQL database
- GitHub OAuth App ([create one here](https://github.com/settings/developers))

### 1. Clone the repository

```bash
git clone https://github.com/<your-username>/fullstack-portfolio.git
cd fullstack-portfolio
```

### 2. Install dependencies

```bash
npm install
```

### 3. Set up environment variables

Create a `.env` file in the project root:

```env
DATABASE_URL="postgresql://user:password@localhost:5432/portfolio"
GITHUB_CLIENT_ID="your_github_client_id"
GITHUB_CLIENT_SECRET="your_github_client_secret"
NEXT_PUBLIC_APP_URL="http://localhost:3000"
```

### 4. Set up the database

```bash
npx prisma generate
npx prisma db push
```

Optionally seed the database with sample blog posts:

```bash
npx prisma db seed
```

### 5. Run the development server

```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

## Database Schema

The app uses 6 models:

- **User** - Authenticated user profiles
- **Session** - Session management with tokens
- **Account** - OAuth provider accounts (GitHub)
- **Verification** - Email verification tokens
- **BlogPost** - Blog articles with slug, title, and markdown content
- **Comment** - User comments linked to authenticated authors

## Scripts

| Command | Description |
|---------|-------------|
| `npm run dev` | Start development server |
| `npm run build` | Build for production |
| `npm start` | Start production server |
| `npm run lint` | Run ESLint |

## Deployment

This app can be deployed on [Vercel](https://vercel.com), [Railway](https://railway.app), or any platform that supports Next.js and PostgreSQL.

Make sure to set all environment variables on your hosting platform before deploying.

# fullstack-portfolio-app
