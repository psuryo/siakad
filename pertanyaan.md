## 1. Pertanyaan pembuka: visi dan masalah

Mulai dari pertanyaan strategis:

1. Apa masalah utama yang ingin diselesaikan ketika sistem akademik ini dibangun?
2. Apa visi universitas terhadap sistem akademik?
3. Apakah sistem ini diposisikan hanya sebagai **Sistem Informasi Akademik**, atau sebagai **platform utama operasional universitas**?
4. Apa indikator bahwa sistem ini dianggap berhasil?
5. Bagian mana dari sistem yang paling memberikan dampak terhadap operasional universitas?
6. Kalau sistem ini dibangun ulang dari awal, apa yang akan dilakukan secara berbeda?

**Pertanyaan nomor 6 sangat penting.** Biasanya justru menghasilkan insight terbaik.

---

# 2. Gali proses bisnis, bukan hanya menu

Tanyakan:

> "Boleh kami melihat satu proses akademik dari awal sampai akhir?"

Misalnya ambil proses **KRS**.

Tanyakan:

* Siapa yang memulai proses?
* Apa saja tahapannya?
* Siapa yang melakukan approval?
* Apa aturan bisnisnya?
* Apa yang terjadi jika mahasiswa terlambat?
* Apa yang terjadi jika dosen wali menolak?
* Bagaimana perubahan KRS dicatat?
* Apakah ada audit trail?
* Siapa yang boleh melakukan override?
* Bagaimana kasus khusus ditangani?

Lakukan hal yang sama untuk:

* Penerimaan mahasiswa baru
* Registrasi
* Pembayaran
* KRS
* Perwalian
* Perkuliahan
* Presensi
* Penilaian
* Ujian
* Yudisium
* Wisuda
* Cuti
* Drop out
* Transfer mahasiswa
* Pindah program studi
* MBKM
* Alumni

Dengan pendekatan ini Anda bisa menemukan **business rules tersembunyi** yang biasanya tidak terlihat dari demo aplikasi.

---

# 3. Pertanyaan tentang arsitektur sistem

Ini bagian yang sangat penting kalau Anda akan membangun sistem baru.

Tanyakan:

### Arsitektur

* Sistem menggunakan monolith, modular monolith, atau microservices?
* Apakah sistem dikembangkan sendiri atau menggunakan vendor?
* Apakah ada sistem legacy?
* Berapa banyak aplikasi yang terlibat?
* Mana yang menjadi **system of record** untuk data mahasiswa?
* Bagaimana pembagian tanggung jawab antar sistem?

Misalnya:

```text
Sistem Akademik
      │
      ├── PMB
      ├── Keuangan
      ├── LMS
      ├── Perpustakaan
      ├── Presensi
      ├── SSO
      ├── HR
      ├── PDDikti
      └── Data Warehouse
```

Lalu tanyakan:

> **"Sistem mana yang menjadi sumber kebenaran untuk setiap jenis data?"**

Ini pertanyaan yang sangat bagus untuk studi banding.

---

# 4. Pertanyaan tentang integrasi

Jangan hanya bertanya *"apakah terintegrasi?"*.

Tanyakan:

* Sistem apa saja yang terintegrasi?
* Integrasinya menggunakan REST API, SOAP, database sharing, message broker, atau metode lain?
* Apakah menggunakan API Gateway?
* Apakah ada Enterprise Service Bus?
* Bagaimana sinkronisasi data dilakukan?
* Real-time atau batch?
* Bagaimana menangani kegagalan integrasi?
* Bagaimana monitoring integrasi dilakukan?
* Apakah setiap sistem memiliki API documentation?
* Bagaimana versioning API dilakukan?

Khusus universitas, tanyakan juga integrasi dengan:

* PDDikti
* SIAKAD
* LMS
* Finance/ERP
* HR
* Library
* SSO
* Email
* WhatsApp/SMS
* Payment gateway
* Presensi
* Repository
* Sistem penelitian
* Sistem MBKM

---

# 5. Pertanyaan tentang master data

Ini sering menjadi **masalah terbesar** dalam sistem universitas.

Tanyakan:

> "Siapa pemilik data mahasiswa?"

Kemudian:

