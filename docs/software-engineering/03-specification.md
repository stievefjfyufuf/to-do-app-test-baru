# Requirements Specification - To-Do App Mahasiswa

Status: Draft untuk prioritisasi; belum menjadi baseline final  
Tanggal: 29 Juni 2026  
Sumber: `01-inception.md` (`DOC-001`) dan `02-elicitation.md` (`DOC-002`)

## 1. Specification Boundary

Dokumen ini menerjemahkan kebutuhan yang telah ditemukan menjadi perilaku yang dapat diuji. Priority seluruh requirement masih `TBD` karena penentuan prioritas merupakan keluaran tahap `04-se-prioritization`.

- `Ready`: cukup jelas untuk dibawa ke prioritisasi, tetapi tetap memerlukan persetujuan product owner.
- `Candidate`: dapat diuji sebagai usulan, tetapi bersumber dari kebutuhan yang belum tervalidasi atau konflik scope.
- `Blocked`: belum boleh menjadi requirement final sebelum pertanyaan atau konflik terkait diselesaikan.

## 2. Actors

| Actor | Upstream ID | Description |
|---|---|---|
| Mahasiswa | STK-001 | Pengguna utama yang mencatat dan mengelola tugas akademik |
| Product owner | STK-002 | Pemilik keputusan scope, prioritas, dan ukuran keberhasilan |
| Developer | STK-003 | Pihak yang membangun dan memelihara sistem |
| Tester/evaluator | STK-004 | Pihak yang memverifikasi perilaku dan kualitas sistem |
| Administrator layanan | STK-005 | Pihak yang mengoperasikan layanan, backup, dan pemulihan |
| Kolaborator | Turunan STK-001; belum tervalidasi | Pengguna lain yang menerima akses atau assignment tugas |

## 3. Functional Requirements

### 3.1 Core Task Management

| ID | Status | Requirement | Source | Priority | Acceptance Criteria |
|---|---|---|---|---|---|
| REQ-001 | Ready | Mahasiswa dapat membuat tugas dengan judul wajib serta deskripsi, prioritas, tenggat, dan status sebagai data opsional/default yang ditentukan. | GOAL-001; ASSUMP-003; NEED-002, NEED-003 | TBD | AC-001, AC-002 |
| REQ-002 | Ready | Sistem menampilkan tugas aktif dan selesai serta detail setiap tugas kepada pemiliknya. | GOAL-002; NEED-003, NEED-011 | TBD | AC-003 |
| REQ-003 | Ready | Pemilik dapat mengubah data tugas yang tersimpan. | GOAL-001, GOAL-002; DOC-001 Scope | TBD | AC-004 |
| REQ-004 | Ready | Pemilik dapat menandai tugas selesai dan mengembalikannya menjadi aktif. | GOAL-002; NEED-014; DOC-001 Scope | TBD | AC-005 |
| REQ-005 | Ready | Pemilik dapat meminta penghapusan tugas dan sistem meminta konfirmasi sebelum tugas tidak lagi tampil pada daftar aktif. | GOAL-002, GOAL-006; DOC-001 Scope | TBD | AC-006 |
| REQ-006 | Ready | Mahasiswa dapat memfilter dan mengurutkan tugas berdasarkan status, prioritas, dan tenggat. | GOAL-002, GOAL-003; NEED-003, NEED-008 | TBD | AC-007 |
| REQ-007 | Ready | Mahasiswa dapat menetapkan dan mengubah prioritas serta tenggat tugas. | GOAL-003; NEED-008 | TBD | AC-008 |
| REQ-008 | Ready | Sistem mempertahankan data tugas setelah aplikasi ditutup, dibuka kembali, atau halaman dimuat ulang. | GOAL-006; DOC-001 Success Signals | TBD | AC-009 |

### 3.2 Productivity Features

