# Scope and verification status

Prepared on 2026-11-23 from read-only implementation and documentation inspection. The application was not launched, dependencies were not installed, and no backend, account or device was accessed for this presentation.

| Evidence class | What can be said | What it does not establish |
| --- | --- | --- |
| Implementation inspected | Screens, services, native adapters, migrations and tests exist for the workflows described in the README. | Successful execution of every branch, the current remote schema or production use. |
| Historical project records | Progress notes describe prior authenticated and Android-device checks, including NFC, photos, movement flows, recovery and PDFs. | Independent repetition, universal device compatibility or current acceptance of later changes. |
| Synthetic tests in source | The project contains domain/service cases and component tests with mocked boundaries. | A real Android layout, camera/tag operation or live backend result. No tests were run during this task. |
| Isolated presentation demo | A fictional scenario and capture instructions have been designed. | An implemented public demo or completed screenshots. No presentation demo was executed. |
| Owner confirmation | Kevin Bortolini confirms full development authorship and regular internal use of all operational workflows every workday. | Independently audited adoption, user counts, measured benefits, every hardware/edge-case result or equivalence of the installed build to this source snapshot. |

## Incomplete or conditional functionality

- The user-management screen is a placeholder; an administrator menu does not prove account provisioning is implemented.
- Historical customer search is implemented locally with a read-only database function and tests. Its migration is documented as not installed remotely, so availability in the working system is unverified.
- Authentication and catalog access require connectivity. Draft/staging recovery is not offline authentication, a complete offline catalog or automatic movement synchronization.
- Historical photo viewing needs available authorized remote objects; no persistent offline historical-photo cache is claimed.
- Device-private files and SQLite are not claimed to have application-level encryption at rest.
- Hardware NFC support, tag placement, camera/storage permissions, signature orientation, interruption recovery, report layout and Android share/save behavior need validation on the actual supported device/build.
- Previously recorded physical results do not establish all newer search, layout or recovery paths. Several destructive/exception scenarios remain described through automated or synthetic coverage rather than forced live failures.

## Screenshot status

Eleven owner-supplied operational application captures were inspected locally, cropped to remove system content and exported as metadata-free flattened RGB PNGs. Identifying fields, operational counts/dates and both photographic thumbnails were fully covered where present. Each final image was visually inspected at its saved resolution, including the thumbnail areas and text. Local OCR was unavailable and was not claimed performed. Opaque-mask pixel checks and PNG metadata/chunk checks supplement visual review.

The original captures were moved outside this presentation folder and verified byte-for-byte. Editing recipes, source mappings and intermediates also remain private and excluded from the proposed file set. The README links only reviewed final exports.

These are redacted **operational screenshots**, not invented records or an isolated demonstration. The original Portuguese UI is intentionally preserved under the owner's screenshot-sanitization instructions; the captions and documentation are English. They show forms, controls and record views, not proof that every action was executed. No populated movement-history event, completed movement, PDF preview or verified NFC read is established by this set.

A separate isolated English fictional demonstration remains optional future work; none was executed here. No application source, live system or account was modified to obtain or sanitize these captures.

## Presentation limits

The application source remains private. Developer authorship and routine-use statements are attributed to the owner. This document is not a security certification, public installation package or independently verified production-readiness assessment. Real operational records, organization-specific settings, reports and raw device captures are intentionally excluded; only reviewed redacted image exports are included. Public release of this presentation and any future images requires a separate review and authorization.