* Siapa pemilik data dosen?
* Siapa pemilik data program studi?
* Siapa pemilik data mata kuliah?
* Siapa yang boleh mengubah data?
* Bagaimana perubahan data didistribusikan ke sistem lain?
* Apakah ada single master data?
* Bagaimana menangani duplikasi mahasiswa?
* Bagaimana menangani perubahan NIM?
* Bagaimana menangani mahasiswa pindah prodi?
* Bagaimana histori perubahan data disimpan?

Saya bahkan akan memberikan perhatian khusus pada konsep:

### **Master Data Management**

karena kalau fondasi datanya salah, sistem akademik yang bagus sekalipun akan bermasalah.

---

# 6. Pertanyaan tentang pengguna

Jangan hanya melihat mahasiswa.

Tanyakan pengalaman:

### Mahasiswa

* Apa saja aktivitas mahasiswa yang dilakukan melalui sistem?
* Berapa banyak aplikasi yang harus mereka buka?
* Apakah ada satu portal?
* Apakah mobile-first?
* Apakah tersedia aplikasi mobile?

### Dosen

* Apa aktivitas dosen yang paling sering dilakukan?
* Apa bagian yang paling menyulitkan dosen?
* Bagaimana dosen melakukan input nilai?
* Bagaimana presensi?
* Bagaimana approval KRS?

### Admin

* Berapa banyak pekerjaan admin yang masih manual?
* Apa pekerjaan yang paling sering dilakukan?
* Apakah admin memiliki dashboard?
* Apakah ada bulk operation/import/export?

### Pimpinan

* Informasi apa yang dibutuhkan rektor/dekan/kaprodi?
* Apakah tersedia dashboard?
* Apakah data bisa drill-down?

---

# 7. Pertanyaan tentang workflow dan approval

Ini sangat penting untuk universitas.

Tanyakan:

* Apakah workflow dapat dikonfigurasi?
* Siapa yang menentukan approver?
* Apakah approval berdasarkan fakultas/prodi?
* Apakah workflow berbeda antar program studi?
* Apakah ada delegation?
* Apa yang terjadi jika approver tidak tersedia?
* Apakah approval melalui mobile/email?
* Apakah semua keputusan memiliki audit trail?

Contoh:

```text
Mahasiswa
   ↓
Dosen Wali
   ↓
Kaprodi
   ↓
BAAK
```

Tetapi bisa saja prodi A membutuhkan 3 approval sedangkan prodi B hanya 2.

Pertanyaan penting:

> **"Apakah workflow seperti ini hard-coded atau dapat dikonfigurasi?"**

Ini akan sangat menentukan fleksibilitas sistem Anda.

---

# 8. Pertanyaan tentang fleksibilitas

Universitas biasanya berubah.

Tanyakan:

* Seberapa mudah menambahkan program studi baru?
* Bagaimana jika struktur fakultas berubah?
* Bagaimana jika kurikulum berubah?
* Apakah sistem harus dimodifikasi oleh programmer?
* Apakah business rule dapat dikonfigurasi oleh administrator?
* Apakah form dapat dikustomisasi?
* Apakah workflow dapat dikustomisasi?
* Apakah laporan dapat dibuat sendiri oleh user?

Pertanyaan yang sangat bagus:

> **"Perubahan apa yang paling sering meminta tim IT melakukan coding ulang?"**

Dari sini Anda bisa mengetahui kelemahan arsitektur sistem mereka.

---

# 9. Pertanyaan tentang data dan reporting

Tanyakan:

* Berapa banyak laporan yang tersedia?
* Siapa yang membuat laporan?
* Apakah ada reporting engine?
* Apakah user bisa membuat laporan sendiri?
* Apakah ada data warehouse?
* Apakah menggunakan BI?
* Apakah dashboard real-time?
* Apakah ada historical data?
* Berapa lama data disimpan?

Kemudian tanyakan:

> **"Data apa yang paling sering diminta pimpinan tetapi paling sulit disediakan?"**

Ini sering mengungkap masalah data yang sebenarnya.

---

# 10. Pertanyaan tentang security

Wajib digali.

* Apakah menggunakan SSO?
* Apakah menggunakan OAuth2/OIDC?
* Bagaimana role dan permission dikelola?
* Apakah RBAC?
* Apakah ada MFA?
* Bagaimana audit log?
* Apakah aktivitas admin dicatat?
* Bagaimana backup?
* Bagaimana disaster recovery?
* Berapa RPO/RTO?
* Apakah pernah terjadi security incident?
* Bagaimana data pribadi mahasiswa dilindungi?

