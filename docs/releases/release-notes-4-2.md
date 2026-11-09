# MyFleet Release 4.2 release notes

**Release date:** 17 November 2026 · **Rollout:** gradual over 2 weeks, all markets
**Applies to:** Dashboard, Driver App 4.2, MT-200 firmware 3.8, API 2.4

## Highlights

### Defect alerts from pre-trip checks
When a driver reports a defect in the Driver App, fleet managers now get an alert straight away, by email or in the Dashboard.
**Why it matters:** unsafe vehicles get fixed before they go back on the road.
**Set it up:** **Settings > Alerts > New alert > Defect reported**.

### OEM Connect for more manufacturers
OEM Connect now supports two more manufacturers in the UK, Spain, and France. See the [Product Availability Matrix](../product/availability-matrix.md) for models.

### Longer trip reports in the API
Developers can now request up to 31 days of trips in one call. See the [API changelog](../api/changelog.md).

## Improvements

- **Dashboard:** the live map loads up to 40% faster for fleets with more than 500 vehicles.
- **Driver App:** you can attach up to 5 photos to a defect report (was 1).
- **MT-200 firmware 3.8:** faster GPS fix after the vehicle has been parked for a long time.

## Fixes

- Trip distances no longer show as 0 km when the trip crosses midnight.
- The Driver App no longer signs you out after an iOS update.

## Changes to be aware of

!!! important "Action needed for API users"
    The `driver_name` field is deprecated and will be removed in API v3. If your integration uses it, switch to `driver_id`.

## Firmware update

MT-200 trackers update over the air when parked with the ignition off. You don't need to do anything.
To check, open the vehicle in the Dashboard and look for **Firmware 3.8** under **Device**.

## Languages

These release notes are available in English, Spanish (Spain and Mexico), and French.
