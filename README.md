# 🤖 n8n Gemini AI Web Chatbot

Repository ini berisi file ekspor *workflow* n8n untuk pembuatan **Agen AI Chatbot Web** berbasis kecerdasan buatan (*Artificial Intelligence*) menggunakan **Google Gemini AI Model**. Chatbot ini dilengkapi dengan penyimpanan memori percakapan konteks pendek dan pengaturan *System Message* khusus.

---

## 🚀 Fitur Utama
* **Web Chat Interface:** Antarmuka obrolan web interaktif publik yang dapat diakses dari browser mana pun.
* **Google Gemini AI Model:** Menggunakan model `models/gemini-2.5-flash` untuk memproses dan menghasilkan respons bahasa alami secara cepat dan cerdas.
* **Contextual Memory (Simple Memory):** Mampu mengingat hingga 5 interaksi percakapan terakhir (`Context Window Length = 5`).
* **System Message Tuning:** Memiliki persona khusus untuk memberikan informasi yang relevan, ramah, dan terstruktur.
* **Rules-based Fallback:** AI diprogram untuk menjawab jujur jika informasi tidak ditemukan di dalam basis pengetahuan dan mengarahkan pengguna ke situs web resmi.

---

## 🛠️ Arsitektur Workflow
Workflow n8n dibentuk oleh 4 komponen node utama:
1. **Chat Trigger (`When chat message received`):** Pemicu utama yang menerima pesan masuk dari pengguna dan menyediakan tautan obrolan web publik.
2. **AI Agent:** Pusat kendali logika obrolan dan pengelola instruksi *System Message*.
3. **Google Gemini Chat Model:** Sub-node model bahasa AI untuk pemrosesan teks.
4. **Simple Memory:** Sub-node memori untuk menyimpan konteks obrolan.

---

## 📋 Cara Mengimpor Workflow ke n8n

1. **Unduh File Workflow:**
   * Unduh file `.json` dari repositori ini.
2. **Impor ke Platform n8n:**
   * Masuk ke dashboard n8n Anda (`n8n.cloud` atau *Self-Hosted*).
   * Buat workflow baru dengan mengklik tombol **Create Workflow**.
   * Klik ikon **titik tiga (`...`)** di pojok kanan atas editor → pilih **Import from File**.
   * Pilih file `.json` yang telah Anda unduh.
3. **Konfigurasi Credential Google Gemini:**
   * Dapatkan API Key melalui [Google AI Studio](https://aistudio.google.com).
   * Klik node **Google Gemini Chat Model**, tambahkan kredensial baru, dan masukkan API Key Anda.
4. **Aktivasi Chatbot Web:**
   * Klik node **When chat message received**, pastikan opsi **Make Chat Publicly Available** diaktifkan.
   * Ubah tombol status workflow menjadi **Active** (atau klik **Publish**) di pojok kanan atas.
   * Salin **Chat URL** dan buka di browser web untuk mulai berinteraksi.

---

## 📂 Struktur Repositori
```text
.
├── n8n-workflow.json   # File ekspor alur kerja n8n
└── README.md           # Dokumentasi proyek
