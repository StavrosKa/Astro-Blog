---
title: "How to Set Up a Free Professional Email with Cloudflare (No Paid Tools Required)"
description: "Step-by-step guide on how to create a free professional email like hello@yourdomain.com using Cloudflare Email Routing and Gmail. No hosting costs required."
pubDate: 2026-07-02
tags: ["cloudflare", "email", "dns", "astro", "web-development"]
---

## 📬 How to Set Up a Free Professional Email with Cloudflare (No Paid Tools Required)

If you own a website, at some point you’ll want a professional email like:

```
hello@yourdomain.com
```

Instead of using a personal Gmail address.

Most people think this requires paid services like Google Workspace or Zoho Mail.

It doesn’t.

You can set up a **fully working professional email for free using Cloudflare Email Routing**.

This is exactly how I set it up for my own site: `stavroskarelis.com`.

---

## 🧠 What we are building

We are creating a simple email flow:

```
hello@yourdomain.com
        ↓
Cloudflare Email Routing
        ↓
Your Gmail inbox
```

You will receive emails inside Gmail, but they will be sent to your domain address.

---

## ⚙️ Step 1: Move DNS to Cloudflare

Before anything, your domain must use Cloudflare DNS.

### Steps:
- Add your domain to Cloudflare
- Change nameservers at your registrar (e.g. Porkbun, Namecheap)
- Wait until Cloudflare status becomes **Active**

This step is required for Email Routing to work.

---

## 📧 Step 2: Enable Cloudflare Email Routing

Go to:

```
Cloudflare Dashboard → Email → Email Routing
```

Click:

```
Enable Email Routing
```

Cloudflare will automatically configure:

- MX records
- SPF records
- DKIM records

No manual DNS setup required.

---

## 📬 Step 3: Add your destination email (Gmail)

This is where emails will be delivered.

Add your Gmail address:

```
yourname@gmail.com
```

Then verify it via the confirmation email from Cloudflare.

---

## 🔁 Step 4: Create your custom email address

Now create your professional email:

```
hello@yourdomain.com → your Gmail
```

You can create multiple aliases if needed:

- contact@yourdomain.com
- hi@yourdomain.com
- support@yourdomain.com

All of them forward to Gmail.

---

## 🧪 Step 5: Test your setup

Send an email from another account to:

```
hello@yourdomain.com
```

If everything is correct, it will appear in your Gmail inbox instantly.

---

## ✉️ Bonus: Send emails from Gmail as your domain

This step makes the setup fully professional.

Inside Gmail:

```
Settings → Accounts → Send mail as → Add another email
```

Use SMTP settings:

```
SMTP Server: smtp.gmail.com
Port: 587
Username: your Gmail address
Password: Gmail App Password
TLS: ON
```

After verification, you can send emails as:

```
hello@yourdomain.com
```

---

## 🚀 Why this setup is powerful

This setup gives you:

 Free professional email
 No paid subscriptions
 Gmail interface (no learning curve)
 Full domain branding
 Fast setup (15–20 minutes)

---

## ⚡ Final thoughts

A custom email makes a website feel complete.

It’s a small change that adds a huge amount of credibility to your project or personal brand.

If you run a blog, portfolio, or SaaS — you should try it.

It takes less time than you think, and the impact is immediate.

---