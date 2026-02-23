# HolyPapa 🕊️
AI-powered holistic & spiritual healing services aggregator with booking + payments.

## Overview
HolyPapa helps users discover and book holistic healing services (TCM, massage, homeopathy, spiritual/religious healing). It includes a Generative AI assistant to recommend service types/providers based on user needs, while enforcing safety disclaimers.

## Stakeholders
1. **Service Seekers (Users)**: browse providers, book appointments, pay securely, read reviews, use AI guidance.
2. **Practitioners (Providers)**: create/manage listings, set availability, receive bookings, view earnings.
3. **Admin**: verify providers, moderate reviews, monitor AI safety, view analytics and payments.

## Key Features
### User
- Sign up / login (JWT)
- Search & filter providers by category, price, location
- View provider profiles & services
- Book a time slot
- Pay via Stripe (test mode)
- Leave reviews
- AI assistant for recommendations (with disclaimers)

### Provider
- Provider onboarding & profile management
- Service management (price, duration)
- Availability calendar
- Booking management (pending/confirmed/completed)

### Admin
- Approve/decline provider verification
- Flag/remove unsafe listings/reviews
- View summary analytics (bookings, revenue, complaints)

## Tech Stack
- **Frontend**: React (Vite) + Tailwind (optional)
- **Backend**: Node.js + Express
- **Database**: PostgreSQL (recommended) via Prisma (or Sequelize)
- **Auth**: JWT (access token)
- **Payments**: Stripe (test mode)
- **Generative AI**: OpenAI API (chat/completions)

## Architecture
- React SPA calls Express REST APIs
- Express uses PostgreSQL for persistence
- Stripe handles payment intents + webhooks
- AI endpoints call OpenAI and store interaction logs

## Safety & Compliance Notes (Important)
- AI output includes: “Not medical advice” disclaimer in every response.
- AI blocks/redirects emergency symptoms (e.g., chest pain, suicidal intent) to seek medical help.
- Provider claims are moderated; verification requires certificate upload (prototype can simulate this).

## Repo Structure (suggested)
holy-papa/
  client/              # React app
  server/              # Express API
  prisma/              # DB schema & migrations
  docs/                # diagrams, screenshots, assessment evidence
  README.md

## Environment Variables
### server/.env
- PORT=4000
- DATABASE_URL=postgresql://...
- JWT_SECRET=...
- STRIPE_SECRET_KEY=...
- STRIPE_WEBHOOK_SECRET=...
- OPENAI_API_KEY=...

### client/.env
- VITE_API_BASE_URL=http://localhost:4000

## Setup
### 1. Clone
git clone <your-repo-url>
cd holy-papa

### 2. Install
cd server && npm install
cd ../client && npm install

### 3. Database
- Create PostgreSQL DB
- Run migrations (Prisma):
  cd server
  npx prisma migrate dev
  npx prisma db seed

### 4. Run
- Start API:
  cd server
  npm run dev
- Start client:
  cd client
  npm run dev

## Stripe Test Cards
- 4242 4242 4242 4242 (any future expiry, any CVC)

## Prototype Capabilities
✅ Login, browse providers, view services  
✅ Booking creation & status updates  
✅ Stripe payment (test mode) + webhook updates booking/payment status  
✅ AI recommendation endpoint + stored AI logs  

## Prototype Limitations
- Limited seed data
- Provider verification may be simulated
- Not medically validated; informational use only
- No real payouts to providers (optional extension)

## Screenshots / Evidence (for Portfolio)
Add to /docs:
- UI screens (home, search, provider, booking, payment, AI chat)
- Fishbone diagram image
- Risk matrix image
- API screenshots (Postman)
- Short demo gif/video link (optional)

## License
Educational use (Bells Institute portfolio).
