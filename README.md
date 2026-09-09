# Nirvasya — Portfolio

Landing page portfolio, dibangun pakai Vue 3 + Vite.

## Cara jalanin

Butuh Node.js terinstall dulu (cek dengan `node -v` di terminal).

```bash
npm install
npm run dev
```

Buka link yang muncul di terminal (biasanya `http://localhost:5173`).

## Struktur

```
src/
  App.vue                    -> merangkai Nav + Hero + Footer
  components/
    SiteNav.vue               -> navbar
    HeroSection.vue           -> headline besar "NIRVASYA / CREATIVE / DEVELOPER"
    InteractiveAvatar.vue     -> bulatan interaktif (tilt ikut kursor)
    SiteFooter.vue            -> footer bar
  style.css                   -> variabel warna & style global
```

## Ganti dengan foto asli

1. Taruh file foto kamu di folder `public/` (buat folder ini kalau belum ada), misal `public/foto-nirvasya.jpg`.
2. Buka `src/components/InteractiveAvatar.vue`, cari baris:
   ```js
   const photoSrc = ref('')
   ```
   ubah jadi:
   ```js
   const photoSrc = ref('/foto-nirvasya.jpg')
   ```
3. Save, foto langsung muncul di avatar dan tetap interactive (ikut tilt kursor).

## Build buat production

```bash
npm run build
```
Hasilnya ada di folder `dist/`, tinggal upload ke hosting (Vercel, Netlify, dll).
