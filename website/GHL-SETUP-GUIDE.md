# Jenk. Website → GHL Deployment Guide

## Overview
Your website is a single HTML file. GHL supports full custom code injection, so we paste the whole thing into a funnel page.

---

## Step-by-Step

### 1. Go to Sites → Funnels
- Open GHL → Jenk Marketing sub-account
- Left sidebar → **Sites** → **Funnels**

### 2. Create New Funnel
- Click **"+ New Funnel"**
- Select **"Create New Funnel"** (not from template)
- Name it: **"Jenk Website"**
- Click **Create**

### 3. Add a Page
- Click **"+ Add New Step"**
- Name: **"Home"**
- Path: **"/"** (or leave as default)
- Click **Save**

### 4. Open the Page Editor
- Click the **"Home"** step to open the drag-and-drop editor
- You'll see a blank page

### 5. Delete Everything on the Page
- Remove any default sections/rows that GHL adds
- You want a completely empty canvas

### 6. Add Custom Code Element
- Click **"+ Add Element"** (or drag from the left panel)
- Scroll down to **"Custom Code"** (under Advanced section)
- Drag it onto the page
- It will create a code block

### 7. Paste the Website HTML
- Click the Custom Code element
- In the settings panel, find **"Custom Code"** or **"HTML"** textarea
- Open the file: `website/index.html`
- Copy the ENTIRE contents of the file
- Paste it into the Custom Code element
- Click **Save**

### 8. Page Settings (important!)
- Click the **gear icon** (Page Settings)
- Under **"Custom CSS/JS"** → **Header Code**:
  - This should be empty — all our code is self-contained
- Under **Page Settings**:
  - Page Title: `Jenk. — Marketing Systems Built For Tradies`
  - Meta Description: `One system. Five automations. Runs while you work. Jenk. builds done-for-you marketing systems for Australian trades businesses.`
  - Favicon: upload Jenk. favicon (if you have one)

### 9. Remove GHL Default Styling
- In Page Settings → **"Custom CSS"**, paste:
```css
/* Remove GHL default padding/margins */
.hl_page-creator--content { padding: 0 !important; margin: 0 !important; }
.hl_page-creator--content > div { padding: 0 !important; }
body { margin: 0 !important; padding: 0 !important; }
```

### 10. Preview & Publish
- Click **Preview** to check it looks right
- Click **Publish** when ready

---

## Connect jenk.com.au Domain

### In GHL:
1. Go to **Settings** → **Domains**
2. Click **"Add Domain"**
3. Enter: `jenk.com.au`
4. GHL will give you a **CNAME record** to add

### In Your Domain Registrar (where you bought jenk.com.au):
1. Go to DNS settings
2. Add a **CNAME record**:
   - **Name/Host:** `@` or leave blank (for root domain)
   - **Value/Target:** the CNAME GHL gives you (usually `sites.gohighlevel.com` or similar)
3. If root domain CNAME doesn't work, add:
   - **Name:** `www`
   - **Value:** the CNAME from GHL
   - Then set up a redirect from `jenk.com.au` → `www.jenk.com.au`

### Back in GHL:
1. Go to **Sites** → **Funnels** → **Jenk Website**
2. Click the **Home** step settings
3. Under **Domain**, select `jenk.com.au`
4. SSL will auto-provision (takes 5-10 mins)

---

## After Go-Live Checklist
- [ ] Test all nav links scroll correctly
- [ ] Test mobile hamburger menu
- [ ] Test FAQ accordion
- [ ] Replace "Book a Free Call" links with your GHL calendar URL
- [ ] Replace video placeholder with Loom/YouTube embed
- [ ] Test on mobile (Chrome DevTools → device toggle)
- [ ] Check Google PageSpeed score
- [ ] Submit sitemap to Google Search Console

---

## File Location
The full website HTML is at:
```
C:\Users\SJ\Documents\Jenk 2.0\.claude\worktrees\determined-cannon\website\index.html
```
Open this file in a text editor, Select All (Ctrl+A), Copy (Ctrl+C), then paste into GHL.
