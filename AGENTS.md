# Repository guidance

## Project Configuration

- SvelteKit 3 application using Svelte 5, TypeScript, npm, prettier, eslint, vitest, playwright, tailwindcss, enhanced-img, sveltekit-adapter, and ai-tools.
- This is a client-rendered SPA: `src/routes/+layout.ts` sets `ssr = false` and `vite.config.ts` uses `@sveltejs/adapter-static` with a `404.html` fallback.
- Svelte runes mode is enabled for project files in `vite.config.ts`.
- Keep provider credentials and other secrets out of browser code. This static deployment has no SvelteKit server runtime; server-only features need a separately deployed backend or an intentional adapter/deployment change.
- The app currently has a minimal starter route. Follow existing project patterns and avoid adding dependencies when the current stack is sufficient.

## Useful commands

- `npm run dev` — start the development server.
- `npm run build` — build the static app.
- `npm run format` - run code formatting tool.
- `npm run lint` — check formatting and lint rules.
- `npm run check` — run Svelte and TypeScript diagnostics.
- `npm run test:unit` — run unit tests.
- `npm run test:e2e` — run Playwright end-to-end tests.

## Svelte documentation and checks

You are able to use the Svelte MCP server, where you have access to comprehensive Svelte 5 and SvelteKit documentation. Here's how to use the available Svelte MCP tools:

### 1. list-sections

Use this FIRST to discover all available documentation sections. Returns a structured list with titles, use_cases, and paths.
When asked about Svelte or SvelteKit topics, ALWAYS use this tool at the start of the chat to find relevant sections.

### 2. get-documentation

Retrieves full documentation content for specific sections. Accepts single or multiple sections.
After calling the list-sections tool, you MUST analyze the returned documentation sections (especially the use_cases field) and then use the get-documentation tool to fetch ALL documentation sections that are relevant for the user's task.

### 3. svelte-autofixer

Analyzes Svelte code and returns issues and suggestions.
You MUST use this tool whenever writing Svelte code before sending it to the user. Keep calling it until no issues or suggestions are returned.
