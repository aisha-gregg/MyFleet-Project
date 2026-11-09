# Install the MyFleet MT-200 tracker

**Applies to:** MT-200, MT-200 Pro · **Time:** about 30 minutes · **Skill level:** trained installer
**Article ID:** KB-0101 · **Last reviewed:** 9 November 2026 (Release 4.2)

This article explains how to install an MT-200 tracker in a vehicle and confirm it reports to MyFleet.
A [video version](mt200-video-script.md) is available in the MyFleet video library.

## Before you start

You need:

- an MT-200 or MT-200 Pro tracker and its wiring harness (in the box)
- the vehicle's registration number and VIN
- the MyFleet Installer app, signed in with your installer account
- a multimeter and cable ties

!!! warning "Disconnect the vehicle battery"
    Disconnect the negative battery terminal before you connect the power wires. A short circuit can damage the vehicle's electronics.

!!! important "Check vehicle compatibility"
    Electric and hybrid vehicles may need the CAN bus adapter (part MT-ACC-04). Check the [Product Availability Matrix](../product/availability-matrix.md) before you go to site.

## Step 1: Choose a mounting location

1. Find a location behind the dashboard, at least 30 cm from the radio and airbag modules.
2. Make sure the top of the tracker (the side with the label) faces the windscreen. The GPS antenna needs a clear view of the sky.

## Step 2: Connect the wiring

| Wire | Connect to | Notes |
|------|-----------|-------|
| Red | Permanent 12/24 V supply | Use the 2 A fuse in the harness |
| Black | Vehicle ground | Bare metal chassis point |
| White | Ignition (switched) supply | Check with the multimeter: 0 V with ignition off |
| Green / Yellow | CAN high / CAN low | Optional. Only for fuel and odometer data |

1. Connect the black wire first, then the red, then the white.
2. Reconnect the vehicle battery.
3. Plug the harness into the tracker. The LED flashes amber while it searches for a network.

## Step 3: Register the tracker

1. In the Installer app, select **New installation**.
2. Scan the QR code on the tracker label.
3. Enter the vehicle's registration number and VIN, then select **Register**.

## Step 4: Test the installation

1. Turn on the ignition.
2. Wait for the LED to turn solid green (up to 3 minutes).
3. In the Installer app, select **Run test**. The app checks GPS, network, and ignition signals.

**Result:** the app shows **Installation passed**, and the vehicle appears on the live map in the MyFleet Dashboard.

## Troubleshooting

| LED | Meaning | What to do |
|-----|---------|-----------|
| Off | No power | Check the red and black wires and the fuse |
| Flashing amber after 5 minutes | No network | Move the vehicle outside; check the SIM is active in the Installer app |
| Flashing red | No GPS fix | Make sure the label side faces the windscreen and is not under metal |

Still stuck? Contact installer support from the Installer app (**Help > Contact support**) and include the tracker serial number.

## Related articles

- [MT-200 installation video script](mt200-video-script.md)
- [Release notes 4.2](../releases/release-notes-4-2.md)
