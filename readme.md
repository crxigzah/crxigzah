# Hi, I'm crxigzah 👋

I build and run **[5kable](https://5kable.net)**, an AI-powered geography training platform for GeoGuessr-style games: a Chrome extension paired with a Flask/Postgres backend, a Stripe-billed Pro tier, and a Discord-integrated community.

### What's in it

- **Chrome extension**: reads live round data, calls a backend AI pipeline (Anthropic Claude API) for scene analysis and post-round teaching, and renders Street View reference panoramas from a community-sourced scene library.
- **Backend API** (Flask + Postgres/Supabase, deployed on Render): auth with 2FA/TOTP, Stripe Checkout for one-time Pro purchases, a full Discord bot integration (slash commands, role sync, reaction-based verification via the Gateway, scheduled announcements), transactional email, and an admin panel for support tickets and content moderation.
- **Public site**: training guides per country, a region map, leaderboards, and daily challenges, statically hosted on Cloudflare Pages.

### Repos

- 🌐 [`5kable-site`](https://github.com/crxigzah/5kable-site): the public website (open)
- 📦 [`5kable-releases`](https://github.com/crxigzah/5kable-releases): packaged extension releases (open)
- 🔒 Backend and extension source are private (paid product), but I'm happy to walk through the architecture or specific code on request.

### Some things I've worked through building this

- Diagnosed a production incident where a background Discord Gateway listener was silently starved by GIL contention with the web server's own request threads, then moved it to a standalone OS process instead of a thread.
- Migrated Stripe billing from a monthly subscription to a one-time payment without breaking existing subscribers.
- Built a label-collision-avoidance system for rendering region maps of 190+ countries.
