# Supabase Setup Guide (Best SAAS Kit V2)

This project now recommends Supabase for PostgreSQL. Neon also works because the app uses standard Postgres.

## 1) Create Supabase project
- https://supabase.com/ → New project
- Choose region and password

## 2) Set DATABASE_URL
- Go to: Project → Settings → Database → Connection string → URI
- Copy the URI and ensure it ends with `?sslmode=require`
- Put it in `.env.local`

```
DATABASE_URL=postgresql://postgres:YOUR_PASSWORD@db.xxxxxx.supabase.co:5432/postgres?sslmode=require
```

## 3) Initialize tables
- Open Supabase → SQL editor
- Execute the SQL in `sql-queries/01-create-users-table.sql`
- Then `sql-queries/02-create-indexes.sql`
- Then `sql-queries/03-create-functions.sql`
- (Optional) `sql-queries/04-insert-sample-data.sql`

> These scripts are Postgres-compatible and run fine on Supabase.

## 4) (Optional) Import existing data from Neon
- Export from Neon
  ```bash
  pg_dump "<NEON_URL>?sslmode=require" -Fc -f neon.dump
  ```
- Restore to Supabase
  ```bash
  pg_restore --no-owner --no-privileges \
    -d "postgresql://postgres:YOUR_PASSWORD@db.xxxxxx.supabase.co:5432/postgres?sslmode=require" \
    neon.dump
  ```

## 5) Run the app
```
npm run dev
```

## 6) FAQ
- SSL errors: ensure `?sslmode=require` is in `DATABASE_URL` and the app sets `ssl: { rejectUnauthorized: false }` in `pg` Pool (already configured).
- Auth: This kit ships with NextAuth (Google OAuth). You can keep NextAuth, or migrate to Supabase Auth later.
