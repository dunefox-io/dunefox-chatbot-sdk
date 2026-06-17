# Add AI Chatbot to WordPress — Dunefox SDK Guide

> **Install a free AI chatbot on your WordPress site in under 2 minutes.**  
> No plugin required — works with any WordPress theme.

## Prerequisites

- WordPress 5.0+
- A free [Dunefox account](https://app.dunefox.io) — get your **Tenant ID** from the Deploy page

---

## Method 1 — functions.php (Recommended for developers)

Add this to your **child theme's `functions.php`**:

```php
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

> ⚠️ Always add to your **child theme**, never the parent theme — parent theme updates will overwrite your changes.

---

## Method 2 — WPCode Plugin (No coding required)

1. Install the free [WPCode plugin](https://wordpress.org/plugins/insert-headers-and-footers/) from the WordPress plugin directory
2. Go to **Code Snippets → + Add Snippet**
3. Choose **HTML Snippet**
4. Paste the following:

```html
<script src="https://app.dunefox.io/api/sdk/chatbot.js"></script>
<script>
  DunefoxChat.init({
    tenantId: 'YOUR_TENANT_ID',
    position: 'bottom-right'
  });
</script>
```

5. Set **Location** to `Footer` → **Save** → **Activate**

---

## Method 3 — WordPress Customizer

1. Go to **Appearance → Customize → Additional CSS** (for CSS only) or use a theme that supports custom footer scripts
2. Most themes support **Theme Options → Footer Scripts** or similar

---

## Customization Options

```js
DunefoxChat.init({
  tenantId: 'YOUR_TENANT_ID',
  position: 'bottom-left',  // bottom-right | bottom-left | top-right | top-left
  offsetX: 24,               // horizontal offset in pixels (0–120)
  offsetY: 16,               // vertical offset in pixels (0–120)
});
```

---

## WooCommerce

The chatbot works automatically on WooCommerce stores — it will appear on product pages, cart, checkout, and all other pages since it's loaded globally via the footer hook.

---

## 🌐 Multiple Webbots — Separate Chatbot per Site

If you run more than one WordPress site (e.g. a main store and a help site), you can deploy a **separate webbot for each domain**. All conversations arrive in a single Dunefox inbox, each tagged with the source domain so your agents always know which site a visitor messaged from.

### How to set up

1. Go to **Console → Services → Web AI Agent** and click **"Add New Web AI Agent"** for each site.
2. Copy the **Config ID** from each webbot's **Deploy / Edit** page.
3. Add `configId` to the snippet on each site.

### Example — two WordPress sites

**Main site (`yourdomain.com`) — `functions.php`:**

```php
add_action('wp_footer', function() {
?>
<script src="https://app.dunefox.io/api/sdk/chatbot.js"></script>
<script>
  DunefoxChat.init({
    tenantId: 'YOUR_TENANT_ID',
    configId: 'CONFIG_ID_FOR_MAIN_SITE',  // from Console → Web AI Agent → Deploy
    position: 'bottom-right'
  });
</script>
<?php
});
```

**Help / subdomain site (`help.yourdomain.com`) — `functions.php`:**

```php
add_action('wp_footer', function() {
?>
<script src="https://app.dunefox.io/api/sdk/chatbot.js"></script>
<script>
  DunefoxChat.init({
    tenantId: 'YOUR_TENANT_ID',
    configId: 'CONFIG_ID_FOR_HELP_SITE',  // different config, same inbox
    position: 'bottom-right'
  });
</script>
<?php
});
```

In your Dunefox Inbox each conversation will display a domain pill (e.g. `help.yourdomain.com`) in the chat header.

> **`configId` is optional.** Single-site installs work exactly as before with no changes needed.

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
