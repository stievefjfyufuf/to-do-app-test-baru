# Requirements Specification — To-Do App Mahasiswa

Status: Baseline kandidat untuk prioritization dan validation
Tanggal: 29 Juni 2026
Sumber: `01-inception.md` (`DOC-001`) dan `02-elicitation.md` (`DOC-002`)

## 1. Specification Boundary

MVP adalah aplikasi web responsif/PWA untuk pengelolaan tugas akademik pribadi. Requirement berstatus `Ready-MVP` menjadi kandidat desain; `Deferred` dipertahankan untuk rilis berikutnya; `Research` bukan fitur produk. Asumsi perencanaan: satu developer, 12 minggu, stack web TypeScript, biaya rendah (`CON-004`).

## 2. Actors

| Actor | Upstream ID | Description |
|---|---|---|
| Mahasiswa | STK-001 | Pemilik akun dan tugas pribadi |
| Product owner | STK-002 | Menetapkan scope dan menerima baseline |
| Developer | STK-003 | Membangun dan mengoperasikan MVP |
| Tester/evaluator | STK-004 | Memverifikasi AC dan NFR |
| Administrator layanan | STK-005 | Menangani backup, recovery, dan insiden tanpa akses rutin ke isi tugas |
| Kolaborator | Turunan STK-001 | Aktor deferred untuk sharing/assignment |

## 3. Functional Requirements

| ID | Status | Requirement | Source | Priority | AC |
|---|---|---|---|---|---|
| REQ-001 | Ready-MVP | Mahasiswa dapat membuat tugas dengan judul wajib, deskripsi opsional, prioritas opsional, tenggat opsional, dan status default `active`. | NEED-002/003/008 | Must | AC-001/002 |
| REQ-002 | Ready-MVP | Sistem menampilkan tugas aktif, selesai, dan terhapus milik akun serta detail tugas yang dipilih. | NEED-003/011/020 | Must | AC-003 |
| REQ-003 | Ready-MVP | Pemilik dapat mengubah judul, deskripsi, prioritas, dan tenggat tugas yang belum dihapus permanen. | GOAL-001/002 | Must | AC-004 |
| REQ-004 | Ready-MVP | Pemilik dapat menandai tugas selesai dan membukanya kembali. | NEED-014 | Must | AC-005 |
| REQ-005 | Ready-MVP | Penghapusan biasa memindahkan tugas ke trash selama 30 hari setelah konfirmasi; penghapusan permanen memerlukan konfirmasi terpisah. | NEED-020 | Must | AC-006 |
| REQ-006 | Ready-MVP | Mahasiswa dapat memfilter dan mengurutkan tugas berdasarkan status, prioritas, dan tenggat. | NEED-003/008 | Must | AC-007 |
| REQ-007 | Ready-MVP | Mahasiswa dapat menetapkan prioritas `low`, `medium`, atau `high` serta tenggat berupa tanggal dan waktu opsional pada zona waktu profil; bila waktu tidak diisi, digunakan pukul 23:59. | NEED-008; CONF-004 | Must | AC-008 |
| REQ-008 | Ready-MVP | Operasi tugas yang berhasil tetap tersedia setelah aplikasi ditutup, restart, atau reload. | GOAL-006 | Must | AC-009 |
| REQ-009 | Deferred | Mahasiswa dapat mengelola tag dan memfilter tugas berdasarkan tag. | NEED-008 | Should | AC-010 |
| REQ-010 | Deferred | Mahasiswa dapat mengelola subtugas; progress adalah jumlah subtugas selesai dibagi jumlah subtugas. | NEED-008 | Should | AC-011 |
| REQ-011 | Deferred | Mahasiswa dapat membuat recurrence harian, mingguan, atau bulanan dengan tanggal akhir opsional. | NEED-008 | Could | AC-012 |
| REQ-012 | Deferred | Mahasiswa dapat membuat reminder in-app untuk tugas bertenggat. | NEED-002/008 | Should | AC-013 |
| REQ-013 | Ready-MVP | Mahasiswa dapat melihat tugas bertenggat pada kalender sesuai zona waktu profil dan membuka detailnya. | NEED-009 | Must | AC-014 |
| REQ-014 | Deferred | Mahasiswa dapat melihat kanban dengan kolom `active` dan `completed`. | NEED-010 | Should | AC-015 |
| REQ-015 | Ready-MVP | Mahasiswa dapat mendaftar, login, logout, dan meminta reset password; data hanya dikaitkan dengan akun terautentikasi. | NEED-006/017 | Must | AC-016/017 |
| REQ-016 | Deferred | Akun yang sama dapat digunakan pada aplikasi Android native setelah API/sync MVP stabil. | NEED-004/007 | Should | AC-018 |
| REQ-017 | Ready-MVP | Saat offline, mahasiswa dapat read, create, edit, complete/reopen, dan soft-delete tugas; perubahan diberi status pending. | NEED-005/019 | Must | AC-019 |
| REQ-018 | Ready-MVP | Saat online kembali, perubahan dikirim idempotent; server memeriksa versi dan mempertahankan kedua versi saat konflik yang tidak dapat digabung. | NEED-007/019 | Must | AC-020/021 |
| REQ-019 | Deferred | Pemilik dapat mengundang pengguna lain ke tugas. | NEED-012/021 | Won't now | AC-022 |
| REQ-020 | Deferred | Pihak berwenang dapat menugaskan tugas kepada kolaborator. | NEED-013/021 | Won't now | AC-023 |
| REQ-021 | Deferred | Sistem menegakkan role-permission matrix kolaborasi. | NEED-021 | Won't now | AC-024 |
| REQ-022 | Ready-MVP | Pemilik dapat memulihkan tugas dari trash sebelum 30 hari. | NEED-020 | Must | AC-025 |
| REQ-023 | Deferred | Pengguna dapat mengekspor data miliknya sebagai JSON atau CSV. | NEED-016/020 | Should | AC-026 |
| REQ-024 | Ready-MVP | Pengguna dapat meminta penghapusan akun dengan masa tenggang 30 hari dan membatalkannya sebelum tenggat. | NEED-016/020 | Must | AC-027 |
| REQ-025 | Ready-MVP | Sistem menampilkan jumlah distinct task yang selesai dalam periode; task yang selesai berulang hanya dihitung sekali per periode. | NEED-014 | Must | AC-028 |
| REQ-026 | Research | Evaluasi hubungan penggunaan dan nilai akademik dilakukan sebagai studi terpisah tanpa klaim sebab-akibat. | NEED-015 | Won't now | Tidak diimplementasikan |

