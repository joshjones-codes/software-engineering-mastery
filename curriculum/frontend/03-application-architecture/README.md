# Application Architecture

Where seniors separate themselves: structure, state, and data flow at app scale.

| Module | Tier | Effort | Covers |
|---|---|---|---|
| [State Management](01-state-management.md) | 🔴 must | ~2 wknds | local vs server vs URL state, context performance, Zustand/Jotai tradeoffs |
| [Data Fetching & Caching](02-data-fetching-and-caching.md) | 🔴 must | ~2 wknds | TanStack Query, optimistic updates, cache invalidation, request waterfalls |
| [Forms & Validation](03-forms-and-validation.md) | 🟡 should | ~1 wknd | React Hook Form + Zod, schemas shared with the API layer |
| [Error, Loading & Offline UX](04-error-loading-and-offline-ux.md) | 🟡 should | ~1 wknd | error boundaries, skeletons vs spinners, retry UX, empty states |
