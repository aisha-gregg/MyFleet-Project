# MyFleet API reference

**Version:** 2.4.0 · **Base URL:** `https://api.myfleet.example/v2`
The full machine-readable spec is in [openapi.yaml](openapi.yaml). Import it into Postman or any OpenAPI tool.

## Authentication

Send your API key in the `X-API-Key` header with every request.
Create keys in the MyFleet Dashboard under **Settings > API keys**.

```bash
curl https://api.myfleet.example/v2/vehicles \
  -H "X-API-Key: YOUR_API_KEY"
```

## Rate limits

You can send up to 600 requests per minute per key. If you go over, you get `429 Too Many Requests`
with a `Retry-After` header that says how many seconds to wait.

## Pagination

List endpoints return up to `limit` items (default 50, max 200) and a `next_cursor`.
Pass `next_cursor` as the `cursor` parameter to get the next page. When `next_cursor` is `null`, you have everything.

## Endpoints

### List vehicles

`GET /vehicles`

| Parameter | In | Type | Required | Description |
|-----------|----|------|----------|-------------|
| `limit` | query | integer | No | Items per page, 1 to 200. Default 50. |
| `cursor` | query | string | No | Cursor from the previous page. |
| `group_id` | query | string | No | Return only vehicles in this group. |

```json title="200 OK"
{
  "data": [
    {
      "id": "veh_8f2k1",
      "registration": "AB12 CDE",
      "vin": "WF0XXXTTGXKA12345",
      "group_id": "grp_north",
      "data_source": "tracker"
    }
  ],
  "next_cursor": "eyJpZCI6MTIzfQ"
}
```

### Get latest position

`GET /vehicles/{vehicle_id}/positions/latest`

Returns the most recent position, whether it came from an MT-200 tracker or from [OEM Connect](oem-connect.md).

```json title="200 OK"
{
  "vehicle_id": "veh_8f2k1",
  "latitude": 53.4808,
  "longitude": -2.2426,
  "speed_kmh": 48,
  "heading": 270,
  "ignition": true,
  "recorded_at": "2026-11-09T08:14:03Z"
}
```

### List trips

`GET /trips`

| Parameter | In | Type | Required | Description |
|-----------|----|------|----------|-------------|
| `from` | query | date-time | Yes | Start of range, ISO 8601 in UTC. |
| `to` | query | date-time | Yes | End of range. Maximum 31 days after `from`. |
| `vehicle_id` | query | string | No | Return trips for one vehicle only. |

!!! note
    `driver_id` is `null` when nobody was logged in to the vehicle during the trip.

### Create a webhook subscription

`POST /webhooks`

```json title="Request body"
{
  "url": "https://example.com/myfleet/events",
  "events": ["trip.ended", "geofence.entered"]
}
```

The response includes a `secret`. It's shown only once, so store it securely. See [Verify webhook signatures](integration-guide.md#step-4-verify-webhook-signatures).

## Errors

| Status | Code | Meaning | What to do |
|--------|------|---------|-----------|
| 400 | `invalid_range` | The time range is longer than 31 days | Split the request into smaller ranges |
| 401 | `invalid_api_key` | Key missing, wrong, or revoked | Check the `X-API-Key` header |
| 404 | `not_found` | The resource doesn't exist or isn't in your account | Check the ID |
| 429 | `rate_limited` | Too many requests | Wait for `Retry-After` seconds |
