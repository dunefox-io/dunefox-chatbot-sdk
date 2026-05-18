# Add AI Chatbot to React — Dunefox SDK Guide

> **Install a free AI chatbot on your React app in under 2 minutes.**  
> Works with React 18+, Vite, Create React App, and any React-based project.

## Prerequisites

- React 18+
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

## Setup

### Add to App.tsx (or App.jsx)

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

That's it — the chatbot widget will appear on every page of your app.

---

## Vite + React Example

```tsx
// src/main.tsx
import React from 'react';
import ReactDOM from 'react-dom/client';
import App from './App';

ReactDOM.createRoot(document.getElementById('root')!).render(
  <React.StrictMode>
    <App />
  </React.StrictMode>
);
```

```tsx
// src/App.tsx
import { DunefoxChatbot } from 'dunefox-chatbot/react';

function App() {
  return (
    <>
      {/* Your existing app routes / components */}
      <DunefoxChatbot tenantId="YOUR_TENANT_ID" />
    </>
  );
}

export default App;
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
