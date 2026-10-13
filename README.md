<h2><strong>Hi, I'm Craig 👋</strong></h2>

I'm an IT Engineer with 5 years of experience, currently working as a Desktop Support Engineer at an MSP. I hold ITIL v5, Microsoft 365 (MS-900) and Azure (AZ-900) certifications.

Outside of work, I like to create software, websites and tools

<br><br>

<h2><strong>Projects at a glance</strong></h2>

🌍 **[5kable](#5kable)**: an AI powered geography training platform with a Chrome extension, backend API, Stripe payments and Discord integration. A live paid product.

🎫 **[5kabled](#5kabled)**: an ITIL based ticketing platform covering incidents, requests, problems, changes, assets and SLAs, with Microsoft sign in.

🖥️ **[Wideside](#wideside)**: a free Windows 11 app that splits ultrawide monitors into snap zones, with automated builds and releases through GitHub Actions.

🍔 **[SnackHack](#snackhack)**: a browser extension that finds and automatically applies takeaway promo codes for Deliveroo, Just Eat and Uber Eats.

<br><br>

<h2><strong>Project 5kable</strong></h2>

Website - [5kable.net](https://5kable.net)

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

<h2><strong>Some things I've worked through building 5kable</strong></h2>


👋 Diagnosed a production incident where a background Discord Gateway listener was silently starved by GIL contention with the web server's own request threads, then moved it to a standalone OS process instead of a thread.

🏆 Root caused a bug where a daily Discord bot job posted twice, by cross checking GitHub Actions logs against the database and real Discord message history, then redesigned the retry logic to tell "failed before Discord ever saw it" apart from "Discord may have already posted it."

🥇 Migrated Stripe billing from a monthly subscription to a single payment without breaking existing subscribers.

🎓 Built a system that avoids overlapping labels when rendering region maps of 190+ countries, including small territories missing from the coarse base map data.

📜 Built a scene library sourced from the community: every player's capture during gameplay adds a location that other players' training guides can reference live, with no imagery ever stored on the server.

⚙️ Added a live multi currency price display that converts a single GBP source of truth in the browser, so Stripe only ever has to know one currency.

<br><br>

<h2><strong>Project 5kabled</strong></h2>

### 5kabled

🎫 A multi tenant IT service desk built around ITIL.

🧩 **Features**: incidents and service requests, problem management, change management with CAB approval, a service catalogue with approvals, asset tracking, business hours SLAs, CSAT surveys, routing rules, a self service portal and knowledge base, and email in and out.

⚙️ **Stack**: Next.js on Vercel with a Supabase (Postgres) backend hosted in the EU. Pricing tiers benchmarked against Freshservice and Halo.

<br><br>

<h2><strong>Project Wideside</strong></h2>

Website - [crxigzah.github.io/wideside](https://crxigzah.github.io/wideside/)

### [Wideside](https://crxigzah.github.io/wideside/)

🖥️ A free Windows tray app that splits ultrawide and large monitors into window zones, in the style of Dell Easy Arrange: drag a window and drop it into a zone, or snap it with keyboard shortcuts.

✨ **Features**: drag to snap with live zone outlines, spanning two zones by dropping on the line between them, browser tabs torn off straight into a zone, seven built in layouts plus custom ones, "arrange all windows" in one keypress, apps that reopen in their remembered zone, and a settings window with layout diagrams.

🚀 **Build and release** (AutoHotkey v2, Inno Setup, GitHub Actions): every push builds on a Windows runner, which validates the script, compiles the exe, builds the installer and a portable zip with the user guide, and publishes a GitHub release tagged from the version in the source. The app checks the GitHub Releases API and updates itself from the tray.

🧰 [`wideside`](https://github.com/crxigzah/wideside): source code, releases and website (open)

<br><br>

<h2><strong>Some things I've worked through building Wideside</strong></h2>

📐 Made zones line up pixel perfect on Windows 11 by measuring each window's invisible resize border through DWM, and running per monitor DPI aware so display scaling doesn't skew the maths.

🧲 Found why dragging a maximised window never snapped: Windows shrinks it at the start of the drag, which looked like a resize. Switched to telling moves and resizes apart by the cursor shape instead.

🌐 Made tabs torn off Chromium browsers snap into zones, even though the browser moves those windows itself and the normal Windows move events never fire.

⚡ Removed drag lag by building the zone overlay windows once per monitor and sliding a single highlight between zones instead of redrawing everything.

🛡️ Paused Windows' own Snap while the app runs without permanently changing the user's settings, so it always comes back, even if the app is force closed.

<br><br>

<h2><strong>Project SnackHack</strong></h2>

### SnackHack

🍔 A browser extension that finds takeaway promo codes for Deliveroo, Just Eat and Uber Eats and tries them for you at checkout.

🔎 **Search**: checks 13 sources per search (deal sites, Reddit and voucher sites), five at a time, including codes hidden behind "reveal code" buttons. Member only deals are included if you have Deliveroo Plus, Just Eat+ or Uber One.

🤖 **One tap try**: watches the checkout page, unlocks once the promo box is visible, tries up to 20 codes, and leaves the best one applied. Codes that worked before are tried first.

📊 **Savings history**: tracks every code's success rate and best saving, plus totals per app.

✅ Covered by 34 automated tests, including end to end runs with the real extension loaded.

🧰 [`snackhack`](https://github.com/crxigzah/snackhack): source code (open)

<br><br>

<h2><strong>More coming soon.</strong></h2>
