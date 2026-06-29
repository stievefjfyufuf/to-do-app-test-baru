# To Do App Test Baru

Repository ini berisi hasil awal software-engineering untuk aplikasi pengelolaan tugas mahasiswa, mulai dari inception sampai requirement validation dan change analysis.

## Status

Tahap saat ini: **Requirement Validation - belum siap menjadi architecture baseline**.

Fondasi requirement inti sudah tersedia, tetapi beberapa keputusan masih perlu divalidasi, terutama:

- kapasitas tim dan deadline;
- batas MVP web-first;
- cakupan operasi offline;
- resolusi konflik sinkronisasi;
- lifecycle penghapusan data;
- target non-functional requirements;
- validasi langsung dengan mahasiswa sasaran.

## Dokumen Software Engineering

Dokumen harus dibaca berurutan:

1. [`01-inception.md`](docs/software-engineering/01-inception.md) - problem statement, stakeholder, goals, scope, asumsi, dan open questions.
2. [`02-elicitation.md`](docs/software-engineering/02-elicitation.md) - elicitation plan, question bank, raw needs, ambiguity, dan conflict log.
3. [`03-specification.md`](docs/software-engineering/03-specification.md) - functional requirements, non-functional requirements, user stories, acceptance criteria, dan traceability.
4. [`04-prioritization.md`](docs/software-engineering/04-prioritization.md) - MoSCoW, scoring, batas MVP, next release, dependency, serta keputusan prioritas.
5. [`05-validation-change.md`](docs/software-engineering/05-validation-change.md) - hasil validasi requirement, issue list, early change analysis, dan readiness decision.

## Ringkasan Scope

MVP yang direkomendasikan berfokus pada web, pengelolaan tugas inti, kalender, akun, persistence, keamanan, dan aksesibilitas. Offline-sync merupakan MVP gate yang masih memerlukan keputusan final. Android, fitur produktivitas lanjutan, dan kolaborasi ditempatkan pada rilis berikutnya atau deferred scope.

## Langkah Berikutnya

Selesaikan temuan dan perubahan wajib pada `05-validation-change.md`. Setelah stakeholder memberikan keputusan dan requirement diperbarui, lakukan validasi ulang sebelum masuk ke architecture design.

