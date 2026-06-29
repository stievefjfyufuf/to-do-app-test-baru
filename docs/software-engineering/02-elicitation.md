# Elicitation Notes — To-Do App Mahasiswa

Status: Draft hasil wawancara awal; memerlukan validasi lanjutan  
Tanggal: 29 Juni 2026  
Sumber utama: `docs/software-engineering/01-inception.md` (`DOC-001`)

## Ringkasan Konteks

Jawaban pada OQ-001 sampai OQ-012 diperlakukan sebagai masukan awal dari STK-002 (product owner/pemilik proyek). Jawaban tersebut belum dianggap mewakili seluruh STK-001 (mahasiswa) sampai divalidasi melalui wawancara, survei, atau observasi terhadap mahasiswa sasaran.

## Elicitation Plan

| Tahap | Stakeholder | Teknik | Tujuan | Output yang Diharapkan |
|---|---|---|---|---|
| 1 | STK-002 Product owner | Interview semi-terstruktur | Menegaskan visi, prioritas, batas MVP, waktu, anggaran, dan ukuran tim | Keputusan scope dan indikator keberhasilan |
| 2 | STK-001 Mahasiswa | Interview 5–8 peserta | Menggali kebiasaan, pain point, konteks offline, serta kebutuhan tersembunyi | Kebutuhan mentah dan variasi workflow |
| 3 | STK-001 Mahasiswa | Survei 20+ responden bila memungkinkan | Mengukur frekuensi masalah dan preferensi fitur secara lebih luas | Urutan kebutuhan berdasarkan bukti pengguna |
| 4 | STK-001 dan STK-002 | Workshop prioritas | Menyelesaikan konflik seluruh fitur dianggap wajib versus batas MVP | Scope MVP yang disepakati |
| 5 | STK-001 Mahasiswa | Observasi singkat/contextual inquiry | Melihat cara tugas kuliah diterima, dicatat, dan diselesaikan | Kesenjangan antara jawaban dan perilaku nyata |
| 6 | STK-003 Developer dan STK-005 Administrator | Workshop risiko/feasibility | Menggali konsekuensi offline, sinkronisasi, keamanan, backup, dan platform | Constraint dan risiko operasional |
| 7 | STK-004 Tester/evaluator | Interview dan document analysis | Menetapkan cara mengevaluasi usability, aksesibilitas, dan dampak akademik | Kriteria evaluasi yang dapat diukur |

## Question Bank dan Jawaban Awal

### STK-001 — Mahasiswa

| ID | Goal | Question | Purpose | Answer Saat Ini | Follow-up Needed |
|---|---|---|---|---|---|
| Q-001 | GOAL-001, GOAL-003 | Dari mana tugas kuliah biasanya datang dan kapan Anda mencatatnya? | Memahami workflow nyata | Belum ada jawaban langsung | Ya; wawancara dan observasi mahasiswa |
| Q-002 | GOAL-001 | Bagian apa yang paling lambat atau merepotkan saat mencatat tugas? | Menggali kebutuhan input cepat | Belum diketahui | Ya |
| Q-003 | GOAL-002, GOAL-003 | Mengapa tugas biasanya terlupakan atau menumpuk? | Menemukan akar pain point | Lupa tugas dan terlalu banyak tugas (OQ-002) | Ya; gali penyebab dan frekuensi |
| Q-004 | GOAL-003 | Bagaimana Anda menentukan tugas yang dikerjakan lebih dahulu? | Memahami aturan prioritas pengguna | Belum diketahui | Ya |
| Q-005 | GOAL-001, GOAL-002 | Dalam situasi apa koneksi internet tidak tersedia? | Memvalidasi kebutuhan offline | Offline dianggap perlu ketika mahasiswa tidak memiliki data internet (OQ-004) | Ya; ukur frekuensi dan aktivitas yang harus tetap tersedia |
| Q-006 | GOAL-002 | Perangkat apa yang paling sering digunakan untuk mengelola tugas? | Menentukan konteks platform | Web dan Android diminta (OQ-003) | Ya; tentukan platform utama dan pola perpindahan perangkat |
| Q-007 | GOAL-002, GOAL-003 | Informasi apa yang harus terlihat pada daftar, kalender, dan kanban? | Menggali kebutuhan tampilan tanpa menetapkan desain detail | Kalender dan kanban diminta (OQ-007) | Ya |
| Q-008 | GOAL-001, GOAL-003 | Kapan subtugas, tugas berulang, tag, prioritas, tenggat, dan pengingat digunakan? | Menguji apakah semua fitur benar-benar wajib | Semuanya dianggap penting (OQ-006) | Ya; minta contoh nyata untuk tiap fitur |
| Q-009 | GOAL-002 | Dengan siapa tugas dibagikan atau ditugaskan, dan apa hak masing-masing orang? | Memahami batas kolaborasi | Tugas dapat pribadi, dibagikan, dan ditugaskan (OQ-008) | Ya; definisikan peran dan izin |
| Q-010 | GOAL-005 | Apa yang membuat aplikasi mudah digunakan bagi Anda? | Menggali usability dan aksesibilitas | Kebutuhan aksesibilitas dinyatakan ada (OQ-011) | Ya; identifikasi kebutuhan spesifik |

