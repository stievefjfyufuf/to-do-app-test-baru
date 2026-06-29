# Requirement Validation and Early Change Analysis - To-Do App Mahasiswa

Status: Validation completed; overall requirement set is not yet ready for architecture baseline  
Tanggal: 29 Juni 2026  
Sumber: `02-elicitation.md` (`DOC-002`), `03-specification.md` (`DOC-003`), dan `04-prioritization.md` (`DOC-004`)

## 1. Validation Method

Setiap requirement diperiksa terhadap enam kualitas:

- `C` - clear: makna tidak ambigu.
- `Cp` - complete: kondisi, aktor, dan hasil penting tercakup.
- `Co` - consistent: tidak bertentangan dengan requirement, scope, atau prioritas lain.
- `F` - feasible: secara teknis dan operasional masuk akal berdasarkan informasi yang tersedia.
- `T` - testable: dapat diverifikasi melalui acceptance criteria atau measurement.
- `Tr` - traceable: terhubung ke `NEED`, `GOAL`, stakeholder, atau sumber upstream.

Nilai: `Y` = memenuhi, `P` = sebagian/bersyarat, `N` = belum memenuhi.

Keterbatasan validasi: belum ada catatan persetujuan langsung dari STK-001, STK-003, STK-004, atau STK-005. Masukan awal berasal terutama dari STK-002 dan keputusan DEC-011 sampai DEC-018 masih berstatus `Proposed`.

## 2. Functional Requirement Validation

| Requirement | C | Cp | Co | F | T | Tr | Validation Status | Notes |
|---|:---:|:---:|:---:|:---:|:---:|:---:|---|---|
| REQ-001 | P | P | Y | Y | Y | Y | Needs clarification | Status/default tugas belum ditentukan dan belum diuji oleh AC-001/AC-002. |
| REQ-002 | Y | Y | Y | Y | Y | Y | Ready | AC-003 sesuai dengan daftar aktif dan selesai. |
| REQ-003 | Y | Y | Y | Y | Y | Y | Ready | AC-004 menguji update tanpa duplikasi. |
| REQ-004 | Y | Y | Y | Y | Y | Y | Ready | AC-005 mencakup selesai dan buka kembali. |
| REQ-005 | P | N | P | Y | P | Y | Needs change | Setelah konfirmasi, belum jelas apakah tugas hard-delete atau soft-delete; beririsan dengan REQ-022. |
| REQ-006 | Y | Y | Y | Y | Y | Y | Ready | Kriteria filter/urut dapat diuji melalui AC-007. |
| REQ-007 | P | P | Y | Y | P | Y | Needs clarification | Jenis tenggat, waktu lokal, zona waktu, dan validitas nilai belum ditentukan. |
| REQ-008 | Y | Y | Y | Y | Y | Y | Ready | AC-009 dan NFR-003 memberikan verifikasi persistence. |
| REQ-009 | Y | Y | Y | Y | Y | Y | Deferred - ready | Requirement cukup jelas, tetapi ditempatkan di next release oleh DOC-004. |
| REQ-010 | P | P | P | Y | P | Y | Deferred - clarify | Definisi kemajuan subtugas dan hubungan status parent-child belum ditentukan; CONF-001 belum disetujui. |
| REQ-011 | P | N | P | P | P | Y | Deferred - clarify | Pola recurrence, tanggal akhir, perubahan occurrence, dan zona waktu belum ditentukan. |
| REQ-012 | P | N | P | P | P | Y | Deferred - clarify | Kanal, izin, retry, dan kondisi pengingat belum disetujui. |
| REQ-013 | Y | P | Y | Y | P | Y | Ready after REQ-007 | AC-014 dapat diuji setelah semantik tenggat/zona waktu ditetapkan. |
| REQ-014 | P | P | Y | Y | P | Y | Deferred - clarify | Kolom/status kanban belum didefinisikan; saat ini model hanya aktif dan selesai. |
| REQ-015 | Y | P | Y | Y | P | Y | Ready with AC gap | Alur valid diuji AC-016, tetapi invalid login, akun duplikat, dan pemulihan akses belum memiliki AC. |
| REQ-016 | P | P | Y | P | P | Y | Deferred - clarify | “Android” belum dibedakan antara aplikasi native, wrapper, atau pengalaman web; AC-018 bergantung sinkronisasi. |
| REQ-017 | N | N | P | P | N | Y | Needs clarification | “Operasi inti yang disepakati” belum disetujui; DEC-012 masih Proposed. |
| REQ-018 | P | N | P | P | P | Y | Needs clarification | Konflik sinkronisasi belum menjadi aturan final; AC-021 merujuk aturan masa depan. |
| REQ-019 | P | N | N | P | P | Y | Deferred - blocked | Model undangan dan izin belum ada serta bertentangan dengan baseline individual. |
| REQ-020 | P | N | N | P | P | Y | Deferred - blocked | Bergantung REQ-019/REQ-021 dan keputusan ownership kolaborasi. |
| REQ-021 | N | N | P | P | N | Y | Deferred - blocked | Role-permission matrix belum ditentukan, sehingga AC-024 belum dapat dieksekusi. |
| REQ-022 | Y | P | Y | Y | Y | Y | Deferred - policy approval | AC-025 testable, tetapi kebijakan 30 hari belum disetujui STK-002/STK-005. |
| REQ-023 | P | P | P | Y | P | Y | Deferred - clarify | “Format umum” dan cakupan ekspor belum ditentukan; juga berkonflik dengan NFR-007 Must MVP. |
| REQ-024 | P | N | P | Y | P | Y | Needs clarification | Masa tenggang belum final; DEC-016 masih Proposed. |
| REQ-025 | P | P | Y | Y | P | Y | Needs clarification | Belum jelas apakah tugas yang dibuka kembali lalu diselesaikan ulang dihitung sekali atau beberapa kali. |
| REQ-026 | N | N | Y | N | N | Y | Deferred - research | Tidak memiliki AC dan sengaja dipindahkan ke research track melalui DEC-017. |

