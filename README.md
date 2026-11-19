# React Café

A feedback widget for Sip Happens Café. Built with Vite, React, and TypeScript for Homework 1.

## Run locally

Use Node.js 20.19+ or 22.12+. From this folder, run:

```sh
nvm use
npm ci
npm run dev
```

The `.nvmrc` file selects the installed Node.js 22.13.0 version. If you do not use nvm, use a supported Node.js version directly. Open the local URL printed by Vite.

## Commands

```sh
npm run build
npm run lint
npm run format:check
npm run preview
```

`build` checks TypeScript and creates the production files in `dist`. `preview` serves these files locally after a build. `npm run format` formats the source with Prettier.

## How it works

- `App` owns the `votes` state and the vote and reset functions.
- `CafeInfo` shows the required title and description.
- `VoteOptions` calls `onVote` with `good`, `neutral`, or `bad`. It shows Reset only when `canReset` is true.
- `VoteStats` receives the counts, total, and positive rate through props.
- `Notification` shows `No feedback yet` when there are no votes.
- `src/types/votes.ts` exports the shared `Votes` interface and `VoteType` union.

Each component has its own folder, `.tsx` file, CSS Module, and default export. Local prop interfaces stay beside their component.

The total and positive rate are calculated in `App` on each render. They are not separate state. Vote updates use the previous state to keep repeated clicks correct. Refreshing the page clears the votes. The assignment does not require saved votes.

## Styles and references

The five CSS Modules come from the [course styles](https://github.com/goitacademy/react-cafe-styles), revision `c8a98fae130ee099d48389b7027deeec3e71ba46`. Prettier only changes their formatting. Global CSS sets the page font and background and adds a visible keyboard focus outline.

The pasted assignment has no usable demo video link. The supplied markup and course CSS are the visual baseline.

- [Vite setup](https://vite.dev/guide/)
- [React: updating objects in state](https://react.dev/learn/updating-objects-in-state)

## Submission

The course requires a repository named `02-react-cafe` and a working Vercel URL.

Source code: [02-react-cafe on GitHub](https://github.com/AurikaSa/02-react-cafe).

Live app: [Sip Happens Café](https://02-react-cafe-ivory-ten.vercel.app/).

Published to Vercel on 19 November 2026 from the local project. The public URL returns HTTP 200 without a Vercel login. Good, Neutral, Bad, the total, 33% positive feedback, and Reset were checked on the live page. No browser console errors or warnings were recorded during this check.

Submit the GitHub URL and the live app URL to the course portal. Course portal submission is still pending.

The assignment asks students to wait at least five minutes after the last push before submission.
