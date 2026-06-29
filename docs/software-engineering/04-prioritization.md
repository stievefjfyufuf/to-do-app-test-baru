# Prioritization - To-Do App Mahasiswa

Status: Rekomendasi provisional untuk validasi stakeholder  
Tanggal: 29 Juni 2026  
Sumber: `01-inception.md` (`DOC-001`) dan `03-specification.md` (`DOC-003`)

## 1. Method and Assumptions

Prioritas menggunakan MoSCoW yang dilengkapi skor value-risk-effort:

- Value (`V`): nilai langsung bagi mahasiswa dan tujuan produk, 1-5.
- Risk reduction (`R`): pengurangan risiko kehilangan data, kegagalan produk, atau ketidakpastian, 1-5.
- Urgency (`U`): seberapa cepat item dibutuhkan untuk memvalidasi MVP, 1-5.
- Compliance impact (`C`): dampak privasi, keamanan, atau aksesibilitas, 0-3.
- Effort (`E`): effort relatif; 1 paling kecil dan 5 paling besar.
- Score = `(2 x V) + R + U + C - E`. Score membantu perbandingan, tetapi tidak otomatis menentukan prioritas karena readiness, dependency, dan konflik tetap menjadi gate.

Arti MoSCoW:

- `Must`: wajib untuk batas MVP yang direkomendasikan.
- `Should`: penting, tetapi MVP masih dapat divalidasi tanpa item tersebut.
- `Could`: bernilai jika kapasitas tersedia setelah Must dan Should aman.
- `Won't now`: tidak masuk MVP/next release saat ini; bukan berarti ditolak selamanya.

Asumsi perencanaan:

- Tim dan deadline belum diketahui (`CON-004`, `DEC-002`), sehingga effort bersifat relatif.
- MVP direkomendasikan web-first; Android mengikuti setelah alur inti, offline, dan sinkronisasi stabil.
- Item berstatus `Candidate` atau `Blocked` di `DOC-003` tidak berubah menjadi approved hanya karena diberi prioritas.
- Item bertanda `Must - gate` harus divalidasi melalui keputusan terkait sebelum menjadi committed scope.

## 2. Functional Requirement Prioritization Matrix

