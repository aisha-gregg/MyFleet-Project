# Integration guide: Sync trips to your system

This guide shows you how to send completed MyFleet trips to your own system, such as a payroll or job-costing tool.
By the end, your system receives each trip within seconds of the vehicle stopping.

**You need:** a MyFleet account with the **API access** add-on, admin rights, and a public HTTPS endpoint.
**Time:** about 1 hour.

## How it works

1. A vehicle's ignition turns off and MyFleet closes the trip.
2. MyFleet sends a `trip.ended` webhook to your endpoint.
3. Your endpoint verifies the signature and stores the trip.
4. Once a night, your system calls `GET /trips` to catch anything it missed.

## Step 1: Create an API key

1. In the MyFleet Dashboard, go to **Settings > API keys**.
2. Select **Create key**, name it (for example `payroll-sync`), and select **Read** access.
3. Copy the key. You won't see it again.

## Step 2: Test your key

```bash
curl https://api.myfleet.example/v2/vehicles?limit=1 \
  -H "X-API-Key: YOUR_API_KEY"
```

A `200` response with one vehicle means the key works.

## Step 3: Subscribe to trip events

```bash
curl -X POST https://api.myfleet.example/v2/webhooks \
  -H "X-API-Key: YOUR_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"url": "https://example.com/myfleet/events", "events": ["trip.ended"]}'
```

Store the `secret` from the response.

## Step 4: Verify webhook signatures

Each webhook has a `MyFleet-Signature` header: an HMAC-SHA256 of the raw request body, using your secret.
Reject any request where the signature doesn't match.

```python
import hmac, hashlib

def is_valid(raw_body: bytes, header: str, secret: str) -> bool:
    expected = hmac.new(secret.encode(), raw_body, hashlib.sha256).hexdigest()
    return hmac.compare_digest(expected, header)
```

!!! important
    Use the raw body bytes. Parsing and re-serializing the JSON changes the bytes and the check fails.

Respond with `2xx` within 10 seconds. If you don't, MyFleet retries 5 times over 24 hours.

## Step 5: Backfill missed trips

Webhooks can be missed during outages. Run a nightly job that requests the last 24 hours and stores any trip IDs you don't have:

```bash
curl "https://api.myfleet.example/v2/trips?from=2026-11-08T00:00:00Z&to=2026-11-09T00:00:00Z" \
  -H "X-API-Key: YOUR_API_KEY"
```

Use the trip `id` to avoid duplicates.

## Next steps

- Add `geofence.entered` events to log site arrivals.
- See the full [API reference](reference.md) and the [changelog](changelog.md).