### STK-002 — Product Owner/Pemilik Proyek

| ID | Goal | Question | Purpose | Answer Saat Ini | Follow-up Needed |
|---|---|---|---|---|---|
| Q-011 | GOAL-004 | Siapa segmen pengguna pertama? | Menetapkan target validasi | Mahasiswa (OQ-001) | Ya; persempit jenjang, konteks, dan karakteristik |
| Q-012 | GOAL-004 | Mana kemampuan yang harus ada pada rilis pertama dan mana yang boleh menyusul? | Menetapkan batas MVP | Seluruh fitur pada OQ-006 dianggap penting | Ya; keputusan terblokir karena belum ada prioritas |
| Q-013 | GOAL-004 | Apa target tanggal, anggaran, ukuran tim, dan kemampuan teknologi tim? | Menentukan constraint delivery | Jawaban “tergantung total tugas dan waktu pengerjaan” belum menjawab constraint proyek (OQ-009) | Ya; wajib diklarifikasi |
| Q-014 | GOAL-005 | Bagaimana jumlah tugas selesai dan nilai akademik dibandingkan sebelum/sesudah penggunaan? | Membuat keberhasilan dapat dievaluasi | Keberhasilan dinilai dari jumlah tugas selesai dan nilai akademik (OQ-010) | Ya; butuh baseline, periode, dan target |
| Q-015 | GOAL-004, GOAL-005 | Apakah penggunaan berulang dan kemudahan pakai juga menjadi ukuran keberhasilan? | Menghindari metrik yang terlalu sempit | Belum diputuskan | Ya |

### STK-003 — Developer/Tim Pengembang

| ID | Goal | Question | Purpose | Answer Saat Ini | Follow-up Needed |
|---|---|---|---|---|---|
| Q-016 | GOAL-006 | Data dan tindakan apa yang wajib tersedia ketika offline? | Menentukan batas perilaku offline | Offline wajib, detail belum ada | Ya |
| Q-017 | GOAL-006 | Apa hasil yang diharapkan bila tugas yang sama berubah di dua perangkat sebelum sinkronisasi? | Menggali aturan konflik data | Belum diputuskan | Ya; keputusan produk diperlukan |
| Q-018 | GOAL-006, GOAL-007 | Apakah satu akun dapat digunakan pada web dan Android secara bersamaan? | Memvalidasi pola sinkronisasi | Akun dan sinkronisasi antarperangkat dibutuhkan (OQ-005) | Ya; detail sesi dan perangkat belum ada |
| Q-019 | GOAL-007 | Kemampuan tim dan batas delivery apa yang membatasi dua platform sekaligus? | Menggali feasibility tanpa memilih teknologi | Belum diketahui | Ya |

### STK-004 — Tester/Evaluator

| ID | Goal | Question | Purpose | Answer Saat Ini | Follow-up Needed |
|---|---|---|---|---|---|
| Q-020 | GOAL-005 | Tugas representatif apa yang harus dapat diselesaikan tanpa bantuan? | Menentukan skenario evaluasi | Membuat, menemukan, mengubah, dan menyelesaikan tugas dari DOC-001 | Ya; tetapkan sampel dan ambang keberhasilan |
| Q-021 | GOAL-005 | Bagaimana pengaruh aplikasi terhadap nilai akademik akan dibedakan dari faktor lain? | Menguji validitas metrik dampak | Belum ditentukan | Ya |
| Q-022 | GOAL-005 | Standar atau kebutuhan aksesibilitas apa yang menjadi target? | Memperjelas kebutuhan aksesibilitas | Aksesibilitas dibutuhkan, tetapi belum spesifik | Ya |

### STK-005 — Administrator Layanan