| Requirement | AC | V | R | U | C | E | Score | Dependency | MoSCoW | Target | Rationale |
|---|---|---:|---:|---:|---:|---:|---:|---|---|---|---|
| REQ-001 | AC-001, AC-002 | 5 | 2 | 5 | 0 | 2 | 15 | REQ-015 untuk data akun | Must | MVP | Pencatatan tugas adalah alur utama GOAL-001. |
| REQ-002 | AC-003 | 5 | 2 | 5 | 0 | 2 | 15 | REQ-001 | Must | MVP | Daftar aktif/selesai diperlukan agar beban tugas terlihat. |
| REQ-003 | AC-004 | 4 | 1 | 4 | 0 | 2 | 11 | REQ-001 | Must | MVP | Data tugas pasti berubah; tanpa edit pengguna harus menghapus dan membuat ulang. |
| REQ-004 | AC-005 | 5 | 2 | 5 | 0 | 2 | 15 | REQ-001 | Must | MVP | Penyelesaian tugas adalah outcome inti dan sumber metrik GOAL-005. |
| REQ-005 | AC-006 | 4 | 3 | 4 | 1 | 2 | 14 | REQ-001 | Must | MVP | Penghapusan dengan konfirmasi menjaga daftar tetap bersih tanpa tindakan tidak sengaja. |
| REQ-006 | AC-007 | 5 | 2 | 5 | 0 | 2 | 15 | REQ-002, REQ-007 | Must | MVP | Mengatasi banyaknya tugas dan membantu menentukan pekerjaan berikutnya. |
| REQ-007 | AC-008 | 5 | 2 | 5 | 0 | 2 | 15 | REQ-001 | Must | MVP | Prioritas dan tenggat langsung mendukung GOAL-003. |
| REQ-008 | AC-009 | 5 | 5 | 5 | 1 | 3 | 18 | Penyimpanan dasar | Must | MVP | Kehilangan data membatalkan nilai seluruh produk. |
| REQ-009 | AC-010 | 4 | 1 | 3 | 0 | 2 | 10 | REQ-001, REQ-006 | Should | Next release | Tag membantu organisasi, tetapi status, prioritas, dan tenggat sudah cukup untuk validasi awal. |
| REQ-010 | AC-011 | 4 | 1 | 3 | 0 | 3 | 9 | REQ-001 | Should | Next release | Subtugas bernilai, tetapi berada dalam CONF-001 dan bukan alur minimum. |
| REQ-011 | AC-012 | 4 | 1 | 3 | 0 | 4 | 8 | REQ-001, aturan recurrence | Could | Next release | Recurring task berguna namun memiliki edge case tanggal dan duplikasi. |
| REQ-012 | AC-013 | 5 | 2 | 4 | 0 | 4 | 12 | REQ-007, keputusan kanal/izin | Should | Next release | Pengingat kuat terhadap pain point lupa tugas, tetapi kanal belum disetujui. |
| REQ-013 | AC-014 | 5 | 2 | 5 | 0 | 3 | 14 | REQ-001, REQ-007 | Must | MVP | Kalender dipilih pengguna dan membuat beban berdasarkan tenggat terlihat. |
| REQ-014 | AC-015 | 4 | 1 | 3 | 0 | 3 | 9 | REQ-001, model status | Should | Next release | Kanban bernilai, tetapi daftar dan kalender cukup untuk MVP web-first. |
| REQ-015 | AC-016 | 5 | 5 | 5 | 3 | 3 | 20 | NFR-006, NFR-007 | Must | MVP | Akun diminta eksplisit dan menjadi dasar kepemilikan serta sinkronisasi data. |
| REQ-016 | AC-018 | 4 | 2 | 3 | 0 | 5 | 8 | REQ-015, REQ-018 | Should | Next release | Web dan Android dibutuhkan, tetapi dua platform sekaligus memperbesar delivery risk. |
| REQ-017 | AC-019 | 5 | 5 | 5 | 0 | 5 | 15 | REQ-001-REQ-008, REQ-015 | Must - gate | MVP | Offline menjawab kondisi mahasiswa tanpa data internet; cakupan operasi harus disahkan. |
| REQ-018 | AC-020, AC-021 | 5 | 5 | 4 | 0 | 5 | 14 | REQ-015, REQ-017, keputusan konflik | Must - gate | MVP | Offline tanpa rekonsiliasi saat online kembali berisiko menghasilkan data terpisah atau hilang. |
| REQ-019 | AC-022 | 3 | 1 | 2 | 1 | 4 | 6 | REQ-015, REQ-021 | Won't now | Deferred | Berbagi masih blocked dan bertentangan dengan baseline individual. |
| REQ-020 | AC-023 | 3 | 1 | 2 | 1 | 4 | 6 | REQ-019, REQ-021 | Won't now | Deferred | Assignment membutuhkan model kolaborasi dan izin lebih dahulu. |
| REQ-021 | AC-024 | 4 | 5 | 2 | 3 | 5 | 13 | Keputusan peran; REQ-019 | Won't now | Deferred | Penting untuk keamanan kolaborasi, tetapi tidak relevan sebelum kolaborasi disetujui. |
| REQ-022 | AC-025 | 3 | 4 | 3 | 2 | 3 | 12 | REQ-005, kebijakan retensi | Should | Next release | Pemulihan meningkatkan keselamatan data; periode 30 hari belum disetujui. |
| REQ-023 | AC-026 | 3 | 3 | 2 | 3 | 3 | 11 | REQ-015, kebijakan privasi | Should | Next release | Ekspor mendukung kontrol data, tetapi format dan proses belum disepakati. |
| REQ-024 | AC-027 | 4 | 4 | 3 | 3 | 4 | 14 | REQ-015, kebijakan retensi | Must - gate | MVP | Akun tanpa jalur penghapusan menimbulkan risiko privasi; masa tenggang perlu disahkan. |
| REQ-025 | AC-028 | 4 | 1 | 4 | 0 | 2 | 11 | REQ-004 | Must | MVP | Menghasilkan ukuran jumlah tugas selesai yang dipilih sebagai success signal. |
| REQ-026 | Belum ada | 2 | 1 | 1 | 0 | 5 | 1 | Metode studi Q-014/Q-021 | Won't now | Research track | Hubungan dengan nilai akademik adalah evaluasi penelitian, bukan fitur MVP saat ini. |

