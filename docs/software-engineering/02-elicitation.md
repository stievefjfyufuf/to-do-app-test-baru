# Elicitation Notes — To-Do App Mahasiswa

Status: Decision baseline untuk specification dan architecture; validasi langsung mahasiswa masih menjadi gate pra-rilis
Tanggal: 29 Juni 2026
Sumber utama: `01-inception.md` (`DOC-001`) dan delegasi keputusan dari STK-002 kepada penyusun pada 29 Juni 2026

## Ringkasan Konteks

STK-002 meminta penyusun menetapkan default yang realistis agar proyek dapat maju. Keputusan di dokumen ini adalah baseline produk untuk desain, bukan klaim bahwa wawancara STK-001 telah dilakukan. Validasi langsung dengan mahasiswa tetap wajib sebelum acceptance/release.

## Stakeholder dan Teknik

| Stakeholder | Teknik/Evidence | Hasil | Status |
|---|---|---|---|
| STK-001 Mahasiswa | Jawaban awal melalui STK-002; interview 5–8 mahasiswa direncanakan | Pain point utama: lupa tugas dan beban tugas tinggi | Belum divalidasi langsung |
| STK-002 Product owner | Jawaban OQ-001–OQ-012 dan delegasi keputusan | Scope, platform, kebijakan data, dan prioritas dapat ditetapkan | Disetujui untuk desain |
| STK-003 Developer | Analisis feasibility konservatif | Baseline solo developer, web-first, 12 minggu | Asumsi perencanaan |
| STK-004 Tester/evaluator | Analisis acceptance criteria | Alur inti dan target usability ditetapkan | Siap untuk test planning |
| STK-005 Administrator | Analisis risiko operasional | Backup, retensi, dan penghapusan diberi baseline | Siap untuk desain; validasi operasi sebelum rilis |

## Keputusan atas Question Bank

| ID | Stakeholder/Goal | Jawaban Baseline | Follow-up |
|---|---|---|---|
| Q-001 | STK-001; GOAL-001/003 | Tugas berasal dari LMS, dosen, grup kelas, dan catatan pribadi; input harus cepat. | Validasi terhadap 5–8 mahasiswa. |
| Q-002 | STK-001; GOAL-001 | Hambatan utama adalah input berulang dan informasi tugas tersebar. | Ukur saat usability test. |
| Q-003 | STK-001; GOAL-002/003 | Tugas terlupa karena tidak tercatat terpusat dan daftar terlalu panjang. | Validasi frekuensi. |
| Q-004 | STK-001; GOAL-003 | Urutan utama: tenggat terdekat, lalu prioritas. | Validasi pada prototype. |
| Q-005 | STK-001; GOAL-001/002 | Daftar/detail serta create, edit, complete/reopen, dan delete harus bekerja offline. | Uji pada kondisi offline nyata. |
| Q-006 | STK-001; GOAL-002 | MVP berupa web responsif/PWA; Android native menjadi next release. | Validasi kenyamanan layar kecil. |
| Q-007 | STK-001; GOAL-002/003 | MVP menyediakan daftar dan kalender; kanban ditunda. | Validasi kalender pada prototype. |
| Q-008 | STK-001; GOAL-001/003 | Prioritas dan tenggat masuk MVP; tag, subtugas, recurring, dan reminder ditunda. | Prioritaskan ulang setelah MVP. |
| Q-009 | STK-001; GOAL-002 | MVP bersifat pribadi; sharing dan assignment ditunda. | Elicitation khusus kolaborasi sebelum re-entry. |
| Q-010 | STK-001; GOAL-005 | Alur inti harus dapat dijalankan dengan keyboard, fokus terlihat, label aksesibel, dan kontras 4.5:1. | Verifikasi dengan STK-004. |
| Q-011 | STK-002; GOAL-004 | Segmen pertama adalah mahasiswa yang mengelola tugas kuliah pribadi. | Tidak ada blocker desain. |
| Q-012 | STK-002; GOAL-004 | Batas MVP mengikuti Q-005–Q-010. | Disetujui untuk desain. |
| Q-013 | STK-002/003; GOAL-004 | Baseline: 1 developer, 12 minggu, biaya rendah, layanan open-source/managed tier, stack web TypeScript. | Re-estimate bila kondisi aktual berbeda. |
| Q-014 | STK-002/004; GOAL-005 | Ukur jumlah tugas unik selesai dan usability; nilai akademik hanya research track. | Studi akademik terpisah. |
| Q-015 | STK-002; GOAL-004/005 | Penggunaan berulang dan keberhasilan alur inti menjadi metrik tambahan. | Tetapkan instrumen saat test planning. |
| Q-016 | STK-003; GOAL-006 | Operasi offline: read, create, edit, complete/reopen, dan soft-delete task. | Disetujui untuk desain. |
| Q-017 | STK-003; GOAL-006 | Optimistic concurrency; bila konflik tidak dapat digabung, simpan kedua versi dan minta pengguna memilih. | Detail kontrak di tahap 7. |
| Q-018 | STK-003; GOAL-006/007 | Satu akun mendukung banyak perangkat melalui sync setelah MVP web stabil. | PWA adalah client pertama. |
| Q-019 | STK-003; GOAL-007 | Modular monolith dipilih agar realistis untuk satu developer. | Tinjau ulang bila tim/scale tumbuh. |
| Q-020 | STK-004; GOAL-005 | Create, view, edit, complete/reopen, delete, filter/sort, calendar, offline/reconnect. | Menjadi dasar test plan. |
| Q-021 | STK-004; GOAL-005 | Dampak nilai akademik tidak diklaim sebagai sebab-akibat. | Research only. |
| Q-022 | STK-004; GOAL-005 | Keyboard, accessible name, visible focus, dan contrast 4.5:1. | Audit aksesibilitas sebelum rilis. |
| Q-023 | STK-005; GOAL-006 | Soft-deleted task dapat dipulihkan 30 hari. | Disetujui sebagai kebijakan baseline. |
| Q-024 | STK-005; GOAL-006 | Backup maksimal setiap 24 jam; target RPO 24 jam dan RTO 4 jam. | Validasi terhadap provider terpilih. |
| Q-025 | STK-005; GOAL-006 | Ekspor JSON/CSV ditunda ke next release. | Tidak memblokir MVP. |
| Q-026 | STK-005; GOAL-006/007 | Data pribadi hanya dapat diakses pemilik; administrator tidak membaca isi tanpa proses insiden yang tercatat. | Detail kontrol di tahap 7. |

