# Architecture overview

## Public delivery

The public site is served by a Next.js application on Vercel. Server rendering provides stable article URLs, metadata, canonical links, archive navigation, sitemap output, robots directives, and an Atom feed. Static media and application responses are delivered through the hosting edge network.

## Content and media

Editorial content is stored in Supabase Postgres and media is managed through Supabase Storage. Public readers receive published material only; draft and administrative data remain behind authenticated authorization boundaries.

## Editorial workflow

The private owner workflow supports drafts, previews, revisions, publishing, media management, SEO fields, tags, comment moderation, and author replies. Authentication is handled through Supabase Auth using secure server-side sessions.

## Reader interaction

Public comments enter a moderation queue before publication. The public submission path applies validation, origin checks, abuse controls, and rate limiting. Published comments can receive an identifiable author reply.

## Migration and continuity

The migration preserved the original Blogger paths, dates, article structure, media references, comments, and discovery surfaces. The production cutover retained a Blogger export and an exact DNS rollback route.

## Deliberate exclusions

This overview omits production source code, route internals, database definitions, migrations, policy expressions, environment values, operational credentials, generated content, and private administrative details.