| ID | Status | Requirement | Source | Priority | Acceptance Criteria |
|---|---|---|---|---|---|
| REQ-009 | Ready | Mahasiswa dapat menambahkan dan menghapus kategori/tag pada tugas serta memfilter tugas berdasarkan tag. | GOAL-003; NEED-008 | TBD | AC-010 |
| REQ-010 | Candidate | Mahasiswa dapat membagi satu tugas menjadi subtugas dan melihat kemajuan subtugas. | GOAL-003; NEED-008; CONF-001 | TBD | AC-011 |
| REQ-011 | Candidate | Mahasiswa dapat menetapkan pola pengulangan tugas dan sistem membuat occurrence berikutnya sesuai pola yang disetujui. | GOAL-003; NEED-008; CONF-001 | TBD | AC-012 |
| REQ-012 | Candidate | Mahasiswa dapat menetapkan pengingat terhadap tenggat dan sistem menyampaikan pengingat melalui kanal yang disetujui. | GOAL-003; NEED-002, NEED-008; CONF-001 | TBD | AC-013 |
| REQ-013 | Ready | Mahasiswa dapat melihat tugas bertenggat pada tampilan kalender dan membuka detailnya dari tanggal terkait. | GOAL-002, GOAL-003; NEED-009 | TBD | AC-014 |
| REQ-014 | Ready | Mahasiswa dapat melihat tugas dalam kolom status kanban dan memindahkan tugas antarstatus. | GOAL-002, GOAL-003; NEED-010 | TBD | AC-015 |

### 3.3 Account, Platform, Offline, and Synchronization

| ID | Status | Requirement | Source | Priority | Acceptance Criteria |
|---|---|---|---|---|---|
| REQ-015 | Ready | Mahasiswa dapat membuat akun, masuk, dan keluar sehingga data tugas dapat dikaitkan dengan akunnya. | GOAL-006; NEED-006 | TBD | AC-016 |
| REQ-016 | Candidate | Akun yang sama dapat digunakan pada web dan Android untuk mengakses data pengguna. | GOAL-004, GOAL-007; NEED-004, NEED-007; CON-001 | TBD | AC-018 |
| REQ-017 | Candidate | Ketika offline, mahasiswa dapat melihat data yang telah tersedia pada perangkat dan melakukan operasi inti yang telah disepakati; perubahan ditandai belum tersinkronisasi. | GOAL-001, GOAL-002, GOAL-006; NEED-005, NEED-019; AMB-003 | TBD | AC-019 |
| REQ-018 | Candidate | Ketika koneksi kembali, sistem menyinkronkan perubahan lokal dengan akun dan menunjukkan hasil sinkronisasi kepada mahasiswa tanpa menghapus perubahan secara diam-diam. | GOAL-006; NEED-007, NEED-019; Q-017 | TBD | AC-020, AC-021 |

### 3.4 Collaboration - Blocked by Scope Decision

| ID | Status | Requirement | Source | Priority | Acceptance Criteria |
|---|---|---|---|---|---|
| REQ-019 | Blocked | Pemilik tugas dapat mengundang pengguna lain untuk melihat atau berpartisipasi pada tugas sesuai izin yang diberikan. | GOAL-007; NEED-012, NEED-021; CONF-001, CONF-003 | TBD | AC-022 |
| REQ-020 | Blocked | Pemilik atau pihak yang diberi wewenang dapat menugaskan tugas kepada kolaborator, dan penerima dapat melihat assignment tersebut. | GOAL-007; NEED-013, NEED-021; CONF-001, CONF-003 | TBD | AC-023 |
| REQ-021 | Blocked | Sistem menegakkan izin lihat, ubah, selesaikan, assign, dan bagikan berdasarkan peran kolaborasi yang disetujui. | GOAL-006, GOAL-007; NEED-016, NEED-017, NEED-021; AMB-005 | TBD | AC-024 |

### 3.5 Data Control and Product Measurement

