# Dunefox Chatbot SDK — Add AI Chatbot to Any Website for Free

[![npm version](https://img.shields.io/npm/v/dunefox-chatbot.svg?style=flat-square)](https://www.npmjs.com/package/dunefox-chatbot)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)](LICENSE)
[![Website](https://img.shields.io/badge/Website-dunefox.io-orange?style=flat-square)](https://dunefox.io)
[![Free Forever](https://img.shields.io/badge/Free%20Plan-Forever-green?style=flat-square)](https://app.dunefox.io)

> **The easiest way to add an AI chatbot + free lead capture forms to your website — no credit card required.**  
> Works with **Next.js, React, Vue, Nuxt, plain HTML, WordPress, Webflow, Shopify, Squarespace** and more.

---

## ✨ Features

- 🤖 **AI-powered web chatbot** — deploy a fully functional chatbot widget in under 2 minutes
- 📋 **Unlimited free lead forms** — capture leads directly into your CRM, forever free
- 💬 **WhatsApp Business integration** — two-way messaging, templates & bulk campaigns
- 📣 **Omnichannel inbox** — WhatsApp, Telegram, Web Chatbot, Facebook Messenger, Instagram
- 📊 **Built-in CRM & lead pipeline** — New → Contacted → Qualified → Negotiating → Converted
- 📂 **Knowledge base** — train your bot with documents, URLs, and FAQs
- 🎯 **Contact management** — groups, tags, and smart filters
- 📈 **Analytics dashboard** — support metrics, agent performance, campaign reports
- 🎟️ **Cases / ticket management** — track and resolve customer issues
- 👥 **Multi-agent team management** — assign conversations to agents
- 🌐 **Works everywhere** — any framework, any CMS, any website builder

---

## 🚀 Quick Start — Add Chatbot to Your Website

### 1. Install via npm

```bash
npm install dunefox-chatbot
```

### 2. Get your free Tenant ID

Sign up free at [app.dunefox.io](https://app.dunefox.io) → Go to **Deploy** → Copy your **Tenant ID**.

> No credit card required. Free plan includes 1 chatbot + unlimited lead forms.

### 3. Embed (pick your framework below)

---

## 📦 Integration Guides

### ⚛️ Next.js (App Router)

```tsx
// components/Chatbot.tsx
'use client';
import { DunefoxChatbot } from 'dunefox-chatbot/react';

export default function Chatbot() {
  return (
    <DunefoxChatbot
      tenantId="YOUR_TENANT_ID"
      position="bottom-right"
    />
  );
}

// app/layout.tsx
import Chatbot from '@/components/Chatbot';

export default function RootLayout({ children }: { children: React.ReactNode }) {
  return (
    <html lang="en">
      <body>
        {children}
        <Chatbot />
      </body>
    </html>
  );
}
```

> ✅ Works perfectly alongside Server Components. Wrap in a `'use client'` component.

[→ Full Next.js guide](./examples/nextjs/README.md)

---

### ⚛️ React (Vite / CRA)

```tsx
// src/App.tsx
import { DunefoxChatbot } from 'dunefox-chatbot/react';

export default function App() {
  return (
    <>
      <YourApp />
      <DunefoxChatbot
        tenantId="YOUR_TENANT_ID"
        position="bottom-right"
      />
    </>
  );
}
```

> ✅ Works with any React 18+ project.

[→ Full React guide](./examples/react/README.md)

---

### 🌐 Plain HTML — Universal (Webflow, Shopify, Squarespace)

```html
<!-- Paste before </body> on any HTML page -->
<script src="https://app.dunefox.io/api/sdk/chatbot.js"></script>
<script>
  DunefoxChat.init({
    tenantId: 'YOUR_TENANT_ID',
    position: 'bottom-right'
  });
</script>
```

> ✅ One CDN script tag — works on Webflow, Shopify, Squarespace, or any HTML page.

[→ Full HTML / Webflow / Shopify guide](./examples/html/README.md)

---

### 💚 Vue 3 / Nuxt

```vue
<!-- App.vue -->
<script setup lang="ts">
import { onMounted, onBeforeUnmount } from 'vue';

onMounted(async () => {
  const { init } = await import('dunefox-chatbot');
  init({ tenantId: 'YOUR_TENANT_ID', position: 'bottom-right' });
});

onBeforeUnmount(async () => {
  const { destroy } = await import('dunefox-chatbot');
  destroy();
});
</script>

<template>
  <RouterView />
</template>
```

> ✅ Dynamic import keeps it SSR-compatible. Works with Vue 3 and Nuxt 3.

[→ Full Vue / Nuxt guide](./examples/vue/README.md)

---

### 🔵 WordPress

```php
// Add to child theme's functions.php
add_action('wp_footer', function() {
?>
<script src="https://app.dunefox.io/api/sdk/chatbot.js"></script>
<script>
  DunefoxChat.init({
    tenantId: 'YOUR_TENANT_ID',
    position: 'bottom-right'
  });
</script>
<?php
});
```

> ✅ Or use the [WPCode plugin](https://wpcode.com/) to add snippets without editing files.

[→ Full WordPress guide](./examples/wordpress/README.md)

---

## 🎛️ Chatbot Widget Customization

Position the chatbot widget anywhere on the page and fine-tune the offset:

| Option | Type | Values | Default |
|--------|------|--------|---------|
| `position` | `string` | `bottom-right` · `bottom-left` · `top-right` · `top-left` | `bottom-right` |
| `offsetX` | `number` | `0–120` (px inward from edge) | `0` |
| `offsetY` | `number` | `0–120` (px inward from edge) | `0` |

**Example with all options:**

```js
DunefoxChat.init({
  tenantId: 'YOUR_TENANT_ID',
  position: 'bottom-left',
  offsetX: 24,
  offsetY: 16,
});
```

> 💡 Use the visual position picker inside your [Dunefox Deploy dashboard](https://app.dunefox.io/console/deploy) to preview placement before grabbing the code.

---

## 📋 Free Embeddable Lead Forms — Unlimited, Forever

Dunefox lead forms capture submissions directly into your CRM pipeline — **no limit on forms or submissions**, forever free.

### Embed via SDK Script (Recommended)

Auto-resizes, no iframe borders, works everywhere:

```html
<div data-form-id="YOUR_FORM_ID"></div>
<script
  src="https://app.dunefox.io/api/sdk/form.js"
  data-form-id="YOUR_FORM_ID"
></script>
```

### Embed via iFrame (Advanced)

For strict CSP environments or manual height control:

```html
<iframe
  id="df-form-YOUR_FORM_ID"
  src="https://app.dunefox.io/f/YOUR_FORM_ID?embed=1"
  width="100%"
  height="600"
  frameborder="0"
  style="border:none;border-radius:12px;">
</iframe>
```

### Supported Field Types

| Field | Description |
|-------|-------------|
| **Short Text** | Single-line text input |
| **Long Text** | Multi-line textarea |
| **Email** | Email with validation + optional regex pattern |
| **Phone** | Phone number with country code selector (30+ countries) |
| **Dropdown** | Select from custom options |
| **Checkbox** | Agreement / boolean toggle |
| **Number** | Numeric with min/max constraints + integer-only mode |
| **Date** | Date picker |
| **URL** | URL field with format validation |

### Form Features

- 🎨 **Custom brand color** — match your website's primary color
- 🖼️ **Custom logo** — add your brand logo to the form header
- 🔗 **CRM sync** — submissions auto-appear in your lead pipeline
- ✅ **Custom success message** — configure post-submit experience
- 🔒 **Encrypted submissions** — all data secured in transit and at rest
- 📊 **Submission analytics** — track response counts per form

[→ Full Lead Forms guide](./lead-forms/README.md)

---

## 💬 WhatsApp Business Integration

Connect your WhatsApp Business account to power:

- ✅ **Team inbox** — all WhatsApp messages in one shared dashboard
- ✅ **Bulk campaigns** — send template messages to contact lists
- ✅ **Message templates** — create and manage approved templates
- ✅ **Two-way messaging** — reply to customers in real time
- ✅ **Auto-webhook configuration** — no manual URL/token setup needed
- ✅ **Campaign analytics** — delivery, read, and reply rates

[→ Set up WhatsApp](https://app.dunefox.io/console/services/whatsapp)

---

## 📥 Omnichannel Inbox

Manage all customer conversations from one unified inbox:

| Channel | Status |
|---------|--------|
| 💬 Web Chatbot | ✅ Live |
| 📱 WhatsApp Business | ✅ Live |
| ✈️ Telegram | ✅ Live |
| 📘 Facebook Messenger | ✅ Live |
| 📸 Instagram DMs | ✅ Live |
| 📧 Email | 🔜 Coming soon |
| 📞 Voice | 🔜 Coming soon |

---

## 🎯 Built-in CRM & Lead Pipeline

Every lead form submission automatically flows into your CRM:

```
New → Contacted → Qualified → Negotiating → Converted → Lost
```

- Filter leads by status, source, or tag
- Assign leads to team agents
- Add notes and track activity timeline

---

## 🔗 Links

| Resource | URL |
|----------|-----|
| 🌐 **Dashboard** | [app.dunefox.io](https://app.dunefox.io) |
| 🏠 **Website** | [dunefox.io](https://dunefox.io) |
| 📦 **npm package** | [npmjs.com/package/dunefox-chatbot](https://www.npmjs.com/package/dunefox-chatbot) |
| 💬 **WhatsApp Setup** | [app.dunefox.io/console/services/whatsapp](https://app.dunefox.io/console/services/whatsapp) |
| 📋 **Lead Forms** | [app.dunefox.io/console/forms](https://app.dunefox.io/console/forms) |
| 🚀 **Deploy Chatbot** | [app.dunefox.io/console/deploy](https://app.dunefox.io/console/deploy) |

---

## ⚖️ License

The **SDK and embed code** in this repository are licensed under the [MIT License](LICENSE).

> The Dunefox platform, API, and backend infrastructure are proprietary.  
> This repository contains only the client-side SDK, embed snippets, and integration examples.

---

## 🤝 Contributing

Found a bug in the embed code or want to add an example for another framework?  
Open an issue or pull request — contributions are welcome!

---

<p align="center">
  Built by <a href="https://dunefox.io">Dunefox</a> — Free AI Chatbot & Lead Generation Platform
</p>
