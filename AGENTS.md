# Workspace Rules

- **Always Maintain `README.md`**: Always create a `README.md` file in any project/workspace if one does not exist, and always keep `README.md` updated whenever the repository data, system count, features, or structure change.
- **Database Synchronization**: Whenever `data.json` is updated with new or modified manufacturing software systems, always validate sector keys against `sectorMap` in `app.js`, re-encrypt `data.json` into `ENCRYPTED_DATABASE` in `app.js`, and update the system count and last-updated date in `index.html` and `README.md`.

