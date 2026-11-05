# Changelog

## Name field fix (2026-11-06)

A Squarespace Name field keyed its parts as "Name First" and "Name Last", which the classifier did not recognise, so `ec_first_name` and `ec_last_name` came through empty on a real form. They are now keyed "Name First Name" and "Name Last Name". Found in a browser test on a live Squarespace form, with the submission request stubbed so no lead was sent.

## 3.3.0 (2026-10-28)

First public standalone Squarespace release, cut from the universal tracker v3.3.0. The shared core and the Squarespace handler match the universal build.

- `squarespace_form_success` and `squarespace_form_failed` events, plus `ec_form_interaction` and `ec_tracker_initialized`
- `ec_event_id` and `ec_detection_method` on every event
- Consent gate (Consent Mode v2, OneTrust, Cookiebot, `EC_FORM_CONSENT_CHECK`) with queue and replay
- PII redaction, optional SHA-256 hashing, always-redacted sensitive field names
- 5-minute dedupe ledger
- First and last touch attribution with click IDs
- E.164 phone normalization with `defaultCountryCode` and `countryCodeField`
- `strictSuccess` option, failure diagnostics, SPA route handling
- GTM paste-ready file with production defaults (`debug: false`, `rawFields: false`) and a raw `.js` whose defaults never override a site's own config
