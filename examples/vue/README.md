# Add AI Chatbot to Vue 3 / Nuxt — Dunefox SDK Guide

> **Install a free AI chatbot on your Vue or Nuxt app in under 2 minutes.**  
> SSR-compatible via dynamic import. Works with Vue 3 and Nuxt 3.

## Prerequisites

- Vue 3 or Nuxt 3
- A free [Dunefox account](https://app.dunefox.io) — get your **Tenant ID** from the Deploy page

---

## Installation

```bash
npm install dunefox-chatbot
# or
yarn add dunefox-chatbot
# or
pnpm add dunefox-chatbot
```

---

## Vue 3 Setup

### Add to App.vue

```vue
<!-- App.vue -->
<script setup lang="ts">
import { onMounted, onBeforeUnmount } from 'vue';

onMounted(async () => {
  const { init } = await import('dunefox-chatbot');
  init({
    tenantId: 'YOUR_TENANT_ID',
    position: 'bottom-right',
  });
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

> The dynamic `import()` ensures the chatbot SDK is only loaded client-side, keeping your SSR output clean.

---

## Nuxt 3 Setup

### Option 1 — Client-only plugin (recommended)

```ts
// plugins/dunefox.client.ts
export default defineNuxtPlugin(async () => {
  const { init } = await import('dunefox-chatbot');
  init({
    tenantId: 'YOUR_TENANT_ID',
    position: 'bottom-right',
  });
});
```

Nuxt automatically detects the `.client.ts` suffix and only runs this plugin in the browser.

### Option 2 — In a layout

```vue
<!-- layouts/default.vue -->
<script setup lang="ts">
import { onMounted } from 'vue';

onMounted(async () => {
  const { init } = await import('dunefox-chatbot');
  init({ tenantId: 'YOUR_TENANT_ID' });
});
</script>

<template>
  <slot />
</template>
```

---

## Customization Options

```ts
init({
  tenantId: 'YOUR_TENANT_ID',
  position: 'bottom-left',  // bottom-right | bottom-left | top-right | top-left
  offsetX: 24,               // horizontal offset in pixels (0–120)
  offsetY: 16,               // vertical offset in pixels (0–120)
});
```

---

## 🌐 Multiple Webbots — Multi-Site Support

If you deploy to multiple domains or maintain separate Vue/Nuxt apps per site, you can link each embed to its own webbot config. All conversations land in a single Dunefox inbox, each tagged with a domain pill so agents know which site the message came from.

### How to set up

1. Go to **Console → Services → Web AI Agent** and click **"Add New Web AI Agent"** for each site.
2. Copy the **Config ID** from each webbot's **Deploy / Edit** page.
3. Pass `configId` in the `init()` call.

### Vue 3 example

```vue
<!-- App.vue -->
<script setup lang="ts">
import { onMounted, onBeforeUnmount } from 'vue';

onMounted(async () => {
  const { init } = await import('dunefox-chatbot');
  init({
    tenantId: 'YOUR_TENANT_ID',
    configId: 'CONFIG_ID_FOR_THIS_SITE',  // from Console → Web AI Agent → Deploy
    position: 'bottom-right',
  });
});

onBeforeUnmount(async () => {
  const { destroy } = await import('dunefox-chatbot');
  destroy();
});
</script>
```

### Nuxt 3 example — with runtime config

```ts
// plugins/dunefox.client.ts
export default defineNuxtPlugin(async () => {
  const config = useRuntimeConfig();
  const { init } = await import('dunefox-chatbot');
  init({
    tenantId: config.public.dunefoxTenantId,
    configId: config.public.dunefoxConfigId,  // optional
    position: 'bottom-right',
  });
});
```

```ts
// nuxt.config.ts
export default defineNuxtConfig({
  runtimeConfig: {
    public: {
      dunefoxTenantId: process.env.DUNEFOX_TENANT_ID,
      dunefoxConfigId: process.env.DUNEFOX_CONFIG_ID,  // optional
    },
  },
});
```

```env
# .env
DUNEFOX_TENANT_ID=your_tenant_id
DUNEFOX_CONFIG_ID=config_id_for_this_site
```

> **`configId` is optional.** Single-site setups work exactly as before with no changes needed.

### Plan limits

| Plan | Webbots allowed |
|------|----------------|
| Free | 3 |
| Fox | 3 |
| Fox Pro | 5 |
| Fox Max | 10 |

---

## Links

- 🌐 [Dunefox Dashboard](https://app.dunefox.io)
- 🤖 [Web AI Agent — Console](https://app.dunefox.io/console/services/webbot)
- 🚀 [Deploy & Get Tenant ID](https://app.dunefox.io/console/deploy)
- 📦 [npm package](https://www.npmjs.com/package/dunefox-chatbot)
- 🏠 [dunefox.io](https://dunefox.io)

---

← [Back to main README](../../README.md)
