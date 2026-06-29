# Prioritization — To-Do App Mahasiswa

Status: Approved planning baseline untuk validation dan architecture
Tanggal: 29 Juni 2026
Sumber: `01-inception.md` (`DOC-001`), `02-elicitation.md` (`DOC-002`), dan `03-specification.md` (`DOC-003`)

## 1. Method and Constraints

Prioritas memakai MoSCoW dengan pertimbangan value, risk reduction, urgency, compliance, effort, dan dependency. Baseline delivery adalah satu developer selama 12 minggu, web responsif/PWA, biaya rendah, dan stack TypeScript (`CON-004`). Item `Must` adalah scope desain MVP; item `Should/Could` tidak boleh menahan MVP.

## 2. Functional Requirement Prioritization

| Requirement | Dependency | MoSCoW | Target | Rationale |
|---|---|---|---|---|
| REQ-001 | REQ-015 | Must | MVP | Entry point GOAL-001. |
| REQ-002 | REQ-001 | Must | MVP | Menampilkan beban dan state task. |
| REQ-003 | REQ-001 | Must | MVP | Data tugas berubah selama pengerjaan. |
| REQ-004 | REQ-001 | Must | MVP | Outcome inti dan sumber metrik. |
| REQ-005 | REQ-001 | Must | MVP | Lifecycle delete harus aman dan konsisten. |
| REQ-006 | REQ-002/007 | Must | MVP | Mengatasi jumlah tugas tinggi. |
| REQ-007 | REQ-001 | Must | MVP | Dasar prioritas dan kalender. |
| REQ-008 | Storage | Must | MVP | Mencegah kehilangan data. |
| REQ-009 | REQ-001/006 | Should | Next release | Filter inti sudah cukup untuk MVP. |
| REQ-010 | REQ-001 | Should | Next release | Menambah model domain dan UI. |
| REQ-011 | REQ-007 | Could | Next release | Edge case recurrence tinggi. |
| REQ-012 | REQ-007 | Should | Next release | Bernilai tetapi kanal/permission menambah scope. |
| REQ-013 | REQ-001/007 | Must | MVP | Kalender dipilih sebagai visual utama. |
| REQ-014 | Model status | Should | Next release | Daftar+kalender cukup untuk MVP. |
| REQ-015 | NFR-006/007 | Must | MVP | Ownership dan isolasi data. |
| REQ-016 | REQ-015/018 | Should | Next release | Android native setelah API/sync stabil. |
| REQ-017 | REQ-001–008/015 | Must | MVP | Menjawab kondisi tanpa data internet. |
| REQ-018 | REQ-015/017 | Must | MVP | Offline tanpa rekonsiliasi berisiko kehilangan data. |
| REQ-019 | REQ-015/021 | Won't now | Deferred | Sharing mengubah ownership/security. |
| REQ-020 | REQ-019/021 | Won't now | Deferred | Assignment bergantung role model. |
| REQ-021 | Role model | Won't now | Deferred | Tidak dibutuhkan pada personal MVP. |
| REQ-022 | REQ-005 | Must | MVP | Menuntaskan soft-delete lifecycle. |
| REQ-023 | REQ-015 | Should | Next release | Export tidak memblokir kontrol data minimum. |
| REQ-024 | REQ-015 | Must | MVP | Kontrol privasi sejak akun digunakan. |
| REQ-025 | REQ-004 | Must | MVP | Success signal produk. |
| REQ-026 | Metode studi | Won't now | Research | Bukan fitur produk. |

## 3. Non-Functional Prioritization

| Requirement | Dependency | MoSCoW | Target | Rationale |
|---|---|---|---|---|
| NFR-001 | Core flow | Must | MVP | Membuktikan usability. |
| NFR-002 | Local dataset | Should | MVP gate | Menjaga daftar tetap responsif. |
| NFR-003 | REQ-008 | Must | MVP | Nol kehilangan operasi sukses. |
| NFR-004 | REQ-017 | Must | MVP | Pending operation harus persisten. |
| NFR-005 | REQ-018 | Must | MVP | No silent overwrite. |
| NFR-006 | REQ-015 | Must | MVP | Security boundary wajib. |
| NFR-007 | REQ-015/024 | Must | MVP | Transparansi dan account deletion. |
| NFR-008 | Core UI | Must | MVP | Accessibility dibangun sejak awal. |
| NFR-009 | Monitoring | Should | Next release | Formal SLA menunggu operasi produksi. |
| NFR-010 | Server storage | Must | MVP release gate | Backup/restore wajib untuk data cloud. |
| NFR-011 | CI/tests | Must | MVP | Mengurangi regresi domain dan sync. |

