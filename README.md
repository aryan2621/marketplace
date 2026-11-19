# Marketplace (AndroHub)

An Android app marketplace: developers publish APKs, reviewers approve them, and users browse and download.

## Services

| Folder | Role | Stack |
|---|---|---|
| `app-market-place` | Public store: browse, search, categories, featured, app detail, report, download | Next.js |
| `app-market-place-admin` | Developer dashboard: sign-in (Clerk), GitHub verification, app listings, submit for review, appeals | Next.js |
| `app-market-place-master` | Reviewer dashboard: review queue, approve / reject / request changes, appeals, reports, Inngest submission pipeline | Next.js |
| `apk-extraction-service` | Downloads an APK from a URL and extracts package name, permissions and SDK versions | Node, Express |

All services share one Firebase (Firestore) database. After a developer submits an app, Admin triggers the reviewer pipeline in Master over an internal HTTP call. See [Knowledge.md](Knowledge.md) for the full product walkthrough and app status flow.

## Run

Each service is independent and has its own `package.json`.

```sh
cd <service>            # for the Next.js apps: cd <service>/client
npm install
npm run dev
```

The extraction service runs with `npm start` (or `npm run dev`) and listens on `PORT` (default `3000`).

## License

MIT, see [LICENSE](LICENSE).
