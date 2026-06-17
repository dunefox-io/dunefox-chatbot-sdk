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

## 🌐 Multiple Webbots — Embed on Multiple Sites

If you manage more than one website, you can deploy a **separate webbot per domain** — all conversations land in a single unified inbox, each tagged with which site it came from.

### How to set up

1. Go to **Console → Services → Web AI Agent** and click **"Add New Web AI Agent"** for each site.
2. Copy the **Config ID** from each webbot's **Deploy / Edit** page.
3. Pass `configId` in each site's embed snippet.

### Example — two sites

**Main site (`yourdomain.com`):**

```html
<script src="https://app.dunefox.io/api/sdk/chatbot.js"></script>
<script>
  DunefoxChat.init({
    tenantId: 'YOUR_TENANT_ID',
    configId: 'CONFIG_ID_FOR_MAIN_SITE',  // from Console → Web AI Agent → Deploy
  });
</script>
```

**Help centre (`help.yourdomain.com`):**

```html
<script src="https://app.dunefox.io/api/sdk/chatbot.js"></script>
<script>
  DunefoxChat.init({
    tenantId: 'YOUR_TENANT_ID',
    configId: 'CONFIG_ID_FOR_HELP_SITE',  // different config, same inbox
  });
</script>
```

In your Dunefox Inbox, each conversation from the help centre will show a `help.yourdomain.com` domain pill so agents immediately know the source.

> **`configId` is optional.** Omitting it still works — existing single-site embeds are completely unaffected.

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
- 🏠 [dunefox.io](https://dunefox.io)

---

← [Back to main README](../../README.md)