### Functional Result Summary

- Ready: REQ-002, REQ-003, REQ-004, REQ-006, REQ-008.
- Ready setelah dependensi/minor gap: REQ-013, REQ-015.
- Memerlukan klarifikasi/perubahan sebelum design: REQ-001, REQ-005, REQ-007, REQ-017, REQ-018, REQ-024, REQ-025.
- Deferred/next release: REQ-009 sampai REQ-012, REQ-014, REQ-016, REQ-022, REQ-023.
- Deferred dan blocked: REQ-019 sampai REQ-021.
- Research only: REQ-026.

## 3. Non-Functional Requirement Validation

| Requirement | C | Cp | Co | F | T | Tr | Validation Status | Notes |
|---|:---:|:---:|:---:|:---:|:---:|:---:|---|---|
| NFR-001 | Y | Y | Y | P | Y | Y | Needs stakeholder validation | Terukur, tetapi sampel dan target 80% belum disetujui STK-002/STK-004. |
| NFR-002 | P | N | Y | P | P | Y | Needs clarification | Perangkat/jaringan minimum belum ditentukan dan target 1.000 tugas belum divalidasi. |
| NFR-003 | Y | Y | Y | Y | Y | Y | Ready | Selaras dengan REQ-008 dan dapat diuji otomatis. |
| NFR-004 | P | P | Y | P | P | Y | Needs clarification | Bergantung pada cakupan offline REQ-017/DEC-012 yang belum disetujui. |
| NFR-005 | P | N | P | P | P | Y | Needs clarification | “Koneksi stabil” tidak terukur dan perangkat kedua tidak selaras penuh dengan MVP web-first. |
| NFR-006 | Y | Y | Y | Y | Y | Y | Ready for security design | Measurement jelas; model authorization rinci masih menjadi hasil design. |
| NFR-007 | Y | P | N | Y | P | Y | Needs change | Must MVP memeriksa REQ-023, sedangkan REQ-023 diprioritaskan next release. |
| NFR-008 | Y | Y | Y | P | Y | Y | Needs stakeholder validation | Testable, tetapi profil kebutuhan pengguna dan target akhir belum divalidasi STK-001/STK-004. |
| NFR-009 | P | P | Y | P | P | Y | Deferred - clarify | Definisi downtime, maintenance, dan monitoring belum lengkap; next release. |
| NFR-010 | Y | Y | Y | P | Y | Y | Needs stakeholder validation | RPO/RTO testable, tetapi bergantung hosting dan belum disetujui STK-005. |
| NFR-011 | Y | P | Y | Y | Y | Y | Ready with boundary note | “Modul domain inti” harus dipetakan saat design agar cakupan 80% tidak ambigu. |

