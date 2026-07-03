# donpa.app

The website for **Donpa Squad** (ドンパ隊) — a manga-styled Minesweeper for iPhone,
iPad, and Mac. Landing, support, and privacy pages, plus the host for the app's
Universal Links.

The game itself is open source (MIT) at
[github.com/vlumi/donpa](https://github.com/vlumi/donpa). **This site is not**:
the marketing copy, brand, and artwork are all rights reserved. The repository is
public for transparency, not for reuse.

## Build

Static site, built with [Hugo](https://gohugo.io/) (extended). No JS, no external
assets — plain HTML/CSS.

```sh
hugo server        # local preview at http://localhost:1313
hugo               # build into ./public
```

## Deploy

Served by nginx over HTTPS (Let's Encrypt / certbot) on the host for `donpa.app`.
Build produces `./public`; publish that directory (pull + `hugo`, or rsync the
built output).

### Universal Links (later — for the v0.5.0 share feature)

The Apple App Site Association file lives at
`static/.well-known/apple-app-site-association` (served with no extension as
`application/json`). nginx must serve it **without a redirect**:

```nginx
location = /.well-known/apple-app-site-association {
    default_type application/json;
}
```
