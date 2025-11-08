# 📊 Excel Reverse-Engineer — Offline (No API Keys)

Client-side PNG → Excel extraction using **Tesseract.js** (OCR), **OpenCV.js** (detection), and **SheetJS** (XLSX).  
Works on **GitHub Pages** without servers or API keys.

## Use
1. Open the site.
2. Upload a PNG containing tables, pies (with % labels), or simple bar/column charts.
3. Click **Extract Data (Offline)**.
4. Click **Download Excel**.

## What it does
- **Tables**: Detects gridlines and OCRs each row.
- **Pie charts**: Detects circles and reads **%** labels; rounds to nearest 1%.
- **Bars/columns**: Pairs lines like `Label : 123` via OCR. (Safe fallback—no pixel interpolation.)

## Deploy on GitHub Pages
1. Create repo, add `index.html` and this `README.md`.
2. Enable **Settings → Pages → Source: main**.
3. Visit `https://<yourusername>.github.io/<repo>/`.

## Notes
- Everything runs locally in your browser (WebAssembly). No data leaves your machine.
- High-resolution PNGs improve OCR accuracy.
- Complex, unlabeled charts will export numeric tokens if structure is unclear, rather than inventing numbers.
