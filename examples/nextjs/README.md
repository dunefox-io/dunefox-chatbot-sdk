# Add AI Chatbot to Next.js — Dunefox SDK Guide

> **Install a free AI chatbot on your Next.js app in under 2 minutes.**  
> Supports Next.js 13+ App Router and Pages Router. Works alongside Server Components.

## Prerequisites

- Next.js 13+ (App Router recommended)
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

## App Router Setup (Next.js 13+)

### Step 1 — Create a Client Component wrapper

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
```

### Step 2 — Add to your Root Layout

```tsx
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

The chatbot will now appear on every page of your Next.js app.

---

## Pages Router Setup (Next.js 12 and below)

```tsx
// pages/_app.tsx
import type { AppProps } from 'next/app';
import { DunefoxChatbot } from 'dunefox-chatbot/react';

export default function App({ Component, pageProps }: AppProps) {
  return (
    <>
      <Component {...pageProps} />
      <DunefoxChatbot tenantId="YOUR_TENANT_ID" />
    </>
  );
}
```

---

## Customization Options

```tsx
<DunefoxChatbot
  tenantId="YOUR_TENANT_ID"
  position="bottom-left"   // bottom-right | bottom-left | top-right | top-left
  offsetX={24}              // horizontal offset in pixels (0–120)
  offsetY={16}              // vertical offset in pixels (0–120)
/>
```

---

## Links

- 🌐 [Dunefox Dashboard](https://app.dunefox.io)
- 🚀 [Deploy & Get Tenant ID](https://app.dunefox.io/console/deploy)
- 📦 [npm package](https://www.npmjs.com/package/dunefox-chatbot)
- 🏠 [dunefox.io](https://dunefox.io)

---

← [Back to main README](../../README.md)
