After several months of building dblayer — a platform that turns your PostgreSQL database into secure, ready-to-use APIs and Apps,
I wanted to share the technical architecture behind it.

dblayer is modular by design. It consists of multiple services — all optimized for performance, maintainability, and scalability.

Let’s dive into the stack

1. API Server (<api>.dblayer.dev)
This is the core Go-based API server that powers requests coming from the frontend or external clients.

- Language: Go 1.22
- Framework: Fiber v2
- Database: PostgreSQL via lib/pq and sqlx
- Logging: zap for high-performance structured logging
- UUID: google/uuid for consistent IDs
- Config: yaml.v3, godotenv
- Caching: go-cache, with optional Redis via go-redis
- Middleware & Compression: Brotli, gzip via valyala/fasthttp

This service acts as the "runtime engine" for all DB-generated APIs.

2. Background Worker (<worker>.dblayer.dev)
Handles asynchronous tasks: email, file processing, S3 uploads, and more.

- Language: Go
- Mailing: go-mail
- Logging: zerolog + lumberjack for daily log rotation
- AWS SDK v2: For uploading to S3 and interacting with cloud services
- Environment Handling: godotenv for secrets
- This allows us to separate performance-sensitive user requests from slower, async operations.

3. Dashboard Backend (<dashboard.backend>.dblayer.dev)
An Express.js backend for managing the dashboard, auth, projects, and billing.

- Language: TypeScript + Node.js
- Framework: Express
- ORM: Drizzle ORM — fully typed, SQL-first
- Auth: passport, jwt, passport-google-oauth20
- Redis: For rate-limiting + caching (rate-limit-redis, ioredis)
- Validation: zod + zod-validation-error
- Security: helmet, express-rate-limit, input sanitization
- Logging: winston, daily-rotate-file

This is the admin engine of dblayer — managing everything from auth to token issuance to flows.

4. App Frontend (<app>.dblayer.dev)
A React-based web app built with Next.js 15, acting as the user-facing playground.

- State Management: zustand
- Editor: Monaco (via @monaco-editor/react) for live code editing
- UI Framework: Radix UI components + Tailwind CSS
- Utils: axios, dayjs, nanoid, clsx, js-cookie
- Animation: framer-motion
- Markdown & XLSX: react-markdown, xlsx, syntax-highlighter

This is where users build, test, and deploy their API endpoints.

5. Landing Page (dblayer.dev)
Built with Next.js and optimized for SEO, performance, and minimal load.

- Next.js 15 with Turbopack
- Dark mode support: next-themes
- Components: shadcn ui
- Animations: framer-motion, tailwindcss-animate

6. Documentation (dblayer-documents)
Static documentation site with MDX support, diagrams, LaTeX, and smart content indexing.

- Framework: Next.js 15
- Markdown tooling: remark, rehype, unified, gray-matter
- Diagram Support: Mermaid.js
- Math Support: KaTeX
- Themes + Animations: Same shared system (Radix UI + Tailwind)

Content is auto-indexed using a custom content.ts script for search-ready JSON output.

Dev Practices & Tooling

- TypeScript everywhere — from backend to docs
- Strict linting & formatting: Prettier, ESLint, Husky
- Modern package managers: pnpm for consistent and fast builds
- Scripts: Unified across all repos (dev, build, lint, format, seed)
- Env Management: .env, dotenv, tsconfig-paths

Architecture Philosophy
I have optimized dblayer to:

- Be modular: APIs, workers, UI, docs — all loosely coupled
- Stay typed: No guesswork across services
- Minimize cold starts: Workers are long-lived; logs and metrics help debug fast
- Enable fast iteration: Fast builds, local-first tooling, cloud-native by default

If you're building a platform or tool and thinking about your stack,  hope this breakdown helps.

You can try DBLayer at https://dblayer.dev
Happy to answer Feedback or questions?
