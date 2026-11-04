<p align="center"><a href="https://genyra.com"><picture><source media="(prefers-color-scheme: dark)" srcset="assets/genyra-light.png"><img src="assets/genyra-dark.png" width="280" alt="Genyra LLC"></picture></a></p>

# Genyra

**Software engineering. Legacy modernisation. Evidence you can inspect.**

Genyra LLC engineers native applications, enterprise platforms and systems integrations. We investigate existing software—its business rules, data and dependencies—and build the next implementation around behaviour that can be tested.

[Genyra.com](https://genyra.com) · [Engineering Lab](ENGINEERING-LAB.md) · [Discuss a project](https://genyra.com/contact)

## Featured engineering

These four application repositories are **forks of upstream open-source projects**. Genyra's contribution is the Rust implementation, migration tooling, verification and documentation described below. Original authorship and licences remain attributed in each repository.

### 1. [Legacy Ledger & Payroll](https://github.com/GenyraLLC/legacy-ledger-rust)

Genyra rebuilt 13 COBOL programs as a standalone Rust banking-and-payroll demonstration, including exact decimal arithmetic and packed-decimal records. Published verification covers **90 simulated days, six nodes and 2,174 byte-for-byte file comparisons**, plus the employee payroll pipeline.

[Evidence and scope](https://github.com/GenyraLLC/legacy-ledger-rust/blob/main/MIGRATION.md) · Upstream: [Albert Mendes / AKD APP BREWING's Legacy Ledger](https://github.com/albertdobmeyer/cobol-legacy-ledger).

### 2. [Hotel Operations](https://github.com/GenyraLLC/hotel-rust)

Genyra rebuilt the COBOL simulator's reservations, stays, services, loyalty and billing workflows in native Rust, with a JSON command interface and persistent snapshots. **155 scenarios and 7,351 byte-for-byte table-record comparisons** are recorded with zero mismatches.

[Evidence and scope](https://github.com/GenyraLLC/hotel-rust/blob/main/MIGRATION.md) · Upstream: [Alejandro Blanco's COBOL hotel simulator](https://github.com/Ghostalex07/cobol-hotel).

### 3. [COBCALC](https://github.com/GenyraLLC/cobcalc-rust)

Genyra rebuilt the expression evaluator in Rust with an explicit decimal contract, offline dependencies and reproducible checks. Evidence separates **2,000 compatibility cases against the original floating-point COBOL program** from **1,000 exact-decimal reference cases**. The two comparisons establish different things.

[Evidence and scope](https://github.com/GenyraLLC/cobcalc-rust/blob/main/MIGRATION.md) · Upstream: [Manny Juan's COBCALC](https://github.com/manyone/cobcalc).

### 4. [Genyra Snitch](https://github.com/GenyraLLC/genyra-snitch)

**Linux alpha.** Genyra replaced the Python collector with Rust for network visibility, application controls and investigation tools. The native desktop and Windows/macOS work remain under validation; full application parity is still in progress.

The published **20-second collector comparison** measured Rust at **2.4% of one CPU core and 168.82 MiB RSS**, versus Python at **15.3% and 144.93 MiB RSS**: lower CPU use, higher resident memory in that sample. This is a limited measurement, not a general performance guarantee.

[Measurements and limits](https://github.com/GenyraLLC/genyra-snitch/blob/main/docs/PERFORMANCE.md) · Upstream: [Snitch by aiXis Studio](https://github.com/aixisstudio/Snitch).

## How to assess the work

The [Engineering Lab](ENGINEERING-LAB.md) links to source provenance, runnable demonstrations, comparison methods and recorded results. These are scoped engineering demonstrations; broader compatibility and production readiness require their own evaluation.

For a larger software modernisation or engineering project, [talk to Genyra](https://genyra.com/contact).