### NFR Result Summary

- Ready: NFR-003, NFR-006, NFR-011.
- Memerlukan validasi threshold stakeholder: NFR-001, NFR-008, NFR-010.
- Memerlukan klarifikasi/perubahan: NFR-002, NFR-004, NFR-005, NFR-007.
- Deferred: NFR-009.

## 4. Acceptance Criteria Validation

| AC | Result | Validation Note |
|---|---|---|
| AC-001 | Partial | Pembuatan valid dapat diuji, tetapi default status belum dinyatakan. |
| AC-002 | Pass | Kondisi judul kosong dan hasil penolakan observable. |
| AC-003 | Pass | Status dan pembukaan detail dapat diverifikasi. |
| AC-004 | Pass | Perubahan tanpa duplikasi dapat diuji. |
| AC-005 | Pass | Transisi selesai dan kembali aktif observable. |
| AC-006 | Partial | Konfirmasi dapat diuji, tetapi state data setelah delete belum ditentukan. |
| AC-007 | Pass | Dataset dengan variasi status/prioritas/tenggat dapat memverifikasi hasil. |
| AC-008 | Partial | Nilai “tenggat yang valid” belum didefinisikan. |
| AC-009 | Pass | Restart/reload memberi tes persistence yang jelas. |
| AC-010 | Pass | Operasi tag dan filter memiliki hasil observable. |
| AC-011 | Partial | “Ringkasan kemajuan” belum memiliki rumus atau tampilan minimum. |
| AC-012 | Partial | “Pola valid” dan kondisi occurrence berikutnya belum didefinisikan. |
| AC-013 | Partial | Kanal, izin, dan toleransi waktu pengiriman belum ditentukan. |
| AC-014 | Partial | Pemetaan tanggal bergantung semantik tenggat dan zona waktu REQ-007. |
| AC-015 | Partial | Kolom status asal/tujuan belum ditetapkan. |
| AC-016 | Partial | Hanya positive path; negative path autentikasi belum tercakup. |
| AC-017 | Pass | Isolasi data antar-akun observable dan sesuai NFR-006. |
| AC-018 | Partial | “Ketika sinkronisasi berhasil” bersifat sirkular tanpa kondisi dan waktu yang jelas. |
| AC-019 | Fail | Operasi offline yang harus diuji belum disepakati. |
| AC-020 | Pass conditional | Testable untuk perubahan tanpa konflik setelah prasyarat sinkronisasi ditetapkan. |
| AC-021 | Fail | Expected result bergantung aturan resolusi yang belum ada. |
| AC-022 | Partial | Role dan izin valid belum didefinisikan. |
| AC-023 | Partial | Pihak berwenang dan lifecycle assignment belum didefinisikan. |
| AC-024 | Fail | Tidak ada role-permission matrix untuk menentukan tindakan allowed/denied. |
| AC-025 | Pass conditional | Testable jika kebijakan 30 hari disetujui. |
| AC-026 | Partial | Format dan field ekspor belum ditentukan. |
| AC-027 | Fail | Masa tenggang belum memiliki nilai yang disetujui. |
| AC-028 | Partial | Aturan perhitungan completion berulang belum ditentukan. |