## 3. Non-Functional Requirement Prioritization Matrix

| Requirement | V | R | U | C | E | Score | Dependency | MoSCoW | Target | Rationale |
|---|---:|---:|---:|---:|---:|---:|---|---|---|---|
| NFR-001 | 5 | 3 | 5 | 0 | 2 | 16 | Alur REQ-001-REQ-007 | Must | MVP | MVP harus membuktikan mahasiswa dapat menyelesaikan alur tanpa bantuan. |
| NFR-002 | 4 | 2 | 3 | 0 | 3 | 10 | Dataset dan perangkat uji | Should | MVP | Respons lambat mengurangi usability, tetapi ambang 1.000 tugas perlu divalidasi. |
| NFR-003 | 5 | 5 | 5 | 1 | 3 | 18 | REQ-008 | Must | MVP | Tidak boleh ada operasi berhasil yang hilang. |
| NFR-004 | 5 | 5 | 5 | 0 | 4 | 16 | REQ-017 | Must - gate | MVP | Menjamin perubahan offline bertahan sampai rekonsiliasi. |
| NFR-005 | 5 | 5 | 4 | 0 | 5 | 14 | REQ-018 | Must - gate | MVP | Sinkronisasi harus terukur dan tidak menimpa perubahan diam-diam. |
| NFR-006 | 5 | 5 | 5 | 3 | 4 | 19 | REQ-015, AC-017 | Must | MVP | Akun dan data pribadi tidak layak dirilis tanpa kontrol akses dan proteksi kredensial. |
| NFR-007 | 4 | 4 | 4 | 3 | 3 | 16 | REQ-015, REQ-024 | Must | MVP | Transparansi dan kontrol data diperlukan sejak akun mulai menyimpan data pribadi. |
| NFR-008 | 4 | 3 | 4 | 2 | 3 | 14 | UI alur inti | Must | MVP | Aksesibilitas diminta eksplisit dan jauh lebih murah bila dibangun sejak awal. |
| NFR-009 | 3 | 4 | 2 | 0 | 4 | 8 | Layanan sinkronisasi/monitoring | Should | Next release | Target availability formal lebih relevan setelah penggunaan dan operasi layanan stabil. |
| NFR-010 | 4 | 5 | 3 | 2 | 4 | 14 | Penyimpanan server, STK-005 | Must - gate | MVP | Jika data tersimpan di layanan, backup dan restore menjadi syarat keselamatan rilis. |
| NFR-011 | 4 | 4 | 4 | 0 | 3 | 13 | CI dan test suite | Must | MVP | Test otomatis mengurangi regresi pada persistence dan offline-sync yang berisiko tinggi. |

## 4. Recommended MVP Boundary

### Committed Recommendation

Item berikut cukup jelas sebagai inti MVP web-first:

- Core task: REQ-001 sampai REQ-008.
- Kalender: REQ-013.
- Akun: REQ-015.
- Statistik tugas selesai: REQ-025.
- Quality gates: NFR-001, NFR-003, NFR-006, NFR-007, NFR-008, NFR-011.
- Performance target: NFR-002 sebagai `Should` yang diuji sebelum rilis, dengan angka final menunggu DEC-010.

### Conditional MVP Gates

Item berikut bernilai `Must`, tetapi belum boleh dianggap committed sampai keputusan terkait disetujui:

- Offline dan sinkronisasi: REQ-017, REQ-018, NFR-004, NFR-005. Memerlukan DEC-004/DEC-005 dan rekomendasi DEC-012/DEC-013.
- Penghapusan akun: REQ-024. Memerlukan DEC-007 dan rekomendasi DEC-016.
- Backup dan recovery: NFR-010. Wajib bila MVP menyimpan data pada layanan; ambang perlu persetujuan STK-005.

### Explicit MVP Exclusions

- Android sebagai aplikasi/platform terpisah: bagian REQ-016; ditargetkan next release.
- Tag, subtugas, tugas berulang, pengingat, dan kanban: REQ-009 sampai REQ-012 serta REQ-014; ditargetkan next release.
- Kolaborasi dan assignment: REQ-019 sampai REQ-021; deferred sampai model peran dan scope disetujui.
- Pengukuran pengaruh terhadap nilai akademik: REQ-026; dipindahkan ke research track.

