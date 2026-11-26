# Gaming Cafe SaaS

The source code is shared as two zip files on the **Releases** page (v1.0):

| File | Contents |
|---|---|
| `gaming-cafe-admin.zip` | Admin website (`frontend/admin-web`) + backend API + shared packages |
| `gaming-cafe-customer.zip` | Customer website (`frontend/customer-web`) + backend API + shared packages |

## Setup (each zip)
1. Install Node 22+, pnpm and Docker Desktop.
2. Unzip, then copy `.env.example` -> `.env` and `backend/api/.env.example` -> `backend/api/.env` and fill in real values.
3. `docker compose up -d mariadb redis`
4. `pnpm install`
5. `pnpm db:generate && pnpm db:deploy && pnpm db:seed`
6. API: `pnpm --filter @gcs/api dev` (http://localhost:4000)
7. Site: `pnpm --filter ./frontend/<admin-web|customer-web> dev`

Each zip also has a `SETUP.md` with the same steps.

Secrets (`.env` files) and database data are not included in this repository.
