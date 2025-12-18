# GitHub Portfolio Sites

A small set of HTML-only portfolio pages that pull live data from the GitHub API.

The project includes two variants:
- **Single User** — for individual developers
- **Organisation** — for teams or companies

Both versions are framework-free, client-side only, and designed to be easy to host or embed.

---

## What’s included

```
/
├─ single-user.html
├─ organisation.html
└─ README.md
```

(File names can be changed if needed — the logic is self-contained.)

---

## Single User Portfolio

The single-user version displays:
- GitHub profile information
- Bio and metadata
- Public repositories
- Recent activity and language data

### Data sources

- https://api.github.com/users/{username}
- https://api.github.com/users/{username}/repos

### Configuration

Edit the following line in the file:

```js
const USER = "your-github-username";
```

---

## Organisation Portfolio

The organisation version displays:
- Organisation profile information
- Organisation-owned repositories
- A curated list of team members

Team members are **explicitly defined** to avoid listing large or private organisation memberships.

### Data sources

- https://api.github.com/orgs/{org}
- https://api.github.com/orgs/{org}/repos
- https://api.github.com/users/{username} (for team members)

### Configuration

Edit the config section in the file:

```js
const ORG = "your-org-name";

const EMPLOYEES = [
  "username1",
  "username2"
];
```

Only users listed in `EMPLOYEES` will appear on the site.

---

## Hosting

Both pages can be:
- Opened locally
- Hosted on GitHub Pages
- Embedded in another site or dashboard

No build step or backend is required.

---

## Notes

- GitHub API is rate-limited (60 requests/hour without authentication)
- Only public repositories are shown
- Forks are displayed but clearly marked

---

## License

MIT License — see LICENSE file.
