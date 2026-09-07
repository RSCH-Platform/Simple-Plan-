# Simple-Plan - 

![Simple-Plan](https://img.shields.io/badge/SP--IKP-Patient_Safety_Incident-blue)
![Workflow](https://img.shields.io/badge/Type-Workflow_Management-purple)
![Tech Stack](https://img.shields.io/badge/Stack-Laravel_%7C_Filament_%7C_MySQL-red)
![Authentication](https://img.shields.io/badge/Auth-NexaID_%2F_IAM-green)
![Ecosystem](https://img.shields.io/badge/Ecosystem-RSCH-darkgreen)
**Simple-Plan** adalah aplikasi Sistem manajemen Inventarisisasi, Maintenance dan Help desk Perangkat Layanan manajemen pelaporan, **Simple-PLan** berbasis workflow. Aplikasi ini dirancang untuk membantu rumah sakit mencatat tiket Helpdesk, inventaris alat, dan helpdesk secara terstruktur, memproses laporan melalui tahapan verifikasi dan delegasi staf pelaksana TIK dan bagian sapras rumah sakit, serta memantau rekomendasi perbaikan sampai tiket selesai.

Simple-Plan merupakan bagian dari ekosistem digital **RSCH** bersama beberapa aplikasi lain seperti **SIIMUT**, **IKP**,**RBV**, **LMS**, **smartpresence**.

> Simple-Plan bukan hanya aplikasi input kegitan helpdesk laporan, tetapi sistem workflow untuk mengubah laporan iventaris,helpdesk dan maintenance menjadi data tindak lanjut yang dapat digunakan dalam evaluasi KPI pekerjaan unit TIK dan umum RT.

---

## Daftar Isi

---

## Latar Belakang

Simple Plan membutuhkan proses pencatatan dan tindak lanjut yang rapi agar tidak berhenti sebagai laporan administratif saja. Setiap kegiatann perlu memiliki alur yang jelas mulai dari pelaporan awal, verifikasi, tiket terbit, rekomendasi, hingga aksi perbaikan.

Tanpa sistem yang terstruktur, beberapa masalah umum dapat terjadi:

* Laporan helpdesk tidak terdokumentasi dengan baik.
* Status penanganan sulit dipantau karena tidak ada tiket yang jelas.
* Rekomendasi tidak memiliki tindak lanjut yang jelas.
* Unit terkait tidak memiliki visibilitas terhadap progres perbaikan.
* Data laporan sulit digunakan untuk evaluasi KPI kinerja unit.

Simple-Plan dibangun untuk menjawab kebutuhan tersebut melalui pendekatan **workflow management**, sehingga setiap laporan memiliki status, penanggung jawab, proses, dan riwayat yang dapat ditelusuri.

---

## Tujuan Sistem

Tujuan utama Simple Plan adalah menyediakan sistem pelaporan Help desk TIK,Help desk Sapras,maintenane pada layanan:

1. **Terstruktur**
   Setiap laporan mengikuti tahapan proses yang jelas dan terdokumentasi.

2. **Traceable**
   Riwayat perubahan status, verifikasi, tiketing, dan tindak lanjut dapat dilacak laporan.

3. **Role-based**
   Akses pengguna disesuaikan berdasarkan role dan unit kerja.

4. **Terintegrasi**
   Menggunakan NexaID / IAM sebagai pusat autentikasi, role, dan unit kerja.

5. **Mendukung Evaluasi pada laporan bulanan**
   Data laporan dapat menjadi konteks pendukung untuk analisis mutu.

---

## Posisi dalam Ekosistem RSCH

Simple Plan berada di antara sistem autentikasi pusat dan sistem inovasi digital rumah sakit.

| Aplikasi         | Fokus                                                                  | Peran terhadap Sistem                            |
| ---------------- | ---------------------------------------------------------------------- | ------------------------------------------------------ |
| **NexaID / IAM** | SSO, user, role, unit kerja, access profile                            | Menyediakan autentikasi dan otorisasi pengguna         |
| **SP-IKP**       | Pelaporan insiden, verifikasi, investigasi, rekomendasi, tindak lanjut | Aplikasi utama pengelolaan insiden keselamatan pasien  |
| **SIIMUT**       | Indikator mutu, monitoring, compliance, laporan mutu                   | Menerima konteks dari data insiden untuk evaluasi mutu |
| **LMS**          | Learning management Syistem                                            |                                                        |
| **RBV**          | Ruang Baca Virtual                                                     |                                                        |
| **Smartpresensi**| Absensi kehadiran rapat                                                |                                                        |
| **Simple-Plan**  | Learning management Syistem                                            |                                                        |




```

---

## Fitur Utama

### 1. Pelaporan Tiketing

Modul ini digunakan untuk mencatat laporan awal pada help desk.

Data yang umumnya dicatat:

* Tanggal dan waktu kejadian.
* Unit kerja terkait.
* Jenis pelaporan.
* Kronologi helpdesk.
* Dampak awal (grating).
* Pelapor.
* Lampiran pendukung jika diperlukan.

---

### 2. Verifikasi Laporan help desk (admin penerima laporan)

Setelah laporan masuk, laporan dapat diverifikasi oleh petugas atau tim yang berwenang.

Proses verifikasi mencakup:

* Pemeriksaan kelengkapan data.
* Validasi jenis kerusakan.
* Penentuan apakah laporan dapat diproses lebih lanjut.
* Penentuan tingkat risiko awal.
* Pengubahan status laporan.

---

### 3. tutup tiket


tutup laporan tiket dapat mencakup:

* Analisis penyebab langsung.
* Analisis akar masalah.
* Keterangan tambahan dari unit terkait.
* Pemeriksaan dokumen pendukung.
* Kesimpulan.
* Penentuan kebutuhan rekomendasi.

---

### 4. Rekomendasi Perbaikan 

Setelah investigasi dilakukan, tim terkait dapat membuat rekomendasi perbaikan.

Contoh rekomendasi:

* pergantian perangkat.
* Edukasi ulang petugas perihal perangkat TIK.
* Perbaikan SOP.
* Peningkatan pengawasan.
* Perbaikan sarana atau sistem pendukung.
* Evaluasi ulang proses kerja unit.

---

### 5. Tindak Lanjut / Aksi

Rekomendasi yang telah dibuat perlu dipantau pelaksanaannya.

Modul tindak lanjut membantu memastikan bahwa rekomendasi tidak hanya berhenti sebagai catatan, tetapi benar-benar dieksekusi.

Data yang dapat dipantau:

* Penanggung jawab aksi.
* Deadline tindak lanjut.
* Status pengerjaan.
* Bukti pelaksanaan.
* Catatan evaluasi.
* Tanggal penyelesaian.

---

### 6. Monitoring Status

Setiap tiket dengan kriteria filter mutu memiliki status agar progres penanganan dapat dipantau.

Contoh status:

* `Pending`
* `Verified`
* `Under Investigation`
* `Action Required`
* `Ongoing`
* `Completed`
* `Rejected`

Status dapat disesuaikan dengan kebutuhan workflow aplikasi.

---

### 7. Dashboard dan Rekapitulasi

Dashboard digunakan untuk memberikan gambaran cepat terhadap kondisi pelaporan simple plan.

Informasi yang dapat ditampilkan:

* Total laporan tiketing TIK.
* Total laporan tiketing Sapras.
* Total laporan permintaan desain Grafis TIK.
* Total laporan maintenance.
* total inventaris TIK,Sapras, elektro, Alkes aktif dan non aktif.
* Tindak lanjut yang melewati deadline.

---

### 8. Export Laporan

Simple Plan dapat mendukung kebutuhan pelaporan melalui fitur export.

Format yang dapat digunakan:

* PDF
* Excel
* Rekap bulanan
* Rekap berdasarkan unit kerja (TIK, Umum RT (Sapras,Elektronik,Alkes)
* Rekap berdasarkan status
* Rekap berdasarkan periode tertentu

---

## Workflow nya 

Alur Helpdesk TIK :



┌──────────────────────────────┐
│        UNIT / USER           │
│ Melaporkan kendala TIK       │
│ • SIMRS                      │
│ • Komputer / Laptop /HP      │
│ • Printer                    │
│ • Jaringan / WiFi /Telepon   │
│ • Akun / Hak Akses           │
│ • software dan hardware      │
└───────────────┬──────────────┘
                │
                ▼
┌────────────────────────────────────────────────────┐
│       HELPDESK TIK                                 │
│ Terima & buat TIKET                                │
│ • Nomor Tiket                                      │
│ • Unit                                             │
│ • Kategori : Mutu                                  │ 
│ a.Kepatuhan Input Operator                         │
│ b.Ketidakstabilan System                           │
│ c.Ketidaksesuain Program                           │
│ d.Akun dan Hak Akses System                        │
│ e.Waktu tanggap kerusakan Hardware                 │
│  f.waktu tanggap kerusakan Software                │
│ • Pilihan Tags IT :                                │
│  a.Manage batal kunjungan pasien                   │
│  b.Edit Asessmen Medis Dokter (Form Perubahan Data)│
│  c.Support Apps Hapus Asessmen Medis Dokter        │
│  d.Edit Asessmen Keperawatn (Form Perubahan Data)  │
│  e.Support Apps Hapus Asessmen Keperawatan         │
│  f.Edit data operasi dari modul Operasi            │
│  g.Hapus Request, Regis dan ID Penjualan LAB       │
│ h.Hapus Request, Regis dan ID Penjualan RAD        │
│  i.Manage edit ID Penjualan LAB                    │
│  j.Manage edit ID Penjualan RAD                    │
│  k.Manage ACC dan Ticketing Unit                   │ 
│  l.Hapus Request BMHP Farmasi                      │
│  m.Manage Master Baru (Jasa, Rikjang, Fasilitas)   │
│  n.Manage Mapping Master (Jasa, Rikjang, Fasilitas)│
│  o.Manage Mapping untuk Bridging IT                │
│  p.Manage Master LAB Test                          │
│  q.Manage Master RAD Test                          │
│  r.Manage Casemix tidak muncul                     │
│  s.Manage unvalidasi RPP                           │
│  t.Manage program Reham Medik Poli Fisioterapi     │
│  u.Manage master Barang Medis Farmasi              │
│  v.Manage tambah hak akses user NUHA               │
│  w.Manage edit hak akses user NUHA                 │
│  x.Manage hapus hak akses user NUHA                │
│  y.Manage pelatihan modul ke Unit                  │
│  z.Manage input Diagnostik Medis                   │
│  aa.Manage input Tindakan Kunjungan di Modul vaksin│
│  bb.Manage tambah master jam kerja + Mapping Unit  │
│  cc.Manage transfer mutase saldo di kas V3         │
│  dd.Manage master tenaga medis                     │
│  ee.Manage mapping master ruangan operasi          │
│  ff.Pergantian Sparpart                            │
│  gg.Perbaikan perangkat                            │
│ ff.Lain - lain                                     │
│ • Waktu laporan                                    │
└───────────────┬────────────────────────────────────┘
                │
                ▼
        ┌─────────────────┐
        │ KLASIFIKASI     │
        │ & PRIORITAS     │
        └────────┬────────┘
                 │
       ┌─────────┼──────────┐
       ▼         ▼          ▼
   KRITIS      SEDANG     RENDAH
       │         │          │
       └─────────┼──────────┘
                 ▼
┌──────────────────────────────┐
│       PENUGASAN PIC          │
│ • Tim Support                │
│ • Tim Desain Grafis          │
│ • Tim SIMRS / Aplikasi       │
│                              │
└───────────────┬──────────────┘
                │
                ▼
┌──────────────────────────────┐
│      ANALISIS & TROUBLESHOOT │
│ • Remote support             │
│ • Datang ke unit             │
│ • Cek perangkat              │
│ • Cek jaringan               │
│ • Cek SIM RS       │
└───────────────┬──────────────┘
                │
                ▼
        ┌─────────────────┐
        │ MASALAH SELESAI?│
        └───────┬─────┬───┘
                │     │
              TIDAK   YA
                │     │
                ▼     ▼
┌──────────────────┐  ┌────────────────────┐
│ ESKALASI         │  │ VERIFIKASI USER    │
│ • management     │  │ User memastikan    │
│ • Vendor         │  │ layanan normal     │
│ • Tim terkait    │  └─────────┬──────────┘
└────────┬─────────┘            │
         │                      ▼
         └──────────────►┌──────────────────┐
                         │ UPDATE TIKET     │
                         │ • Tindakan       │
                         │ • Penyebab       │
                         │ • Waktu selesai  │
                         │ • PIC            │
                         └────────┬─────────┘
                                  │
                                  ▼
                         ┌──────────────────┐
                         │ TIKET DITUTUP    │
                         └────────┬─────────┘
                                  │
                                  ▼
                         ┌──────────────────┐
                         │ MONITORING &     │
                         │ LAPORAN HELPDESK │
                         │ • SLA            │
                         │ • Response Time  │
                         │ • Resolution Time│
                         │ • Rekap masalah  │
                         └──────────────────┘



Alur ini memastikan bahwa setiap laporan memiliki proses yang jelas dari awal sampai selesai.

---

## Role dan Hak Akses

Hak akses dalam Simple-Plan dapat disesuaikan berdasarkan kebutuhan organisasi. Secara umum, pembagian role dapat dibuat seperti berikut:

| Role                | Deskripsi                                     | Akses Utama                                        |
| ------------------- | --------------------------------------------- | -------------------------------------------------- |
| **Super Admin**     | Pengelola sistem secara penuh                 | Semua modul, konfigurasi, user, role               |
| **Koordi Sarpras**  | Pengelola utama aplikasi Simple-Plan          | Kelola laporan, verifikasi, investigasi, dashboard |
| **Petugas Unit**    | Tim yang memantau kegiatan lapang             | Verifikasi, investigasi, rekomendasi, monitoring   |
| **Unit Kerja**      | Pengguna dari masing-masing unit              | Membuat laporan, melihat laporan unit terkait      |
| **Manajemen**       | Pihak pemantau tingkat manajerial             | Melihat dashboard, rekap, dan laporan akhir        |

---

## Status Penanganan Help Desk



---

## Arsitektur Sistem

Simple-Plan menggunakan arsitektur aplikasi web berbasis Laravel dengan panel administrasi Filament.

```mermaid
flowchart LR
    USER[User / Unit Kerja] --> UI[Filament Panel]
    UI --> APP[Laravel Application]
    APP --> DB[(MySQL / MariaDB)]
    APP --> IAM[NexaID / IAM]
    APP --> STORAGE[Local / S3 / MinIO Storage]

    IAM --> APP
    STORAGE --> APP
```

Komponen utama:

* **Laravel App**
  Menangani business logic, workflow, validasi, autentikasi, dan integrasi.

* **Filament Panel**
  Menyediakan interface admin untuk pengelolaan laporan, investigasi, dan tindak lanjut.

* **MySQL / MariaDB**
  Menyimpan data utama aplikasi.

* **NexaID / IAM**
  Menyediakan autentikasi SSO, user, role, dan unit kerja.

* **Storage**
  Menyimpan file lampiran, dokumen pendukung, atau export laporan.

---

## Tech Stack

| Komponen         | Teknologi                              |
| ---------------- | -------------------------------------- |
| Backend          | Laravel                                |
| Admin Panel      | Filament PHP                           |
| Frontend Runtime | Blade / Livewire / Filament Components |
| Database         | MySQL / MariaDB                        |
| Authentication   | NexaID / IAM SSO                       |
| Authorization    | Role-based Access Control              |
| Queue            | Laravel Queue                          |
| Cache            | Laravel Cache                          |
| Storage          | Local / S3 / MinIO                     |
| Infrastructure   | Docker / Docker Compose                |
| Package Manager  | Composer, NPM                          |

---

## Struktur Direktori

Struktur umum aplikasi:

```txt
sp-ikp/
├── app/
│   ├── Filament/
│   │   ├── Resources/
│   │   ├── Pages/
│   │   └── Widgets/
│   ├── Models/
│   ├── Services/
│   ├── Policies/
│   └── Http/
│       ├── Controllers/
│       └── Middleware/
├── config/
│   ├── app.php
│   ├── auth.php
│   └── iam.php
├── database/
│   ├── migrations/
│   ├── seeders/
│   └── factories/
├── resources/
│   ├── views/
│   ├── css/
│   └── js/
├── routes/
│   ├── web.php
│   └── api.php
├── storage/
├── tests/
├── composer.json
├── package.json
└── README.md
```

---


Menggunakan local server:

```bash
php artisan serve
```

Atau menggunakan Docker:

```bash
docker compose up -d
```

---





## Integrasi SSO NexaID / IAM

Simple Plan menggunakan NexaID / IAM sebagai pusat autentikasi dan otorisasi.

Fungsi IAM:

* Login terpusat melalui SSO.
* Sinkronisasi data user.
* Sinkronisasi role.
* Sinkronisasi unit kerja.
* Validasi token.
* Pengelolaan akses aplikasi.

Alur login:

```mermaid
sequenceDiagram
    participant User
    participant Simple plan
    participant IAM as NexaID / IAM

    User->>SPSimplePlan: Akses aplikasi
    SPSimplePlan->>IAM: Redirect ke login SSO
    IAM->>User: Form login
    User->>IAM: Login menggunakan kredensial
    IAM->>SPSimpleplan: Callback dengan token
    SPSimplePlan->>IAM: Verifikasi token
    IAM->>SPSimpleplan: Data user, role, unit kerja
    SPSimpleplan->>User: Masuk dashboard
```

---


```

Contoh konfigurasi S3 / MinIO:

```env
FILESYSTEM_DISK=local

AWS_ACCESS_KEY_ID=
AWS_SECRET_ACCESS_KEY=
AWS_DEFAULT_REGION=us-east-1
AWS_BUCKET=
AWS_URL=
AWS_ENDPOINT=
AWS_USE_PATH_STYLE_ENDPOINT=true
```

---

## Testing Checklist

Gunakan checklist berikut setelah melakukan perubahan fitur atau deployment.

### Authentication

* [ ] User dapat login melalui NexaID / IAM.
* [ ] Callback SSO berhasil diproses.
* [ ] Token berhasil diverifikasi.
* [ ] Session tidak aktif setelah token expired.
* [ ] Logout berjalan normal.

### User & Role

* [ ] Data user tersinkron dari IAM.
* [ ] Role user tersinkron dengan benar.
* [ ] Hak akses sesuai role.
* [ ] User tanpa role tidak dapat mengakses modul yang dibatasi.
* [ ] Unit kerja user terbaca dengan benar.

### Laporan Insiden

* [ ] User dapat membuat laporan insiden.
* [ ] Validasi form berjalan.
* [ ] Data unit kerja tersimpan.
* [ ] Lampiran dapat diunggah jika fitur tersedia.
* [ ] Laporan masuk ke status awal yang benar.

### Workflow

* [ ] Laporan dapat diverifikasi.
* [ ] Laporan dapat ditolak atau dikembalikan.
* [ ] Investigasi dapat diisi.
* [ ] Rekomendasi dapat dibuat.
* [ ] Tindak lanjut dapat dipantau.
* [ ] Status berubah sesuai alur.

### Dashboard & Export

* [ ] Dashboard menampilkan data sesuai filter.
* [ ] Rekap berdasarkan periode berjalan.
* [ ] Export PDF berjalan.
* [ ] Export Excel berjalan.
* [ ] Data export sesuai data di aplikasi.

---

## Deployment Checklist

Sebelum deploy ke production, pastikan:

* [ ] `APP_ENV=production`
* [ ] `APP_DEBUG=false`
* [ ] `APP_KEY` sudah terisi.
* [ ] `APP_URL` sesuai domain aplikasi.
* [ ] Konfigurasi database production sudah benar.
* [ ] Konfigurasi IAM production sudah benar.
* [ ] Migration sudah diuji di staging.
* [ ] Storage sudah dikonfigurasi.
* [ ] Queue worker aktif jika digunakan.
* [ ] Scheduler aktif jika digunakan.
* [ ] Permission folder `storage` dan `bootstrap/cache` sudah benar.
* [ ] Log tidak dalam mode debug berlebihan.
* [ ] Backup database tersedia.
* [ ] Monitoring error/log tersedia.

Command umum production:

```bash
composer install --no-dev --optimize-autoloader
npm ci
npm run build

php artisan migrate --force
php artisan config:cache
php artisan route:cache
php artisan view:cache
php artisan event:cache
```

---

## Command Artisan yang Sering Digunakan

```bash
# Generate key
php artisan key:generate

# Migration
php artisan migrate
php artisan migrate:status
php artisan migrate --force

# Seeder
php artisan db:seed

# Clear cache
php artisan optimize:clear

# Build cache production
php artisan config:cache
php artisan route:cache
php artisan view:cache

# Queue
php artisan queue:work

# Storage
php artisan storage:link
```

---

## Prinsip Desain Sistem

Simple_plan dikembangkan dengan beberapa prinsip utama:

1. **Workflow-first**
   Setiap data insiden harus memiliki alur, status, dan proses yang jelas.

2. **Audit-friendly**
   Data penting sebaiknya mudah ditelusuri untuk kebutuhan evaluasi dan pemeriksaan.

3. **Role-aware**
   Tampilan dan akses sistem mengikuti peran pengguna.

4. **Unit-based Access**
   Data dapat dibatasi berdasarkan unit kerja pengguna.

5. **Integration-ready**
   Sistem disiapkan untuk terhubung dengan IAM dan aplikasi mutu lainnya.

6. **Operational Simplicity**
   Fitur dibuat agar mudah digunakan oleh pengguna non-teknis di lingkungan rumah sakit.

---


---

## Roadmap

Beberapa pengembangan yang dapat dilakukan ke depan:

* [ ] Pemisahan Entity Antara Insiden dan Investigasi.
* [ ] Reminder tindak lanjut otomatis.
* [ ] Notifikasi email atau WhatsApp internal (Telegram).
* [ ] Export laporan KPRS.
* [ ] Integrasi insight ke Sistem lainya.
* [ ] API internal untuk rekap data.
* [ ] SLA monitoring untuk tindak lanjut.

---

## Catatan Pengembangan

Beberapa hal yang perlu diperhatikan saat mengembangkan fitur baru:

* Jangan mengubah alur status tanpa mempertimbangkan efek ke laporan dan dashboard.
* Pastikan setiap perubahan akses diuji dengan beberapa role berbeda.
* Hindari hardcode unit kerja atau role.
* Gunakan konfigurasi IAM untuk mapping user, role, dan unit kerja.
* Pastikan export laporan mengikuti data hasil filter.
* Validasi input penting terutama pada laporan, investigasi, dan tindak lanjut.
* Gunakan migration untuk semua perubahan struktur database.

---



## License

Aplikasi ini dikembangkan untuk kebutuhan internal ekosistem RSCH.

Penggunaan, distribusi, dan modifikasi mengikuti kebijakan internal pemilik sistem.

---
