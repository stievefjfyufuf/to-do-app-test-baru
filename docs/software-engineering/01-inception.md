# Inception dan Stakeholder — To-Do App

Status: Draft awal untuk discovery  
Tanggal: 29 Juni 2026

# Problem Statement

## Background

Pengguna perlu mengingat dan mengatur berbagai tugas, tetapi tugas yang tersebar di ingatan, catatan, atau media lain mudah terlupakan dan sulit diprioritaskan. Konteks pengguna, platform, dan pola penggunaan belum dikonfirmasi sehingga dokumen ini menjadi baseline awal untuk proses elicitation.

## Primary Problem

Pengguna belum memiliki cara yang sederhana dan terpusat untuk mencatat, meninjau, memprioritaskan, serta menandai penyelesaian tugas. Akibatnya, pengguna berisiko lupa terhadap tugas dan kesulitan mengetahui pekerjaan yang harus dilakukan berikutnya.

## Goals

### Tujuan Pengguna

- GOAL-001: Memungkinkan pengguna mencatat tugas dengan cepat.
- GOAL-002: Membantu pengguna memahami tugas yang masih aktif dan yang sudah selesai.
- GOAL-003: Membantu pengguna menentukan urutan pengerjaan melalui prioritas dan/atau tenggat waktu.

### Tujuan Produk/Bisnis

- GOAL-004: Menghasilkan MVP yang cukup berguna untuk memvalidasi kebutuhan pengelolaan tugas pengguna sasaran.
- GOAL-005: Mengukur apakah pengguna dapat menyelesaikan alur inti tanpa kebingungan berarti.

### Tujuan Teknis

- GOAL-006: Menjaga data tugas tetap konsisten dan dapat dipulihkan setelah aplikasi ditutup atau dimuat ulang.
- GOAL-007: Menyediakan fondasi yang mudah dikembangkan setelah kebutuhan autentikasi, sinkronisasi, dan kolaborasi tervalidasi.

## Stakeholders

| Stakeholder | Kategori/Role | Needs | Influence | Notes |
|---|---|---|---|---|
| STK-001 Pengguna individu | Primer | Mencatat, mengatur, menemukan, dan menyelesaikan tugas dengan mudah | High | Profil pengguna sasaran perlu dipersempit saat elicitation |
| STK-002 Product owner/pemilik proyek | Pengambil keputusan | Menetapkan visi, prioritas MVP, dan indikator keberhasilan | High | Untuk proyek personal, peran ini dapat dipegang pembuat aplikasi |
| STK-003 Developer/tim pengembang | Operasional/teknis | Requirement jelas, scope stabil, dan keputusan teknis terdokumentasi | High | Bertanggung jawab atas pembangunan dan pemeliharaan |
| STK-004 Tester/evaluator | Sekunder/quality | Acceptance criteria serta alur yang dapat diuji | Medium | Dapat berupa pengguna uji, dosen, QA, atau product owner |
| STK-005 Administrator layanan | Operasional | Visibilitas insiden, backup, keamanan, dan kesehatan layanan | Low–Medium | Relevan bila aplikasi memakai backend atau dirilis publik |

## Scope

### In Scope — Usulan MVP

- Membuat tugas.
- Melihat daftar tugas aktif dan selesai.
- Mengubah judul serta detail dasar tugas.
- Menandai tugas selesai dan mengembalikannya menjadi aktif.
- Menghapus tugas dengan pencegahan penghapusan tidak sengaja.
- Menentukan prioritas dan/atau tenggat waktu.
- Memfilter atau mengurutkan tugas berdasarkan status, prioritas, atau tenggat.
- Menyimpan data sehingga tetap tersedia saat aplikasi digunakan kembali.
- Menyediakan kondisi UI dasar: kosong, loading bila diperlukan, sukses, dan error.

### Out of Scope — Sampai Divalidasi

- Kolaborasi tim, assignment tugas, komentar, dan workspace bersama.
- Integrasi kalender, email, atau layanan pihak ketiga.
- Lampiran file dan rich-text editor.
- Fitur produktivitas lanjut seperti recurring task, subtasks, habit tracking, dan gamification.
- Notifikasi lintas perangkat.
- Analitik organisasi dan dashboard administrator kompleks.
- Monetisasi atau paket berlangganan.

## Assumptions