| ID | Status | Requirement | Source | Priority | Acceptance Criteria |
|---|---|---|---|---|---|
| REQ-022 | Candidate | Pengguna dapat memulihkan tugas yang dihapus biasa selama 30 hari dan dapat meminta penghapusan permanen dengan konfirmasi. | GOAL-006; NEED-020; AMB-009 | TBD | AC-025 |
| REQ-023 | Candidate | Pengguna dapat mengekspor data miliknya dalam format umum yang dapat dibaca mesin. | GOAL-006; NEED-016, NEED-020; AMB-009 | TBD | AC-026 |
| REQ-024 | Candidate | Pengguna dapat meminta penghapusan akun dan data melalui alur konfirmasi serta masa tenggang yang disetujui. | GOAL-006; NEED-016, NEED-020; AMB-009 | TBD | AC-027 |
| REQ-025 | Ready | Sistem mencatat jumlah tugas yang diselesaikan per pengguna dan periode untuk ditampilkan kepada pengguna tersebut. | GOAL-005; NEED-014 | TBD | AC-028 |
| REQ-026 | Blocked | Sistem mendukung pengukuran hubungan penggunaan aplikasi dengan hasil akademik tanpa menyatakan hubungan sebab-akibat yang belum terbukti. | GOAL-005; NEED-015; AMB-007 | TBD | Belum dibuat; metode studi harus diputuskan melalui Q-014/Q-021 |

## 4. Non-Functional Requirements

Semua ambang di bawah adalah target kandidat untuk divalidasi oleh STK-002, STK-003, STK-004, dan STK-005. Angka tersebut belum menjadi komitmen rilis.

| ID | Status | Attribute | Requirement | Measurement | Source |
|---|---|---|---|---|---|
| NFR-001 | Candidate | Usability | Sedikitnya 80% dari minimal 5 mahasiswa uji dapat membuat, menemukan, mengubah, dan menyelesaikan tugas tanpa bantuan fasilitator. | Moderated usability test dengan skenario AC-001, AC-003, AC-004, AC-005 | GOAL-005; DOC-001 Success Signals |
| NFR-002 | Candidate | Performance | Pada perangkat dan jaringan minimum yang kelak disetujui, 95% pembukaan daftar tugas lokal selesai dalam 2 detik untuk 1.000 tugas milik pengguna. | Instrumented performance test | GOAL-002; NEED-003; Q-019 |
| NFR-003 | Candidate | Reliability | Operasi tugas yang telah dikonfirmasi berhasil tidak boleh hilang setelah restart aplikasi atau reload halaman. | Automated persistence and restart test; 0 kehilangan pada suite rilis | GOAL-006; REQ-008 |
| NFR-004 | Candidate | Offline reliability | Perubahan yang dilakukan offline tetap tersedia setelah restart dan memiliki status pending sampai berhasil atau gagal disinkronkan secara eksplisit. | Offline/reconnect integration test; 0 silent data loss | GOAL-006; NEED-005, NEED-019 |
| NFR-005 | Candidate | Synchronization | Setelah koneksi stabil kembali, perubahan tanpa konflik terlihat pada perangkat kedua dalam waktu maksimal 30 detik; konflik tidak boleh ditimpa diam-diam. | Two-device synchronization test | GOAL-006; NEED-007, NEED-019; Q-017 |
| NFR-006 | Candidate | Security | Data nonpublik hanya dapat diakses oleh akun yang berwenang; kredensial tidak disimpan sebagai teks biasa; data ditransmisikan melalui koneksi terenkripsi. | Authorization tests, configuration review, and credential-storage inspection | NEED-016, NEED-017; ASSUMP-006 |
| NFR-007 | Candidate | Privacy | Pengguna dapat mengetahui data utama yang disimpan serta meminta ekspor dan penghapusan data miliknya. | Privacy-flow test dan pemeriksaan terhadap REQ-023/REQ-024 | NEED-016, NEED-020 |
| NFR-008 | Candidate | Accessibility | Semua alur inti dapat dijalankan dengan keyboard, kontrol memiliki nama yang dapat dikenali teknologi bantu, fokus terlihat, dan kontras teks normal minimal 4.5:1. | Manual keyboard/screen-reader checks dan automated contrast scan | NEED-018; Q-022 |
| NFR-009 | Candidate | Availability | Layanan sinkronisasi tersedia sedikitnya 99.5% per bulan di luar pemeliharaan terjadwal; aplikasi tetap menyediakan cakupan offline yang disepakati saat layanan tidak tersedia. | Service monitoring report bulanan | GOAL-006; NEED-005, NEED-007 |
| NFR-010 | Candidate | Backup and Recovery | Backup data layanan dibuat minimal setiap 24 jam; uji pemulihan menunjukkan kehilangan data maksimal 24 jam dan layanan pulih maksimal 4 jam. | Quarterly restore drill; RPO <= 24 jam, RTO <= 4 jam | NEED-020; Q-024 |
| NFR-011 | Candidate | Maintainability | Logika domain untuk operasi inti memiliki automated test, dan seluruh test wajib lulus sebelum perubahan dirilis. | CI report dengan 100% pass untuk suite wajib; cakupan cabang target 80% pada modul domain inti | GOAL-007; STK-003 |

