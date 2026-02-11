# 📊 Tracking Setup Guide

## How to Track Visitors

Your Valentine's website now has advanced tracking that captures:
- ✅ **IP Address**
- ✅ **Location** (City, Region, Country)
- ✅ **Coordinates** (Latitude/Longitude)
- ✅ **Timezone**
- ✅ **ISP/Organization**
- ✅ **Device Info** (Screen size, User agent)
- ✅ **Time** (When they opened it)
- ✅ **Answer** (If they clicked YES)

## Setup Options

### Option 1: Webhook.site (Easiest - Real-time)

1. Go to https://webhook.site
2. You'll get a unique URL like: `https://webhook.site/your-unique-id`
3. Open [index.html](index.html) and replace `YOUR_WEBHOOK_URL_HERE` with your webhook URL (appears twice in the file)
4. Every visit/click will be sent to webhook.site where you can view it in real-time!

**Example:**
```javascript
const webhookUrl = 'https://webhook.site/abc123-your-id-here';
```

### Option 2: Google Forms (Free & Stores Data)

1. Create a Google Form at https://forms.google.com
2. Add fields for: timestamp, ip, city, country, answer
3. Get the form's pre-filled link
4. Use a service like https://script.google.com to create a webhook
5. Replace `YOUR_WEBHOOK_URL_HERE` with your Google Apps Script webhook

### Option 3: Discord Webhook (Get notifications)

1. Go to your Discord server → Server Settings → Integrations → Webhooks
2. Create a new webhook
3. Copy the webhook URL
4. You'll get Discord notifications every time someone visits!

### Option 4: Browser Console (Basic - No setup needed)

Already working! Just:
1. Open your browser's Developer Tools (F12)
2. Go to Console tab
3. You'll see all tracking data logged when someone visits

## Viewing Tracked Data

### Method 1: Check Console Logs
When YOU open the site, press `F12` and go to Console to see example data.

### Method 2: After Setup
Once webhook is configured, all visits are automatically sent to your chosen service.

### Method 3: LocalStorage (Browser)
Data is saved in the visitor's browser. To view:
1. Press F12 → Console
2. Type: `JSON.parse(localStorage.getItem('valentineVisits'))`
3. See all visits from that device

## What You'll See

Example tracking data:
```json
{
  "timestamp": "2026-02-14T10:30:00.000Z",
  "localTime": "2/14/2026, 10:30:00 AM",
  "ip": "102.xxx.xxx.xxx",
  "city": "Harare",
  "region": "Harare Province",
  "country": "Zimbabwe",
  "countryCode": "ZW",
  "latitude": -17.8292,
  "longitude": 31.0522,
  "timezone": "Africa/Harare",
  "isp": "Liquid Telecom",
  "userAgent": "Mozilla/5.0 (iPhone; CPU iPhone OS...)",
  "screenSize": "390x844",
  "language": "en-US",
  "referrer": "Direct visit",
  "answer": "YES"
}
```

## Quick Start (Recommended)

1. Visit https://webhook.site
2. Copy your unique URL
3. Edit `index.html` and replace `YOUR_WEBHOOK_URL_HERE` (line ~207 and ~229)
4. Commit and push to GitHub
5. When she opens the site, check webhook.site to see her location!

## Privacy Note

The tracking uses ipapi.co which has a free tier of 1,000 requests/day - perfect for this use case!

---

Need help? The tracking data is automatically logged to the browser console for testing.
