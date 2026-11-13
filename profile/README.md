<h1 align="center">🌱 Arbore</h1>
<h3 align="center">Design your garden in augmented reality, then keep it alive.</h3>

<p align="center">
  <a href="https://arbore.app"><img src="https://img.shields.io/badge/Website-arbore.app-2E7D32?style=for-the-badge" alt="Website"></a>
  <a href="https://web.arbore.app"><img src="https://img.shields.io/badge/Web%20app-web.arbore.app-1565C0?style=for-the-badge" alt="Web app"></a>
  <a href="https://apps.apple.com/fr/app/arbore/id6762100087?l=en-GB"><img src="https://img.shields.io/badge/iOS-Download%20on%20the%20App%20Store-0D96F6?style=for-the-badge&logo=apple&logoColor=white" alt="Download on the App Store"></a>
</p>

---

Point your phone at a balcony, a terrace or a garden. Arbore measures the space,
suggests plants that actually suit its light, soil and exposure, and lets you
place true-to-scale 3D models before you buy anything. Once planted, it tells you
when to water.

A 4th and 5th year student project, built as a real product: shipped to the App
Store, documented like a system someone else will maintain.

## What's here

| Repository | |
|---|---|
| **[Arbore](https://github.com/ArboreTeam/Arbore)** | The product. iOS app, Go backend, Next.js web companion, AI generation service, infrastructure as code, and the technical documentation. |
| **[Arbore_SiteVitrine](https://github.com/ArboreTeam/Arbore_SiteVitrine)** | The public site at [arbore.app](https://arbore.app), including the privacy policy and terms. |

## How it's built

**iOS** — Swift and SwiftUI, with ARKit and RoomPlan for scanning, SceneKit and
RealityKit for placement. Plants are USDZ models served at two levels of detail,
swapped on device according to distance and thermal state.

**Backend** — Go and Gin on MongoDB Atlas, behind Firebase Auth. Two barriers on
every request: an API key checked in constant time, then a verified Firebase
token. The web companion never sees either, because a same-origin server proxy
holds them.

**Infrastructure** — Terraform for DNS and object storage, encrypted secrets
committed to the repository, Docker images built in CI and pulled on the server,
two independent stacks on one host. The repository is the complete definition of
a deployment: clone it, supply the secrets, run the deploy.

**Observability** — Sentry across iOS, web and backend. Crash reporting is
opt-in and anonymous by default.

## Documentation

The [technical documentation](https://github.com/ArboreTeam/Arbore/blob/main/docs/README.md)
is bilingual and kept at parity, with a CI job that fails the build when a
documented code path no longer exists.

C4 architecture views, user flows, per-screen specifications, architecture
decision records, and operations runbooks — from the first scan to the deploy.

## Availability

The iOS app is **[on the App Store](https://apps.apple.com/fr/app/arbore/id6762100087?l=en-GB)**
and ships in French, English, Spanish and German. The web companion is live and
open. A [TestFlight beta](https://testflight.apple.com/join/xyUGxhKH) stays open
for anyone who wants the next version early.

It is free, non-commercial, and carries no advertising, tracking, subscription or
in-app purchase.

<p align="center">
  <sub>Made in France 🇫🇷 · <a href="mailto:support@arbore.app">support@arbore.app</a></sub>
</p>
