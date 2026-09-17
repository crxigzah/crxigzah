<h2><strong>Hi, I'm crxigzah 👋</strong></h2>

I am an IT Engineer with 5 years of experience, currently working as a Desktop Support Engineer for an MSP. I hold ITIL v5, Azure and Microsoft certifications. Outside of the day job, I build websites, scripts, and software.

<br><br>

<h2><strong>Project 5kable</strong></h2>

Website = 5kable.net

Support email - support@5kable.net

### [5kable](https://5kable.net)

🌍 A geography training platform powered by AI: a Chrome extension paired with a Flask/Postgres backend, a Pro tier billed through Stripe, and a community integrated with Discord.

✋ **Chrome extension**: reads live round data, calls a backend AI pipeline (Anthropic Claude API) for scene analysis and teaching after each round, and renders Street View reference panoramas from a scene library sourced from the community.

🖥️ **Backend API** (Flask + Postgres/Supabase, deployed on Render): auth with 2FA/TOTP, Stripe Checkout for single Pro purchases, a full Discord bot integration (slash commands, role sync, reaction based verification via the Gateway, scheduled announcements), transactional email, and an admin panel for support tickets and content moderation.

🔌 **Public site**: training guides per country, a region map, leaderboards, and daily challenges, statically hosted on Cloudflare Pages.

<br><br>

<h2><strong>Repos</strong></h2>

🧰 [`5kable-site`](https://github.com/crxigzah/5kable-site): the public website (open)

✈️[`5kable-releases`](https://github.com/crxigzah/5kable-releases): packaged extension releases (open)

💼 Backend and extension source are private (it's a paid product), but I'm happy to walk through the architecture or specific code on request.

<br><br>

<h2><strong>Some things I've worked through building this</strong></h2>


👋 Diagnosed a production incident where a background Discord Gateway listener was silently starved by GIL contention with the web server's own request threads, then moved it to a standalone OS process instead of a thread.

🏆 Root caused a bug where a daily Discord bot job posted twice, by cross checking GitHub Actions logs against the database and real Discord message history, then redesigned the retry logic to tell "failed before Discord ever saw it" apart from "Discord may have already posted it."

🥇 Migrated Stripe billing from a monthly subscription to a single payment without breaking existing subscribers.

🎓 Built a system that avoids overlapping labels when rendering region maps of 190+ countries, including small territories missing from the coarse base map data.

📜 Built a scene library sourced from the community: every player's capture during gameplay adds a location that other players' training guides can reference live, with no imagery ever stored on the server.

⚙️ Added a live multi currency price display that converts a single GBP source of truth in the browser, so Stripe only ever has to know one currency.

<br><br>

<h2><strong>More coming soon.</strong></h2>
