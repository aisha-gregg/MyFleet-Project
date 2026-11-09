# Set up MyFleet OEM Connect

OEM Connect brings vehicle data straight from the manufacturer's cloud into MyFleet, with no tracker to install.
Use it for new vehicles from supported manufacturers, or for mixed fleets where some vehicles already have built-in telematics.

## Supported data

| Data | Tracker (MT-200) | OEM Connect |
|------|:---:|:---:|
| Position and speed | ✓ every 15 s | ✓ every 60 s (varies by manufacturer) |
| Ignition on/off | ✓ | ✓ |
| Odometer | With CAN | ✓ |
| Fuel level / battery charge | With CAN | ✓ |
| Driver ID | MT-200 Pro only | ✗ |
| Harsh driving events | ✓ | Some manufacturers |

Check supported manufacturers and models for each market in the [Product Availability Matrix](../product/availability-matrix.md).

## Before you start

- MyFleet admin rights.
- The VIN of each vehicle.
- Permission from the vehicle owner to share data. In most markets, the manufacturer asks the owner to confirm in their own app or portal.

## Step 1: Add the manufacturer connection

1. In the MyFleet Dashboard, go to **Settings > OEM Connect**.
2. Select **Add connection** and choose the manufacturer.
3. Accept the data-sharing terms.

## Step 2: Add vehicles

1. Select **Add vehicles**.
2. Enter VINs one by one, or upload a CSV file with one VIN per line.
3. Select **Request access**.

Each vehicle shows **Pending consent** until the owner approves.

## Step 3: Get owner consent

The manufacturer sends a consent request to the registered owner. When the owner approves, the status changes to **Active** (usually within 24 hours).

!!! note "Leased vehicles"
    For leased vehicles, the leasing company is the registered owner. Send them the VIN list and ask them to approve the requests.

## Step 4: Check data is arriving

1. Open the live map and find the vehicle.
2. Check the data source icon shows **OEM**.
3. Through the API, the vehicle's `data_source` is `oem_connect`.

## Use cases

- **No-install onboarding:** get new vans on the map the day they're delivered.
- **Electric fleets:** use the manufacturer's battery data for charging reports.
- **Mixed fleets:** combine trackers and OEM data in one map and one API.

## Troubleshooting

| Status | Meaning | What to do |
|--------|---------|-----------|
| Pending consent for more than 7 days | Owner hasn't approved | Ask the owner to check the manufacturer app |
| Not eligible | Model or year not supported | Install an MT-200 instead |
| Data delayed | Manufacturer cloud is slow | Normal delays are up to 5 minutes; check the status page if longer |