## 5. User Stories

| ID | User Story | Related Requirements |
|---|---|---|
| US-001 | Sebagai mahasiswa, saya ingin mencatat tugas beserta tenggatnya agar saya tidak melupakannya. | REQ-001, REQ-007 |
| US-002 | Sebagai mahasiswa dengan banyak tugas, saya ingin memfilter dan mengurutkan tugas agar mengetahui pekerjaan berikutnya. | REQ-006, REQ-009 |
| US-003 | Sebagai mahasiswa, saya ingin menandai tugas dan subtugas selesai agar dapat melihat kemajuan pekerjaan. | REQ-004, REQ-010 |
| US-004 | Sebagai mahasiswa, saya ingin melihat tugas pada kalender agar dapat memahami beban berdasarkan tanggal. | REQ-013 |
| US-005 | Sebagai mahasiswa, saya ingin mengatur tugas pada kanban agar dapat melihat status pekerjaan. | REQ-014 |
| US-006 | Sebagai mahasiswa yang kadang tidak memiliki koneksi, saya ingin tetap mengakses dan memperbarui tugas agar pekerjaan tidak terhenti. | REQ-017, REQ-018 |
| US-007 | Sebagai mahasiswa yang memakai web dan Android, saya ingin data tersedia pada kedua perangkat agar tidak mencatat ulang. | REQ-016, REQ-018 |
| US-008 | Sebagai pemilik tugas, saya ingin mengontrol siapa yang dapat melihat atau mengubah tugas agar data pribadi tetap terlindungi. | REQ-019, REQ-021 |
| US-009 | Sebagai mahasiswa, saya ingin menugaskan tugas bersama kepada kolaborator agar tanggung jawab terlihat jelas. | REQ-020 |
| US-010 | Sebagai pengguna, saya ingin memulihkan, mengekspor, atau menghapus data saya agar tetap memiliki kendali atas data pribadi. | REQ-022, REQ-023, REQ-024 |
| US-011 | Sebagai mahasiswa, saya ingin melihat jumlah tugas yang selesai agar dapat memantau konsistensi belajar. | REQ-025 |
| US-012 | Sebagai administrator layanan, saya ingin backup dapat dipulihkan agar kegagalan layanan tidak menghilangkan seluruh data pengguna. | NFR-010 |

## 6. Acceptance Criteria

### Core Task Management

- **AC-001 - Membuat tugas valid**  
  Given mahasiswa telah masuk dan membuka form tugas  
  When mahasiswa mengisi judul serta data opsional lalu menyimpan  
  Then sistem membuat satu tugas dan menampilkannya dengan nilai yang dimasukkan.

- **AC-002 - Menolak judul kosong**  
  Given form tugas terbuka  
  When mahasiswa menyimpan tanpa judul yang berisi karakter non-spasi  
  Then sistem tidak membuat tugas dan menunjukkan kesalahan pada kolom judul.

- **AC-003 - Melihat tugas**  
  Given akun memiliki tugas aktif dan selesai  
  When mahasiswa membuka daftar dan memilih masing-masing status  
  Then sistem menampilkan tugas sesuai status dan membuka detail tugas yang dipilih.

- **AC-004 - Mengubah tugas**  
  Given mahasiswa memiliki sebuah tugas  
  When mahasiswa mengubah data lalu menyimpan  
  Then detail tugas menampilkan nilai terbaru dan tidak membuat tugas duplikat.

