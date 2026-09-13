# Supabase + Google OAuth Setup for MGGS Website

## 1. Create Supabase Project
https://supabase.com → New Project

## 2. Keys (put in login.html)
Project Settings → API:
- Project URL → SUPABASE_URL
- anon public key → SUPABASE_ANON_KEY

## 3. Auth Providers (Supabase Dashboard → Authentication → Providers)
- **Email**: Enable
- **Phone**: Enable (add SMS provider e.g. Twilio if needed)
- **Google**: Enable
  - Client ID from Google Cloud
  - Client Secret from Google Cloud
  - **Callback / Redirect URI (IMPORTANT):**
```
https://YOUR_PROJECT_REF.supabase.co/auth/v1/callback
```

## 4. Google Cloud Console
Create OAuth 2.0 Client ID (Web application)

**Authorized JavaScript origins:**
- https://mggs-lalchandpura-open-source1.vercel.app
- https://mggs-lalchandpura.vercel.app (if custom domain)

**Authorized redirect URIs:**
- https://YOUR_PROJECT_REF.supabase.co/auth/v1/callback

## 5. After Google login redirect
Already set in code:
`redirectTo: window.location.origin + '/dashboard.html'`

## Demo accounts (without Supabase)
- principal@mggs.local / principal123
- teacher@mggs.local / teacher123

## Vercel Environment Variables (optional later)
If you move keys out of HTML:
- NEXT_PUBLIC_SUPABASE_URL
- NEXT_PUBLIC_SUPABASE_ANON_KEY
