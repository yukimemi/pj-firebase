# pj-firebase

Firebase Hosting + Firestore + Storage + Vercel mirror layer for
[`kata`](https://github.com/yukimemi/kata).

Optional layer — compose into a preset only when the project
actually uses Firebase. Sits at the top of the stack:
`pj-base → pj-pnpm → pj-react-web → pj-firebase`.

Ships:

- `firebase.json` (Tera-rendered hosting site)
- `firestore.rules` / `storage.rules` (signed-in-only starter)
- `vercel.json` (Hosting mirror with matching SPA rewrite + COOP)
- `.github/workflows/deploy.yml` (pnpm + Firebase Hosting deploy)
- `.env.example` (the `VITE_FIREBASE_*` surface)

See [`template.toml`](./template.toml) for the file list and merge
modes, and [`AGENTS.md.firebase`](./AGENTS.md.firebase) for the
layer's agent guidance (which becomes a marker block in the
consuming repo's `AGENTS.md`).

## License

MIT.
