# Deploying a Next.js App to Cloudflare Workers

This guide details the steps to deploy your Next.js application to Cloudflare Workers using Wrangler and the `@cloudflare/next-on-pages` adapter.

## Prerequisites

- [Node.js](https://nodejs.org/) (v18 or later recommended)
- Cloudflare account

## Setup

### Step 1: Create a Next.js App

```sh
npx create-next-app@latest my-next-app
cd my-next-app
```

### Step 2: Install Dependencies

```sh
npm install -D @cloudflare/next-on-pages wrangler
```

### Step 3: Configure Scripts in `package.json`

Edit your `package.json`:

```json
"scripts": {
  "build": "next build",
  "deploy": "next build && npx @cloudflare/next-on-pages"
}
```

### Step 4: Authenticate Wrangler

Authenticate with Cloudflare:

```sh
npx wrangler login
```

### Step 5: Initialize Wrangler

Create `wrangler.toml`:

```sh
npx wrangler init
```

Configure your `wrangler.toml` as:

```toml
name = "your-nextjs-app"
compatibility_date = "2024-06-01"
pages_build_output_dir = ".vercel/output/static"
```

### Step 6: Deploy Your App

Deploy your app:

```sh
npm run deploy
```

### Step 7: Access Your App

Your app is now accessible at:

```
https://<your-project-name>.<your-account>.workers.dev
```

## Useful Links

- [Next.js Documentation](https://nextjs.org/docs)
- [Cloudflare Workers](https://developers.cloudflare.com/workers)
- [Next-on-pages GitHub Repository](https://github.com/cloudflare/next-on-pages)

---

**Happy Deploying! 🚀**

