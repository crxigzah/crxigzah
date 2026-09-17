Hi, I'm **crxigzah** 👋

I am a ITIL aligned Azure & Microsoft certified IT Engineer

I build and run **[5kable](https://5kable.net)**, an AI powered geography training platform for Geography style games: a Chrome extension paired with a Flask/Postgres backend, a Stripe billed Pro tier, and a Discord integrated community.

## **What's in it** ## 
Chrome extension: reads live round data, calls a backend AI pipeline (Anthropic Claude API) for scene analysis and post round teaching, and renders Street View reference panoramas from a community sourced scene library.
Backend API (Flask + Postgres/Supabase, deployed on Render): auth with 2FA/TOTP, Stripe Checkout for one time Pro purchases, a full Discord bot integration (slash commands, role sync, reaction based verification via the Gateway, scheduled announcements), transactional email, and an admin panel for support tickets and content moderation.
Public site: training guides per country, a region map, leaderboards, and daily challenges, statically hosted on Cloudflare Pages.

## **Repos** ##
🌐 5kable-site: the public website (open)
📦 5kable-releases: packaged extension releases (open)
🔒 Backend and extension source are private (paid product), but I'm happy to walk through the architecture or specific code on request.

## **Some things I've worked through building this** ## 
Diagnosed a production incident where a background Discord Gateway listener was silently starved by GIL contention with the web server's own request threads, then moved it to a standalone OS process instead of a thread.
Root caused a duplicate post bug in a daily Discord bot job by cross referencing GitHub Actions logs against the database and real Discord message history, then redesigned the retry logic to tell "failed before Discord    ever saw it" apart from "Discord may have already posted it."
Migrated Stripe billing from a monthly subscription to a one time payment without breaking existing subscribers.
Built a label collision avoidance system for rendering region maps of 190+ countries, including small territories missing from the low resolution base map data.
Built a community sourced Street View scene library: every player's in game capture adds a location that other players' training guides can reference live, with no imagery ever stored server side.
Added a live multi currency price display that converts a single GBP source of truth client side, so Stripe only ever has to know one currency.
