# Free Embeddable Lead Forms — Dunefox

> **Capture unlimited leads from any website — free forever.**  
> Dunefox lead forms embed on any site via iFrame or SDK and feed submissions directly into your CRM pipeline.

## Why Dunefox Lead Forms?

- ✅ **Unlimited forms** — create as many as you need
- ✅ **Unlimited submissions** — no caps, no paywalls
- ✅ **Free forever** — no credit card required
- ✅ **Built-in CRM** — submissions auto-populate your lead pipeline
- ✅ **9 field types** — text, email, phone, dropdown, checkbox, number, date, URL, textarea
- ✅ **Embed anywhere** — iFrame or SDK, works on any website

---

## Getting Your Form ID

1. Sign up free at [app.dunefox.io](https://app.dunefox.io)
2. Go to **Lead Forms** in the console
3. Create a form and configure your fields
4. Click **Distribute** tab → copy your **Form ID**

---

## Embed via iFrame (Simplest)

Works on any website — Webflow, Shopify, Squarespace, WordPress, plain HTML:

```html
<iframe
  src="https://app.dunefox.io/f/YOUR_FORM_ID"
  width="100%"
  height="600"
  frameborder="0"
  style="border: none; border-radius: 12px;">
</iframe>
```

**Responsive iFrame (auto-height):**

```html
<iframe
  src="https://app.dunefox.io/f/YOUR_FORM_ID"
  width="100%"
  height="600"
  frameborder="0"
  style="border: none; width: 100%; max-width: 520px; display: block; margin: 0 auto;">
</iframe>
```

---

## Embed via SDK Script

For more control over placement and styling:

```html
<!-- Add the container where you want the form -->
<div data-dunefox-form="YOUR_FORM_ID"></div>

<!-- Load the SDK (once per page, before </body>) -->
<script src="https://app.dunefox.io/api/sdk/forms.js"></script>
```

---

## Direct Form Link

Share a standalone form page — no embed needed:

```
https://app.dunefox.io/f/YOUR_FORM_ID
```

Use this in:
- Email signatures
- Social media bios
- SMS campaigns
- QR codes

---

## Supported Field Types

| Field Type | Description | Special Options |
|-----------|-------------|-----------------|
| **Short Text** | Single-line input | Regex validation pattern |
| **Long Text** | Multi-line textarea | — |
| **Email** | Email input | Regex validation pattern |
| **Phone** | Phone number | Default country code (30+ countries) |
| **Dropdown** | Select from options | Custom option list |
| **Checkbox** | Boolean / agreement | — |
| **Number** | Numeric input | Min value, Max value, Integer only |
| **Date** | Date picker | — |
| **URL** | URL input | Format validation |

---

## Form Customization

All form settings are configured in your [Dunefox Forms dashboard](https://app.dunefox.io/console/forms):

| Setting | Description |
|---------|-------------|
| **Form Title** | Displayed at the top of the form |
| **Description** | Subtitle / instructions below the title |
| **Button Label** | Text on the submit button (default: "Submit") |
| **Primary Color** | Brand color for the button and accents |
| **Logo URL** | Your brand logo shown in the form header |
| **Success Message** | Message shown after successful submission |
| **CRM Sync** | Toggle to send submissions to your lead pipeline |

---

## CRM Pipeline Integration

When **CRM Sync** is enabled on a form, every submission:

1. Creates a new lead in your pipeline under **New** status
2. Captures all field values (name, email, phone, etc.)
3. Records the submission source
4. Appears in your [Leads dashboard](https://app.dunefox.io/console/leads) instantly

Pipeline stages:
```
New → Contacted → Qualified → Negotiating → Converted → Lost
```

---

## Viewing Submissions

Go to [Lead Forms](https://app.dunefox.io/console/forms) → select your form → click **Responses** tab.

Export as CSV is available from the Responses view.

---

## Security

- All submissions are **encrypted in transit** (HTTPS)
- Form data is **encrypted at rest**
- Each form displays a **"Secured & encrypted"** badge to build visitor trust

---

## Links

- 🌐 [Create a free form](https://app.dunefox.io/console/forms)
- 🎯 [View your leads](https://app.dunefox.io/console/leads)
- 🏠 [dunefox.io](https://dunefox.io)

---

← [Back to main README](../README.md)
