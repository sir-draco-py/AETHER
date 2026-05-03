# 🌌 Aether — Weather Dashboard

> Dashboard cuaca interaktif real-time dengan desain glassmorphism, animasi 3D, dan scrollytelling sinematik. Dibangun hanya dengan HTML, CSS, dan JavaScript murni — tanpa framework, tanpa API key.

![Aether Banner](https://img.shields.io/badge/Aether-Weather%20Dashboard-60c8ff?style=for-the-badge&labelColor=040610)
![HTML](https://img.shields.io/badge/HTML-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS](https://img.shields.io/badge/CSS-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Open-Meteo](https://img.shields.io/badge/API-Open--Meteo-c084fc?style=for-the-badge)

---

## ✨ Fitur Utama

### 🎬 Pengalaman Visual
- **Animasi masuk sinematik** — overlay intro logo, lalu elemen hero muncul satu per satu dengan stagger
- **Background langit malam** — awan bergerak perlahan di atas bintang yang berkelip dengan Canvas API
- **Glassmorphism** — semua card menggunakan `backdrop-filter` blur dengan border transparan
- **3D Tilt Interaktif** — 3 card kondisi cuaca merespons gerakan mouse dengan rotasi 3D dan shine highlight dinamis
- **Scrollytelling Sinematik** — setiap seksi udara (UV, Visibilitas, Curah Hujan) memiliki animasi masuk tersendiri saat di-scroll

### 🌦️ Data Cuaca Real-Time
| Seksi | Data yang Ditampilkan |
|---|---|
| **Kondisi Saat Ini** | Suhu, kondisi cuaca, kelembaban, kecepatan angin |
| **Per Jam** | Prakiraan 24 jam ke depan dengan probabilitas hujan |
| **Mingguan** | Prakiraan 7 hari dengan temperature range bar |
| **Udara & Cahaya** | UV index (arc gauge), visibilitas (lens rings), curah hujan (animasi tetes + gauge) |
| **Lokasi** | Koordinat kota, radar pulse, scan line atmosferik |

### ⚡ Teknis
- **Zero dependency** — tidak ada npm, tidak ada framework
- **Zero API key** — menggunakan [Open-Meteo](https://open-meteo.com/) dan [Open-Meteo Geocoding](https://open-meteo.com/en/docs/geocoding-api) yang sepenuhnya gratis
- **Single file** — seluruh app dalam satu file `index.html`
- **Responsif** — layout menyesuaikan di mobile

---

### Deploy ke Vercel
Sambungkan GitHub repo ke Vercel, deploy and done
---

## 🗂️ Struktur Scrollytelling

```
📄 index.html
│
├── 🏠  Hero            — Search kota + animasi masuk
├── 🌡️  Kondisi Saat Ini — 3 card 3D: suhu, kelembaban, angin
├── ⏱️  Per Jam          — 24 jam ke depan (scroll horizontal)
├── 📅  Mingguan         — 7 hari prakiraan
├── 💨  Udara            — 3 chapter scrollytelling:
│       ├── 01 UV Index      (arc gauge SVG animasi)
│       ├── 02 Visibilitas   (lens rings + scan line)
│       └── 03 Curah Hujan   (animasi tetes + gauge meter)
└── 📍  Lokasi           — Grid atmosferik + radar pulse + pin animasi
```

---

## 🛠️ Teknologi

| Teknologi | Kegunaan |
|---|---|
| **HTML5 Canvas API** | Background langit malam + awan bergerak + bintang |
| **CSS Animations & Keyframes** | Semua animasi masuk, scrollytelling, float, pulse |
| **CSS `backdrop-filter`** | Efek glassmorphism |
| **CSS `transform-style: preserve-3d`** | Efek 3D tilt pada card |
| **Intersection Observer API** | Trigger animasi saat elemen masuk viewport |
| **Fetch API** | Memanggil Open-Meteo & Geocoding API |
| **SVG** | Arc gauge UV index, awan curah hujan |
| **Google Fonts** | Syne (display) + DM Sans (body) |

---

## 🌐 API yang Digunakan

Semua **gratis, tanpa API key**, tanpa registrasi.

```
# Geocoding (nama kota → koordinat)
GET https://geocoding-api.open-meteo.com/v1/search?name={kota}

# Cuaca (koordinat → data cuaca)
GET https://api.open-meteo.com/v1/forecast
    ?latitude={lat}
    &longitude={lon}
    &current=temperature_2m,relative_humidity_2m,apparent_temperature,
             weather_code,wind_speed_10m,uv_index,visibility,precipitation
    &hourly=temperature_2m,weather_code,precipitation_probability
    &daily=weather_code,temperature_2m_max,temperature_2m_min
    &forecast_days=7
    &timezone=auto
```

---

## 🎨 Design System

```css
--accent:  #60c8ff  /* Biru langit    */
--accent2: #c084fc  /* Ungu aurora    */
--accent3: #f472b6  /* Pink senja     */
--bg1:     #040610  /* Hitam malam    */
--glass:   rgba(255,255,255,0.07)  /* Glass fill   */
```

Font: **Syne** (heading, 800) + **DM Sans** (body, 300–500)

---

## 📸 Preview

| Halaman | Seksi |
|---|---|
| Hero | Animasi masuk + search bar |
| Kondisi Saat Ini | 3 card 3D glassmorphism |
| Scrollytelling Udara | UV, Visibilitas, Curah Hujan |
| Lokasi | Radar pulse + atmospheric grid |

---

## 📄 Lisensi

MIT License — bebas digunakan, dimodifikasi, dan didistribusikan.

---

<div align="center">
  <p>Dibuat dengan ☁️ dan banyak <code>backdrop-filter</code></p>
  <p>
    <a href="https://open-meteo.com/">Open-Meteo API</a> ·
    <a href="https://fonts.google.com/specimen/Syne">Syne Font</a> ·
    <a href="https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API">Canvas API</a>
  </p>
</div>