## 5. Next Release

Urutan rekomendasi setelah MVP tervalidasi:

1. REQ-012 - pengingat, karena langsung mengurangi risiko lupa tugas.
2. REQ-009 dan REQ-010 - tag dan subtugas untuk menangani banyak tugas.
3. REQ-014 - kanban sebagai tampilan tambahan.
4. REQ-011 - tugas berulang setelah aturan recurrence tervalidasi.
5. REQ-022 sampai REQ-023 - pemulihan 30 hari dan ekspor data setelah kebijakan disetujui.
6. REQ-016 - Android dan akses lintas platform setelah REQ-018/NFR-005 stabil.
7. NFR-009 - target availability serta monitoring layanan yang lebih formal.

## 6. Deferred and Research Scope

| Item | Disposition | Re-entry Condition |
|---|---|---|
| REQ-019, REQ-020, REQ-021 | Deferred | STK-002 menyetujui kolaborasi; peran, izin, ownership, dan penerima telah ditentukan. |
| REQ-026 | Research track | STK-002/STK-004 menyetujui baseline, periode, metode, consent, dan cara mengendalikan faktor lain. |
| Komentar, workspace bersama, lampiran, rich text, habit tracking, gamification, monetisasi | Won't now | Ada bukti pengguna dan change request yang memperluas baseline. |

Tidak ada requirement formal yang ditolak permanen pada tahap ini.

## 7. Dependency and Delivery Sequence

| Wave | Dependency Outcome | Requirements |
|---|---|---|
| 0 - Validation gates | Keputusan platform, offline scope, konflik sinkronisasi, retensi/penghapusan, NFR target, kapasitas tim | DEC-002 sampai DEC-010; DEC-011 sampai DEC-018 di bawah |
| 1 - Core foundation | Model tugas, persistensi, test harness, dan aturan kualitas dasar tersedia | REQ-001, REQ-007, REQ-008; NFR-003, NFR-011 |
| 2 - Core workflow | Mahasiswa dapat melihat, mengubah, menyelesaikan, menghapus, memfilter, dan memakai kalender | REQ-002 sampai REQ-006, REQ-013 |
| 3 - Identity and protection | Data dikaitkan ke akun, diisolasi, dan memiliki kontrol privasi dasar | REQ-015, REQ-024; NFR-006, NFR-007, NFR-008 |
| 4 - Offline and reconciliation | Operasi offline yang disetujui bertahan dan tersinkronisasi tanpa silent loss | REQ-017, REQ-018; NFR-004, NFR-005, NFR-010 |
| 5 - Measurement and release validation | Metrik produk, usability, dan performance tervalidasi | REQ-025; NFR-001, NFR-002 |
| 6 - Next release | Fitur produktivitas, Android, recovery/export, dan operasi layanan diperluas | REQ-009 sampai REQ-012, REQ-014, REQ-016, REQ-022, REQ-023; NFR-009 |
| 7 - Collaboration | Kolaborasi dibangun hanya setelah model izin disetujui | REQ-019 sampai REQ-021 |

## 8. Conflict and Decision Log

Keputusan berikut adalah rekomendasi prioritisasi, bukan perubahan baseline yang telah disetujui. ID dilanjutkan dari DEC-001 sampai DEC-010 pada `DOC-003`.

