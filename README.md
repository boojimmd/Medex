# Medex — راهنمای انتشار روی GitHub Pages

## ساختار فایل‌ها (این چیدمان را دقیقاً حفظ کنید)
```
medex/
├── index.html       ← فایل اصلی برنامه
├── manifest.json     ← تنظیمات PWA (نام، آیکون، رنگ)
├── sw.js             ← Service Worker (کارکرد آفلاین)
└── icons/
    ├── icon-32.png
    ├── icon-48.png
    ├── icon-72.png
    ├── icon-96.png
    ├── icon-128.png
    ├── icon-144.png
    ├── icon-152.png
    ├── icon-167.png
    ├── icon-180.png
    ├── icon-192.png
    ├── icon-512.png
    ├── icon-maskable-192.png
    └── icon-maskable-512.png
```

## مرحله ۱: ساخت ریپازیتوری
1. وارد github.com شوید (همان اکانت boojimmd)
2. New repository → نام: `medex` (یا هر نام دیگری) → Public → Create

## مرحله ۲: آپلود فایل‌ها
**روش ساده (بدون نیاز به git):**
1. وارد ریپازیتوری خالی شوید → روی «uploading an existing file» کلیک کنید
2. تمام فایل‌ها و پوشه `icons/` را با همین چیدمان درگ کنید (مرورگرهای Chrome/Edge ساختار پوشه را حفظ می‌کنند)
3. Commit changes

**روش git (اگر ترمینال دارید):**
```bash
cd medex
git init
git add .
git commit -m "Initial PWA release"
git remote add origin https://github.com/boojimmd/medex.git
git branch -M main
git push -u origin main
```

## مرحله ۳: فعال‌سازی GitHub Pages
1. Settings → Pages
2. Source: Deploy from a branch
3. Branch: `main` / `(root)` → Save
4. بعد از ۱-۲ دقیقه آدرس فعال می‌شود:
   **https://boojimmd.github.io/medex/**

## مرحله ۴: نصب روی ویندوز
1. آدرس بالا را در **Chrome** یا **Edge** باز کنید
2. در نوار آدرس، آیکون نصب (⊕ یا کامپیوتر کوچک) ظاهر می‌شود
3. کلیک → Install → برنامه به صورت یک پنجره مستقل با آیکون در Start Menu نصب می‌شود

## نصب روی اندروید/آیفون
- اندروید (Chrome): منو ⋮ → «Add to Home screen»
- آیفون (Safari): دکمه Share → «Add to Home Screen»

## نکات مهم
- هر بار که `index.html` را آپدیت کردید، فقط فایل را در گیت‌هاب جایگزین کنید (commit جدید) — Service Worker خودکار نسخه جدید را می‌گیرد
- اگر بعد از آپدیت تغییرات دیده نشد، در برنامه نصب‌شده چند ثانیه صبر کنید یا یک‌بار کامل ببندید و باز کنید (SW نسخه قبلی را تا یک رفرش کامل cache می‌کند)
- `manifest.json` با مسیر نسبی (`./`) نوشته شده — روی هر زیرپوشه‌ای از GitHub Pages کار می‌کند، نیازی به تغییر نیست
