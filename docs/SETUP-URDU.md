# PharmaCore — Complete Setup Guide (Roman Urdu, sab kuch ek jagah)

Ye zip COMPLETE hai. Is me sab kuch hai: poora source code, GitHub workflow,
gitignore, README, user manual, schema doc, import template. Purane zips delete
kar do, sirf isi zip ko use karo. Koi file alag se edit karne ki zaroorat nahi
hai — icon wali line ka fix bhi is me pehle se hai.

## Is zip me kya hai
- src/ — poori app (Dashboard, POS, Inventory, Scan to Add, Purchases, Reports, Settings)
- electron/ — Electron main, database (SQLite), services
- .github/workflows/build-windows.yml — GitHub Actions se Windows .exe banane ke liye
- .gitignore, electron-builder.yml, package.json, templates/, docs/, tests/

## Rasta 1: Apne PC par chalana (local)
1. Node.js LTS install karo (nodejs.org se).
2. Zip extract karo, us folder me jao jahan package.json hai.
3. Usi folder me cmd kholo (address bar me cmd likh kar Enter).
4. `npm install` chalao. Pehli dafa internet zaroori hai.
   - Agar ECONNRESET aaye to dobara `npm install` chalao.
   - Agar node-gyp / Visual Studio ka error aaye to Visual Studio Community
     (Free download) install karo, us me "Desktop development with C++" tick karo,
     phir dobara `npm install` chalao.
5. `npm run build` chalao — ye zaroori hai, is se dist/ banta hai.
6. `npm run dev` chalao — app khul jayegi.
7. Login PIN: Owner 1234, Cashier 1111.

## Rasta 2: Apne PC par .exe banana
1. Upar wale steps complete karo, app dev me test kar lo.
2. `npm run build:win` chalao.
3. `release` folder me `PharmaCore Setup 1.0.0.exe` milegi. Us par double-click
   karke install karo. Install ke baad Node/npm ki zaroorat nahi.

## Rasta 3: GitHub se .exe banana (apne PC par kuch install kiye baghair)
1. github.com par free account banao, new repository banao (naam: PharmaCore, Public).
2. Is zip ki files upload karo — check karo ke `.github/workflows/build-windows.yml`
   repo me mojood ho, warna Actions build nahi karega.
3. Actions tab me build khud shuru ho jayega, 5-10 minute wait karo.
4. Build complete hone par us run ke Artifacts me `PharmaCore-Windows-Setup`
   milega, us me .exe download karo aur install karo.

## Aam errors (is zip me ye pehle se theek hain)
- Khaali window: `npm run dev` se pehle `npm run build` chalana zaroori hai.
- Icon error: electron-builder.yml me icon wali line hata di gayi hai.
- Network error: `npm install` dobara chalao, npm wahi se continue karta hai.
