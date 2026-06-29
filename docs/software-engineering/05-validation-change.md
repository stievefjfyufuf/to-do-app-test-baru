# Requirement Validation and Early Change Analysis — To-Do App Mahasiswa

Status: Revalidation completed; committed MVP is ready for architecture baseline
Tanggal: 29 Juni 2026
Sumber: `02-elicitation.md` (`DOC-002`), `03-specification.md` (`DOC-003`), dan `04-prioritization.md` (`DOC-004`)

## 1. Validation Method

Setiap requirement dinilai `C` clear, `Cp` complete, `Co` consistent, `F` feasible, `T` testable, dan `Tr` traceable. `Y` berarti memenuhi. Feasibility didasarkan pada baseline satu developer/12 minggu; interview mahasiswa dan restore drill tetap menjadi gate sebelum release.

## 2. Functional Requirement Validation

| Requirement | C | Cp | Co | F | T | Tr | Validation Status | Notes |
|---|:---:|:---:|:---:|:---:|:---:|:---:|---|---|
| REQ-001 | Y | Y | Y | Y | Y | Y | Ready-MVP | Default `active` dan validasi judul jelas. |
| REQ-002 | Y | Y | Y | Y | Y | Y | Ready-MVP | State active/completed/trashed eksplisit. |
| REQ-003 | Y | Y | Y | Y | Y | Y | Ready-MVP | Editable fields dan ownership jelas. |
| REQ-004 | Y | Y | Y | Y | Y | Y | Ready-MVP | Complete/reopen dan `completed_at` testable. |
| REQ-005 | Y | Y | Y | Y | Y | Y | Ready-MVP | Soft-delete 30 hari dan konfirmasi permanent-delete konsisten. |
| REQ-006 | Y | Y | Y | Y | Y | Y | Ready-MVP | Filter/sort observable. |
| REQ-007 | Y | Y | Y | Y | Y | Y | Ready-MVP | Enum priority serta aturan UTC/profile timezone jelas. |
| REQ-008 | Y | Y | Y | Y | Y | Y | Ready-MVP | Persistence diverifikasi AC-009/NFR-003. |
| REQ-009 | Y | Y | Y | Y | Y | Y | Deferred-ready | Next release. |
| REQ-010 | Y | Y | Y | Y | Y | Y | Deferred-ready | Rumus progress telah ditetapkan. |
| REQ-011 | Y | Y | Y | Y | Y | Y | Deferred-ready | Pola dasar telah dibatasi; detail tahap next release. |
| REQ-012 | Y | Y | Y | Y | Y | Y | Deferred-ready | Kanal dibatasi in-app. |
| REQ-013 | Y | Y | Y | Y | Y | Y | Ready-MVP | Calendar mengikuti zona profil. |
| REQ-014 | Y | Y | Y | Y | Y | Y | Deferred-ready | Kolom active/completed jelas. |
| REQ-015 | Y | Y | Y | Y | Y | Y | Ready-MVP | Positive dan negative auth paths tercakup. |
| REQ-016 | Y | Y | Y | Y | Y | Y | Deferred-ready | Android native memiliki re-entry condition. |
| REQ-017 | Y | Y | Y | Y | Y | Y | Ready-MVP | Operasi offline eksplisit. |
| REQ-018 | Y | Y | Y | Y | Y | Y | Ready-MVP | Idempotency, version checking, dan no-silent-overwrite eksplisit. |
| REQ-019 | P | N | Y | P | P | Y | Deferred-blocked | Invitation dan role model wajib ditetapkan sebelum re-entry; tidak menjadi input MVP. |
| REQ-020 | P | N | Y | P | P | Y | Deferred-blocked | Bergantung REQ-019/021 dan ownership model masa depan. |
| REQ-021 | P | N | Y | P | N | Y | Deferred-blocked | Role-permission matrix wajib sebelum AC-024 dapat dieksekusi. |
| REQ-022 | Y | Y | Y | Y | Y | Y | Ready-MVP | Menutup lifecycle soft-delete. |
| REQ-023 | Y | Y | Y | Y | Y | Y | Deferred-ready | JSON/CSV eksplisit; next release. |
| REQ-024 | Y | Y | Y | Y | Y | Y | Ready-MVP | Masa tenggang 30 hari dan cancellation jelas. |
| REQ-025 | Y | Y | Y | Y | Y | Y | Ready-MVP | Distinct task per period menghapus ambiguity. |
| REQ-026 | Y | Y | Y | Y | Y | Y | Research-only | Bukan fitur implementasi. |

## 3. Non-Functional Requirement Validation

| Requirement | C | Cp | Co | F | T | Tr | Status | Notes |
|---|:---:|:---:|:---:|:---:|:---:|:---:|---|---|
| NFR-001 | Y | Y | Y | Y | Y | Y | Ready-MVP | Sampel dan threshold eksplisit. |
| NFR-002 | Y | Y | Y | Y | Y | Y | Ready-MVP | P95, dataset, dan target jelas. |
| NFR-003 | Y | Y | Y | Y | Y | Y | Ready-MVP | Nol kehilangan pada suite rilis. |
| NFR-004 | Y | Y | Y | Y | Y | Y | Ready-MVP | Pending state bertahan setelah restart. |
| NFR-005 | Y | Y | Y | Y | Y | Y | Ready-MVP | 30 detik dan conflict behavior terukur. |
| NFR-006 | Y | Y | Y | Y | Y | Y | Ready-MVP | Authorization/hash/TLS dapat diuji. |
| NFR-007 | Y | Y | Y | Y | Y | Y | Ready-MVP | Export dipisah sehingga tidak konflik. |
| NFR-008 | Y | Y | Y | Y | Y | Y | Ready-MVP | Keyboard/name/focus/contrast terukur. |
| NFR-009 | Y | Y | Y | Y | Y | Y | Deferred-ready | SLA formal next release. |
| NFR-010 | Y | Y | Y | Y | Y | Y | Ready-MVP | RPO/RTO eksplisit; proof tetap release gate. |
| NFR-011 | Y | Y | Y | Y | Y | Y | Ready-MVP | CI pass dan coverage boundary jelas. |