| Decision | Conflict/Stakeholders | Recommended Decision | Rationale | Owner/Status |
|---|---|---|---|---|
| DEC-011 | CONF-002; STK-001, STK-002, STK-003 | Gunakan MVP web-first; pindahkan Android (REQ-016) ke next release. | Mempertahankan akses web dan mengurangi risiko dua client sebelum domain serta sinkronisasi stabil. | STK-002; Proposed |
| DEC-012 | AMB-003/DEC-004; STK-001, STK-002 | Scope offline MVP: lihat daftar/detail, buat, ubah, selesaikan/buka kembali, dan hapus tugas; operasi akun memerlukan koneksi. | Cakupan ini menjaga alur inti tetap berguna tanpa menjadikan semua fitur offline sejak rilis pertama. | STK-002; Proposed |
| DEC-013 | Q-017/DEC-005; STK-001, STK-003 | Jika konflik tidak dapat digabung otomatis, pertahankan kedua versi dan minta pengguna memilih; dilarang silent overwrite. | Mengutamakan pencegahan kehilangan data sampai aturan domain yang lebih spesifik tersedia. | STK-002, STK-003; Proposed |
| DEC-014 | CONF-001; STK-001, STK-002 | Kalender masuk MVP; tag, subtugas, recurring task, pengingat, dan kanban masuk next release. | Kalender dan tenggat paling langsung membantu beban akademik; fitur lain tetap dipertahankan tetapi tidak menahan validasi inti. | STK-002; Proposed |
| DEC-015 | CONF-003; STK-001, STK-002, STK-003 | Tunda REQ-019 sampai REQ-021 sampai setelah MVP/next release dan lakukan elicitation khusus kolaborasi. | Kolaborasi mengubah ownership, keamanan, sinkronisasi, dan asumsi produk individual. | STK-002; Proposed |
| DEC-016 | AMB-009/DEC-007; STK-001, STK-005 | MVP menyediakan permintaan penghapusan akun dengan masa tenggang 30 hari; trash tugas 30 hari dan ekspor mengikuti next release. | Memberi kontrol minimum sejak akun digunakan sambil menunda fitur data-control yang lebih luas. | STK-002, STK-005; Proposed |
| DEC-017 | AMB-007/DEC-009; STK-002, STK-004 | Jangan implementasikan REQ-026 sebagai fitur MVP; ukur jumlah tugas selesai melalui REQ-025 dan rancang studi akademik terpisah. | Nilai akademik tidak dapat diatribusikan ke aplikasi hanya dari telemetry produk. | STK-002, STK-004; Proposed |
| DEC-018 | DEC-010; STK-002, STK-003, STK-004, STK-005 | Perlakukan angka NFR sebagai target kandidat dan validasi sebelum release baseline disetujui. | Requirement tetap testable tanpa mengklaim kapasitas atau risiko yang belum diketahui. | Multi-stakeholder; Proposed |

## 9. Risks and Trade-offs

| Risk | Impact | Mitigation/Owner |
|---|---|---|
| Deadline dan kapasitas tim belum diketahui | MVP rekomendasi masih mungkin terlalu besar | STK-002/STK-003 menyelesaikan DEC-002 sebelum commitment. |
| Offline-sync dimasukkan sebagai gate MVP | Effort dan risiko data jauh lebih tinggi dibanding CRUD biasa | Spike teknis pada tahap desain; test NFR-004/NFR-005; rollback ke MVP local-only hanya melalui keputusan scope baru. |
| Web-first menunda Android | Sebagian mahasiswa mungkin tidak mendapatkan pengalaman platform yang diharapkan | Validasi web responsif dengan STK-001; REQ-016 menjadi prioritas next release. |
| Kolaborasi ditunda | Kebutuhan berbagi/assignment belum terpenuhi | Lakukan elicitation khusus setelah pola penggunaan individual tervalidasi. |
| Target NFR belum disetujui | Definition of done dan estimasi dapat berubah | Validasi DEC-018 sebelum planning implementasi. |
| Pengumpulan metrik tugas selesai | Menambah data perilaku pengguna | Batasi akses, jelaskan tujuan, dan terapkan NFR-006/NFR-007. |

## 10. Handoff to Validation and Change

Tahap `05-se-validation-change` harus memvalidasi:

1. Apakah STK-001 dan STK-002 menerima batas MVP web-first.
2. Apakah DEC-012, DEC-013, dan DEC-016 disetujui atau perlu diubah.
3. Apakah semua `Must - gate` dapat menjadi committed requirement.
4. Apakah target NFR-001 sampai NFR-011 realistis bagi STK-003/STK-005.
5. Apakah dependency waves dan penundaan kolaborasi dapat diterima.

Backlog tidak siap untuk implementation planning sampai DEC-002 (deadline/tim), DEC-004/DEC-005 (offline-sync), dan DEC-010 (target NFR) memiliki keputusan stakeholder yang tercatat.