- **AC-005 - Menyelesaikan dan membuka kembali**  
  Given sebuah tugas aktif  
  When mahasiswa menandainya selesai lalu mengembalikannya menjadi aktif  
  Then status dan tampilan tugas berubah mengikuti setiap tindakan.

- **AC-006 - Konfirmasi penghapusan**  
  Given mahasiswa meminta menghapus tugas  
  When mahasiswa membatalkan konfirmasi  
  Then tugas tetap tersedia; dan ketika mahasiswa mengonfirmasi, tugas tidak lagi tampil pada daftar aktif.

- **AC-007 - Filter dan urutkan**  
  Given terdapat tugas dengan status, prioritas, dan tenggat berbeda  
  When mahasiswa menerapkan filter atau urutan  
  Then seluruh tugas yang tampil sesuai kriteria dan urutan yang dipilih.

- **AC-008 - Prioritas dan tenggat**  
  Given mahasiswa membuka tugas miliknya  
  When mahasiswa menetapkan atau mengubah prioritas dan tenggat yang valid  
  Then nilai tersebut tersimpan dan terlihat pada detail tugas.

- **AC-009 - Persistensi**  
  Given suatu operasi tugas telah dikonfirmasi berhasil  
  When aplikasi ditutup dan dibuka kembali atau halaman dimuat ulang  
  Then hasil operasi tersebut tetap tersedia.

### Productivity Features

- **AC-010 - Tag**  
  Given beberapa tugas memiliki tag berbeda  
  When mahasiswa memilih satu tag sebagai filter  
  Then hanya tugas dengan tag tersebut yang tampil; tag juga dapat ditambahkan dan dilepas dari tugas milik pengguna.

- **AC-011 - Subtugas**  
  Given mahasiswa membuka suatu tugas  
  When subtugas ditambahkan dan status salah satunya diubah  
  Then daftar subtugas dan ringkasan kemajuan diperbarui tanpa mengubah status subtugas lain.

- **AC-012 - Tugas berulang**  
  Given pola pengulangan valid telah ditetapkan  
  When kondisi pembentukan occurrence berikutnya tercapai  
  Then satu occurrence baru dibuat sesuai pola tanpa menggandakan occurrence yang sama.

- **AC-013 - Pengingat**  
  Given pengingat valid telah ditetapkan dan izin kanal tersedia  
  When waktu pengingat tercapai  
  Then satu pengingat dikirim dan mengarah ke tugas terkait.

- **AC-014 - Kalender**  
  Given beberapa tugas memiliki tenggat  
  When mahasiswa membuka kalender dan memilih tanggal atau tugas  
  Then tugas tampil pada tanggal yang sesuai dan detailnya dapat dibuka.

- **AC-015 - Kanban**  
  Given tugas tampil pada kolom status saat ini  
  When mahasiswa memindahkan tugas ke kolom status lain  
  Then status tugas berubah satu kali dan tetap konsisten pada daftar serta detail.

### Account, Offline, and Synchronization

- **AC-016 - Akses akun**  
  Given data pendaftaran atau login valid  
  When mahasiswa menyelesaikan proses autentikasi  
  Then sistem memulai sesi akun; setelah logout, area pribadi tidak dapat dibuka tanpa autentikasi ulang.

- **AC-017 - Isolasi data**  
  Given dua akun berbeda memiliki tugas pribadi  
  When salah satu akun mencoba membuka pengenal tugas akun lain tanpa izin  
  Then sistem menolak akses dan tidak mengungkap isi tugas.

- **AC-018 - Dua platform**  
  Given akun yang sama digunakan pada web dan Android  
  When sinkronisasi berhasil  
  Then kedua platform menampilkan himpunan data akun yang sama.

- **AC-019 - Operasi offline**  
  Given perangkat telah memiliki data akun dan koneksi terputus  
  When mahasiswa melakukan salah satu operasi inti yang telah disepakati  
  Then perubahan tetap terlihat setelah restart dan ditandai menunggu sinkronisasi.

- **AC-020 - Sinkronisasi kembali**  
  Given terdapat perubahan lokal tanpa konflik yang menunggu sinkronisasi  
  When koneksi stabil kembali  
  Then perubahan dikirim satu kali, status pending hilang setelah konfirmasi, dan perangkat lain menerima hasilnya.

