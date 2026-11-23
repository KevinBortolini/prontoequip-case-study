# Implementation decisions

This account summarizes inspected implementation patterns. It is not source distribution, a complete security audit or a reproducible application installation guide.

## Identity and scope

ProntoEquip Internal is a distinct Android-first application, not an assumed rename of a similarly named equipment-tracking repository. Its current client integrates directly with Supabase Auth, PostgreSQL functions and private Storage. The reviewed stack does not depend on the separate NestJS/MinIO application used elsewhere.

## Server authority and retry

Client screens enforce navigation and validation, but critical movement decisions also belong in the database. The reviewed migrations include authorization checks, company scope, row-level security, transactional functions, equipment-state checks, locks and unique operation identities.

Checkout and return reuse a durable operation identity after an interrupted attempt. The orchestration distinguishes preparation, evidence upload, evidence readiness and final movement commitment. It handles an already committed operation separately from one still being prepared. This is an implementation strategy for avoiding duplicate or partially represented business actions; it is not a guarantee that every concurrency or network scenario has been verified.

## Device persistence is deliberately limited

SQLite stores movement drafts and staging metadata, with private filesystem storage for local evidence. Sessions and NFC pending records use SecureStore. These stores have different responsibilities; local persistence is not an alternative source of official equipment status.

Movement drafts use a draft-only execution policy. They are not automatically queued for remote business execution. The recovery UI allows deliberate continuation or discard. Authentication, initial equipment selection and remote revalidation still depend on connectivity. Historical evidence is not downloaded automatically for offline use.

## NFC has two confirmation boundaries

The native reader/writer checks support and availability, works with NDEF content and verifies a write through readback. Server-side binding then establishes which equipment the token resolves to. A failed remote step after a successful physical write needs a recoverable pending record and explicit reconciliation rather than another unrequested tag write.

Manual equipment lookup avoids requiring NFC for every workflow. It does not constitute validation of the NFC hardware path. Reading an opaque token is not described as proof of customer identity or an anti-cloning guarantee.

## Historical records and reports

Movement records retain snapshots rather than treating editable current master data as historical fact. Reports assemble the historical record and permitted evidence, validate retrieved bytes, render HTML and generate a local PDF through Expo Print. The native action layer handles viewing, sharing and saving.

Temporary report files have scoped cleanup. A copy explicitly saved by the user has a different lifecycle and must not be removed as a temporary artifact. Android layout, viewer behavior and sharing still depend on the device and native runtime. Report generation is implemented; no report was generated from live or private data for this case study.

## Privacy and maintenance

The code separates domain rules, application services, native/platform adapters, UI and versioned database migrations. The test tree contains domain, service, component-harness and platform-boundary cases; mocks are not physical Android tests.

The presentation omits exact operational identities, storage paths, private configuration and detailed organization-specific policies. It describes technical decisions without reproducing SQL, source excerpts or private documentation. No ownership, deployment or performance claim follows solely from inspecting this structure.
