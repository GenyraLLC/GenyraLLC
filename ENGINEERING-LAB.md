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
- [Upstream attribution and licence notice](https://github.com/GenyraLLC/cobcalc-rust/blob/main/NOTICE)
- [Build and run the application](https://github.com/GenyraLLC/cobcalc-rust#run-the-finished-application)

## 4. Genyra Snitch

[Repository](https://github.com/GenyraLLC/genyra-snitch) · [Original project](https://github.com/aixisstudio/Snitch)

**Original work:** Snitch by aiXis Studio, under its retained AGPL-3.0 licence and upstream notices.

**Genyra engineering:** a native Rust collector replacing the Python backend, compatibility with the upstream REST/WebSocket contracts, native security integrations and documented migration and resource checks. The native desktop and platform adapters are developed on the repository's single `main` branch.

**Maturity:** the published application is a Linux x86-64 alpha. Native desktop parity and Windows/macOS work remain in progress. Successful platform builds and synthetic service-lifecycle tests do not establish privileged live-capture or firewall parity across all operating systems.

**Published resource measurements:** separate five-minute Linux cohorts measured background and full-application use. Background original/native CPU was 104.36% / 1.83% of one logical core; mean RSS was 109.94 / 44.89 MiB. The revised native alpha.5 application, including its collector, averaged 10.16% CPU, 171.89 MiB summed RSS and 113.77 MiB PSS versus original Python/Electron at 324.33%, 1,279.49 MiB and 755.24 MiB. Full-app PSS accounts for shared resident pages. Capture policies, algorithms and update cadences differ; native RSS grew 18.44 MiB during its run. These are scoped observations, not full parity, equal-cadence rendering or long-term stability claims. The guide retains the earlier sample with higher native RSS.

**Native interface:** Genyra light/dark themes and eight-language navigation/overview. The published busy screenshots are actual native renders of a separately generated, entirely fictional Rust dataset. They contain no personal hosts or captured network connections. The application remains a **Linux alpha**.

- [Background and application evidence, visual timing and build identities](https://github.com/GenyraLLC/genyra-snitch/blob/main/docs/benchmarks/2026-11-04-linux-application.md)
- [Privacy-safe light/dark alpha gallery](https://github.com/GenyraLLC/genyra-snitch/blob/main/docs/images/README.md)
- [Resource methodology and limits](https://github.com/GenyraLLC/genyra-snitch/blob/main/docs/PERFORMANCE.md)
- [Feature coverage and validation boundaries](https://github.com/GenyraLLC/genyra-snitch/blob/main/docs/FEATURES.md)
- [Native rewrite status](https://github.com/GenyraLLC/genyra-snitch/blob/main/docs/NATIVE-REWRITE.md)
- [Upstream provenance](https://github.com/GenyraLLC/genyra-snitch/blob/main/UPSTREAM.json)

## Reading the evidence

Each result belongs to its stated source revision, test corpus and comparison method. Original source, licensing and attribution remain available. Genyra's implementation and verification work are identified separately from the upstream application. The repositories' build instructions explain how to reproduce each demonstration and its checks.