- **AC-021 - Konflik sinkronisasi**  
  Given entitas yang sama diubah pada dua perangkat sebelum keduanya tersinkronisasi  
  When kedua perubahan mencapai layanan  
  Then sistem mengikuti aturan resolusi yang kelak disetujui, menyimpan jejak hasil, dan tidak menghapus perubahan secara diam-diam.

### Collaboration and Data Control

- **AC-022 - Berbagi tugas**  
  Given pemilik memilih pengguna lain dan izin yang valid  
  When undangan diterima  
  Then penerima dapat mengakses tugas hanya sesuai izin tersebut; pengguna lain tetap ditolak.

- **AC-023 - Assignment**  
  Given pengguna berwenang memilih kolaborator pada tugas bersama  
  When assignment disimpan  
  Then identitas penerima tampil bagi pihak berwenang dan tugas tersedia pada daftar assignment penerima.

- **AC-024 - Penegakan izin**  
  Given kolaborator memiliki suatu peran  
  When kolaborator mencoba setiap tindakan yang diizinkan dan dilarang  
  Then sistem menerima tindakan yang diizinkan serta menolak tindakan lain tanpa mengubah data.

- **AC-025 - Pemulihan tugas**  
  Given tugas dihapus biasa kurang dari 30 hari lalu  
  When pemilik memulihkan tugas  
  Then tugas kembali dengan data sebelumnya; penghapusan permanen selalu membutuhkan konfirmasi terpisah.

- **AC-026 - Ekspor data**  
  Given pengguna terautentikasi meminta ekspor  
  When ekspor selesai  
  Then pengguna menerima data miliknya dalam format umum dan ekspor tidak memuat data yang tidak diizinkan.

- **AC-027 - Penghapusan akun**  
  Given pengguna terautentikasi meminta penghapusan akun  
  When pengguna mengonfirmasi permintaan  
  Then sistem menyatakan masa tenggang dan menyediakan pembatalan sampai batas yang disetujui sebelum penghapusan permanen.

- **AC-028 - Statistik tugas selesai**  
  Given mahasiswa menyelesaikan tugas pada beberapa tanggal  
  When mahasiswa memilih periode statistik  
  Then sistem menampilkan jumlah tugas selesai dalam periode tersebut tanpa memasukkan tugas di luar periode.

## 7. Traceability Matrix