Untuk universitas, tanyakan juga:

> "Bagaimana membatasi akses data mahasiswa agar seorang admin hanya dapat melihat data yang memang menjadi kewenangannya?"

---

# 11. Pertanyaan tentang teknologi dan DevOps

Kalau Anda juga ingin belajar dari sisi IT:

* Teknologi backend apa?
* Database apa?
* Frontend apa?
* Mobile apa?
* Cloud atau on-premise?
* Apakah menggunakan container?
* Apakah menggunakan Docker/Kubernetes?
* Bagaimana CI/CD?
* Apakah ada staging environment?
* Bagaimana deployment dilakukan?
* Berapa lama biasanya deployment?
* Bagaimana rollback?
* Bagaimana monitoring?
* Apakah menggunakan centralized logging?
* Bagaimana load testing dilakukan?

Dan pertanyaan yang sering menghasilkan jawaban menarik:

> **"Apa bottleneck teknis terbesar yang pernah dialami sistem ini?"**

---

# 12. Pertanyaan tentang performa dan skala

Jangan lupa menanyakan angka.

Misalnya:

* Berapa jumlah mahasiswa?
* Berapa jumlah dosen?
* Berapa concurrent users?
* Berapa transaksi KRS pada periode sibuk?
* Berapa transaksi pembayaran?
* Berapa request per second?
* Apa yang terjadi saat KRS dibuka secara bersamaan?
* Bagaimana sistem menghadapi peak load?
* Apakah pernah down saat KRS?

Kemudian:

> **"Berapa kapasitas yang dirancang dan berapa kapasitas aktualnya?"**

---

# 13. Pertanyaan tentang implementasi

Ini sering lebih penting daripada teknologi.

Tanyakan:

* Berapa lama sistem dibangun?
* Berapa orang dalam tim?
* Berapa orang developer?
* Apakah ada project manager?
* Siapa pemilik proyek?
* Siapa pengambil keputusan?
* Bagaimana keterlibatan fakultas?
* Bagaimana melibatkan dosen?
* Bagaimana melibatkan mahasiswa?
* Apakah ada pilot project?
* Bagaimana migrasi dari sistem lama?
* Berapa lama masa transisi?

---

# 14. Pertanyaan tentang kegagalan

Saya sangat menyarankan menyediakan satu sesi khusus:

> **"Apa yang tidak berhasil ketika membangun sistem ini?"**

Lalu gali:

* Fitur apa yang ternyata tidak digunakan?
* Fitur apa yang terlalu kompleks?
* Keputusan teknologi apa yang akhirnya disesali?
* Apakah pernah salah memilih vendor?
* Apakah pernah terjadi masalah migrasi data?
* Apakah pernah terjadi resistensi dari pengguna?
* Bagaimana mengatasinya?
* Jika membangun ulang, apa yang akan diubah?

Biasanya bagian ini jauh lebih berharga daripada demo fitur.

---

# 15. Pertanyaan tentang governance

Ini sering terlupakan ketika kampus membangun sistem sendiri.

Tanyakan:

* Siapa pemilik sistem?
* Apakah di bawah UPT TIK?
* Apakah ada steering committee?
* Siapa yang menentukan prioritas fitur?
* Bagaimana permintaan perubahan diajukan?
* Siapa yang menyetujui perubahan?
* Bagaimana governance data dilakukan?
* Apakah ada Data Owner?
* Apakah ada Data Steward?
* Bagaimana konflik antar unit diselesaikan?

Misalnya Fakultas meminta aturan A, tetapi BAAK meminta aturan B.

**Siapa yang memiliki keputusan final?**

---

# 16. Pertanyaan tentang biaya

Tidak harus meminta angka jika mereka tidak nyaman.

Tanyakan:

* Model pengembangan: internal/vendor?
* CAPEX atau OPEX?
* Biaya lisensi?
* Biaya cloud/infrastruktur?
* Biaya maintenance?
* Biaya support?
* Biaya pengembangan fitur baru?
* Berapa besar tim yang diperlukan untuk mempertahankan sistem?

Pertanyaan menarik:

> **"Dari total biaya sistem, bagian terbesar biasanya ada di development, infrastructure, license, atau maintenance?"**

---

# 17. Pertanyaan yang menurut saya paling bernilai

