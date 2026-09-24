# BankDash 

Dashboard responsif berbasis Vue 3 yang dibuat mengikuti referensi desain BankDash dari Figma.

## Stack

- **Vue 3** untuk membangun antarmuka dan komponen halaman.
- **Vite** sebagai development server dan build tool.
- **Tailwind CSS 4** untuk styling responsif.
- **TypeScript** untuk konfigurasi dan dukungan type checking.


### Instalasi dan development server

```bash
npm install
npm run dev
```

Setelah server berjalan, buka URL lokal yang ditampilkan di terminal, biasanya `http://localhost:5173`.

## Pages included
- Credit Cards
- Services
- Setting (Edit Profile, Preferences, Security)

## Build untuk Production
```bash
npm run build
```

Untuk melihat hasil build secara lokal:

```bash
npm run preview
```

```link github
https://wildaqonitat-design.github.io/Bankdash/
```
```link live
http://localhost:5173/
```

The UI uses responsive Tailwind breakpoints for desktop, tablet, and mobile. Sidebar becomes a mobile drawer, tables scroll horizontally on small screens, and interactive controls show feedback toasts.
