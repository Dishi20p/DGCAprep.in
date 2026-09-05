# DGCAPrep
Full-stack DGCA CPL question-bank platform.

## Run locally
1. Install Node.js 18+.
2. `npm install`
3. Copy `.env.example` to `.env`.
4. Keep `DEMO_MODE=true` to test payments without Razorpay/domain.
5. `npm start`
6. Open http://localhost:5000

## Supabase setup
This project supports optional Supabase storage while keeping the current local JSON files as a fallback.

1. Create a Supabase project.
2. Add these values to your `.env` file:
   - `USE_SUPABASE=true`
   - `SUPABASE_URL=https://<project-ref>.supabase.co`
   - `SUPABASE_ANON_KEY=<anon-key>`
   - `SUPABASE_SERVICE_ROLE_KEY=<service-role-key>`
3. Run the SQL from `supabase/schema.sql` in the Supabase SQL editor.
4. Start the app.

When Supabase is enabled, user and purchase records are stored in Supabase instead of `data/users.json` and `data/purchases.json`.

## Question bank
Add questions to these files:
- question-bank/air-regulations.json
- question-bank/meteorology.json
- question-bank/air-navigation.json
- question-bank/technical-general.json
- question-bank/rtr.json
- question-bank/piper-archer-iii.json

Change free/paid status in `question-bank/subjects.json`.

Question format:
{"id":"reg-1","question":"Question text","options":["A","B","C","D"],"answer":0,"explanation":"Explanation","chapter":"Chapter","difficulty":"medium"}

Answer is zero-based: 0=A, 1=B, 2=C, 3=D.


## Production
Use a real database (PostgreSQL/MongoDB), HTTPS, strong secrets, backups, rate limiting, email verification/password reset, and a production hosting setup.
