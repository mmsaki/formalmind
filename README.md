# Getting Started

First, clone this repo and run

```sh
bun install
```

Project stack:

- Github app - wehooks /api/github/webhook
- Auth0 - Gen AI auth
- Redis - real time event
- LLMs

## Setup

1. Copy .env file to `.env.local` and add environment variables

   ```sh
   cp example.env.local .env.local
   ```

2. Update auth0 secrets

   ```txt
   # auth0
   AUTH0_SECRET='use [openssl rand -hex 32] to generate a 32 bytes value'
   APP_BASE_URL=http://localhost:3000
   AUTH0_DOMAIN=
   AUTH0_CLIENT_ID=
   AUTH0_CLIENT_SECRET=
   AUTH0_M2M_CLIENT_ID=
   AUTH0_M2M_CLIENT_SECRET=

   # llms api
   OPENAI_API_KEY=
   LAMBDA_BASE_URL=https://api.lambda.ai/v1
   LAMBDA_API_KEY=
   GROQ_BASE_URL=https://api.groq.com/openai/v1
   GROQ_API_KEY=
   HF_TOKEN=


   # github app
   GITHUB_APP_ID=
   GITHUB_WEBHOOK_SECRET=
   GITHUB_APP_PRIVATE_KEY=

   # redis
   REDIS_URL=redis://localhost:6379
   REDIS_PASSWORD=
   WEBHOOK_URL=http://localhost:3000/api/github/webhook
   ```

> [!TIP]
>
> ### Auth0 setup authentication
>
> Dependencies `npm i @auth0/nextjs-auth0`
>
> - [ ] [User authentication](https://auth0.com/ai/docs/user-authentication)

3. Run the development server:

   ```sh
   bun dev
   ```

## Using redis server for github events

Run locally on docker:

```sh
docker compose up -d
```

