# weedweedwiki

## About the Project
`weedweedwiki` is a Hugo based website about growing plants.

### Content
A site about cannabis, yes, but also all other plants; because really, growing cannabis is just a gateway drug to a gardening obsession.

The term "Weed" is used generally to refer to a fast-growing plant that is often not desirable. But in a way, it's a bit of a derogatory term. There are no "weeds", just plants growing in a world where plants should grow.


### Technical
The hugo template in use is custom made and based on wikimedia.
In carrying the legacy of community-driven open source knowledge that wikipedia immortalized, this site can be updated by anyone (with a github account). The entire site is derived from documents saved on github.

With a standard wiki style site, a backend is required to store and update data. The purpose of this site is to keep things light and deployable anywhere as a static site. No backend needing to be deployed.
Users who wish to update the site can do so easily via github, and approved by a simple pull request. Every change can be seen, everything is public.

Maybe some day it will not be stored on github, but the idea is the same.


## Requirements

- **Hugo extended** (developed against `v0.163.3+extended`) — the theme needs the extended build.
- **Node + npm** — only used to install and run [`pagefind`](https://pagefind.app), which generates the search index.

```bash
npm install
```


## Start the Dev Server

```bash
hugo server
```

The site is then available at <http://localhost:1313/>. Hugo watches `content/`,
`layouts/`, `assets/` and `static/`, and live-reloads on save. `npm run dev` is a
thin alias for the same command.

### Search in dev

`hugo server` does **not** run pagefind, so the `/search/` page has no index to
read from until one has been built at least once:

```bash
npm run build     # hugo && pagefind --site public
hugo server       # search now works, using the index in public/
```

The index is written to `public/pagefind/` and is **not** regenerated as you
edit — it reflects the content as of the last `npm run build`. Re-run the build
whenever you need search results to match new or renamed pages.


## Build Site

```bash
npm run build
```

This runs `hugo && pagefind --site public`: Hugo renders the static site into
`public/`, then pagefind crawls that output and writes the search index into
`public/pagefind/`. `--site public` is a relative path, so run this from the root
of the repo.

`public/` is the deployable artifact — serve it from any static host.
