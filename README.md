To build a Svelte project, using [`create-svelte`](https://github.com/sveltejs/kit/tree/main/packages/create-svelte).

```bash
# create a new project in the current directory
npm create svelte@latest

# create a new project in my-app
npm create svelte@latest my-app
```

To start a development server:
After installing `npm install` (or `pnpm install` or `yarn`)

```bash
npm run dev
or
npm run dev -- --open
```

To create a production version of your app:

```bash
npm run build
```

To preview tehe production:

```bash
npm run preview
```

Install [adapter](https://kit.svelte.dev/docs/adapters) for the target environment.