## 4. Non-Functional Requirements

| ID | Status | Attribute | Requirement dan Measurement | Source |
|---|---|---|---|---|
| NFR-001 | Ready-MVP | Usability | ≥80% dari minimal 5 mahasiswa uji menyelesaikan create, find, edit, dan complete tanpa bantuan. | GOAL-005 |
| NFR-002 | Ready-MVP | Performance | P95 pembukaan daftar lokal ≤2 detik untuk 1.000 tugas pada perangkat uji baseline. | NEED-003 |
| NFR-003 | Ready-MVP | Reliability | Nol operasi tugas yang telah sukses hilang pada suite restart/reload. | REQ-008 |
| NFR-004 | Ready-MVP | Offline reliability | Perubahan offline bertahan setelah restart dan tetap pending sampai hasil sync eksplisit. | REQ-017 |
| NFR-005 | Ready-MVP | Synchronization | Perubahan tanpa konflik terlihat pada client kedua ≤30 detik setelah koneksi stabil; tidak ada silent overwrite. | REQ-018 |
| NFR-006 | Ready-MVP | Security | Data nonpublik hanya untuk akun berwenang; password memakai hash adaptif; transport memakai TLS; authorization diuji pada setiap resource. | NEED-017 |
| NFR-007 | Ready-MVP | Privacy | Pengguna dapat melihat ringkasan data yang disimpan dan menghapus akun; ekspor dipisahkan ke REQ-023 next release. | NEED-016/020 |
| NFR-008 | Ready-MVP | Accessibility | Alur inti keyboard-accessible, memiliki accessible name, visible focus, dan contrast teks normal ≥4.5:1. | NEED-018 |
| NFR-009 | Deferred | Availability | Target 99.5% per bulan setelah monitoring produksi tersedia. | GOAL-006 |
| NFR-010 | Ready-MVP | Backup/recovery | Backup ≤24 jam; restore drill membuktikan RPO ≤24 jam dan RTO ≤4 jam. | NEED-020 |
| NFR-011 | Ready-MVP | Maintainability | Semua test wajib lulus; branch coverage domain inti target ≥80%. | GOAL-007 |