Acceptance criteria result: 8 `Pass`, 2 `Pass conditional`, 14 `Partial`, dan 4 `Fail`. AC-019, AC-021, AC-024, serta AC-027 harus diperbaiki sebelum requirement terkait dapat menjadi baseline design.

## 5. Validation Findings

| Finding | Severity | Upstream IDs | Finding and Impact | Route/Owner |
|---|---|---|---|---|
| VAL-001 | High | STK-001; NEED-001 sampai NEED-021 | Belum ada bukti validasi langsung dari mahasiswa; kebutuhan masih terutama berasal dari STK-002. Risiko: produk memvalidasi asumsi product owner, bukan workflow mahasiswa. | Kembali ke `02-se-elicitation`; STK-001/STK-002 |
| VAL-002 | Blocker | CON-004; DEC-002; Q-013 | Deadline, anggaran, ukuran tim, dan kemampuan teknologi belum diketahui. Feasibility MVP tidak dapat dikonfirmasi. | Elicitation/decision; STK-002/STK-003 |
| VAL-003 | Medium | REQ-001; AC-001 | Default status tugas tidak ditentukan. | `03-se-specification`; STK-002 |
| VAL-004 | High | REQ-005, REQ-022; AC-006, AC-025; DEC-007/DEC-016 | Lifecycle delete tidak konsisten antara MVP dan next release. Architecture storage tidak dapat menetapkan hard/soft delete dengan aman. | `03-se-specification`; STK-002/STK-005 |
| VAL-005 | High | REQ-007, REQ-011 sampai REQ-013; AC-008, AC-012 sampai AC-014; ASSUMP-002 | Semantik date/time/timezone belum ditentukan dan memengaruhi kalender, recurring task, serta reminder. | Elicitation lalu specification; STK-001/STK-002 |
| VAL-006 | Blocker | REQ-017, NFR-004, AC-019; DEC-004/DEC-012 | Cakupan offline belum mendapat approval; AC-019 tidak dapat diuji. | Stakeholder decision lalu `03-se-specification`; STK-002 |
| VAL-007 | Blocker | REQ-018, NFR-005, AC-021; DEC-005/DEC-013 | Aturan konflik sinkronisasi belum final; silent-loss risk tetap terbuka. | Stakeholder decision lalu `03-se-specification`; STK-002/STK-003 |
| VAL-008 | High | NFR-007, REQ-023, REQ-024; AC-026, AC-027 | NFR-007 berstatus Must MVP tetapi measurement bergantung REQ-023 yang ditunda. | Split/revise NFR-007 di `03`; reprioritize di `04`; STK-002/STK-005 |
| VAL-009 | High | REQ-024, AC-027; DEC-007/DEC-016 | Masa tenggang penghapusan akun belum disetujui, padahal REQ-024 adalah Must-gate. | Stakeholder validation; STK-002/STK-005 |
| VAL-010 | Medium | REQ-015; AC-016 | Negative paths autentikasi dan pemulihan akses tidak tercakup. | `03-se-specification`; STK-002/STK-003 |
| VAL-011 | Medium | REQ-025; AC-028 | Definisi “jumlah tugas selesai” ambigu ketika tugas dibuka dan diselesaikan ulang. | `03-se-specification`; STK-002/STK-004 |
| VAL-012 | High | NFR-001 sampai NFR-011; DEC-010/DEC-018 | Seluruh threshold NFR masih kandidat; definition of done belum disetujui. | Validation workshop; STK-002 sampai STK-005 |
| VAL-013 | Medium | REQ-016, NFR-005; DEC-003/DEC-011 | Web-first hanya rekomendasi, bukan keputusan stakeholder; konteks “perangkat kedua” belum jelas. | Approve/reject DEC-011; STK-002 |
| VAL-014 | Medium | REQ-019 sampai REQ-021; CONF-003; DEC-015 | Kolaborasi sudah ditunda secara masuk akal, tetapi belum ada approval formal atas perubahan ekspektasi awal. | STK-002 approval; elicitation khusus sebelum re-entry |
| VAL-015 | Medium | NFR-008; NEED-018; DEC-008 | Accessibility target testable, tetapi kebutuhan mahasiswa dengan disabilitas belum divalidasi. | `02-se-elicitation`; STK-001/STK-004 |

