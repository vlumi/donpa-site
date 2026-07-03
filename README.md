# donpa.app

The website for **Donpa Squad** (ドンパ隊) — a manga-styled Minesweeper for iPhone,
iPad, and Mac. Landing, support, and privacy pages, plus the host for the app's
Universal Links.

The game itself is open source (MIT) at
[github.com/vlumi/donpa](https://github.com/vlumi/donpa). **This site is not**:
the marketing copy, brand, and artwork are all rights reserved. The repository is
public for transparency, not for reuse.

## Build

Static site, built with [Hugo Extended](https://gohugo.io/). No JS, no external
assets — plain HTML/CSS.

The Hugo version is **pinned** in [`.hugoversion`](.hugoversion). Hugo is a
build-time tool, not a runtime — there's no security reason to chase updates, and
a bump is the thing most likely to *break* the build. So pin it and update
**deliberately**: bump `.hugoversion`, run a local build, and commit only if it's
clean. (The box's nginx / OS / certbot are what stay current, not Hugo.)

```sh
hugo server        # local preview at http://localhost:1313
hugo               # one-off build into ./public
```

## Deploy

Served by nginx over HTTPS (Let's Encrypt / certbot) on the host for `donpa.app`.
[`deploy.sh`](deploy.sh) does it in one step: it fetches the **pinned** Hugo
Extended (cached per-version under `~/.local/share/donpa-hugo`, no root, never the
system Hugo), pulls, and builds straight into the web root.

```sh
./deploy.sh                          # pull, build, publish to /var/www/donpa.app
WEBROOT=/some/other/path ./deploy.sh # override the publish dir
./deploy.sh --no-pull                # build the working tree as-is
```

The build writes directly into `WEBROOT` (`--cleanDestinationDir` removes stale
files), so **nginx `root` points at the web root itself** (e.g.
`root /var/www/donpa.app;`), not a `public/` subdir — no repo or source files ever
live under the served path.

### Universal Links (later — for the v0.5.0 share feature)

The Apple App Site Association file lives at
`static/.well-known/apple-app-site-association` (served with no extension as
`application/json`). nginx must serve it **without a redirect**:

```nginx
location = /.well-known/apple-app-site-association {
    default_type application/json;
}
```