## 4. Acceptance Criteria Validation

- AC-001–AC-009, AC-014, AC-016–AC-017, AC-019–AC-021, AC-025, AC-027, dan AC-028: `Pass` untuk design/testability.
- AC-010–AC-013, AC-015, AC-018, AC-022–AC-024, dan AC-026: `Pass-deferred`; testable tetapi tidak masuk MVP.
- Tidak ada AC MVP yang `Partial` atau `Fail`.

## 5. Resolution of Previous Findings

| Previous Finding | Resolution | Evidence |
|---|---|---|
| VAL-002 delivery constraint | Baseline satu developer, 12 minggu, TypeScript, biaya rendah. | CON-004; Q-013 |
| VAL-003 default status | Default `active`. | REQ-001; AC-001 |
| VAL-004 delete lifecycle | Soft-delete/trash 30 hari; restore MVP. | REQ-005/022; AC-006/025 |
| VAL-005 date/time | Instant UTC dan zona profil; priority enum. | REQ-007; AC-008/014 |
| VAL-006 offline scope | Read/create/edit/complete/reopen/soft-delete. | REQ-017; AC-019; DEC-012 |
| VAL-007 sync conflict | Idempotency + optimistic concurrency + retain both versions. | REQ-018; AC-020/021; DEC-013 |
| VAL-008 privacy/export conflict | Privacy transparency/delete MVP; export next release. | NFR-007; REQ-023/024 |
| VAL-009 account grace | 30 hari dan dapat dibatalkan. | REQ-024; AC-027 |
| VAL-010 auth gaps | Invalid credentials, duplicate email, invalid reset token ditambahkan. | AC-016 |
| VAL-011 completion count | Distinct task per period. | REQ-025; AC-028 |
| VAL-012 NFR thresholds | Diterima sebagai baseline design/test. | DEC-018; NFR-001–011 |
| VAL-013 platform | Web/PWA first; Android next release. | DEC-011; REQ-016 |
| VAL-014 collaboration | Deferred dengan re-entry role elicitation. | DEC-015; REQ-019–021 |
| VAL-015 accessibility | Target terukur ditetapkan. | NFR-008 |

## 6. Open Risks (Non-Blocking for Architecture)

| Finding | Severity | Upstream IDs | Risk and Gate | Owner |
|---|---|---|---|---|
| VAL-016 | Medium | STK-001; NFR-001/008 | Belum ada bukti langsung mahasiswa. Wajib usability/accessibility test minimal 5 mahasiswa sebelum acceptance. | STK-001/004 |
| VAL-017 | Medium | CON-004 | Baseline solo/12 minggu adalah planning assumption; lakukan re-estimation saat kondisi aktual diketahui. | STK-002/003 |
| VAL-018 | High-release | NFR-010 | Provider belum membuktikan restore. Wajib restore drill sebelum production release. | STK-005 |
| VAL-019 | High-delivery | REQ-017/018 | Offline-sync kompleks; architecture harus menyediakan spike, observability, idempotency, dan rollback scope. | STK-003 |

## 7. Architecture Input Set

- Functional: REQ-001–REQ-008, REQ-013, REQ-015, REQ-017, REQ-018, REQ-022, REQ-024, REQ-025.
- Quality: NFR-001–NFR-008, NFR-010, NFR-011.
- Deferred items tidak boleh mengembangkan MVP secara diam-diam.

## 8. Readiness Decisions

| Decision | Decision | Rationale | Status |
|---|---|---|---|
| DEC-019 | Keputusan `not ready` sebelumnya disupersede setelah perbaikan DOC-002–004. | Semua blocker architecture lama telah memiliki keputusan dan AC testable. | Superseded |
| DEC-021 | Larangan memulai tahap 6 sebelumnya disupersede. | VAL-002–VAL-015 telah diselesaikan atau dipindahkan menjadi release gate yang eksplisit. | Superseded |
| DEC-023 | Committed MVP requirement set siap menjadi architecture baseline. | Semua MVP REQ/NFR clear, complete, consistent, feasible, testable, dan traceable. | Approved for design |
| DEC-024 | Lanjut ke `06-se-architecture-design`. | Input architecture dan risk gate telah terdefinisi. | Approved |
| DEC-025 | Interview mahasiswa dan restore drill tetap wajib sebelum acceptance/release. | Architecture readiness tidak boleh disalahartikan sebagai release readiness. | Mandatory gate |

## 9. Readiness Decision

**Ready for design: Yes**

Reason: scope MVP telah dipersempit, keputusan offline/sync/delete/timezone/platform telah difinalkan untuk desain, seluruh AC MVP testable, dan risiko yang masih membutuhkan evidence ditempatkan sebagai gate acceptance/release dengan owner jelas.

## 10. Handoff

Kirim Architecture Input Set, DEC-023–DEC-025, dan VAL-016–VAL-019 ke `06-se-architecture-design`. Jangan membawa requirement deferred ke component MVP kecuali sebagai extension boundary.
