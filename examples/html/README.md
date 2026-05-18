# Add AI Chatbot to Any HTML Website — Dunefox SDK Guide

> **Add a free AI chatbot to any website with one script tag.**  
> Works on plain HTML sites, Webflow, Shopify, Squarespace, Wix, and any platform that lets you add custom code.

## Prerequisites

- Any website where you can add custom HTML/JavaScript
- A free [Dunefox account](https://app.dunefox.io) — get your **Tenant ID** from the Deploy page

---

## Universal Embed (Any HTML Page)

Paste this before the closing `</body>` tag on your page:

```html
<!-- Dunefox AI Chatbot — add before </body> -->
<script src="https://app.dunefox.io/api/sdk/chatbot.js"></script>
<script>
  DunefoxChat.init({
    tenantId: 'YOUR_TENANT_ID'
  });
</script>
```

---

## Platform-Specific Instructions

### Webflow

1. Go to **Project Settings → Custom Code**
2. Paste the snippet in the **Footer Code** section
3. Publish your site

### Shopify

1. Go to **Online Store → Themes → Edit Code**
2. Open `theme.liquid`
3. Paste the snippet before `</body>`
4. Save

### Squarespace

1. Go to **Settings → Advanced → Code Injection**
2. Paste the snippet in the **Footer** field
3. Save

### Wix

1. Go to **Settings → Custom Code**
2. Click **+ Add Custom Code**
3. Paste the snippet, set placement to **Body - end**
4. Apply to **All Pages**

### WordPress (via plugin)

Use the [WPCode plugin](https://wpcode.com/) (free):
1. Install WPCode
2. Go to **Code Snippets → + Add Snippet → HTML Snippet**
3. Paste the snippet, set location to **Footer**
4. Save and activate

---

## Customization Options

```html
<script>
  DunefoxChat.init({
    tenantId: 'YOUR_TENANT_ID',
    position: 'bottom-left',  // bottom-right | bottom-left | top-right | top-left
    offsetX: 24,               // horizontal offset in pixels (0–120)
    offsetY: 16,               // vertical offset in pixels (0–120)
  });
</script>
```

---

## Links

- 🌐 [Dunefox Dashboard](https://app.dunefox.io)
- 🚀 [Deploy & Get Tenant ID](https://app.dunefox.io/console/deploy)
- 🏠 [dunefox.io](https://dunefox.io)

---

← [Back to main README](../../README.md)
