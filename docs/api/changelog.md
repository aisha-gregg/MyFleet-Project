# MyFleet API changelog

All notable API changes. We follow [semantic versioning](https://semver.org): breaking changes only in a new major version, with at least 6 months' notice.

## 2.4.0 — 2026-11-17 (Release 4.2)

### Added
- `data_source` field on `Vehicle` (`tracker` or `oem_connect`), so you can tell where a vehicle's data comes from.
- `vehicle.defect_reported` webhook event, sent when a driver reports a defect in a pre-trip check.

### Changed
- `GET /trips` now accepts ranges up to **31 days** (was 7 days).

### Deprecated
- The `driver_name` field on `Trip` is deprecated. Use `driver_id` and `GET /drivers/{id}` instead. It will be removed in `v3`, no earlier than 2027-06-01.

## 2.3.1 — 2026-09-02

### Fixed
- `GET /vehicles` sometimes returned a `next_cursor` on the last page. It now returns `null`.

## 2.3.0 — 2026-08-18 (Release 4.1)

### Added
- `geofence.entered` and `geofence.exited` webhook events.
- `heading` field on `Position`.
