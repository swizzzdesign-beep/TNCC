# Tamil Nadu Creators Club (TNCC) — Web Application

> Tamil Nadu's premiere discovery platform and creative marketplace — connecting creators, businesses, projects, and opportunities into one living creative network from Chennai to Kanyakumari.

---

## 🚀 Tech Stack

- **Framework**: Next.js 16 (App Router)
- **Language**: TypeScript 5
- **Styling**: Tailwind CSS v4 + Custom HSL Design Tokens
- **Backend & Database**: Supabase (PostgreSQL + RLS)
- **Authentication**: Supabase Auth (`@supabase/ssr`)
- **Storage**: Supabase Storage
- **Motion**: Framer Motion + GSAP
- **Deployment**: Vercel Ready

---

## ⚙️ Environment Variables

Create a `.env.local` file in the project root (never commit this file):

```bash
# Supabase Project URL
NEXT_PUBLIC_SUPABASE_URL=https://hdpzpbzhciyjvewcaxkl.supabase.co

# Supabase Client Anon / Public Key
NEXT_PUBLIC_SUPABASE_ANON_KEY=your_supabase_anon_key_here
```

Refer to `.env.example` for reference templates.

---

## 📦 Local Installation & Setup

1. **Clone the repository**:
   ```bash
   git clone https://github.com/swizzzdesign-beep/TNCC.git
   cd TNCC
   ```

2. **Install dependencies**:
   ```bash
   npm install
   ```

3. **Configure Environment Variables**:
   Copy `.env.example` to `.env.local` and add your Supabase project credentials.

4. **Run Database Migrations & Seed**:
   Execute the migration and seed SQL scripts in your Supabase SQL Editor:
   - `supabase/migrations/001_initial_schema.sql` (Creates 22 tables, RLS policies, triggers)
   - `supabase/seed.sql` (Seeds Tamil Nadu categories, skills, and sample data)

5. **Start Development Server**:
   ```bash
   npm run dev
   ```
   Open [http://localhost:3000](http://localhost:3000) in your browser.

---

## 🏗️ Production Build & Verification

```bash
# Type check and build Next.js application
npm run build

# Start production server locally
npm run start
```

---

## 🔒 Security & Row Level Security (RLS)

- Row Level Security (RLS) is enabled on all 22 database tables.
- Public read policies are restricted to published items (projects, public profiles, active packages, upcoming events).
- User-owned tables (`proposals`, `saved_projects`, `package_orders`, `messages`) require user authorization via `auth.uid()`.
- **No secret keys** (such as `service_role`) are exposed in source code or `NEXT_PUBLIC_*` environment variables.

---

## 🚢 Deployment to Vercel

1. Push your repository to GitHub: `https://github.com/swizzzdesign-beep/TNCC.git`
2. Connect the repository in your [Vercel Dashboard](https://vercel.com).
3. Set the Environment Variables in Vercel settings:
   - `NEXT_PUBLIC_SUPABASE_URL`
   - `NEXT_PUBLIC_SUPABASE_ANON_KEY`
4. Trigger deployment. Build command: `npm run build`.

---

© 2026 Tamil Nadu Creators Club. All rights reserved.
