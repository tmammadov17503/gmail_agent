# Email Agent

Static Gmail inbox agent for scanning, sorting, reading, replying to, and bulk-cleaning email across multiple accounts.

## What It Does

- Connects up to 3 Gmail accounts from a single interface
- Keeps the real Gmail folder source visible: Primary, Promotions, Social, or Updates
- Classifies threads into useful categories like Important, Work, Finance, Social, Newsletter, Ads, Spam, and Other
- Lets you read full emails inside the app
- Drafts replies with Groq when a key is provided
- Adds bulk delete actions for each category and each Gmail folder
- Handles larger cleanup runs with throttled batch trashing instead of tiny one-shot deletes
- Works as a single static HTML app with no backend
- Uses a responsive layout for desktop and mobile

## Why This Version Is Better

This version was rebuilt to make Gmail folder detection more accurate, bulk deletion more practical, and the UI more polished across devices. If Gmail says a thread came from Social, the app keeps that source visible instead of guessing.

## Quick Start

1. Open `docs/index.html`.
2. Add your Google OAuth Client ID in the built-in `BUILTIN_DEFAULTS` block or enter it in the app UI.
3. Keep the Groq key empty in code if the repo is public.
4. Add your exact app URL to the Google Cloud OAuth redirect URIs.
5. Open the app and click `Scan Inbox`.
6. Authenticate the Gmail account(s) you want to use.

## Configuration

The app has a built-in config block inside `docs/index.html`:

```js
const BUILTIN_DEFAULTS = Object.freeze({
  groqKey: '',
  clientId: '',
  numAccounts: 3,
  scanLimit: 250
});
```

### Recommended setup

- `clientId`: set this once
- `groqKey`: leave empty in the code for a public repo
- `numAccounts`: choose your default number of Gmail accounts
- `scanLimit`: choose how many threads to pull per account

If you enter values in the app UI, they are stored in your browser `localStorage`.

## Groq Is Optional

You can use the app without a Groq key.

Without Groq:
- Gmail folder detection still works
- local heuristic categorization still works
- reading and deleting still work
- auto-drafted replies are disabled

With Groq:
- categorization becomes smarter
- reply drafting is enabled

## Gmail Permissions

The app uses the full Gmail scope:

```txt
https://mail.google.com/
```

That is required because the app can:

- read inbox threads
- move threads to Trash
- send replies

## Public Repo Safety

If this project is public:

- do not commit a live Groq key
- do not commit personal API keys in text files
- do not commit private client secrets you do not want exposed

Your Google OAuth client ID is fine to expose for a browser app. That is normal.

## Project Structure

```txt
gmail_agent/
  docs/
    index.html
```

## Deployment

This project works well as a static site, including GitHub Pages.

If you deploy it, make sure the deployed URL exactly matches the redirect URI configured in Google Cloud.

## UX Highlights

- folder-aware email badges
- per-category `Delete All`
- folder-wide bulk cleanup
- full email reader modal
- AI reply modal
- mobile-friendly responsive layout

## Notes

- The app is client-side only
- No backend database is required
- Account tokens are browser-session based
- Saved settings and memory live locally in the browser

## Future Ideas

- smarter sender rules
- custom category presets
- undo queue for bulk actions
- export scan summaries
- better thread-level analytics