| ID | Goal | Question | Purpose | Answer Saat Ini | Follow-up Needed |
|---|---|---|---|---|---|
| Q-023 | GOAL-006 | Berapa lama data yang dihapus dapat dipulihkan? | Menetapkan kebijakan pemulihan | Belum diputuskan | Ya; rekomendasi awal tersedia di NEED-020 |
| Q-024 | GOAL-006 | Seberapa sering backup dilakukan dan berapa lama salinannya disimpan? | Menggali toleransi kehilangan data | Belum diputuskan | Ya |
| Q-025 | GOAL-006 | Format data apa yang perlu dapat diekspor dan oleh siapa? | Menggali portabilitas serta kontrol pengguna | Belum diputuskan | Ya |
| Q-026 | GOAL-006, GOAL-007 | Data pribadi apa yang disimpan dan siapa yang boleh mengaksesnya? | Menggali privasi dan otorisasi | Kebutuhan privasi dan keamanan dinyatakan ada (OQ-011) | Ya |

## Raw Needs

| ID | Type | Raw Need | Source | Traceability |
|---|---|---|---|---|
| NEED-001 | Explicit | Pengguna sasaran awal adalah mahasiswa. | STK-002, OQ-001 | GOAL-004 |
| NEED-002 | Pain point | Mahasiswa perlu mengurangi risiko melupakan tugas. | STK-002, OQ-002 | GOAL-001, GOAL-002 |
| NEED-003 | Pain point | Mahasiswa perlu menangani jumlah tugas yang banyak. | STK-002, OQ-002 | GOAL-002, GOAL-003 |
| NEED-004 | Explicit | Pengguna perlu mengakses layanan melalui web dan Android. | STK-002, OQ-003 | GOAL-004, GOAL-007 |
| NEED-005 | Constraint | Kemampuan inti yang belum ditentukan rinci perlu tetap dapat digunakan tanpa koneksi internet. | STK-002, OQ-004 | GOAL-001, GOAL-002, GOAL-006 |
| NEED-006 | Explicit | Pengguna memerlukan akun. | STK-002, OQ-005 | GOAL-006 |
| NEED-007 | Explicit | Data pengguna perlu tersedia lintas perangkat. | STK-002, OQ-005 | GOAL-006, GOAL-007 |
| NEED-008 | Explicit | Pengguna menganggap prioritas, tenggat, kategori/tag, subtugas, tugas berulang, dan pengingat penting. | STK-002, OQ-006 | GOAL-001, GOAL-003 |
| NEED-009 | Explicit | Pengguna perlu melihat tugas dalam kalender. | STK-002, OQ-007 | GOAL-002, GOAL-003 |
| NEED-010 | Explicit | Pengguna perlu melihat tugas dalam kanban. | STK-002, OQ-007 | GOAL-002, GOAL-003 |
| NEED-011 | Explicit | Tugas dapat bersifat pribadi. | STK-002, OQ-008 | GOAL-001, GOAL-002 |
| NEED-012 | Explicit | Pengguna perlu membagikan tugas kepada orang lain. | STK-002, OQ-008 | GOAL-007 |
| NEED-013 | Explicit | Pengguna perlu menugaskan tugas kepada orang lain. | STK-002, OQ-008 | GOAL-007 |
| NEED-014 | Explicit | Keberhasilan produk perlu mempertimbangkan jumlah tugas yang diselesaikan. | STK-002, OQ-010 | GOAL-005 |
| NEED-015 | Explicit | Keberhasilan produk diharapkan berkaitan dengan nilai akademik pengguna. | STK-002, OQ-010 | GOAL-005 |
| NEED-016 | Unresolved | Pengguna membutuhkan perlindungan privasi, tetapi jenis data, kontrol, dan batas akses belum dijelaskan. | STK-002, OQ-011 | GOAL-006; ASSUMP-006 |
| NEED-017 | Unresolved | Pengguna membutuhkan keamanan, tetapi risiko, tingkat perlindungan, dan model akses belum dijelaskan. | STK-002, OQ-011 | GOAL-006; ASSUMP-006 |
| NEED-018 | Unresolved | Aplikasi perlu dapat diakses oleh pengguna dengan kebutuhan beragam, tetapi kebutuhan spesifik belum dijelaskan. | STK-002, OQ-011 | GOAL-005 |
| NEED-019 | Inferred | Pengguna perlu mengetahui status sinkronisasi dan tidak kehilangan perubahan ketika berpindah antara offline dan online. | Inferensi dari STK-002, OQ-004/OQ-005 | GOAL-006 |
| NEED-020 | Proposed policy | Rekomendasi awal: penghapusan biasa masuk ke tempat pemulihan selama 30 hari; pengguna dapat memulihkan atau menghapus permanen; data akun dibackup secara berkala; pengguna dapat mengekspor data miliknya dalam format umum; penghapusan akun memiliki konfirmasi dan masa tenggang. | Rekomendasi analis untuk OQ-012; belum disetujui STK-002/STK-005 | GOAL-006; ASSUMP-006 |
| NEED-021 | Inferred | Dalam kolaborasi, pengguna perlu memahami siapa yang dapat melihat, mengubah, menyelesaikan, dan meneruskan tugas. | Inferensi dari STK-002, OQ-008 | GOAL-007 |

