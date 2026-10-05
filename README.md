# Pulse Care — Healthcare App Foundation

A work-in-progress healthcare application foundation using Next.js, TypeScript, Tailwind CSS, and Zod. The repository currently contains shared validation schemas, healthcare types, theme setup, a button component, and Sentry configuration; the home page renders a single demonstration button.

**Stack:** Next.js 14 · React 18 · TypeScript · Tailwind CSS 3 · Zod · Sentry

## Highlights

- Next.js 14.2 App Router and React 18.
- Zod schemas for user details, patient registration, and appointment operations.
- Type definitions for users, patients, and appointment statuses.
- Reusable button built with Radix Slot and class-variance-authority.
- Dark theme setup through `next-themes`.
- Client, edge, and server Sentry configuration.

## Run locally

Install Node.js and npm, then:

```sh
git clone https://github.com/itzhoman/pulse-care.git
cd pulse-care
npm ci
npm run dev
```

Open http://localhost:3000. Font setup uses `next/font/google`; initial font fetching may require internet access.

## Development commands

| Command | Purpose |
| --- | --- |
| `npm run dev` | Start the development server |
| `npm run build` | Build the production app |
| `npm run start` | Serve the production Next.js build |
| `npm run lint` | Run the configured lint command |

Run `npm run build` before `npm run start`.

No automated test script is currently defined in `package.json`.

## Project structure

| Path | Responsibility |
| --- | --- |
| `app/page.tsx` | Current Click Me button demonstration |
| `app/layout.tsx` | Application metadata, font setup, and theme provider |
| `components/ui/button.tsx` | Reusable styled button |
| `components/theme-provider.tsx` | next-themes wrapper |
| `lib/validation.ts` | User, patient, and appointment validation schemas |
| `types/` | Healthcare models and Appwrite-related type declarations |
| `constants/index.ts` | Static form/healthcare constants |
| `sentry.client.config.ts` | Browser monitoring configuration |
| `sentry.server.config.ts` | Server monitoring configuration |
| `sentry.edge.config.ts` | Edge monitoring configuration |
| `next.config.mjs` | Next.js/Sentry build integration |

## Customize

- Build the registration and appointment pages using the existing schemas and types.
- Add server-side Appwrite operations only when the required project and collections exist.
- Replace the inherited Sentry organization, project, and DSNs with your own monitoring configuration before running a personal deployment.

## Current scope

Patient registration screens, booking routes, admin workflows, Appwrite CRUD operations, and Twilio SMS sending are not implemented in the current source. Packages for those services do not by themselves provide working integrations. No Appwrite/Twilio environment-variable setup is required by the committed home page. The original README included tutorial snippets and full-app features that were not present in the source.

## Tutorial attribution

This repository is based on the JavaScript Mastery / Adrian Hajdin healthcare tutorial, credited in the original README. Reference: [upstream healthcare repository](https://github.com/adrianhajdin/healthcare) and [tutorial video](https://youtu.be/lEflo_sc82g). This README documents this repository's current implementation, while retaining the tutorial attribution.

## Repository

[Source on GitHub](https://github.com/itzhoman/pulse-care) · [Hooman Hajimohamadi](https://github.com/itzhoman)

Documentation reviewed against source commit [`16c6857`](https://github.com/itzhoman/pulse-care/commit/16c6857520e6888bba5f3ceafd986654de8cffbb).
