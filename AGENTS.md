## Development

When starting the dev server, use background mode:

```
astro dev --background
```

Manage the background server with `astro dev stop`, `astro dev status`, and `astro dev logs`.

Use `pnpm` for everything — never `npm`, `yarn`, or `bun`.

## Constraints

**TypeScript is pinned to 6.x.** `astro check` drives the TypeScript compiler through a
programmatic API that the native compiler in TypeScript 7 does not expose, so bumping to 7
makes `pnpm check` fail — and with it the build job. Keep the pin until
[withastro/roadmap#1321](https://github.com/withastro/roadmap/discussions/1321) lands
support, then bump both together.

**`public/CNAME` must contain the apex domain.** Astro copies `public/` verbatim into
`dist/`, and GitHub Pages reads `CNAME` from the published artifact to keep the custom
domain attached. If it goes missing, the site silently reverts to `*.github.io` on the next
deploy. The build job asserts the file survives.

## Documentation

Full documentation: https://docs.astro.build

Consult these guides before working on related tasks:

- [Adding pages, dynamic routes, or middleware](https://docs.astro.build/en/guides/routing/)
- [Working with Astro components](https://docs.astro.build/en/basics/astro-components/)
- [Using React, Vue, Svelte, or other framework components](https://docs.astro.build/en/guides/framework-components/)
- [Adding or managing content](https://docs.astro.build/en/guides/content-collections/)
- [Adding styles or using Tailwind](https://docs.astro.build/en/guides/styling/)
- [Supporting multiple languages](https://docs.astro.build/en/guides/internationalization/)