- ASSUMP-001: Produk awal ditujukan untuk satu pengguna yang mengelola tugas pribadi.
- ASSUMP-002: MVP menggunakan satu bahasa dan satu zona waktu utama.
- ASSUMP-003: Data tugas dasar mencakup judul, deskripsi opsional, status, prioritas opsional, tenggat opsional, serta waktu pembuatan/perubahan.
- ASSUMP-004: Aplikasi harus dapat digunakan tanpa fitur kolaborasi.
- ASSUMP-005: Platform awal belum ditentukan; rancangan scope dibuat netral terhadap web, mobile, atau desktop.
- ASSUMP-006: Data tugas dapat mengandung informasi pribadi sehingga akses dan penyimpanan perlu disesuaikan dengan model akun yang dipilih.

## Constraints

- Batas waktu, anggaran, ukuran tim, dan kemampuan teknis belum diketahui.
- Platform target dan kebutuhan online/offline belum diputuskan.
- Belum ada keputusan mengenai akun pengguna, sinkronisasi, hosting, atau penyimpanan lokal.
- Jika menggunakan layanan pihak ketiga, ketersediaan, biaya, privasi, dan ketergantungan vendor perlu dievaluasi.

## Success Signals

- Pengguna uji dapat membuat, menemukan, mengubah, dan menyelesaikan tugas dalam satu alur tanpa bantuan.
- Tugas yang disimpan tidak hilang setelah aplikasi ditutup atau dimuat ulang sesuai model penyimpanan yang dipilih.
- Sebagian besar pengguna uji memahami tugas mana yang perlu dikerjakan berikutnya.
- MVP mendapatkan bukti penggunaan berulang atau umpan balik yang cukup untuk memutuskan iterasi berikutnya.

## Early Risks and Ownership

- Product owner (STK-002) perlu memutuskan target pengguna dan batas MVP; tanpa keputusan ini scope mudah melebar.
- Developer (STK-003) perlu menjaga integritas data, menangani kegagalan penyimpanan, dan menyediakan jalur backup/restore bila data disimpan di server.
- Jika akun dan cloud sync digunakan, autentikasi, otorisasi, privasi, penghapusan akun/data, serta pemulihan insiden menjadi perhatian awal.
- Strategi rilis perlu memungkinkan rollback aplikasi dan migrasi data yang aman bila backend diperkenalkan.

## Open Questions

1. OQ-001: Siapa pengguna sasaran pertama—pribadi umum, mahasiswa, pekerja, atau tim?
- sasarannya adalah mahasiswa
2. OQ-002: Masalah paling menyakitkan saat ini apa: lupa tugas, sulit menentukan prioritas, terlalu banyak tugas, atau koordinasi?
- masalahnya adalah lupa tugas, terlalu banyak tugas
3. OQ-003: Platform pertama yang dibutuhkan apa: web, Android, iOS, atau desktop?
- web dan android
4. OQ-004: Apakah aplikasi harus dapat dipakai secara offline?
- iya harus karena kalau mahasiswa tidak ada data maka nanti akan repot
5. OQ-005: Apakah pengguna memerlukan akun dan sinkronisasi antarperangkat pada MVP?
- iya butuh
6. OQ-006: Dari prioritas, tenggat, kategori/tag, subtugas, recurring task, dan pengingat, mana yang benar-benar wajib?
-kalau pertanyaan ini semuanya penting
7. OQ-007: Bagaimana pengguna ingin melihat tugas: daftar sederhana, kalender, kanban, atau kombinasi?
- kalender dan kamban
8. OQ-008: Apakah tugas hanya bersifat pribadi atau perlu dibagikan/ditugaskan kepada orang lain?
- pribadi dan perlu di bagikan dan di tugaskan kepada orang lain
9. OQ-009: Berapa target waktu, anggaran, ukuran tim, dan teknologi yang dikuasai?
- tergantung pada total tugas nya dan waktu pengerjaan
10. OQ-010: Bagaimana keberhasilan MVP akan dinilai—kemudahan pakai, jumlah tugas selesai, penggunaan berulang, nilai akademik, atau metrik lain?
- jumlah tugas selesai dan nilai akademik
11. OQ-011: Apakah ada kebutuhan privasi, keamanan, aksesibilitas, atau kepatuhan khusus?
- ada. Kebutuhan privasi keamanan dan aksebilitas
12. OQ-012: Apa kebijakan yang diinginkan untuk penghapusan, backup, pemulihan, dan ekspor data?
- ini pertanyaan saya bingung nanti tolong anda yang selesaikan kalau unutk perntanyaan ini

## Handoff ke Elicitation

Pada tahap `02-se-elicitation`, validasi terlebih dahulu STK-001 dan STK-002, kemudian gunakan OQ-001 sampai OQ-012 sebagai panduan wawancara. Setelah jawaban diperoleh, perbarui asumsi menjadi keputusan tervalidasi sebelum menyusun requirement detail.
