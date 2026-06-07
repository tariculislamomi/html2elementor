# ⚡ HTML2Elementor — Free AI Converter

যেকোনো HTML template কে Elementor JSON-এ convert করুন, সম্পূর্ণ বিনামূল্যে।

**Live Demo:** [আপনার Vercel URL]  
**Built with:** Claude AI (Anthropic) + Vanilla JS + Vercel

---

## 🚀 Vercel-এ Deploy করার Step-by-Step নির্দেশনা

### Step 1: GitHub-এ Upload করুন

1. [github.com](https://github.com) এ যান → New Repository
2. Repository name: `html2elementor`
3. Public রাখুন → Create Repository
4. এই project folder-এর সব files upload করুন:
   ```
   html2elementor/
   ├── api/
   │   └── convert.js       ← Backend (API key এখানে সুরক্ষিত)
   ├── public/
   │   ├── index.html
   │   ├── css/style.css
   │   └── js/
   │       ├── app.js
   │       └── examples.js
   ├── vercel.json
   ├── package.json
   └── .env.example
   ```

### Step 2: Anthropic API Key নিন

1. [aistudio.google.com](https://aistudio.google.com) এ account করুন
2. **API Keys** → **Create Key**
3. Key টি copy করে রাখুন: `AIzaSy_...`
4. New account-এ $5 free credit পাবেন (শুরুর জন্য যথেষ্ট)

### Step 3: Vercel-এ Deploy করুন

1. [vercel.com](https://vercel.com) এ যান → **Sign in with GitHub**
2. **New Project** → আপনার `html2elementor` repository select করুন
3. **Import** করুন
4. Deploy করার আগে **Environment Variables** add করুন:

   | Name | Value |
   |------|-------|
   | `GEMINI_API_KEY` | `AIzaSy_আপনার-key` |

5. **Deploy** বাটনে চাপুন
6. ✅ 2-3 মিনিটে আপনার tool live হয়ে যাবে!

### Step 4: Custom Domain (ঐচ্ছিক)

Vercel Dashboard → Project → Settings → Domains → Add Domain

---

## 🔐 Security — API Key কীভাবে সুরক্ষিত?

```
❌ আগে (unsafe):
Browser → Claude API (key visible in browser)

✅ এখন (safe):
Browser → আপনার Vercel API (/api/convert) → Claude API
                    ↑
         API key শুধু server-এই থাকে
         Client কখনো key দেখতে পায় না
```

- API key শুধু Vercel-এর Environment Variables-এ থাকে
- `/api/convert.js` server-side-এ run হয়
- Browser থেকে key access করা সম্পূর্ণ অসম্ভব

---

## 📁 Project Structure

```
html2elementor/
│
├── api/
│   └── convert.js          # Vercel Serverless Function
│                           # Claude API call এখানে হয়
│                           # API key env variable থেকে নেওয়া হয়
│
├── public/                 # Static frontend files
│   ├── index.html          # Main page
│   ├── css/
│   │   └── style.css       # All styles
│   └── js/
│       ├── app.js          # Main app logic
│       └── examples.js     # Example HTML snippets
│
├── vercel.json             # Vercel routing config
├── package.json            # Dependencies
└── .env.example            # Environment variables template
```

---

## 🛠️ Local Development (Optional)

```bash
# Vercel CLI install করুন
npm install -g vercel

# Project folder-এ যান
cd html2elementor

# .env.local file তৈরি করুন
echo "GEMINI_API_KEY=AIzaSy_your-key" > .env.local

# Local server চালু করুন
vercel dev
# http://localhost:3000 এ দেখুন
```

---

## ⚡ Features

- ✅ HTML + CSS paste করুন → Elementor JSON পান
- ✅ 4টি ready example (Hero, Cards, CTA, Pricing)
- ✅ Syntax highlighted JSON output
- ✅ Widget stats breakdown
- ✅ Original HTML preview
- ✅ One-click JSON download
- ✅ Copy to clipboard
- ✅ WordPress import guide
- ✅ Elementor Free ও Pro-তে কাজ করে
- ✅ Mobile responsive

---

## 📥 WordPress-এ Import করার নিয়ম

1. WordPress → যেকোনো Page → **Edit with Elementor**
2. বাম নিচে **Folder icon** (Import Template) চাপুন
3. **My Templates** → **Import Template**
4. Download করা `.json` file upload করুন
5. **Insert** চাপুন → Done! ✅

---

## 🆓 Cost

| Component | Cost |
|-----------|------|
| Vercel Hosting | **Free** (Hobby plan) |
| Anthropic API | ~$0.003 per conversion |
| Domain (optional) | Free on vercel.app |

প্রতি conversion-এ মাত্র $0.003 খরচ হয়। $5 free credit দিয়ে প্রায় 1600+ conversion করা যাবে!

---

## 🤝 এই tool আরো improve করতে পারেন

- [ ] Rate limiting যোগ করুন (abuse থেকে বাঁচতে)
- [ ] User accounts যোগ করুন (history save)
- [ ] More widget support (tabs, accordion, slider)
- [ ] Elementor Pro widgets support
- [ ] Batch conversion (multiple sections)

---

Built with ❤️ | Powered by Claude AI
