# Workout Tracker - V1 Specifications

## Overview

A workout tracking web/mobile app focused on giving the user the ability to
create custom & repeatable workout templates. The focus for the mobile app is
creating and logging exercises & body metrics. The web app will mainly cover
analytics but will still have the same base functionality as the mobile version.

## V1 Features

### Authentication

- Guest mode with local SQLite storage
- Registered accounts with PostgreSQL sync
- JWT authentication

### Workout Logging

- Start and end workout sessions
- Edit workouts after they are done
- Add/remove exercises during the session
- Log sets, reps, weight per exercise
- Rep ranges for template exercises
- Superset grouping
- Cardio tracking (duration, distance)
- Track rate of perceived exertion (RPE)
- PRs can be entered separately from a workout session

### Exercise Library

- Predefined exercise list
- Muscle group categorization
- Exercise types (strength, cardio, bodyweight)
- List of required equipment

### Templates

- Create reusable workout templates
- Assign exercises with target sets and rep ranges

### Analytics (Web Dashboard)

- Progress over time
- PR tracking
- Volume by muscle group (heatmap)

## Out of Scope for V1

- Offline sync conflict resolution
- Social features
- Wearable device integration

## Tech Stack

### Backend

- Runtime: Node.js
- Framework: NestJS
- Language: TypeScript
- ORM: Prisma
- Database: PostgreSQL (production), SQLite (local device)
- Auth: JWT with refresh tokens

### Frontend

- Web: React + TypeScript
- Mobile: React Native + TypeScript
- Tooling: Expo
- Monorepo: Turborepo

### Infrastructure

- Backend hosting: TBD (AWS EC2 or Railway)
- Database hosting: TBD (AWS RDS or Railway)
- Mobile: Expo EAS for builds

## Monetization

### Free Tier

- Unlimited workout logging with all functionality
- Session history
- PR entry/tracking
- Data export **(it's their data)**
- Guest mode

### Premium Tier

- Web analytics dashboard
- Progress charts
- Cloud backup and cross-device sync

## Open Questions

- How long should the trial of premium be?
- Lifetime pricing vs monthly/annual subscription?
- Should cloud sync be free or premium?
- Start with a basic exercise list or let users add/create their own?
- How do we handle guest account to registered user migration?
- Conflict resolution strategy for offline sync (V2)
- Payment processor: Stripe?
