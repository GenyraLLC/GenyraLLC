# Genyra Engineering Lab

[Genyra profile](README.md) · [Genyra.com](https://genyra.com) · [Discuss a project](https://genyra.com/contact)

This index describes what Genyra independently engineered in four attributed modernisation forks and where to inspect the proof. It prioritises the larger, evidence-backed migrations before the experimental security project. Evidence reviewed on **4 November 2026**.

## 1. Legacy Ledger & Payroll

[Repository](https://github.com/GenyraLLC/legacy-ledger-rust) · [Original project](https://github.com/albertdobmeyer/cobol-legacy-ledger)

**Original work:** Albert Mendes / AKD APP BREWING's COBOL Legacy Ledger, under its retained MIT licence.

**Genyra engineering:** a standalone Rust implementation of nine banking and four payroll programs; checked decimal arithmetic; COMP-3 record encoding; persistent fixed-width records; and a reproducible comparison harness against the running originals.

**Published evidence:** 90 simulated days across six banking nodes; 860 operations; 2,174 exact file comparisons covering 185,968 record images; and four payroll programs processing 25 employees and producing 23 packed pay stubs. The recorded corpus reports zero failures and zero monetary tolerance.

**Boundary:** the verified banking and employee-payroll simulator workflows. The preserved Python console and separate merchant/dispute/risk programs are outside that Rust conversion's verified scope. Equivalence retains documented legacy quirks; it does not certify production banking rules or current tax calculations.

- [Verification summary](https://github.com/GenyraLLC/legacy-ledger-rust/blob/main/evidence-rust/verification.json)
- [Conversion decisions and limitations](https://github.com/GenyraLLC/legacy-ledger-rust/blob/main/MIGRATION.md)
- [Pinned upstream provenance](https://github.com/GenyraLLC/legacy-ledger-rust/blob/main/UPSTREAM.json)
- [Build and run the demonstration](https://github.com/GenyraLLC/legacy-ledger-rust#build-and-demonstrate)

## 2. Hotel Operations

[Repository](https://github.com/GenyraLLC/hotel-rust) · [Original project](https://github.com/Ghostalex07/cobol-hotel)

**Original work:** Alejandro Blanco's COBOL hotel simulator, under its retained MIT licence.

**Genyra engineering:** a native Rust implementation of the original eight operating areas, a JSON command interface, exact-cent billing, rollback on rejected commands, persistent snapshots and comparison of active table records against the original.

**Published evidence:** 155 operations scenarios and 7,351 byte-for-byte table-record comparisons, with zero failures and zero monetary tolerance. The report explains the observation-only source instrumentation and the test setup needed for an original booking-screen defect.

**Boundary:** a simulator using the original session date, preloaded records and explicit nights. The comparison covers the documented workflows and active table snapshots; it is not a live reservations or payment service.

- [Verification summary](https://github.com/GenyraLLC/hotel-rust/blob/main/evidence/verification.json)
- [Conversion decisions and limitations](https://github.com/GenyraLLC/hotel-rust/blob/main/MIGRATION.md)
- [Pinned upstream provenance](https://github.com/GenyraLLC/hotel-rust/blob/main/UPSTREAM.json)
- [Build and run the demonstration](https://github.com/GenyraLLC/hotel-rust#build-and-demonstrate)

## 3. COBCALC

[Repository](https://github.com/GenyraLLC/cobcalc-rust) · [Original project](https://github.com/manyone/cobcalc)

**Original work:** Manny Juan's COBOL expression evaluator, under its retained GPL-3.0-or-later licence.

**Genyra engineering:** an independently runnable Rust evaluator using decimal arithmetic, explicit precision and rounding limits, vendored dependencies for offline builds, native tests and reproducible comparison tooling.

**Published evidence:** 2,000 of 2,000 compatibility cases against the original floating-point program, using absolute and relative tolerances of `2e-12`; 1,000 exact-decimal cases against a separate Decimal reference with zero failures; and one selected 13-expression transcript matching byte for byte. The floating-point comparison is not a zero-tolerance financial-equivalence claim.

**Boundary:** this expression evaluator and its documented numeric contract. The migration report identifies approximation limits and intentional changes to invalid-input handling; it does not establish compatibility for unrelated enterprise COBOL systems.

- [Verification summary](https://github.com/GenyraLLC/cobcalc-rust/blob/main/evidence/verification.json)
- [Numeric contract, conversion decisions and limitations](https://github.com/GenyraLLC/cobcalc-rust/blob/main/MIGRATION.md)
- [Pinned upstream provenance](https://github.com/GenyraLLC/cobcalc-rust/blob/main/UPSTREAM.json)
- [Build and run the application](https://github.com/GenyraLLC/cobcalc-rust#run-the-finished-application)

## 4. Genyra Snitch

[Repository](https://github.com/GenyraLLC/genyra-snitch) · [Original project](https://github.com/aixisstudio/Snitch)

**Original work:** Snitch by aiXis Studio, under its retained AGPL-3.0 licence and upstream notices.

**Genyra engineering:** a native Rust collector replacing the Python backend, compatibility with the upstream REST/WebSocket contracts, native security integrations and documented migration and resource checks. A separate native-desktop branch is extending the Rust UI and platform adapters.

**Maturity:** the published application is a Linux x86-64 alpha. Native desktop parity and Windows/macOS work remain in progress. Successful platform builds and synthetic service-lifecycle tests do not establish privileged live-capture or firewall parity across all operating systems.

**Published resource measurement:** one 20-second Linux collector comparison measured Rust CPU at 2.4% of one core versus Python at 15.3%. Rust RSS was 168.82 MiB versus Python's 144.93 MiB. Both the lower CPU and higher resident-memory result are material. The sample excludes a general guarantee about a full desktop session or sustained workloads; optional inference has additional costs.

- [Resource methodology and limits](https://github.com/GenyraLLC/genyra-snitch/blob/main/docs/PERFORMANCE.md)
- [Feature coverage and validation boundaries](https://github.com/GenyraLLC/genyra-snitch/blob/main/docs/FEATURES.md)
- [Native rewrite status](https://github.com/GenyraLLC/genyra-snitch/blob/native-desktop/docs/NATIVE-REWRITE.md)
- [Upstream provenance](https://github.com/GenyraLLC/genyra-snitch/blob/main/UPSTREAM.json)

## Reading the evidence

Each result belongs to its stated source revision, test corpus and comparison method. Original source, licensing and attribution remain available. Genyra's implementation and verification work are identified separately from the upstream application. The repositories' build instructions explain how to reproduce each demonstration and its checks.
