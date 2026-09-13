# Digipacket RePublish AI

WordPress plugin that automatically rewrites your new posts with Google Gemini AI (free tier), then publishes them to a second WordPress site through the REST API — **keeping every image untouched**.

[![Version](https://img.shields.io/badge/version-1.1.2-2271b1)](https://github.com/digipacket-net/digipacket-republish-ai/releases/latest)
[![WordPress](https://img.shields.io/badge/WordPress-5.8%2B-21759b)](https://wordpress.org/)
[![PHP](https://img.shields.io/badge/PHP-7.4%2B-777bb4)](https://www.php.net/)
[![License](https://img.shields.io/badge/license-GPL--2.0--or--later-green)](LICENSE)

---

## 📥 Download

**[⬇️ Download the latest version](https://github.com/digipacket-net/digipacket-republish-ai/releases/latest/download/digipacket-republish-ai.zip)**

---

## 🚀 Installation

### Option 1 — Over SSH (recommended)

Connect to your server, then run:

```bash
cd /path/to/wordpress/wp-content/plugins

wget https://github.com/digipacket-net/digipacket-republish-ai/releases/latest/download/digipacket-republish-ai.zip

unzip -o digipacket-republish-ai.zip
rm digipacket-republish-ai.zip
```

Then activate the plugin from **Plugins** in your WordPress admin.

> If `wget` is unavailable, use `curl -L -O <url>` instead.

### Option 2 — Over SSH with WP-CLI

A single command, activation included:

```bash
wp plugin install https://github.com/digipacket-net/digipacket-republish-ai/releases/latest/download/digipacket-republish-ai.zip --activate
```

### Option 3 — From the WordPress admin

1. Download the `.zip` file using the link above.
2. Go to **Plugins → Add New → Upload Plugin**.
3. Select the `.zip` file → **Install Now** → **Activate**.

### Updating

Run the same command again: `unzip -o` overwrites the old files. Your settings and activity log are preserved.

---

## ⚙️ Setup in 5 minutes

This plugin is installed on **both sites**.

### On SITE B (destination) — do this first

1. **RePublish AI → Receiver mode** → tick **"This site is a destination site"** → Save.
2. **Users → Profile → Application Passwords**: create a password named `Digipacket RePublish`, then copy it.

> Site B must run on **HTTPS**, otherwise WordPress hides application passwords.

### On SITE A (source)

1. Get a free Gemini API key from **[Google AI Studio](https://aistudio.google.com/app/apikey)**.
2. **RePublish AI → Artificial intelligence**: paste the key → Save → **Test Google Gemini**.
3. **RePublish AI → Site B (destination)**: URL, username and application password → Save → **Test site B**.
4. Start with **Status on site B: Draft** while you review the quality of the rewrites.

---

## ✨ Features

- **Automatic detection** of every newly published post.
- **AI rewriting**: new title, new introduction, reworded body, SEO metadata and tags.
- **Images guaranteed intact** — extracted and replaced with placeholders before reaching the AI, then reinserted verbatim. The AI never sees their markup, so it cannot alter or lose them.
- **Asynchronous processing**: publishing is never slowed down.
- **Automatic retries** that honour the exact delay returned by Google when a quota is reached.
- **Categories preserved** from the source site, created automatically when missing.
- **Multilingual**: the original language and script are preserved (Arabic, French, …), including the URL slug. Can also translate.
- **SEO**: works with Yoast SEO, Rank Math, All in One SEO and SEOPress.
- **Loop and duplicate protection**: a received post never travels back, and an already-sent post is updated rather than duplicated.
- **Full activity log** for every step, with timings and exact error messages.

---

## 📋 Requirements

| | |
|---|---|
| WordPress | 5.8 or higher |
| PHP | 7.4 or higher |
| Site B | HTTPS, REST API reachable (`/wp-json/`) |
| Site B account | Editor or Administrator role |
| API key | Google Gemini — [free tier](https://aistudio.google.com/app/apikey) |

---

## 🌍 Interface language

The admin interface is in **English**, and a complete **French (`fr_FR`)** translation ships with the plugin.
WordPress picks one automatically from your site locale — no setting to change.

Translators can start from `languages/digipacket-republish-ai.pot` inside the plugin folder
(text domain `digipacket-republish-ai`).

---

## 🆘 Support

Questions or problems: **[digipacket.net/contact](https://digipacket.net/contact)**

Please include the relevant lines from the **Log** tab — they carry the HTTP status code and the exact error message, which makes diagnosis immediate.

---

## 📄 License

GPL-2.0-or-later — © [Digipacket](https://digipacket.net)
