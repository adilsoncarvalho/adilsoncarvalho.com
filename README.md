# adilsoncarvalho.com

Personal landing page for Adilson Carvalho.

Built with [Astro](https://astro.build), published to [GitHub Pages](https://pages.github.com),
with DNS hosted in [AWS Route 53](https://aws.amazon.com/route53/).

## Stack

| Concern | Choice |
| --- | --- |
| Static site generator | Astro |
| Package manager | pnpm |
| Hosting | GitHub Pages |
| DNS | AWS Route 53 |
| TLS | GitHub Pages managed certificate (Let's Encrypt) |

## Local development

Requires Node.js 20+ and [pnpm](https://pnpm.io).

```sh
pnpm install     # install dependencies
pnpm dev         # start the dev server at http://localhost:4321
pnpm build       # build the production site into dist/
pnpm preview     # serve the built site locally
```

## Deployment

The site is built by GitHub Actions and published to GitHub Pages on every push to `main`.

For the custom domain to survive each deploy, `public/CNAME` must contain the apex domain
(`adilsoncarvalho.com`) — Astro copies `public/` verbatim into `dist/`, and GitHub Pages
reads `CNAME` from the published artifact.

### DNS (Route 53)

In the hosted zone for `adilsoncarvalho.com`:

- **Apex (`adilsoncarvalho.com`)** — four `A` records pointing at the GitHub Pages IPv4
  addresses, and four `AAAA` records for IPv6. The current addresses are published in the
  [GitHub Pages apex domain docs](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site#configuring-an-apex-domain);
  verify against that page rather than copying them from elsewhere, as they do change.
- **`www`** — a `CNAME` to `adilsoncarvalho.github.io`.

Enable **Enforce HTTPS** in the repository's Pages settings once the domain verifies.

## License

Everything in this repository — the code, the writing, and the images — is licensed under
[Creative Commons Attribution 4.0 International](https://creativecommons.org/licenses/by/4.0/)
(CC BY 4.0). See [LICENSE](LICENSE) for the full text.

You are free to share and adapt this work, including commercially, provided you give
appropriate credit: name Adilson Carvalho, link back to this repository or to
<https://adilsoncarvalho.com>, and indicate whether you made changes.
