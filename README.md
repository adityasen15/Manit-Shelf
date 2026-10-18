# MANIT Shelf

**Current project maintainer:** Aditya Sen

MANIT Shelf is a React/Vite client and Node.js/Express/MongoDB server application for sharing notes. This is a clean source handoff: the original Git metadata is not included. Existing contributor history, if applicable, remains with the original remote repository.

## Local setup

Requires Node.js, npm, MongoDB connection, and Cloudinary account credentials.

### Server

```bash
cd server
npm ci
cp .env.example .env
# Fill in .env with YOUR credentials
npm start
```

The backend currently listens on port 6969.

### Client

```bash
cd client
npm ci
npm run dev
```

The frontend currently uses `http://localhost:6969` in requests, so replace that with your deployed backend URL for production. Configure deployment CORS restrictions as appropriate.

## Publishing in Aditya's GitHub account

Create an empty repo under Aditya's GitHub username (do not initialize it with a README), then from this project's root run:

```bash
git init -b main
git config user.name "Aditya Sen"
git config user.email "ADITYA_GITHUB_EMAIL"
git add .
git commit -m "Initial project handoff"
git remote add origin https://github.com/ADITYA_GITHUB_USERNAME/MANIT-Shelf.git
git push -u origin main
```

Update the email and username placeholders first. Git identity is a local commit setting, not a verified transfer of repository ownership.

## Security and privacy

- The original `server/.env` contained credentials and is deliberately excluded. **Rotate the old Cloudinary API secret and other credentials before deploying**, since they may have been exposed in the original copy/history.
- Uploaded notes and photos under `server/files` and `server/images` are intentionally omitted to avoid distributing personal files. Recreate these directories if required for uploads.
- `node_modules` is excluded; use `npm ci` to reinstall.
- Do not commit `.env`, uploads, or `node_modules` to Git.