## 5. User Stories

- US-001: Sebagai mahasiswa, saya ingin mencatat tugas dan tenggat agar tidak melupakannya (`REQ-001`, `REQ-007`).
- US-002: Sebagai mahasiswa, saya ingin mengurutkan tugas agar tahu pekerjaan berikutnya (`REQ-006`).
- US-003: Sebagai mahasiswa, saya ingin menyelesaikan dan membuka kembali tugas agar status tetap benar (`REQ-004`).
- US-004: Sebagai mahasiswa, saya ingin kalender agar beban tugas per tanggal terlihat (`REQ-013`).
- US-005: Sebagai mahasiswa tanpa koneksi, saya ingin mengelola tugas tanpa kehilangan perubahan (`REQ-017`, `REQ-018`).
- US-006: Sebagai pengguna, saya ingin mengontrol penghapusan tugas dan akun agar data tetap aman (`REQ-005`, `REQ-022`, `REQ-024`).
- US-007: Sebagai pengguna, saya ingin data pribadi terisolasi agar akun lain tidak dapat membacanya (`REQ-015`, `NFR-006`).
- US-008: Sebagai mahasiswa, saya ingin statistik tugas selesai agar dapat melihat konsistensi (`REQ-025`).

## 6. Acceptance Criteria

- **AC-001 — Create valid:** Given pengguna login, when judul non-spasi disimpan, then satu task berstatus `active` dibuat dengan field opsional yang diberikan.
- **AC-002 — Reject blank title:** Given form terbuka, when judul kosong/spasi disimpan, then tidak ada task dibuat dan error field tampil.
- **AC-003 — View by state:** Given akun memiliki task active/completed/trashed, when state dipilih, then hanya task milik akun pada state itu tampil dan detail dapat dibuka.
- **AC-004 — Edit:** Given task milik pengguna belum permanent-delete, when field valid diubah, then nilai terbaru tersimpan tanpa duplikasi.
- **AC-005 — Complete/reopen:** Given task active, when complete lalu reopen dilakukan, then status dan `completed_at` berubah sesuai aksi.
- **AC-006 — Delete lifecycle:** Given task aktif, when soft-delete dikonfirmasi, then task masuk trash dengan `deleted_at`; permanent-delete hanya terjadi setelah konfirmasi terpisah.
- **AC-007 — Filter/sort:** Given variasi status/prioritas/tenggat, when filter/sort diterapkan, then hasil sepenuhnya cocok dengan kriteria.
- **AC-008 — Priority/due:** Given zona profil tersedia, when priority dan due lokal valid disimpan, then sistem memakai 23:59 bila waktu kosong, menyimpan instant UTC, serta menampilkan kembali nilai lokal yang sama.
- **AC-009 — Persistence:** Given operasi dikonfirmasi sukses, when restart/reload terjadi, then hasil tetap tersedia.
- **AC-010 — Tag (deferred):** Given tag tersedia, when tag dipilih, then hanya task bertag itu tampil.
- **AC-011 — Subtask (deferred):** Given subtasks tersedia, when satu diselesaikan, then progress dihitung `completed/total`.
- **AC-012 — Recurrence (deferred):** Given pola valid, when waktu berikutnya tercapai, then tepat satu occurrence dibuat.
- **AC-013 — Reminder (deferred):** Given izin in-app tersedia, when waktu reminder tercapai, then satu notifikasi terkait task dibuat.
- **AC-014 — Calendar:** Given tasks memiliki due, when kalender dibuka, then task muncul pada tanggal zona profil yang benar.
- **AC-015 — Kanban (deferred):** Given task pada kolom active, when dipindah ke completed, then status berubah satu kali.
- **AC-016 — Authentication:** Given data valid, when register/login/logout/reset dilakukan, then hasil sesuai; kredensial salah, email duplikat, dan token reset invalid ditolak tanpa membocorkan akun.
- **AC-017 — Isolation:** Given dua akun, when akun A meminta resource akun B, then akses ditolak tanpa isi data.
- **AC-018 — Android (deferred):** Given API/sync stabil, when akun sama dipakai pada Android, then dataset konsisten.
- **AC-019 — Offline:** Given cache akun tersedia dan koneksi putus, when salah satu operasi scope offline dilakukan, then perubahan bertahan setelah restart dan berstatus pending.
- **AC-020 — Reconnect:** Given command pending tanpa konflik, when koneksi stabil, then command dengan idempotency key diterapkan sekali dan pending dibersihkan setelah acknowledgement.
- **AC-021 — Conflict:** Given versi server berbeda dari base version client, when sync terjadi, then tidak ada silent overwrite; kedua versi dipertahankan dan konflik ditampilkan untuk dipilih.
- **AC-022 — Sharing (deferred):** Given role model disetujui, when undangan diterima, then akses mengikuti izin.
- **AC-023 — Assignment (deferred):** Given user berwenang, when assignment disimpan, then penerima melihat assignment.
- **AC-024 — Permission (deferred):** Given role matrix, when aksi allowed/denied dicoba, then sistem menerima/menolak sesuai matrix.
- **AC-025 — Restore task:** Given `deleted_at` kurang dari 30 hari, when restore dilakukan, then task kembali dengan data sebelumnya; setelah retensi berakhir restore ditolak.
- **AC-026 — Export (deferred):** Given pengguna login, when ekspor JSON/CSV selesai, then hanya data miliknya disertakan.
- **AC-027 — Delete account:** Given pengguna login, when penghapusan dikonfirmasi, then `scheduled_deletion_at` 30 hari ditampilkan dan dapat dibatalkan sebelum tenggat.
- **AC-028 — Completion metric:** Given completion events, when periode dipilih, then distinct `task_id` pada periode dihitung satu kali dan task di luar periode tidak dihitung.