Kalau waktu studi banding Anda **hanya 2–3 jam**, saya justru akan memilih 15 pertanyaan ini:

### Strategi

1. Apa masalah utama yang ingin diselesaikan sistem ini?
2. Apa indikator keberhasilan sistem?

### Proses

3. Proses akademik apa yang paling kompleks?
4. Bisa diperlihatkan satu proses dari awal sampai selesai?
5. Apa saja business rules penting yang ada di balik proses tersebut?

### Arsitektur

6. Bagaimana arsitektur keseluruhan sistem?
7. Sistem mana yang menjadi **source of truth** untuk setiap data?
8. Sistem apa saja yang terintegrasi?

### Data

9. Bagaimana master data dikelola?
10. Bagaimana menghindari duplikasi dan inkonsistensi data?

### User

11. Apa keluhan terbesar mahasiswa, dosen, dan admin?
12. Fitur apa yang paling sering digunakan?

### Teknologi

13. Apa masalah teknis terbesar yang pernah dialami?
14. Bagaimana sistem menangani peak load?

### Lessons learned

15. **Kalau universitas ini membangun Sistem Akademik dari nol lagi hari ini, apa tiga hal yang akan Anda lakukan secara berbeda?**

Nomor **15** menurut saya adalah pertanyaan "emas".

---

## Saya juga menyarankan mengubah format studi banding

Jangan hanya:

> "Kami ingin melihat demo Sistem Akademik."

Lebih baik meminta mereka mempersiapkan **5 sesi**:

```text
1. Business Process
       ↓
2. System Architecture
       ↓
3. Data & Integration
       ↓
4. User Experience
       ↓
5. Technology & Governance
```

Dan minta mereka memperlihatkan **satu kasus nyata**, misalnya:

> "Tunjukkan perjalanan seorang mahasiswa mulai dari diterima sebagai mahasiswa baru → registrasi → mengambil KRS → mengikuti kuliah → mendapatkan nilai → yudisium → wisuda."

Dari satu *end-to-end journey* itu Anda bisa melihat hubungan antar modul dan sistem jauh lebih jelas daripada melihat menu satu per satu.

---

### Kalau ini proyek Sistem Akademik Universitas Anda

Saya malah akan membuat **instrumen studi banding dalam bentuk tabel**, misalnya:

| Area            | Pertanyaan              | Jawaban Universitas A | Universitas B | Universitas C | Insight untuk sistem kita |
| --------------- | ----------------------- | --------------------- | ------------- | ------------- | ------------------------- |
| PMB             | Bagaimana proses PMB?   |                       |               |               |                           |
| KRS             | Bagaimana approval KRS? |                       |               |               |                           |
| Master Data     | Siapa source of truth?  |                       |               |               |                           |
| Integrasi       | Sistem apa saja?        |                       |               |               |                           |
| SSO             | Mekanisme SSO?          |                       |               |               |                           |
| Workflow        | Configurable?           |                       |               |               |                           |
| Reporting       | Self-service BI?        |                       |               |               |                           |
| Mobile          | Ada mobile app?         |                       |               |               |                           |
| Security        | RBAC/MFA/audit?         |                       |               |               |                           |
| Architecture    | Monolith/microservices? |                       |               |               |                           |
| DevOps          | CI/CD?                  |                       |               |               |                           |
| Governance      | Siapa system owner?     |                       |               |               |                           |
| Lessons Learned | Apa yang akan diubah?   |                       |               |               |                           |

Dengan format seperti ini, hasil studi banding Anda akhirnya bisa langsung berubah menjadi **requirement dan arsitektur Sistem Akademik baru**, bukan hanya menjadi laporan kunjungan.

Kalau Anda mau, saya juga bisa bantu membuat **"Kuesioner Studi Banding Sistem Akademik Universitas" yang sangat lengkap (100+ pertanyaan), dikelompokkan berdasarkan PMB, akademik, kurikulum, KRS, nilai, dosen, mahasiswa, keuangan, integrasi, SSO, data, AI, keamanan, infrastruktur, dan governance**, sekaligus dibuat dalam format yang siap dibawa saat kunjungan.
Pertanyaan: 
CPMK tiap mata kuliah ada berapa? ada 3 penilaian formatif dan 1 sumatif
Apakah setelah disetujui RPS bisa diubah?
