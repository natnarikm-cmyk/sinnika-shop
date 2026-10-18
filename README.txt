Sinnika Shop — starter website

Files:
- index.html: public storefront and review submission form
- admin.html: admin login and review moderation

Before deploying:
1. In BOTH index.html and admin.html, replace:
   YOUR_SUPABASE_PROJECT_URL
   YOUR_SUPABASE_ANON_KEY
   with the Supabase Project URL and anon/public key from Project Settings > API.
2. Never use the service_role key in browser code.
3. The site expects the existing tables shop_reviews and shop_admins.
4. Admin page uses Supabase Auth email/password and checks membership in shop_admins.
5. Photo field currently accepts an image URL; direct image upload needs Supabase Storage setup.
6. Before public launch, confirm RLS policies/grants allow public INSERT of pending reviews, public SELECT only published reviews, and admin UPDATE/DELETE/SELECT.
7. The /admin.html path is not secret; security comes from Supabase Auth + RLS, not hiding the URL.
8. Deploy by uploading index.html and admin.html to a GitHub repository, then import that repo into Netlify (free static hosting).
