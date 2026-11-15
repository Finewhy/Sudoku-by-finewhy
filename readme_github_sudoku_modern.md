# 🧩 Sudoku Modern — Game Puzzle HTML5 Interaktif

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![TailwindCSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Zero Dependencies](https://img.shields.io/badge/Assets-100%25_Procedural-8B5CF6?style=for-the-badge)

Game web **Sudoku Modern Interaktif** berbasis HTML5 single-file dengan tampilan *glassmorphism*, animasi interaktif yang halus, generator puzzle dengan jaminan solusi tunggal, serta efek suara sintetis tanpa membutuhkan aset audio maupun gambar eksternal.

---

## ✨ Fitur Unggulan

### 🧠 Generator & Solver Cerdas
* **Jaminan Solusi Unik:** Menggunakan algoritma *backtracking* yang dipadukan dengan heuristik **MRV (*Minimum Remaining Values*)** untuk memastikan setiap puzzle yang dibuat hanya memiliki **satu solusi valid**.
* **4 Tingkat Kesulitan:**
  * **Mudah** — 35 sel kosong
  * **Sedang** — 44 sel kosong
  * **Sulit** — 50 sel kosong
  * **Ahli** — 55 sel kosong

### 🎨 Desain & Animasi Modern
* **Glassmorphism UI & Dual Theme:** Mendukung pergantian mulus antara **Dark Mode** dan **Light Mode** lengkap dengan latar belakang cahaya ambien (*floating orbs*).
* **Smart Highlighting:** Otomatis menyorot sel yang dipilih, baris, kolom, kotak 3×3 terkait, serta seluruh angka yang bernilai sama di papan.
* **Animasi Responsif:**
  * *Pop-in* saat memasukkan angka.
  * *Shake* (getar) pada sel dan penghitung saat terjadi kesalahan.
  * *Completion Wave* (efek gelombang berurutan) setiap kali berhasil melengkapi 1 baris, 1 kolom, atau 1 blok 3×3.
  * *Confetti Celebration* berbasis HTML5 `<canvas>` saat memenangkan permainan.

### 🎮 Mekanik Gameplay Lengkap
* **Mode Catatan (*Pencil Marks*):** Tulis kandidat angka kecil di dalam sel, lengkap dengan pembersihan otomatis catatan yang bertentangan ketika angka benar dimasukkan.
* **Urungkan (*Undo*):** Kembalikan langkah sebelumnya kapan saja tanpa batas.
* **Petunjuk (*Hint*):** Bantuan pengisian sel otomatis (maksimal 3 kali per sesi).
* **Sistem Kesalahan & Ulangi Puzzle:** Batas maksimal 3 kesalahan dengan opsi untuk mencoba puzzle baru atau mengulangi puzzle yang sama dari awal.
* **Timer & Jeda Anti-Curang (*Pause*):** Menutup papan permainan secara otomatis saat waktu dijeda.
* **Indikator Sisa Angka:** Keypad 1–9 menampilkan sisa kuota masing-masing angka dan otomatis meredup jika seluruh 9 angkanya sudah terpasang benar.

### 🔊 Audio Prosedural (Web Audio API)
* Seluruh efek suara (klik sel, catatan, angka benar, salah, penyelesaian unit, hingga fanfare kemenangan) disintesis secara *real-time* menggunakan **Web Audio API**—ringan, instan, dan bebas file `.mp3`/`.wav`.

---

## ⌨️ Kontrol & Pintasan Keyboard

Selain mendukung layar sentuh (*mobile/tablet*) dan klik mouse, game ini juga dapat dimainkan sepenuhnya menggunakan keyboard:

| Tombol | Fungsi |
| :--- | :--- |
| `Panah` atau `W A S D` | Navigasi antar sel di papan 9×9 |
| `1` – `9` | Memasukkan angka atau catatan |
| `Backspace` / `Delete` / `0` | Menghapus angka atau catatan pada sel aktif |
| `N` | Mengaktifkan / mematikan **Mode Catatan (Notes)** |
| `Z` | **Urungkan (Undo)** langkah terakhir |
| `H` | Menggunakan **Petunjuk (Hint)** |
| `P` | **Jeda (Pause)** / lanjutkan permainan |

---

## 🚀 Cara Menjalankan & Deploy ke GitHub Pages

Karena dibangun dalam arsitektur **single-file** (`index.html`), proyek ini tidak memerlukan proses *build*, Node.js, maupun *bundler*.

### 1. Menjalankan Secara Lokal
1. Clone repositori ini:
   ```bash
   git clone https://github.com/username-kamu/nama-repo-sudoku.git
   ```
2. Buka folder proyek dan klik dua kali file `index.html` untuk langsung memainkannya di browser.

### 2. Publikasi Gratis via GitHub Pages
1. Unggah `index.html` dan `README.md` ke repositori GitHub milikmu.
2. Masuk ke menu **Settings** → **Pages** pada repositori tersebut.
3. Pada bagian **Build and deployment** (*Source*), pilih **Deploy from a branch**.
4. Pilih branch `main` (folder `/root`), lalu klik **Save**.
5. Tunggu beberapa saat hingga tautan live website muncul di `https://username-kamu.github.io/nama-repo-sudoku/`.

---

## 🏗️ Arsitektur Kode

Seluruh logika di dalam `index.html` dipisahkan ke dalam empat kelas utama berbasis JavaScript ES6+:

* `SudokuGenerator` — Pembangkit papan acak dan validator solusi tunggal berbasis *backtracking*.
* `SudokuGame` — Pengelola *state* papan, riwayat *undo*, validasi aturan Sudoku, *timer*, serta interaksi UI/keyboard.
* `SoundEngine` — Synthesizer efek suara berbasis `AudioContext`.
* `ConfettiEngine` — Sistem partikel konfeti berbasis `requestAnimationFrame` dan HTML5 Canvas.

---

## 📄 Lisensi

Proyek ini bersifat *open-source* dan bebas digunakan maupun dimodifikasi di bawah lisensi [MIT](https://opensource.org/licenses/MIT).