# pj-firebase

Firestore + Storage + two deploy targets (Firebase Hosting and
Vercel) for [`kata`](https://github.com/yukimemi/kata).

Optional layer — compose into a preset only when the project
actually uses Firebase. Sits at the top of the stack:
`pj-base → pj-pnpm → pj-react-web → pj-firebase`.

Ships:

- `firebase.json` (Tera-rendered hosting site)
- `firestore.rules` / `storage.rules` (signed-in-only starter)
- `vercel.json` (Hosting mirror with matching SPA rewrite + COOP)
- `.github/workflows/deploy.yml` (pnpm + Firebase Hosting deploy)
- `.env.example` (the `VITE_FIREBASE_*` surface)

**Two targets, one choice.** Hosting and Vercel are both wired so
a static app gets Hosting plus Vercel PR previews for free. A
project with server-side code (`api/` Vercel Functions, route
handlers) cannot use Hosting at all — it serves static files and
cannot execute a function — so that project drops `deploy.yml`
and deploys only to Vercel. `AGENTS.md.firebase` spells out how
to make that choice stick.

See [`template.toml`](./template.toml) for the file list and merge
modes, and [`AGENTS.md.firebase`](./AGENTS.md.firebase) for the
layer's agent guidance (which becomes a marker block in the
consuming repo's `AGENTS.md`).

## License

MIT.
