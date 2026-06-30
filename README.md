# oled
oled animation

# ESP32 Music Visualizer & Animasi Stickman (Melodi: Revenge - XXXTENTACION)
![Screenshot 2026-06-30 222538.png](https://github.com/devandraakhdanpratama-svg/oled/blob/809dfd940ebe00d6bd6172b8088546458a187d8b/Screenshot%202026-06-30%20222538.png)

Projek ini adalah pemutar musik non-blocking berbasis ESP32 yang menampilkan animasi stickman sedang mendengarkan musik (*head-banging*) dan audio equalizer dinamis pada layar OLED SSD1306 (128x64). Melodi yang dimainkan adalah lagu **"Revenge" oleh XXXTENTACION** melalui sebuah Piezo Buzzer.

Berbeda dengan kode Arduino biasa yang menggunakan fungsi `delay()`, projek ini menggunakan pendekatan **non-blocking dengan `millis()`**. Hal ini memastikan animasi grafik pada OLED tetap berjalan dengan sangat halus (FPS tinggi) tanpa terganggu oleh jeda ketukan nada musik.

---

## 🚀 Fitur Utama

* **Non-Blocking Audio Playback:** Musik dan grafik berjalan secara paralel tanpa interupsi.
* **Animasi Stickman Headbang:** Animasi 2-frame kustom menggunakan array bitmap yang berganti state setiap ketukan nada.
* **Dinamis Audio Equalizer:** 8 bar visualizer yang tingginya memetakan (*mapping*) frekuensi nada aktif secara real-time ditambah sedikit efek acak (*randomizer*) agar terlihat lebih hidup.
* **Optimasi ESP32:** Menggunakan pin I2C default ESP32 dengan transisi grafik yang responsif.

---

## 🛠️ Komponen yang Dibutuhkan

1. **ESP32 Development Board** (NodeMCU ESP32 / sejenisnya)
2. **Layar OLED SSD1306 128x64** (Koneksi I2C)
3. **Piezo Buzzer** (Pasif)
4. **Kabel Jumper** & Breadboard

---

## 📌 Skema Pengabelan (Pinout)

Hubungkan komponen ke ESP32 sesuai dengan tabel berikut:

| Komponen | Pin OLED / Buzzer | Pin ESP32 | Keterangan |
|---|---|---|---|
| **OLED SSD1306** | VCC | 3.3V / 5V | Daya Utama |
| | GND | GND | Ground |
| | SDA | GPIO 21 | Data I2C |
| | SCL | GPIO 22 | Clock I2C |
| **Piezo Buzzer** | Positif (+) | GPIO 18 | Sinyal Nada (PWM/Tone) |
| | Negatif (-) | GND | Ground |

---

## 📚 Library yang Diperlukan

Sebelum melakukan *upload* kode, pastikan kamu sudah menginstal library berikut melalui **Library Manager** di Arduino IDE:

1. **Adafruit SSD1306** (oleh Adafruit)
2. **Adafruit GFX Library** (oleh Adafruit)
3. **Wire** (Sudah bawaan/built-in)

---

## 💻 Cara Penggunaan

1. **Clone Repositori:**
   ```bash
   git clone [https://github.com/USERNAME_KAMU/NAMA_REPOSITORI.git](https://github.com/USERNAME_KAMU/NAMA_REPOSITORI.git)
