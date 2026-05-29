Markdown

# 🎵 Gempak Jam Session Component (Season 5)

Satu komponen web premium berasaskan reka bentuk **Bento Box** dan **Hero Spotlight (Cinematic Layout)** yang dibangunkan khas untuk memaparkan senarai main (_playlist_) video persembahan akustik **Gempak Jam Session** secara dinamik.

Komponen ini menggunakan seni bina modular di mana struktur paparan (_frontend_) diasingkan sepenuhnya daripada kemasukan data. Data video ditarik secara _live_ melalui fail JSON yang disimpan di dalam repository GitHub ini.

---

## ✨ Ciri-Ciri Utama

- **Hero Spotlight Framework:** Slot utama (Episod Terbaru) akan dipaparkan secara automatik sebagai video tumpuan dengan saiz _thumbnail_ berskala besar.
- **Sistem Dynamic Rename Automatik:** Sistem JavaScript akan mengira susunan nombor episod secara automatik secara terbalik (dari episod tertinggi ke episod terendah) berdasarkan bilangan objek dalam JSON.
- **Bento Box Archive Grid:** Arkib koleksi musim terdahulu disusun secara horizontal menggunakan reka bentuk grid 2 tingkat yang mesra skrol (_2-layer horizontal scrolling chips_).
- **Premium Dark Aesthetic:** Skema warna gelap (_Dark Magenta_) yang disesuaikan dengan identiti visual jenama Astro Gempak.
- **100% Client-Side Architecture:** Selamat daripada risiko kebocoran data akses kerana fungsi penjaliran video dijalankan terus menggunakan struktur URL standard benaman YouTube tanpa memerlukan Google API Keys.

---

## 🛠️ Struktur Fail Projek

```text
__GEMPAK_JAM_SESSION_COMPONENT/
├── __DATA_ENTRY_GITHUB_JSON/
│   └── gempak-jam-session.json      # Fail pusat data video (Sila kemaskini di sini)
└── __HTML_CSS_JAVASCRIPT/
    ├── component-layout-e.html      # Kod muktamad frontend untuk CMS
    └── logo.png                     # Imej sandaran (Fallback) jika Youtube mini lambat dimuat
🚀 Panduan Penggunaan & Kemas Kini
1. Cara Menambah Video / Episod Baru
Untuk mengemas kini kandungan video tanpa perlu menukar kod HTML di CMS, anda hanya perlu mengubah suai fail JSON pusat.

Buka fail __DATA_ENTRY_GITHUB_JSON/gempak-jam-session.json.

Klik ikon pensel 📝 (Edit) di GitHub atau sunting fail ini terus di VS Code.

Tambah objek video baharu di bahagian paling atas di dalam susunan array "episodes". Ini bagi memastikan video terkini diangkat sebagai Hero Spotlight.

JSON
{
  "episodes": [
    {
      "id": "ID_VIDEO_YOUTUBE_BARU",
      "title": "[Akustik] Tajuk Lagu Baru - Nama Artis",
      "desc": "Saksikan persembahan eksklusif lagu baru ini secara akustik."
    },
    {
      "id": "8xmuzk-gH4g",
      "title": "Fiza Thomas & NAKI - Lain Semesta [Versi Akustik]",
      "desc": "Saksikan gandingan Fiza Thomas & NAKI membawakan lagu Lain Semesta..."
    }
  ]
}
Lakukan Commit changes (atau lakukan git push dari VS Code). Komponen pada tapak web utama akan dikemas kini secara automatik dalam masa beberapa minit.

2. Memasukkan Kod ke Dalam CMS
Salin keseluruhan kod di dalam fail __HTML_CSS_JAVASCRIPT/component-layout-e.html.

Tampal (paste) kod tersebut ke dalam komponen HTML khusus di dalam sistem pengurusan kandungan (CMS) tapak web anda.

Pastikan status repository ini telah ditukar kepada Public di bahagian tetapan GitHub (Settings > Danger Zone) supaya fungsi fetch() dapat membaca URL fail raw JSON dengan lancar.

🔒 Protokol Keselamatan & Amalan Terbaik
Two-Factor Authentication (2FA): Semua akaun pentadbir yang mempunyai akses kolaborasi ke fail repository ini wajib mengaktifkan 2FA melalui aplikasi pengesah bagi mengelakkan manipulasi data pihak ketiga.

Privasi Data: Kod ini adalah komponen frontend tulen. Jangan sesekali memasukkan data sensitif (token akses, kunci pelayan, fail konfigurasi sistem .env, atau data peribadi artis) ke dalam fail JSON atau fail HTML awam ini.
```