## 7. Traceability Summary

| Design concern | Requirements | Quality/Verification |
|---|---|---|
| Core task domain | REQ-001–REQ-008, REQ-013, REQ-022, REQ-025 | AC-001–009, AC-014, AC-025, AC-028; NFR-001–003/008/011 |
| Identity/privacy | REQ-015, REQ-024 | AC-016/017/027; NFR-006/007 |
| Offline/sync | REQ-017/018 | AC-019–021; NFR-004/005 |
| Operations | REQ-008/024 | AC-009/027; NFR-010 |
| Deferred growth | REQ-009–012/014/016/019–021/023 | AC-010–013/015/018/022–024/026 |

## 8. Resolved Decisions and Remaining Gate

- DEC-001/011: Web responsif/PWA first; Android deferred.
- DEC-002: Planning baseline satu developer, 12 minggu, biaya rendah, TypeScript.
- DEC-004/012: Offline scope ditetapkan pada REQ-017.
- DEC-005/013: Conflict resolution ditetapkan pada REQ-018/AC-021.
- DEC-007/016: Task dan account deletion memakai 30 hari.
- DEC-008: Accessibility target ditetapkan pada NFR-008.
- DEC-009/017: Nilai akademik menjadi research track.
- DEC-010/018: Target NFR diterima sebagai design/test baseline.
- Gate pra-rilis: validasi langsung minimal 5 mahasiswa dan restore drill provider terpilih.

## 9. Handoff to Prioritization

`04-se-prioritization` menetapkan item `Ready-MVP` sebagai committed design scope, menjaga semua item `Deferred` di luar MVP, dan mempertahankan gate pra-rilis tanpa memblokir architecture.