## 4. Committed MVP Boundary

- Core task dan lifecycle: REQ-001–REQ-008, REQ-022.
- Kalender dan statistik: REQ-013, REQ-025.
- Account dan privacy control: REQ-015, REQ-024.
- Offline dan synchronization: REQ-017, REQ-018.
- Quality gates: NFR-001–NFR-008, NFR-010, NFR-011.

## 5. Next Release dan Deferred

- Next release: REQ-009–REQ-012, REQ-014, REQ-016, REQ-023, NFR-009.
- Deferred sampai elicitation khusus: REQ-019–REQ-021.
- Research only: REQ-026.

## 6. Dependency Sequence

| Wave | Outcome | Scope |
|---|---|---|
| 1 | Domain, persistence, dan test foundation | REQ-001/007/008; NFR-003/011 |
| 2 | Identity dan protection | REQ-015/024; NFR-006/007 |
| 3 | Core workflow dan kalender | REQ-002–006/013/022; NFR-001/002/008 |
| 4 | Offline queue dan conflict-safe sync | REQ-017/018; NFR-004/005 |
| 5 | Measurement dan operational release gate | REQ-025; NFR-010 |
| 6 | Next release | REQ-009–012/014/016/023; NFR-009 |

## 7. Conflict and Decision Log

| Decision | Decision | Rationale | Owner/Status |
|---|---|---|---|
| DEC-011 | Web responsif/PWA first; Android native next release. | Menekan risiko dua client. | STK-002; Approved for design |
| DEC-012 | Offline mencakup read/create/edit/complete/reopen/soft-delete. | Menjaga alur inti berguna tanpa koneksi. | STK-002; Approved for design |
| DEC-013 | Optimistic concurrency; simpan kedua versi pada konflik. | Mencegah silent loss. | STK-002/003; Approved for design |
| DEC-014 | Kalender masuk MVP; fitur produktivitas lain next release. | Scope 12 minggu tetap realistis. | STK-002; Approved for design |
| DEC-015 | Kolaborasi dan assignment deferred. | Personal MVP tidak memerlukan role complexity. | STK-002; Approved for design |
| DEC-016 | Task trash dan account deletion memakai 30 hari; task restore masuk MVP; export next release. | Lifecycle konsisten dan aman. | STK-002/005; Approved for design |
| DEC-017 | Statistik tugas selesai masuk MVP; nilai akademik research only. | Menghindari klaim sebab-akibat. | STK-002/004; Approved for design |
| DEC-018 | Threshold NFR-001–011 menjadi baseline design/test; provider-specific proof tetap release gate. | Requirement dapat didesain dan diuji. | STK-002; Approved for design |

## 8. Risks and Gates

| Risk/Gate | Impact | Mitigation/Owner |
|---|---|---|
| Belum ada interview langsung mahasiswa | Salah prioritas UX | Uji minimal 5 mahasiswa sebelum acceptance; STK-001/004. |
| Solo developer dan offline-sync | Delivery overrun | Modular monolith, wave delivery, spike sync lebih awal; STK-003. |
| Provider belum dipilih | RPO/RTO belum terbukti | Restore drill sebelum rilis; STK-005. |
| PWA menunda Android native | Ekspektasi platform | Validasi mobile responsive; REQ-016 tetap next release. |

## 9. Handoff to Validation

`05-se-validation-change` memvalidasi committed MVP terhadap kejelasan, completeness, consistency, feasibility, testability, dan traceability. Interview STK-001 serta restore drill adalah gate acceptance/release, bukan blocker pembuatan architecture baseline.