## Pain Points

- PP-001: Tugas mudah terlupakan (sumber: STK-002; terkait NEED-002).
- PP-002: Banyaknya tugas membuat mahasiswa kesulitan mengelola beban pekerjaan (sumber: STK-002; terkait NEED-003).
- PP-003: Ketergantungan pada koneksi internet dapat menghambat penggunaan ketika mahasiswa tidak memiliki akses data (sumber: STK-002; terkait NEED-005).

## Constraints Found

- CON-001: Aplikasi diharapkan mendukung web dan Android, tetapi platform prioritas belum ditentukan.
- CON-002: Penggunaan offline diwajibkan, sementara cakupan tindakan offline dan aturan sinkronisasi belum ditentukan.
- CON-003: Akun dan sinkronisasi antarperangkat diminta pada MVP.
- CON-004: Target waktu, anggaran, ukuran tim, dan kemampuan teknologi belum tersedia.
- CON-005: Privasi, keamanan, dan aksesibilitas wajib diperhatikan, tetapi belum memiliki tolok ukur.

## Ambiguities

- AMB-001 / Q-011: Istilah “mahasiswa” masih luas; jenjang, program studi, pola kuliah, dan konteks institusi belum dipersempit.
- AMB-002 / Q-008: “Semua fitur penting” belum membedakan kebutuhan wajib rilis pertama dari kebutuhan iterasi berikutnya.
- AMB-003 / Q-005/Q-016: “Harus offline” belum menjelaskan aktivitas apa yang tersedia offline atau berapa lama perangkat dapat tidak tersambung.
- AMB-004 / Q-006: Permintaan web dan Android belum menjawab platform yang menjadi prioritas pertama.
- AMB-005 / Q-009: Berbagi dan menugaskan tugas belum menjelaskan penerima, peran, izin, undangan, serta kepemilikan data.
- AMB-006 / Q-013: Jawaban tentang waktu pengerjaan belum menetapkan deadline, anggaran, ukuran tim, atau kapasitas proyek.
- AMB-007 / Q-014/Q-021: Nilai akademik dipengaruhi banyak faktor; metode atribusi dampak aplikasi belum ada.
- AMB-008 / Q-022: Privasi, keamanan, dan aksesibilitas disebut wajib tetapi belum didefinisikan secara terukur.
- AMB-009 / Q-023–Q-025: Kebijakan penghapusan, backup, pemulihan, dan ekspor belum disetujui; NEED-020 hanya rekomendasi awal.

## Conflicts

- CONF-001: DOC-001 menempatkan kolaborasi, assignment, recurring task, subtasks, dan notifikasi lintas perangkat di luar scope sampai divalidasi, tetapi jawaban OQ-006 dan OQ-008 menganggap kemampuan tersebut penting atau diperlukan. Resolusi: workshop prioritas dengan STK-001 dan STK-002.
- CONF-002: GOAL-004 mengarah pada MVP untuk validasi, sedangkan gabungan web, Android, offline, sinkronisasi, seluruh fitur produktivitas, kalender, kanban, dan kolaborasi menghasilkan scope besar. Resolusi: tetapkan batas waktu/kapasitas lalu urutkan kebutuhan berdasarkan bukti pengguna.
- CONF-003: ASSUMP-001 dan ASSUMP-004 menggambarkan penggunaan individual tanpa kolaborasi, sedangkan NEED-012 dan NEED-013 meminta berbagi dan assignment. Resolusi: STK-002 menentukan apakah asumsi dibatalkan atau kolaborasi dipindahkan ke fase berikutnya melalui proses perubahan baseline.
- CONF-004: ASSUMP-002 mengasumsikan satu zona waktu utama, sedangkan kolaborasi dapat melibatkan pengguna dengan zona waktu berbeda. Resolusi: validasi jangkauan kolaborasi sebelum specification.

## Recommended Next Elicitation Session

Sebelum masuk ke specification, lakukan satu sesi keputusan dengan STK-002 untuk menjawab Q-012, Q-013, serta memvalidasi NEED-020. Secara paralel, wawancarai beberapa STK-001 menggunakan Q-001 sampai Q-010 agar scope tidak hanya didasarkan pada asumsi product owner.

## Handoff ke Specification

NEED-001 sampai NEED-021 dapat menjadi input awal untuk `03-se-specification`, tetapi NEED-016 sampai NEED-021 harus tetap ditandai belum tervalidasi. AMB-001 sampai AMB-009 dan CONF-001 sampai CONF-004 belum boleh diterjemahkan menjadi requirement final sebelum keputusan stakeholder dicatat.