| Requirement | Need/Source | Goal | Stakeholder | Verification Link |
|---|---|---|---|---|
| REQ-001 | NEED-002, NEED-003; ASSUMP-003 | GOAL-001 | STK-001 | AC-001, AC-002 |
| REQ-002 | NEED-003, NEED-011 | GOAL-002 | STK-001 | AC-003 |
| REQ-003 | DOC-001 Scope | GOAL-001, GOAL-002 | STK-001 | AC-004 |
| REQ-004 | NEED-014; DOC-001 Scope | GOAL-002 | STK-001 | AC-005 |
| REQ-005 | DOC-001 Scope | GOAL-002, GOAL-006 | STK-001 | AC-006 |
| REQ-006 | NEED-003, NEED-008 | GOAL-002, GOAL-003 | STK-001 | AC-007 |
| REQ-007 | NEED-008 | GOAL-003 | STK-001 | AC-008 |
| REQ-008 | DOC-001 Success Signals | GOAL-006 | STK-001, STK-003 | AC-009, NFR-003 |
| REQ-009 | NEED-008 | GOAL-003 | STK-001 | AC-010 |
| REQ-010 | NEED-008; CONF-001 | GOAL-003 | STK-001, STK-002 | AC-011 |
| REQ-011 | NEED-008; CONF-001 | GOAL-003 | STK-001, STK-002 | AC-012 |
| REQ-012 | NEED-002, NEED-008; CONF-001 | GOAL-003 | STK-001, STK-002 | AC-013 |
| REQ-013 | NEED-009 | GOAL-002, GOAL-003 | STK-001 | AC-014 |
| REQ-014 | NEED-010 | GOAL-002, GOAL-003 | STK-001 | AC-015 |
| REQ-015 | NEED-006 | GOAL-006 | STK-001, STK-003 | AC-016; authorization covered by AC-017/NFR-006 as candidate quality scope |
| REQ-016 | NEED-004, NEED-007; CON-001 | GOAL-004, GOAL-007 | STK-001, STK-002 | AC-018 |
| REQ-017 | NEED-005, NEED-019; AMB-003 | GOAL-001, GOAL-002, GOAL-006 | STK-001, STK-003 | AC-019, NFR-004 |
| REQ-018 | NEED-007, NEED-019; Q-017 | GOAL-006 | STK-001, STK-003 | AC-020, AC-021, NFR-005 |
| REQ-019 | NEED-012, NEED-021; CONF-001, CONF-003 | GOAL-007 | STK-001, STK-002 | AC-022 |
| REQ-020 | NEED-013, NEED-021; CONF-001, CONF-003 | GOAL-007 | STK-001, STK-002 | AC-023 |
| REQ-021 | NEED-016, NEED-017, NEED-021; AMB-005 | GOAL-006, GOAL-007 | STK-001, STK-003 | AC-024, NFR-006 |
| REQ-022 | NEED-020; AMB-009 | GOAL-006 | STK-001, STK-005 | AC-025 |
| REQ-023 | NEED-016, NEED-020; AMB-009 | GOAL-006 | STK-001, STK-005 | AC-026, NFR-007 |
| REQ-024 | NEED-016, NEED-020; AMB-009 | GOAL-006 | STK-001, STK-005 | AC-027, NFR-007 |
| REQ-025 | NEED-014 | GOAL-005 | STK-001, STK-004 | AC-028 |
| REQ-026 | NEED-015; AMB-007 | GOAL-005 | STK-002, STK-004 | Q-014, Q-021 |

## 8. Open Decisions and Blockers

| ID | Decision Required | Blocks | Owner |
|---|---|---|---|
| DEC-001 | Tetapkan fitur MVP versus fase berikutnya. | REQ-011, REQ-012, REQ-019 sampai REQ-021; CONF-001, CONF-002 | STK-002 |
| DEC-002 | Tetapkan deadline, anggaran, ukuran tim, dan kemampuan teknologi. | Feasibility seluruh scope; Q-013 | STK-002, STK-003 |
| DEC-003 | Pilih platform rilis pertama atau setujui dua platform sekaligus. | REQ-016; CON-001, AMB-004 | STK-002 |
| DEC-004 | Tentukan operasi yang wajib tersedia offline. | REQ-017, AC-019; Q-016 | STK-001, STK-002 |
| DEC-005 | Tentukan aturan konflik sinkronisasi. | REQ-018, AC-021; Q-017 | STK-002, STK-003 |
| DEC-006 | Tentukan peran, izin, kepemilikan, dan penerima kolaborasi. | REQ-019 sampai REQ-021; AMB-005, CONF-003 | STK-001, STK-002 |
| DEC-007 | Setujui atau ubah kebijakan pemulihan 30 hari, backup, ekspor, dan penghapusan akun. | REQ-022 sampai REQ-024; NFR-010; AMB-009 | STK-002, STK-005 |
| DEC-008 | Tetapkan standar aksesibilitas dan profil kebutuhan pengguna. | NFR-008; NEED-018, Q-022 | STK-001, STK-004 |
| DEC-009 | Tetapkan metode, baseline, periode, dan target evaluasi hasil akademik. | REQ-026; AMB-007 | STK-002, STK-004 |
| DEC-010 | Validasi target angka pada seluruh NFR. | NFR-001 sampai NFR-011 | STK-002, STK-003, STK-004, STK-005 |

## 9. Handoff to Prioritization

Tahap `04-se-prioritization` harus memprioritaskan REQ-001 sampai REQ-025 dan NFR-001 sampai NFR-011 dengan mempertimbangkan CONF-001 sampai CONF-004. Item berstatus `Blocked` tidak boleh masuk committed MVP sebelum DEC terkait selesai. REQ-026 tetap menjadi pertanyaan penelitian, bukan fitur implementasi, sampai metode evaluasi disetujui.
