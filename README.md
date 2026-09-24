# Marketplace

Android app marketplace (AndroHub) with a public store, developer dashboard, reviewer queue, and APK metadata extraction.

## Services

- `app-market-place` — public store (browse, search, download)
- `app-market-place-admin` — developer dashboard (listings, submit for review)
- `app-market-place-master` — reviewer dashboard (approve, reject, reports)
- `apk-extraction-service` — extracts package name, permissions, and SDK versions from APKs

## Stack

Next.js, Firebase, Node.js, Express.

Each service has its own `package.json`. See the service directories for setup.
