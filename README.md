# SENTINEL MARINE

**Marine Medical Management** — Premium maritime medical management platform for superyachts, commercial vessels, and private yachts.

## Status: Phase 1 Prototype (Functional)

This is a working Progressive Web App prototype demonstrating the core journey:

**Open Sentinel → Select vessel → Select crew → Start incident → Record observations → Generate IMIST-AMBO handover**

### What works now

- Branded splash / login / registration (local auth for prototype)
- Demo account one-tap login
- Main dashboard with prominent **START MEDICAL INCIDENT** button
- Multi-vessel management
- Crew medical profiles (fictional data)
- Medical inventory with Green / Amber / Red status
- Full incident lifecycle:
  - One-tap start with automatic timestamp
  - Patient selection + allergy display
  - Progressive documentation
  - Timestamped observations (vitals)
  - Medication administration records
  - Live incident timeline
- **IMIST-AMBO structured medical handover** (print / save as PDF)
- Incident history
- Mobile-first UI (iPhone optimised), responsive
- Local persistence (survives refresh)

### What is simulated / not yet production

- Authentication is localStorage-based (not Supabase Auth)
- No real backend / PostgreSQL yet
- No offline sync engine
- No Stripe billing (infrastructure prepared in design only)
- No real PDF generation library (uses browser print)
- No clinical decision support (intentionally disabled)
- Fictional medical data only

## Quick start

```bash
cd sentinel-marine
npm install
npm run dev
```

Open the URL shown (usually http://localhost:5173).

**Recommended:** Use Chrome DevTools device toolbar → iPhone 14/15 Pro for the intended experience. Or install as PWA on a phone.

### Demo login

On the login screen tap **Continue with Demo Account**.

Demo vessel: **M/Y Aurora** with 4 crew members and sample inventory.

## Tech stack

| Layer        | Choice                          |
|--------------|---------------------------------|
| Frontend     | React 19 + TypeScript + Vite    |
| Styling      | Tailwind CSS v4                 |
| Routing      | React Router 7                  |
| Icons        | Lucide React                    |
| Persistence  | localStorage (prototype)        |
| Target       | Progressive Web App             |

## Project structure

```
src/
  components/   Layout, shared UI
  pages/        Dashboard, Login, Incident flows, etc.
  lib/          AuthContext, AppDataContext, mockData, storage
  types/        TypeScript interfaces
```

## Next phases (roadmap)

1. **Phase 2** — Full crew medical profile editing, consent, access logs
2. **Phase 3** — Inventory CRUD, consumption from incidents, reports
3. **Phase 4–5** — Harden incident + handover, observation graphs
4. **Phase 6** — Supabase (Auth + Postgres + Realtime), offline (IndexedDB + sync), Stripe subscriptions, production security & privacy controls

## Connecting Supabase later

1. Create a Supabase project
2. Add `@supabase/supabase-js`
3. Replace `lib/storage.ts` + contexts with Supabase client + RLS policies
4. Map tables to the types in `src/types/index.ts`

## Important notices

- This software is a prototype. Not certified for clinical use.
- Do not enter real patient data.
- Australian privacy / GDPR / HIPAA compliance has **not** been assessed.
- No emergency response or dispatch features are included.

---

Built for the founder of Sentinel Marine · AI-assisted development