## Raw Needs

| ID | Type | Raw Need | Source | Traceability |
|---|---|---|---|---|
| NEED-001 | Explicit | Pengguna sasaran awal adalah mahasiswa. | STK-002, OQ-001 | GOAL-004 |
| NEED-002 | Pain point | Mahasiswa perlu mengurangi risiko melupakan tugas. | STK-002, OQ-002 | GOAL-001/002 |
| NEED-003 | Pain point | Mahasiswa perlu mengelola jumlah tugas yang tinggi. | STK-002, OQ-002 | GOAL-002/003 |
| NEED-004 | Explicit | Web responsif/PWA adalah platform pertama; Android menyusul. | Q-006, Q-019 | GOAL-004/007 |
| NEED-005 | Constraint | Operasi tugas inti harus tersedia offline. | Q-005, Q-016 | GOAL-001/002/006 |
| NEED-006 | Explicit | Pengguna memerlukan akun. | STK-002, OQ-005 | GOAL-006 |
| NEED-007 | Explicit | Data akun perlu dapat disinkronkan lintas perangkat tanpa silent overwrite. | Q-017/Q-018 | GOAL-006/007 |
| NEED-008 | Explicit | Prioritas dan tenggat masuk MVP; fitur produktivitas lain ditunda. | Q-008/Q-012 | GOAL-001/003 |
| NEED-009 | Explicit | Kalender masuk MVP. | Q-007 | GOAL-002/003 |
| NEED-010 | Deferred | Kanban dibutuhkan setelah MVP. | Q-007 | GOAL-002/003 |
| NEED-011 | Explicit | Tugas MVP bersifat pribadi. | Q-009 | GOAL-001/002 |
| NEED-012 | Deferred | Sharing dipertimbangkan setelah MVP. | Q-009 | GOAL-007 |
| NEED-013 | Deferred | Assignment dipertimbangkan bersama model role. | Q-009 | GOAL-007 |
| NEED-014 | Explicit | Produk mengukur jumlah tugas unik yang selesai. | Q-014 | GOAL-005 |
| NEED-015 | Research | Hubungan dengan nilai akademik diuji terpisah, bukan sebagai klaim produk. | Q-014/Q-021 | GOAL-005 |
| NEED-016 | Policy | Pengguna mengetahui data utama yang disimpan dan dapat menghapus akun. | Q-026 | GOAL-006 |
| NEED-017 | Policy | Data pribadi hanya dapat diakses akun berwenang. | Q-026 | GOAL-006 |
| NEED-018 | Constraint | Alur inti memenuhi target aksesibilitas yang terukur. | Q-010/Q-022 | GOAL-005 |
| NEED-019 | Inferred | Status sync harus terlihat dan perubahan tidak boleh hilang diam-diam. | Q-017 | GOAL-006 |
| NEED-020 | Approved policy | Task memakai soft-delete 30 hari; akun memiliki masa tenggang penghapusan 30 hari; backup harian; ekspor ditunda. | Q-023–Q-025 | GOAL-006 |
| NEED-021 | Deferred | Kolaborasi kelak memerlukan role-permission matrix. | Q-009 | GOAL-007 |

## Constraints Found

- CON-001: MVP web responsif/PWA; Android native tidak termasuk MVP.
- CON-002: Operasi task inti harus offline-capable dan disinkronkan secara idempotent.
- CON-003: Akun dan isolasi data wajib; sync menggunakan version checking.
- CON-004: Baseline perencanaan adalah satu developer, 12 minggu, biaya rendah, stack web TypeScript.
- CON-005: Security, privacy, accessibility, backup, dan no-silent-data-loss adalah quality gate.

## Ambiguities dan Konflik Tersisa

- AMB-001: Bukti langsung STK-001 belum tersedia. Ini tidak memblokir architecture, tetapi memblokir acceptance/release sampai usability validation dilakukan.
- AMB-002: Provider hosting/auth belum dipilih; architecture menjaga boundary agar provider dapat diganti.
- CONF-001: Keinginan semua fitur diselesaikan dengan scope bertahap: prioritas/tenggat/kalender di MVP; sisanya next release.
- CONF-002: Web+Android diselesaikan dengan web/PWA first.
- CONF-003: Individual versus collaboration diselesaikan dengan personal MVP dan kolaborasi deferred.
- CONF-004: MVP memakai satu zona waktu profil; waktu disimpan sebagai UTC dan ditampilkan pada zona profil.

## Handoff ke Specification

NEED-001–NEED-021, keputusan Q-001–Q-026, serta CON-001–CON-005 menjadi input `03-se-specification`. AMB-001 tetap menjadi validation gate pra-rilis, bukan blocker architecture.