## 6. Duplicate, Conflict, and Oversize Review

- Tidak ditemukan duplicate exact. Pasangan REQ-008/NFR-003, REQ-017/NFR-004, dan REQ-018/NFR-005 saling melengkapi sebagai behavior versus quality threshold.
- Konflik material ditemukan pada NFR-007 versus prioritas REQ-023 (`VAL-008`).
- Konflik lifecycle ditemukan pada REQ-005 versus REQ-022 (`VAL-004`).
- REQ-017/REQ-018 terlalu besar untuk implementation issue tunggal; setelah aturan final, keduanya perlu dipecah saat issue planning, tetapi tetap dapat dipertahankan sebagai product-level requirement.
- NFR-006 menggabungkan authorization, credential storage, dan encryption. Requirement masih dapat digunakan untuk architecture, tetapi harus menghasilkan beberapa control/test terpisah.
- REQ-019 sampai REQ-021 memang besar dan belum lengkap; keputusan deferred mencegahnya mengaburkan MVP.

## 7. Required Changes Before Architecture Baseline

| Order | Required Change | Related Finding | Target Artifact |
|---:|---|---|---|
| 1 | Catat deadline, ukuran tim, kemampuan teknologi, dan batas delivery. | VAL-002 | `02-elicitation.md` atau approved decision note |
| 2 | Validasi web-first, scope operasi offline, aturan konflik, dan kebijakan penghapusan akun dengan owner. | VAL-006, VAL-007, VAL-009, VAL-013 | Stakeholder decision record; lalu `03`/`04` |
| 3 | Tentukan semantik tenggat: date-only atau date-time, zona waktu, dan perilaku saat zona berubah. | VAL-005 | `03-specification.md` setelah elicitation |
| 4 | Selaraskan REQ-005 dengan REQ-022 dan tetapkan hard/soft delete per release. | VAL-004 | `03-specification.md` |
| 5 | Split NFR-007 menjadi privacy transparency/account deletion untuk MVP dan export requirement untuk next release, atau naikkan REQ-023 ke MVP. | VAL-008 | `03-specification.md`, lalu `04-prioritization.md` |
| 6 | Tambahkan/finalkan AC untuk autentikasi negatif, offline operations, conflict resolution, account deletion, dan completion counting. | VAL-003, VAL-006, VAL-007, VAL-009 sampai VAL-011 | `03-specification.md` |
| 7 | Validasi angka NFR melalui STK-003/STK-004/STK-005. | VAL-012, VAL-015 | `03-specification.md`/validation notes |
| 8 | Peroleh bukti minimal dari mahasiswa sasaran untuk workflow, offline context, dan prioritas kalender. | VAL-001, VAL-015 | `02-elicitation.md` |

Dokumen upstream tidak diubah oleh tahap ini. Perubahan di atas adalah change proposal dan harus dicatat melalui workflow yang sesuai sebelum mengganti baseline.

## 8. Early Change Impact Notes

| Change Proposal | Reason | Impact | Decision Status |
|---|---|---|---|
| Pisahkan NFR-007 menjadi dua scope release. | Menghapus konflik dengan REQ-023 next release. | Specification, priority, privacy tests, dan architecture data-control berubah. | Proposed; owner STK-002/STK-005 |
| Tetapkan soft-delete atau hard-delete untuk REQ-005. | Storage lifecycle saat ini ambigu. | Database schema, API, offline queue, recovery, dan AC-006/AC-025 berubah. | Proposed; owner STK-002/STK-005 |
| Adopsi DEC-012 sebagai cakupan offline MVP. | Membuat REQ-017/AC-019 testable. | UI status, local persistence, synchronization, dan test scope bertambah. | Proposed; owner STK-002 |
| Adopsi DEC-013 sebagai aturan konflik sementara. | Mencegah silent overwrite. | Model versioning, UI conflict, audit data, dan test AC-021 bertambah. | Proposed; owner STK-002/STK-003 |
| Pertahankan web-first dan tunda Android. | Mengurangi scope delivery awal. | REQ-016 tetap next release; architecture harus menjaga boundary agar Android dapat ditambahkan. | Proposed; owner STK-002 |

