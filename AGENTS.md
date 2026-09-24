# Shopify Hydrogen development

This storefront is scaffolded from Shopify's Hydrogen skeleton template. See the README for framework-specific details.

Use the [Shopify AI Toolkit](https://shopify.dev/docs/apps/build/ai-toolkit) for all Shopify API and platform work. If missing, install it in the agent host per that page (or `npx skills add Shopify/shopify-ai-toolkit --list` for skill-compatible hosts).

## React Router imports (not Remix)

This project is built on React Router v7 (framework mode), not Remix. Documentation and examples for Hydrogen written before the React Router migration still use Remix packages; adapt them.

- Import routing hooks and components from `react-router`: `useLoaderData`, `Link`, `Form`, `useActionData`, `useNavigation`, `useSubmit`, `useFetcher`, `redirect`, `data`, etc.
- NEVER import from `react-router-dom`.
- NEVER import from any `@remix-run/*` package.

| Remix v2 package | React Router v7 package |
|------------------|-------------------------|
| `@remix-run/react` | `react-router` |
| `@remix-run/server-runtime` | `react-router` |
| `@remix-run/testing` | `react-router` |
| `@remix-run/dev` | `@react-router/dev` |
| `@remix-run/route-config` | `@react-router/dev` |
| `@remix-run/fs-routes` | `@react-router/fs-routes` |
| `@remix-run/node` | `@react-router/node` |
| `@remix-run/cloudflare` | `@react-router/cloudflare` |
| `@remix-run/express` | `@react-router/express` |
| `@remix-run/architect` | `@react-router/architect` |
| `@remix-run/serve` | `@react-router/serve` |
| `@remix-run/routes-option-adapter` | `@react-router/remix-routes-option-adapter` |

Follow the patterns already established in `app/routes/` and `app/components/`. Route types come from the generated `./+types/<route>` modules. Upgrade guide: https://reactrouter.com/upgrading/remix
