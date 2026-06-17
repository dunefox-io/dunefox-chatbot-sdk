# Changelog

All notable changes to the Dunefox Chatbot SDK are documented here.

---

## [1.0.9] — 2026-06-18

### Added

- **`configId` option** — new optional parameter for `DunefoxChat.init()` and `<DunefoxChatbot />` that links a widget embed to a specific `WebbotBusinessConfig` record.  
  `configId` is appended to the iframe `src` as `?configId=<id>` and propagated through the socket → MongoDB conversation at creation time.
- **Multi-webbot (multi-site) support** — accounts can now have multiple webbots (one per site/domain). Plan limits enforced server-side:
  | Plan | Webbots allowed |
  |------|----------------|
  | Free | 3 |
  | Fox | 3 |
  | Fox Pro | 5 |
  | Fox Max | 10 |
- **Inbox source label** — webbot conversations now store `webbotSource` (snapshot of `websiteUrl` / `botName` at creation time). The Inbox chat header displays a domain pill (e.g. `help.yourdomain.com`) for agents to see which site each message came from at a glance.
- **Inline CDN bundle (`chatbot.js`) updated** — the inline fallback bundle now reads and forwards `configId` to match the npm package behaviour.

### Changed

- `DunefoxChatOptions` TypeScript interface extended with `configId?: string`.
- README updated with Multi-Site guide, plan limits table, full API reference table, and backwards-compatibility table.

### Backwards Compatible

Existing embeds without `configId` continue to work exactly as before. No breaking changes.

---

## [1.0.0] — 2025-05-01

### Added
- Initial release of `dunefox-chatbot` npm package
- React component `DunefoxChatbot` for Next.js and React apps
- Vanilla JS `DunefoxChat.init()` for HTML, WordPress, Webflow, Shopify
- Vue 3 / Nuxt 3 support via dynamic import
- Position configuration: `bottom-right`, `bottom-left`, `top-right`, `top-left`
- Pixel offset customization: `offsetX`, `offsetY`
- Integration guides for Next.js, React, Vue, HTML, WordPress
- Lead forms embed: iFrame + SDK embed support
- Free embeddable lead forms with 9 field types
- WhatsApp Business inbox integration
- CRM lead pipeline (New → Contacted → Qualified → Negotiating → Converted)
- Omnichannel inbox: WhatsApp, Telegram, Web Chatbot, Facebook, Instagram

---

For the latest updates, visit [dunefox.io](https://dunefox.io).
