# STCK002 Frontend Web

Next.js App Router user interface for the product catalogue and persistent cart. It calls `stock-api` through REST only and never connects to PostgreSQL.

## Run

```bash
cp .env.example .env.local
npm install
npm run dev
```

Set `NEXT_PUBLIC_STOCK_API_BASE_URL` to the .NET API URL, normally `http://localhost:5000`. If that port is already used locally, run the API on another port (for example `http://localhost:5055`) and update `.env.local`; restart Next.js after changing any `NEXT_PUBLIC_*` value.

## Structure

| Area | Purpose |
| --- | --- |
| `src/app` | App Router pages and global visual tokens/styles |
| `src/features/products` | Catalogue loading and product cards |
| `src/features/cart` | Cart view, quantity controls, checkout outcome |
| `src/providers/cart-provider.tsx` | Authoritative browser cart state populated by API responses |
| `src/lib/stock-api-client.ts` | Typed REST client, cookie credentials, and API error mapping |
| `src/components` | Shared header and accessible status banner |

The `@/*` import alias maps to `./src/*` through `compilerOptions.paths` in `tsconfig.json`. The explicit relative path lets TypeScript resolve it without `baseUrl`.

## Verify

```bash
npm run typecheck
npm run build
```
# stck002-frontend
