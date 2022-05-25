# next-auth-google

## Notes from creating this repository

**Started from next-auth-github**

**Start dev:**

```
npm run dev
```

**Generate Prisma Client with the following command**

```
npx prisma generate
```

**Migrate database:**

```
npx prisma migrate dev --name init
```

## Create Google API key

Open Google Cloud account, free but want CC number

https://console.cloud.google.com

On Google Cloud Platform, go to: API & Services>Credentials>+CREATE CREDENTIALS>OAuth client ID

- Application: Web application
- Authorized JavaScript origins, URIs: http://localhost:3000
- Authorized redirect URIs: http://localhost:3000/api/auth/callback/google

Add Client ID and Client Secret to .env file:

```ini
# Google Next Auth Provider
GOOGLE_CLIENT_ID=
GOOGLE_CLIENT_SECRET=
```

**Add to pages/api/auth/[...nextauth].ts file:**

```js
Providers.Google({
  clientId: process.env.GOOGLE_CLIENT_ID,
  clientSecret: process.env.GOOGLE_CLIENT_SECRET,
})
```

**Restart dev:**

```
Ctrl-c
npm run dev
```

**Should work now**

**Done**

### Settings are from:

**Next.js Google Authentication with NextAuth**

https://www.youtube.com/watch?v=QK24lEvRTI8

https://github.dev/ishan-me/next-google-auth