Tidak ada change proposal yang dianggap approved pada dokumen ini karena belum ada stakeholder approval note.

## 9. Stakeholder Validation Notes

| Stakeholder | Evidence Available | Validation State | Required Action |
|---|---|---|---|
| STK-001 Mahasiswa | Belum ada interview/survey langsung; kebutuhan disampaikan STK-002 | Not validated | Wawancarai/observasi mahasiswa sasaran dan validasi pain point serta offline workflow. |
| STK-002 Product owner | Jawaban OQ-001 sampai OQ-012 tersedia | Partially validated | Approve/reject DEC-011 sampai DEC-018 serta tetapkan delivery constraints. |
| STK-003 Developer | Belum ada feasibility note | Not validated | Nilai effort, architecture risk, offline-sync, dan NFR threshold. |
| STK-004 Tester/evaluator | Belum ada test/measurement approval | Not validated | Validasi NFR-001, NFR-008, AC, dan metrik REQ-025/REQ-026. |
| STK-005 Administrator | Belum ada operational approval | Not validated | Validasi NFR-010, retention, backup, recovery, export, dan account deletion. |

## 10. Readiness Decisions

| Decision | Decision | Rationale | Owner/Status |
|---|---|---|---|
| DEC-019 | Overall requirement set is **not ready** for architecture baseline. | VAL-002, VAL-006, VAL-007, VAL-008, VAL-009, dan VAL-012 memengaruhi MVP serta architecture secara material. | Validation result; pending STK-002 approval |
| DEC-020 | REQ-002, REQ-003, REQ-004, REQ-006, REQ-008, NFR-003, NFR-006, dan NFR-011 dinyatakan structurally ready. | Item jelas, konsisten, testable, dan traceable; tetap tunduk pada persetujuan baseline. | Proposed validation decision |
| DEC-021 | Jangan mulai `06-se-architecture-design` sebagai baseline final sebelum Required Changes 1-8 selesai. | Architecture saat ini harus menebak offline, sync conflict, delete lifecycle, privacy scope, dan capacity. | STK-002/STK-003; pending |
| DEC-022 | REQ-019 sampai REQ-021 tetap deferred dan REQ-026 tetap research-only. | Item tidak diperlukan untuk MVP dan belum lengkap. | Consistent with DEC-015/DEC-017; pending approval |

## 11. Readiness Decision

**Ready for design: No**

Reason: requirement inti CRUD memiliki fondasi yang baik, tetapi MVP yang diprioritaskan masih bergantung pada keputusan yang belum disetujui mengenai kapasitas tim, web-first, operasi offline, resolusi konflik sinkronisasi, lifecycle penghapusan, serta target NFR. Empat acceptance criteria masih gagal divalidasi: AC-019, AC-021, dan AC-027 langsung memblokir MVP gate, sedangkan AC-024 memblokir scope kolaborasi yang telah ditunda.

### Handoff

- Kembali ke `02-se-elicitation` untuk VAL-001, VAL-002, VAL-005, dan VAL-015.
- Kembali ke `03-se-specification` untuk VAL-003 sampai VAL-011 setelah keputusan stakeholder tersedia.
- Perbarui `04-se-prioritization` hanya jika perubahan specification mengubah MVP atau release boundary.
- Lanjut ke `06-se-architecture-design` setelah DEC-019 dapat diubah menjadi ready berdasarkan bukti dan approval yang tercatat.
