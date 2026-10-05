# Portfolio — Mostafa Atef

موقع بورتفوليو شخصي، صفحة واحدة ثابتة (HTML + CSS + JavaScript بدون أي مكتبات).
الملفات هنا الآن:

```
portfolio/
├── index.html          # الموقع كله في ملف واحد
├── assets/
│   ├── cv.pdf          # السيرة الذاتية (PDF) — جاهزة
│   └── cv.html         # نفس الـ CV لكن HTML — للتعديل ثم إعادة توليد الـ PDF
└── README.md
```

---

## 1) الروابط التي يجب تعديلها

افتح `index.html` وابحث عن هذه النصوص واستبدلها بروابطك الحقيقية:

| النص الموجود | استبدله بـ |
|---|---|
| `YOUR-LINKEDIN-USERNAME` | اسم المستخدم في لينكدإن |
| `YOUR-GITHUB-USERNAME` | اسم المستخدم في جيتهاب |
| `https://YOUR-APP-LINK.streamlit.app` | رابط تطبيق Car Price Predictor بعد نشره على Streamlit Cloud |

بحث سريع في VS Code: `Ctrl + Shift + F` → ابحث عن `YOUR-`.

---

## 2) الصورة الشخصية

ضع صورتك باسم `photo.jpg` داخل `portfolio\assets\` — سيظهر مكان الدائرة الفارغة تلقائيًا.
حجم مقترح: مربع (مثلًا 800×800 بكسل)، خلفية محايدة.

---

## 3) تعديل الـ CV ثم إعادة توليد الـ PDF

عدّل `portfolio\assets\cv.html`، ثم نفّذ هذا الأمر في PowerShell:

```powershell
& "C:\Program Files\Google\Chrome\Application\chrome.exe" --headless=new --disable-gpu --no-pdf-header-footer --print-to-pdf="C:\Users\IT SHOP\OneDrive\Documents\Default Project\portfolio\assets\cv.pdf" "file:///C:/Users/IT SHOP/OneDrive/Documents/Default%20Project/portfolio/assets/cv.html"
```

أو ببساطة: افتح `cv.html` في المتصفح → `Ctrl + P` → Save as PDF.

---

## 4) معاينة الموقع محليًا

افتح `index.html` بالضغط المزدوج، أو شغّل سيرفر محلي:

```powershell
python -m http.server 8000
```

ثم افتح: http://localhost:8000

---

## 5) النشر (Deploy)

### Netlify — الأسهل (سحب وإفلات)
1. ادخل https://app.netlify.com/drop
2. اسحب مجلد `portfolio` بالكامل وأفلته.
3. ستحصل على رابط فورًا مثل `mostafa-atef.netlify.app` — استخدمه في لينكدإن.

### GitHub Pages
```powershell
cd "C:\Users\IT SHOP\OneDrive\Documents\Default Project\portfolio"
git init
git add .
git commit -m "Add portfolio site"
git branch -M main
git remote add origin https://github.com/YOUR-GITHUB-USERNAME/YOUR-GITHUB-USERNAME.git
git push -u origin main
```
ثم من المستودع: **Settings → Pages → Source: main / (root) → Save**.
الرابط سيكون: `https://YOUR-GITHUB-USERNAME.github.io/YOUR-GITHUB-USERNAME/`

### Cloudflare Pages
اربط المستودع، واترك أمر البناء فارغًا ومجلد الإخراج `/` (root).

---

## 6) بعد النشر — قائمة التحقق

- [ ] استبدال روابط لينكدإن وجيتهاب في `index.html`
- [ ] استبدال رابط الـ Live Demo لتطبيق Car Price
- [ ] إضافة `assets/photo.jpg`
- [ ] زر **Download CV** يعمل (الملف `assets/cv.pdf` موجود ✅)
- [ ] اختبار الموقع على الموبايل (المتجاوب موجود، لكن تأكد بنفسك)